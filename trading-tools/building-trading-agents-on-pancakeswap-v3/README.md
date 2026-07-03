# 🤖 BNB AI Agent Studio

> Una guida per gli sviluppatori che costruiscono agenti autonomi — con [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) o qualsiasi framework — che interagiscono con i pool di liquidità e le Farm V3 di PancakeSwap su BNB Smart Chain.
>
> Descrivi una strategia; il tuo agente la esegue on-chain, senza presidio umano. Questa pagina copre la parte PancakeSwap: i contratti da chiamare, l'ordine sicuro in cui chiamarli e un esempio completo (un ribilanciatore automatico di range V3). Per come descrivere, costruire e distribuire l'agente stesso, consulta la documentazione di BNB Agent Studio.

PancakeSwap **non richiede alcuna integrazione** per funzionare. I pool e le Farm V3 sono smart contract permissionless — il tuo agente li chiama direttamente, allo stesso modo in cui lo fa il frontend di PancakeSwap. Tutto ciò che segue è superficie pubblica on-chain.

***

### 1. Cosa può fare un agente con PancakeSwap

La liquidità concentrata (V3) offre agli LP una maggiore efficienza del capitale rispetto a V2, al costo di una gestione attiva: una posizione guadagna commissioni solo quando il prezzo è all'interno del suo range di tick, e le ricompense/rendimenti cambiano costantemente. Quel carico operativo è esattamente ciò che un agente elimina. Strategie comuni:

* **Ribilanciatore di range** — monitora una posizione LP; quando il prezzo si avvicina al bordo del range, ritira e re-minta attorno al nuovo prezzo in modo che la posizione continui a guadagnare commissioni. _(Esempio pratico nel §6.)_
* **Router APR Farm** — traccia il rendimento CAKE + commissioni tra i pool e sposta la liquidità verso il rendimento totale più alto.
* **Bot Swap/quotazione** — instrada gli scambi attraverso lo Smart Router per la migliore esecuzione su V2 + V3.

Tutte queste sono composizioni delle stesse poche chiamate di contratto qui sotto.

***

### 2. Superficie del contratto (BNB Smart Chain, chainId 56)

| Contratto                             | Indirizzo                                    | Il tuo agente lo usa per                                                                         |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Creare/gestire posizioni LP — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Eseguire swap con il miglior routing V2+V3                                                       |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Fare Staking di un NFT di posizione per fare Farm di CAKE — `harvest`, `withdraw`                |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Quotare uno swap prima di inviarlo                                                               |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Risolvere un indirizzo di pool da `(token0, token1, fee)`                                        |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Approvazioni di token gasless/batch per **swap con Smart Router** (vedi §5.1)                    |

> ⚠️ **Conferma sempre gli indirizzi** rispetto all'elenco canonico di deployment di PancakeSwap prima di inviare valore reale. Considera la tabella precedente come punto di partenza.

Un **pool** V3 è identificato da `(token0, token1, fee)`. Livelli di commissione e spaziatura dei tick:

| Commissione | Valore `fee` | Spaziatura tick | Utilizzo tipico               |
| ----------- | ------------ | --------------- | ----------------------------- |
| 0,01%       | `100`        | 1               | Stable–stable                 |
| 0,05%       | `500`        | 10              | Correlati (es. ETH/BTC)       |
| 0,25%       | `2500`       | 50              | La maggior parte delle coppie |
| 1,00%       | `10000`      | 200             | Esotici / volatili            |

Una **posizione** V3 è un NFT ERC-721 detenuto nel NonfungiblePositionManager. Memorizza `tickLower`, `tickUpper`, `liquidity` e le commissioni maturate. Vi fai riferimento tramite `tokenId`.

***

### 3. Strumenti

