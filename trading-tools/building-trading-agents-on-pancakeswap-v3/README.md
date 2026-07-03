# 🤖 BNB AI Agent Studio

> Um guia para desenvolvedores criando agentes autônomos — com o [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) ou qualquer framework — que interagem com os pools de Liquidez e farms V3 da PancakeSwap na BNB Smart Chain.
>
> Você descreve uma estratégia; seu agente a executa onchain, sem supervisão. Esta página aborda a parte da PancakeSwap: os contratos a serem chamados, a ordem segura para chamá-los e um exemplo completo de trabalho (um rebalanceador de intervalo V3 automatizado). Para saber como descrever, criar e implantar o próprio agente, consulte a documentação do BNB Agent Studio.

A PancakeSwap **não requer integração** para que isso funcione. Os pools V3 e farms são contratos inteligentes sem permissão — seu agente os chama diretamente, da mesma forma que o frontend da PancakeSwap faz. Tudo abaixo é superfície pública onchain.

***

### 1. O que um agente pode fazer na PancakeSwap

A Liquidez concentrada (V3) oferece aos LPs uma eficiência de capital muito melhor do que a V2, ao custo de gerenciamento ativo: uma posição só ganha taxas enquanto o preço estiver dentro de seu intervalo de tick, e recompensas/rendimentos mudam constantemente. Essa sobrecarga operacional é exatamente o que um agente remove. Estratégias comuns:

* **Rebalanceador de intervalo** — monitora uma posição LP; quando o preço se aproxima da borda do intervalo, retira e reminta em torno do novo preço para que a posição continue ganhando taxas. _(Exemplo trabalhado no §6.)_
* **Roteador de APR de Farm** — rastreia rendimento de CAKE + taxas em pools e move Liquidez para o maior rendimento total.
* **Bots de Swap/cotação** — roteia negociações pelo Smart Router para melhor execução em V2 + V3.

Todas essas são composições das mesmas poucas chamadas de contrato abaixo.

***

### 2. Superfície de contratos (BNB Smart Chain, chainId 56)

| Contrato                              | Endereço                                     | Seu agente o usa para                                                                                  |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Criar/gerenciar posições LP — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn`      |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Executar Swaps com melhor roteamento V2+V3                                                             |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Fazer Staking de um NFT de posição para ganhar CAKE — `harvest`, `withdraw`                            |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Cotar um Swap antes de enviá-lo                                                                        |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Resolver um endereço de pool a partir de `(token0, token1, fee)`                                       |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Aprovações de tokens sem gas/em lote para **Swaps no Smart Router** (ver §5.1)                         |

> ⚠️ **Sempre reconfirme os endereços** na lista de implantação canônica da PancakeSwap antes de enviar valor real. Trate a tabela acima como um ponto de partida.

Um **pool** V3 é identificado por `(token0, token1, fee)`. Camadas de taxa e seus espaçamentos de tick:

| Taxa  | valor `fee` | Espaçamento de tick | Uso típico                  |
| ----- | ----------- | ------------------- | --------------------------- |
| 0,01% | `100`       | 1                   | Stable–stable               |
| 0,05% | `500`       | 10                  | Correlacionados (ex.: ETH/BTC) |
| 0,25% | `2500`      | 50                  | Maioria dos pares           |
| 1,00% | `10000`     | 200                 | Exóticos / voláteis         |

Uma **posição** V3 é um NFT ERC-721 mantido no NonfungiblePositionManager. Armazena `tickLower`, `tickUpper`, `liquidity` e taxas acumuladas. Você o referencia por `tokenId`.

***

### 3. Ferramentas

Você pode se comunicar com esses contratos com ABIs brutos e qualquer biblioteca web3, mas os pacotes **`@pancakeswap/v3-sdk`** e **`@pancakeswap/smart-router`** fazem as contas difíceis (tick ↔ preço, mínimos ajustados por Slippage, codificação calldata) por você. Os exemplos abaixo os usam com [viem](https://viem.sh/).

```bash
pnpm add @pancakeswap/v3-sdk @pancakeswap/smart-router @pancakeswap/sdk viem
```

```tsx
import { createPublicClient, createWalletClient, http } from 'viem'
import { bsc } from 'viem/chains'
import { privateKeyToAccount } from 'viem/accounts'

