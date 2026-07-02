# 🌊 Pools de Liquidez

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

No novo Exchange V3, a liquidez será gerenciada na forma de posições não fungíveis. Você ainda receberá uma parte das taxas enquanto fornece liquidez.

Quando você adiciona seus tokens a um Pool de Liquidez, receberá tokens NFT de Provedor de Liquidez e participará das taxas.

### **Posições de liquidez não fungíveis**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

No V3, os provedores de liquidez agora têm mais controle sobre qual faixa de preço desejam implantar sua liquidez. Portanto, ao adicionar seus tokens a um Pool de Liquidez no V3, você criará uma nova posição de liquidez não fungível com suas configurações exclusivas.

Portanto, no V3, as posições de liquidez são NFTs. Observe que esses NFTs são transferíveis e representam a propriedade dos ativos subjacentes e das taxas de negociação que geraram.

No V3, as taxas de negociação não serão mais automaticamente compostas na posição. Você pode reivindicá-las manualmente em cada uma das páginas de detalhes da posição.

Você pode resgatar seus fundos a qualquer momento removendo sua liquidez.

### **Liquidez ativa e faixas de preço**

No V3, os provedores de liquidez podem configurar suas posições para fornecer liquidez apenas quando o preço estiver dentro de um determinado intervalo. Se o preço de negociação sair do intervalo, a posição consistirá em apenas um tipo de token do par e se tornará inativa.

As posições de liquidez inativas não participarão das negociações nem gerarão taxas de negociação.

### **Liquidez concentrada**

No V3, os provedores de liquidez podem concentrar seus depósitos de tokens para fornecer liquidez apenas dentro de uma faixa de preço específica. Com a mesma quantidade de ativos subjacentes, o V3 pode suportar uma negociação muito maior.

Isso resulta em um nível de liquidez relativa muito maior em comparação ao V2. E os provedores de liquidez podem ganhar mais taxas de negociação com a mesma quantidade de capital.

Aqui está um exemplo:

> Baller e Claire forneceram liquidez no pool CAKE/USDT com $1.000 USD em ativos de tokens. O preço atual do CAKE é 5 USDT.
>
> Similar ao PancakeSwap v2, Baller forneceu sua liquidez em toda a faixa de preço. Portanto, ele depositou todo o seu capital: 500 USDT e 100 CAKE.
>
> Claire utiliza o novo recurso de liquidez concentrada do PancakeSwap v3 e criou uma posição com faixa de preço de 2 a 12,5 USDT por CAKE. Ela depositou 185 USDT e 37 CAKE, totalizando $370. Agora ela pode usar os $630 restantes em outro lugar, como bloquear CAKE no Syrup Pool para desfrutar de alto rendimento de CAKE enquanto recebe uma série de benefícios do ecossistema PancakeSwap.
>
> Enquanto o CAKE permanecer na faixa de preço de 2 a 12,5, tanto Baller quanto Claire receberão a mesma quantidade de recompensas de taxas de negociação, enquanto Claire depositou muito menos capital no pool de liquidez.

### **Taxas de negociação**&#x20;

Fornecer liquidez garante uma recompensa na forma de taxas de negociação quando as pessoas usam seu pool de liquidez para realizar swaps.

Sempre que alguém negocia na PancakeSwap, para cada salto (swap) em cada pool de liquidez Exchange V3, dependendo do nível de taxa do pool de liquidez, o trader paga uma taxa que varia de 0,01% a 1%. As taxas e seus detalhamentos são mostrados da seguinte forma:

<details>

<summary>Taxas de Negociação (EVM)</summary>

| Componente de Taxa / Nível de taxa | 0,01% | 0,05% | 0,25% | 1%  |
| ---------------------------------- | ----- | ----- | ----- | --- |
| Provedor de Liquidez                | 67%   | 66%   | 68%   | 68% |
| Queima de CAKE                     | 15%   | 15%   | 23%   | 23% |
| Tesouro                            | 18%   | 19%   | 9%    | 9%  |

Por exemplo, em um pool com nível de taxa de 0,25%:

* Entre todas as posições de liquidez ativas (dentro do intervalo), há um total de 10 CAKE e 10 BNB tokens.
* Alguém troca 1 CAKE por 1 BNB.
* Outra pessoa troca 1 BNB por 1 CAKE.
* Os provedores de liquidez que estão no intervalo fornecendo liquidez ativa ganharam um total de 0,0017 CAKE e 0,0017 BNB com as negociações.
* Posições com faixas de preço que não cobrem o preço atual, portanto inativas, não contribuirão para a negociação nem ganharão taxas.

</details>

<details>

<summary><strong>Taxas de negociação (Solana)</strong></summary>

**Níveis de taxa disponíveis para pools V3 CLMM:**\
0,01%, 0,02%, 0,03%, 0,04%, 0,05%, 0,1%, 0,15%, 0,16%, 0,18%, 0,2%, 0,25%, 0,4%, 0,6%, 0,8%, 1%, 2%, 3%, 4%

**Nota:** A **distribuição de taxas permanece a mesma** em todos os níveis de taxa.

| Componente de Taxa                | % da Taxa Total de Swap | Descrição                                                      |
| --------------------------------- | ----------------------- | -------------------------------------------------------------- |
| **LPs (Provedores de Liquidez)**  | 84%                     | Ganho pelos LPs que fornecem liquidez na faixa de preço ativa  |
| **Queima**                        | 8%                      | Removido permanentemente para reduzir o fornecimento de CAKE   |
| **Tesouro**                       | 8%                      | Alocado ao tesouro do protocolo PancakeSwap                    |

**Exemplo: Distribuição de Taxas em um Pool CAKE/SOL de 0,25%**

1. **Configuração do Pool:** Liquidez ativa total: 10 CAKE e 10 SOL (posições dentro do intervalo).
2. **Swaps Realizados:**
   * Usuário A troca 1 CAKE → 1 SOL.
   * Usuário B troca 1 SOL → 1 CAKE.
3. **Total de Taxas Coletadas:**
   * 0,25% por trade × 2 trades = **0,005 CAKE + 0,005 SOL**.
4. **Distribuição de Taxas:**
   * **84% para LPs:** 0,0042 CAKE + 0,0042 SOL
   * **8% para Queima:** 0,0004 CAKE + 0,0004 SOL
   * **8% para Tesouro:** 0,0004 CAKE + 0,0004 SOL
5. **Ganhos dos LPs:**
   * Apenas os **LPs dentro do intervalo** ganham taxas. As taxas são distribuídas proporcionalmente com base na participação de cada LP.
   * **LPs fora do intervalo** não ganham **nenhuma taxa**.

</details>

### **Ganhando CAKE**

Para tornar ainda mais vantajoso ser um provedor de liquidez, você também pode colocar suas posições de liquidez para trabalhar e gerar rendimento fresco nas [CAKE Farms](https://pancakeswap.finance/liquidity/pools), enquanto ainda ganha recompensas de taxas de negociação.

***

## Exchange V2

### LP Tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Como exemplo, se você depositou **CAKE** e **BNB** em um Pool de Liquidez, você receberia tokens **CAKE-BNB LP**.

O número de LP Tokens que você recebe representa sua porção do Pool de Liquidez CAKE-BNB.

Você também pode resgatar seus fundos a qualquer momento removendo sua liquidez.

### **Ganhando taxas de negociação**

Sempre que alguém negocia na PancakeSwap, para cada salto (swap) em cada pool de liquidez Exchange V2, o trader paga uma taxa fixa de 0,25%, **sendo 0,17%** adicionado de volta ao Pool de Liquidez na forma de taxas de negociação.

### **Ganhando CAKE**

O antigo Exchange V2 continuará funcionando em paralelo com o novo Exchange V3. Portanto, alguns pares de negociação permanecerão na PancakeSwap Exchange V2 e terão seus Farms V2 correspondentes. Verifique as etiquetas para identificar as versões do exchange.



## Perda Impermanente

Fornecer liquidez não está isento de riscos, pois você pode estar exposto à perda impermanente.

["Simplificando, a perda impermanente é a diferença entre manter tokens em um AMM e mantê-los na sua carteira." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