Puoi comunicare con questi contratti con ABI raw e qualsiasi libreria web3, ma i pacchetti **`@pancakeswap/v3-sdk`** e **`@pancakeswap/smart-router`** eseguono la matematica complessa (tick ↔ prezzo, minimi adeguati allo slippage, codifica calldata) per te. Gli esempi qui sotto li usano con [viem](https://viem.sh/).

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

Il tuo agente è semplicemente questo portafoglio che esegue transazioni su un calendario o trigger. Il portafoglio è finanziato e gestito da Agent Studio — consulta la documentazione BNB.

***

### 4. Lettura dello stato (fallo prima di ogni azione)

Un agente decide _se_ agire leggendo la chain. Le tre letture che guidano la maggior parte delle strategie:

**Prezzo del pool e tick corrente** — costruisci un'entità `Pool` da `slot0` + `liquidity` on-chain:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress risolto dalla factory o computePoolAddress()
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

console.log('price token0→token1:', pool.token0Price.toSignificant(6))
console.log('current tick:', pool.tickCurrent)
```

**Una posizione che possiedi** — leggila dal NonfungiblePositionManager tramite `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**La posizione è nel range?** Quel singolo booleano è il trigger per un ribilanciatore. Puoi restringerlo a "entro N tick dal confine" per agire _prima_ che esca dal range.

***

### 5. Sequenze di transazione sicure

Questa è la parte da capire correttamente. Un agente non presidiato non ha nessun umano a correggere una transazione errata, quindi ogni chiamata che modifica lo stato deve essere difesa con i quattro guardrail qui sotto.

#### 5.1 Approvazioni

Prima che un contratto possa spostare i tuoi token ha bisogno di un'allowance. Il meccanismo corretto dipende dal contratto che stai chiamando — tutti e tre qui sotto sono permissionless:

* **ERC-20 `approve`** — funziona sia per lo Smart Router che per il NonfungiblePositionManager, con qualsiasi token. Una transazione per token/spender. Il più semplice, ma un'approvazione infinita permanente è un rischio permanente.
* **`selfPermit` (EIP-2612)** — per le operazioni di liquidità del **NonfungiblePositionManager**. Se il token supporta EIP-2612, l'SDK può raggruppare un permit firmato e limitato all'importo _inline_ con `mint`/`increaseLiquidity` tramite multicall — nessuna transazione di approvazione separata. Torna ad `approve` per i token senza EIP-2612.
* **Permit2** — per gli swap dello **Smart Router**. Approva Permit2 una volta per token, poi concedi allowance firmate, limitate nel tempo e nell'importo per ogni swap.

Per un agente autonomo: limita ogni permit all'importo esatto e a una scadenza breve. **Non concedere mai un'approvazione illimitata da un portafoglio agente che detiene saldi significativi.**

#### 5.2 Slippage — non inviare mai `amountMin = 0`

Ogni aggiunta/rimozione/swap deve specificare un output minimo accettabile. Lascia che l'SDK lo derivi da una tolleranza invece di calcolarlo manualmente:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0,50%

// quando si minta / aggiunge:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// quando si rimuove:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Per gli swap, lo Smart Router applica `slippageTolerance` e calcola `amountOutMinimum` per te (§6, passo 0). **Un minimo zero è un invito aperto ai bot sandwich** — su un portafoglio non presidiato questo può significare perdite ripetute e silenziose.

#### 5.3 Scadenze — impostane sempre una

Ogni chiamata richiede una `deadline` (secondi unix). Se la transazione è ancora in sospeso a quel momento, viene annullata invece di eseguirsi a un prezzo non aggiornato. Tienila breve per un agente:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minuti
```

#### 5.4 Multicall — rendi atomiche le azioni multi-step

Il NonfungiblePositionManager e lo Smart Router supportano `multicall`: diverse chiamate raggruppate in **una transazione** che vanno tutte a buon fine o vengono tutte annullate. Non si tratta solo di risparmio sul gas — è una proprietà di sicurezza. Un ribilanciamento che esegue `decreaseLiquidity` poi `collect` non deve mai eseguirsi a metà. L'SDK raggruppa per te:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Non esiste una funzione atomica "ribilancia".** Spostare un range è una sequenza _composta_ (rimozione → raccolta → mint). La rimozione e il nuovo mint avvengono in transazioni separate; il prezzo può muoversi nel mezzo. Rileggi lo stato e ricalcola i minimi per il mint dopo la conferma della rimozione — non riutilizzare i numeri pre-rimozione.

#### Checklist dei guardrail (applica a ogni azione dell'agente)

* \[ ] Allowance del token limitata all'importo (Permit2), non illimitata
* \[ ] `amount*Min` / `amountOutMinimum` derivati da una tolleranza allo slippage esplicita, mai `0`
* \[ ] `deadline` breve su ogni chiamata
* \[ ] Azioni multi-step raggruppate tramite `multicall`
* \[ ] Stato riletto tra transazioni separate di una sequenza
* \[ ] Un limite per esecuzione sul valore spostato e un controllo di sanità che il prezzo del pool sia entro i limiti previsti prima di agire (difesa economica contro l'agire in un pool manipolato/illiquido)

***

### 6. Esempio pratico — ribilanciatore automatico di range V3

L'agente di riferimento. Monitora una posizione; quando il prezzo si avvicina al confine del range, ritira la liquidità e re-minta un range fresco centrato sul prezzo attuale. Cinque passaggi.

**Trigger:** `pool.tickCurrent` è entro un buffer di `tickLower`/`tickUpper` (dal §4).

#### Passo 0 — (opzionale) ribilancia il rapporto dei token

Dopo il ritiro, terrai token0 e token1 nel rapporto prodotto dal vecchio range. Un nuovo range ricentrato di solito necessita di un rapporto diverso, quindi scambia l'eccesso tramite lo Smart Router:

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

#### Passi 1–3 — rimozione della liquidità, raccolta, burn (una transazione)

`removeCallParameters` costruisce l'intero bundle: esegue `decreaseLiquidity` a zero, raccoglie (`collect`) sia il capitale ritirato che le commissioni maturate, e brucia (`burn`) il NFT ora vuoto — come un unico `multicall` atomico.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — uscita completa
  slippageTolerance: new Percent(50, 10_000),     // 0,50% — imposta amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // attendi — il prossimo mint dipende da questi token
```

> Se la posizione è **in staking su MasterChefV3**, non la rimuovi dal NFPM. Chiama prima `MasterChefV3.withdraw(tokenId, to)` per fare l'unstaking (questo raccoglie anche il CAKE in sospeso), che restituisce il NFT al tuo portafoglio — poi esegui la rimozione sopra. Vedi §7.

#### Passo 4 — minta il nuovo range

Ricalcola i tick attorno al prezzo _corrente_ (rileggi il pool — vedi §5.4), allineali alla spaziatura del livello di commissione, costruisci una `Position` dai token che ora detieni e minta.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* rileggi slot0 + liquidity → nuovo Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // ampiezza del range definita dalla strategia

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
  slippageTolerance: new Percent(50, 10_000), // imposta amount0Min/amount1Min per il mint
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

L'agente ora detiene un NFT fresco nel range. Se stava facendo Farm, mettilo di nuovo in staking (§7). Torna alla lettura §4 al prossimo tick.

***

### 7. Interazioni con le Farm (MasterChefV3)

Fare Staking di un NFT di posizione V3 in MasterChefV3 guadagna CAKE oltre alle commissioni di swap.

> **Solo le posizioni di pool con una Farm attiva guadagnano CAKE.** La Governance di PancakeSwap registra quali pool sono eligible per le Farm (ognuno ottiene un `pid`). Fare Staking di una posizione il cui pool non è registrato genera un errore con `InvalidPid`. Questo è l'unico punto in cui l'attività dell'agente dipende da un elenco lato PancakeSwap — ed è a livello di pool, non a livello di agente: qualsiasi portafoglio può fare staking in qualsiasi Farm attiva. (Gestire una posizione tramite il NonfungiblePositionManager — mint/collect/ribilanciamento — non necessita di Farm e funziona per ogni pool.)

> **Solo le posizioni di pool con una Farm attiva guadagnano CAKE.** La Governance di PancakeSwap registra quali pool sono eligible per le Farm (ognuno ottiene un `pid`). Fare Staking di una posizione il cui pool non è registrato genera un errore con `InvalidPid`. Questo è l'_unico_ punto in cui l'attività dell'agente dipende da un elenco lato PancakeSwap — ed è a livello di pool, non a livello di agente: qualsiasi portafoglio può fare staking in qualsiasi Farm _attiva_. Controlla che il pool abbia una Farm attiva prima di costruire una strategia di farming attorno ad essa. (Gestire una posizione tramite il NonfungiblePositionManager — mint/collect/ribilanciamento — non necessita di Farm e funziona per ogni pool.)

* **Staking** — trasferisci il NFT di posizione a MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). La Farm ora ha in custodia il NFT.
* **Harvest** — `harvest(tokenId, to)` rivendica il CAKE in sospeso senza fare l'unstaking. Usa `batchHarvest` per rivendicare su diverse posizioni in una transazione.
* **Withdraw / exit** — `withdraw(tokenId, to)` fa l'unstaking, raccoglie il CAKE in sospeso e restituisce il NFT al tuo portafoglio. Devi fare il withdraw prima di poter eseguire `decreaseLiquidity`/`burn` (le chiamate NFPM nel §6 funzionano solo su un NFT detenuto dal tuo portafoglio).