const account = privateKeyToAccount(process.env.AGENT_PRIVATE_KEY as `0x${string}`)

const publicClient = createPublicClient({ chain: bsc, transport: http() })
const walletClient = createWalletClient({ chain: bsc, account, transport: http() })
```

Seu agente é apenas esta Carteira executando transações em um cronograma ou gatilho. A Carteira é financiada e gerenciada pelo Agent Studio — consulte a documentação do BNB.

***

### 4. Lendo o estado (faça isso antes de cada ação)

Um agente decide _se_ deve agir lendo o chain. As três leituras que impulsionam a maioria das estratégias:

**Preço do pool e tick atual** — construa uma entidade `Pool` a partir de `slot0` + `liquidity` onchain:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress resolvido a partir da factory ou computePoolAddress()
const [slot0, liquidity] = await Promise.all([
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'slot0' }),
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'liquidity' }),
])

const pool = new Pool(
  token0, token1, FeeAmount.MEDIUM,
  slot0[0],      // sqrtPriceX96
  liquidity,
  slot0[1],      // tick
)

console.log('preço token0→token1:', pool.token0Price.toSignificant(6))
console.log('tick atual:', pool.tickCurrent)
```

**Uma posição que você possui** — leia do NonfungiblePositionManager por `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**A posição está no intervalo?** Esse único booleano é o gatilho para um rebalanceador. Você pode restringi-lo para "dentro de N ticks da fronteira" para agir _antes_ de sair do intervalo.

***

### 5. Sequências de transações seguras

Esta é a parte que deve ser feita exatamente certa. Um agente sem supervisão não tem um humano para captar uma transação ruim, então toda chamada de mudança de estado deve ser defendida com os quatro controles abaixo.

#### 5.1 Aprovações

Antes que um contrato possa mover seus tokens, ele precisa de uma permissão. O mecanismo correto depende de qual contrato você está chamando — todos os três abaixo são sem permissão:

* **ERC-20 `approve`** — funciona tanto para o Smart Router quanto para o NonfungiblePositionManager, com qualquer token. Uma tx por token/gastador. O mais simples, mas uma aprovação infinita permanente é um risco permanente.
* **`selfPermit` (EIP-2612)** — para operações de Liquidez do **NonfungiblePositionManager**. Se o token suporta EIP-2612, o SDK pode agrupar uma permissão assinada com escopo de valor _inline_ com `mint`/`increaseLiquidity` via multicall — sem tx de aprovação separada. Retorna para `approve` para tokens sem EIP-2612.
* **Permit2** — para Swaps do **Smart Router**. Aprove o Permit2 uma vez por token, depois conceda permissões assinadas de curta duração com escopo de valor por Swap.

Para um agente autônomo: limite toda permissão ao valor exato e a uma expiração curta. **Nunca conceda uma aprovação ilimitada de uma Carteira de agente que mantém saldos significativos.**

#### 5.2 Slippage — nunca envie `amountMin = 0`

Toda adição/remoção/Swap deve especificar uma saída mínima aceitável. Deixe o SDK derivá-la de uma tolerância em vez de calcular manualmente:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0,50%

// ao fazer mint / adicionar:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// ao remover:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Para Swaps, o Smart Router aplica `slippageTolerance` e computa `amountOutMinimum` para você (§6, passo 0). **Um mínimo zero é um convite aberto para bots de ataque sandwich** — em uma Carteira sem supervisão, isso pode significar perdas repetidas e silenciosas.

#### 5.3 Prazos — sempre defina um

Toda chamada recebe um `deadline` (segundos unix). Se a tx ainda estiver pendente nesse momento, ela é revertida em vez de executar com um preço desatualizado. Mantenha curto para um agente:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutos
```

#### 5.4 Multicall — torne ações de múltiplos passos atômicas

O NonfungiblePositionManager e o Smart Router suportam `multicall`: várias chamadas agrupadas em **uma transação** que todas são bem-sucedidas ou todas são revertidas. Isso não é apenas economia de gas — é uma propriedade de segurança. Um rebalanceamento que faz `decreaseLiquidity` e depois `collect` nunca deve ser executado parcialmente. O SDK agrupa para você:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Não existe uma função atômica de "rebalanceamento".** Mover um intervalo é uma sequência _composta_ (remover → coletar → mintar). A remoção e o novo mint acontecem em transações separadas; o preço pode se mover entre elas. Releia o estado e recalcule os mínimos para o mint após a remoção confirmar — não reutilize números pré-remoção.