Un ribilanciatore per una posizione **in Farm** quindi esegue: `withdraw` → rimozione/raccolta/burn → mint → `safeTransferFrom` di nuovo in MasterChefV3.

***

### 8. Sicurezza, limiti e avvertenze

Leggi questo prima di distribuire un agente che gestisce fondi reali.

* **L'autonomia è irreversibile.** Un agente distribuito firma e invia transazioni senza conferma umana. Un bug, un trigger errato o un feed di prezzo manipolato si esegue per davvero. Testa sulla testnet BSC, poi limita l'esposizione su mainnet (limiti per operazione e giornalieri) prima di scalare.
* **Slippage e scadenze sono obbligatori**, non opzionali (§5). Un agente che li omette verrà prima o poi sottoposto ad attacchi sandwich.
* **Difesa dalla manipolazione dei prezzi.** Prima di agire, controlla il prezzo del pool rispetto a un riferimento indipendente e salta l'esecuzione se divergono — assicurazione economica contro il trading in un pool manipolato o poco liquido.
* **Gas e finanziamento.** Tieni il portafoglio dell'agente finanziato con BNB per il gas; un agente a corto di fondi può lasciare una posizione a metà del ribilanciamento (rimossa ma non re-mintata). Rileggere lo stato ad ogni esecuzione (§4) gli consente di recuperare al prossimo tick.
* **Token Scaled-UI / RWA.** Alcuni token BSC (es. Binance Stock Tokens) usano moltiplicatori UI on-chain (ERC-8056). Gli importi raw on-chain differiscono dagli importi visualizzati. Se il tuo agente scambia questi token, esegui tutta la matematica del contratto in unità raw e applica il moltiplicatore solo per la visualizzazione destinata agli utenti.
* **Sei responsabile del tuo agente.** I pool di PancakeSwap sono contratti permissionless; distribuire un agente autonomo contro di essi è una tua decisione e un tuo rischio. Questa guida è un riferimento tecnico, non un consiglio finanziario, e PancakeSwap non fornisce garanzie sui risultati.

***

### 9. Riferimenti

* **`@pancakeswap/smart-router`** — routing + calldata di swap (i migliori esempi nel repo sono nel suo README)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, matematica tick/prezzo
* **BNB Agent Studio** — descrivere, costruire e distribuire l'agente (documentazione BNB)
* **Indirizzi di deployment PancakeSwap** — elenco canonico dei contratti (verifica prima dell'uso)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