#### Lista de verificação de controles (aplique a cada ação do agente)

* \[ ] Permissão de token limitada ao valor (Permit2), não infinita
* \[ ] `amount*Min` / `amountOutMinimum` derivado de uma tolerância de Slippage explícita, nunca `0`
* \[ ] `deadline` curto em toda chamada
* \[ ] Ações de múltiplos passos agrupadas via `multicall`
* \[ ] Estado relido entre transações separadas de uma sequência
* \[ ] Um limite por execução no valor movido, e uma verificação de sanidade de que o preço do pool está dentro dos limites esperados antes de agir (defesa barata contra agir em um pool manipulado/com pouca Liquidez)

***

### 6. Exemplo trabalhado — rebalanceador de intervalo V3 automatizado

O agente de referência. Ele monitora uma posição; quando o preço se aproxima da fronteira do intervalo, retira Liquidez e reminta um novo intervalo centrado no preço atual. Cinco passos.

**Gatilho:** `pool.tickCurrent` está dentro de um buffer de `tickLower`/`tickUpper` (do §4).

#### Passo 0 — (opcional) rebalancear a proporção de tokens

Após retirar, você terá token0 e token1 na proporção que o antigo intervalo produziu. Um novo intervalo recentrado geralmente precisa de uma proporção diferente, então troque o excesso pelo Smart Router:

```tsx
import { SmartRouter, SwapRouter } from '@pancakeswap/smart-router'
import { TradeType } from '@pancakeswap/swap-sdk-core' 

const quoteProvider = SmartRouter.createQuoteProvider({ onChainProvider: () => publicClient })                                                                                                     
const trade = await SmartRouter.getBestTrade(amountIn, tokenOut, TradeType.EXACT_INPUT, {
  gasPriceWei: () => publicClient.getGasPrice(),
  maxHops: 2,
  poolProvider: SmartRouter.createStaticPoolProvider(candidatePools),
  quoteProvider,
})

const { calldata, value } = SwapRouter.swapCallParameters(trade, {
  slippageTolerance: new Percent(50, 10_000),
  deadlineOrPreviousBlockhash: deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: SMART_ROUTER_ADDRESS, data: calldata, value: BigInt(value) })
```

#### Passos 1–3 — remover Liquidez, coletar, queimar (uma transação)

`removeCallParameters` constrói o pacote inteiro: faz `decreaseLiquidity` para zero, `collect` tanto o principal retirado quanto as taxas acumuladas, e `burn` do NFT agora vazio — como um único `multicall` atômico.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — saída total
  slippageTolerance: new Percent(50, 10_000),     // 0,50% — define amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // aguarde — o próximo mint depende desses tokens
```

> Se a posição estiver **em Staking no MasterChefV3**, você não remove do NFPM. Chame `MasterChefV3.withdraw(tokenId, to)` primeiro para remover o Staking (isso também colhe CAKE pendente), que devolve o NFT à sua Carteira — depois execute a remoção acima. Veja §7.

#### Passo 4 — mintar o novo intervalo

Recalcule os ticks em torno do preço _atual_ (releia o pool — veja §5.4), ajuste-os ao espaçamento de tick da camada de taxa, construa uma `Position` a partir dos tokens que você agora tem e faça o mint.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* releia slot0 + liquidity → novo Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // largura de intervalo definida pela estratégia

const tickLower = nearestUsableTick(freshPool.tickCurrent - halfWidth, spacing)
const tickUpper = nearestUsableTick(freshPool.tickCurrent + halfWidth, spacing)

const newPosition = Position.fromAmounts({
  pool: freshPool,
  tickLower,
  tickUpper,
  amount0: balance0,
  amount1: balance1,
  useFullPrecision: true,
})

const { calldata, value } = NonfungiblePositionManager.addCallParameters(newPosition, {
  slippageTolerance: new Percent(50, 10_000), // define amount0Min/amount1Min para o mint
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

O agente agora possui um NFT novo e dentro do intervalo. Se estava em farming, refaça o Staking (§7). Volte para a leitura do §4 no próximo tick.

***

### 7. Interações com o Farm (MasterChefV3)

Fazer Staking de um NFT de posição V3 no MasterChefV3 ganha CAKE além das taxas de Swap.

> **Apenas posições de pools com um farm ativo ganham CAKE.** A Governança da PancakeSwap registra quais pools são farmáveis (cada um recebe um `pid`). Fazer Staking de uma posição cujo pool não está registrado reverte com `InvalidPid`. Este é o único lugar onde a atividade do agente depende de uma lista da PancakeSwap — e é no nível do pool, não do agente: qualquer Carteira pode fazer Staking em qualquer farm ativo. (Gerenciar uma posição via NonfungiblePositionManager — mint/coletar/rebalancear — não precisa de farm e funciona para todo pool.)

> **Apenas posições de pools com um farm ativo ganham CAKE.** A Governança da PancakeSwap registra quais pools são farmáveis (cada um recebe um `pid`). Fazer Staking de uma posição cujo pool não está registrado reverte com `InvalidPid`. Este é o _único_ lugar onde a atividade do agente depende de uma lista da PancakeSwap — e é no nível do pool, não do agente: qualquer Carteira pode fazer Staking em qualquer farm _ativo_. Verifique se o pool tem um farm ativo antes de construir uma estratégia de farming em torno dele. (Gerenciar uma posição via NonfungiblePositionManager — mint/coletar/rebalancear — não precisa de farm e funciona para todo pool.)

* **Staking** — transfira o NFT de posição para o MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). O farm agora custodia o NFT.
* **Harvest** — `harvest(tokenId, to)` reivindica CAKE pendente sem remover o Staking. Use `batchHarvest` para reivindicar em várias posições em uma tx.
* **Withdraw / sair** — `withdraw(tokenId, to)` remove o Staking, colhe CAKE pendente e devolve o NFT à sua Carteira. Você deve fazer o withdraw antes de poder fazer `decreaseLiquidity`/`burn` (as chamadas NFPM no §6 só funcionam em um NFT que sua Carteira possui).

Um rebalanceador para uma posição **em farming** portanto executa: `withdraw` → remover/coletar/queimar → mintar → `safeTransferFrom` de volta para o MasterChefV3.

***

### 8. Segurança, limites e isenções de responsabilidade

Leia isto antes de implantar um agente que move fundos reais.

* **Autonomia é irreversível.** Um agente implantado assina e envia transações sem confirmação humana. Um bug, um gatilho ruim ou um feed de preços manipulado executa de verdade. Teste na testnet BSC, depois limite a exposição na mainnet (limites por negociação e por dia) antes de escalar.
* **Slippage e prazos são obrigatórios**, não opcionais (§5). Um agente que os omite eventualmente será vítima de ataque sandwich.
* **Defesa contra manipulação de preço.** Antes de agir, verifique o preço do pool em relação a uma referência independente e pule a execução se eles divergirem — seguro barato contra trading em um pool manipulado ou com pouca Liquidez.
* **Gas e financiamento.** Mantenha a Carteira do agente financiada com BNB para gas; um agente sem fundos pode deixar uma posição no meio do rebalanceamento (removida mas não remintada). Reler o estado em cada execução (§4) permite que ele se recupere no próximo tick.
* **Tokens Scaled-UI / RWA.** Alguns tokens BSC (ex.: Binance Stock Tokens) usam multiplicadores de UI onchain (ERC-8056). Os valores brutos onchain diferem dos valores exibidos. Se seu agente negocia esses tokens, faça todo cálculo contratual em unidades brutas e aplique o multiplicador apenas para exibição humana.
* **Você é responsável pelo seu agente.** Os pools da PancakeSwap são contratos sem permissão; implantar um agente autônomo contra eles é sua decisão e seu risco. Este guia é referência técnica, não conselho financeiro, e a PancakeSwap não faz nenhuma garantia sobre os resultados.

***

### 9. Referência

* **`@pancakeswap/smart-router`** — roteamento + calldata de Swap (os melhores exemplos no repositório estão no README)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, matemática de tick/preço
* **BNB Agent Studio** — descrição, criação e implantação do agente (documentação BNB)
* **Endereços de implantação PancakeSwap** — lista canônica de contratos (verifique antes de usar)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
