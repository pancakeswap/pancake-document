# Pools de Liquidez

![](../../.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#03e94594-5a75-4687-b260-0dc69574b953" id="03e94594-5a75-4687-b260-0dc69574b953"></a>

Na nova Exchange V3, a liquidez será administrada na forma de posições não-fungíveis. Você ainda ganhará uma participação nas taxas enquanto fornece liquidez. Ao adicionar seu token a uma pool de liquidez, você receberá tokens de provedor de liquidez (LP) e compartilhará as taxas.

## **Posições de liquidez Não-fungíveis**

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

Na V3, os fornecedores de liquidez agora têm mais controle sobre a faixa(range) de preço que desejam para implantar sua liquidez. Portanto, ao adicionar seu token em uma pool de liquidez na V3, você criará uma nova posição de liquidez não-fungível com suas configurações exclusivas.&#x20;

Portanto, na V3, as posições de liquidez são NFTs. Observe que esses NFTs são transferíveis e representam a propriedade dos ativos subjacentes e as taxas de negociação que eles ganharam.&#x20;

Na V3, as taxas de negociação não serão mais compostas automaticamente na posição. Você pode reivindicá-los manualmente em cada uma das páginas de detalhes da posição.&#x20;

Você pode resgatar seus fundos a qualquer momento removendo sua liquidez.

## **Liquidez Ativa e Ranges de Preço**

No V3, os provedores de liquidez podem configurar suas posições para fornecer liquidez apenas quando o preço estiver dentro de um determinado intervalo. Se o preço de negociação sair do intervalo, a posição consistirá em apenas um tipo de token no par e ficará inativa.&#x20;

As posições de liquidez inativas não participarão da negociação nem receberão quaisquer taxas de negociação.

### **Liquidez Concentrada**

Na V3, por causa da liquidez, os provedores podem concentrar seus depósitos de token para fornecer liquidez apenas dentro de uma faixa de preço específica. Com a mesma quantidade de ativos subjacentes, a V3 pode suportar uma negociação muito maior.

Isso resulta em um nível de liquidez relativa muito maior quando comparado ao V2. E os provedores de liquidez podem ganhar mais taxas de negociação com a mesma quantidade de capital.&#x20;

Aqui está um exemplo:

> Baller e Claire forneceram liquidez na pool CAKE/USDT com US$ 1.000 em valor de ativos em tokens. O preço atual do CAKE é de 5 USDT.&#x20;
>
> Semelhante à PancakeSwap v2, Baller forneceu sua liquidez em toda a faixa de preço. Portanto, ele depositou todo o seu capital, 500 USDT e 100 CAKE.&#x20;
>
> Claire utilizou o novo recurso de liquidez concentrada na PancakeSwap v3 e criou uma posição com uma faixa de preço de 2 a 12,5 USDT por CAKE. Ela depositou 185 USDT e 37 CAKE, no valor total de $ 370. Ela agora pode gastar os $ 630 restantes em outro lugar, como bloquear o CAKE na pool de syrup para aproveitar o alto rendimento do CAKE enquanto recebe uma série de benefícios do ecossistema PancakeSwap.&#x20;
>
> Enquanto o CAKE permanecer na faixa de preço de 2 a 12,5, tanto Baller quanto Claire receberão a mesma quantidade de recompensas de taxas de negociação, enquanto Claire depositou muito menos capital na pool de liquidez.

## **Taxas de Trade Ganhas**

Fornecer liquidez oferece uma recompensa na forma de taxas de negociação quando as pessoas usam sua pool de liquidez para fazer swaps.&#x20;

Sempre que alguém negocia na PancakeSwap, para cada hop (swap) em cada pool de liquidez da Exchange V3, dependendo do nível de taxa da pool de liquidez, o trader paga uma taxa que varia de 0,01% a 0,1%. As faixas de taxas e repartições das taxas são mostradas a seguir:

|                      | 0.01% | 0.05% | 0.25% | 1%  |
| -------------------- | ----- | ----- | ----- | --- |
| Provedor de Liquidez | 67%   | 66%   | 68%   | 68% |
| Queima de CAKE Burn  | 10%   | 10%   | 23%   | 23% |
| Tesouro              | 23%   | 24%   | 9%    | 9%  |

Por exemplo, em uma pool com taxa de 0,25%:&#x20;

* Entre todas as posições de liquidez ativas (dentro do intervalo), há um total de 10 tokens CAKE e 10 BNB.&#x20;
* Alguém troca 1 CAKE por 1 BNB.&#x20;
* Outra pessoa troca 1 BNB por 1 CAKE.&#x20;
* Os provedores de liquidez que estão na faixa de fornecimento de liquidez ativa ganharam um total de 0,0017 CAKE e 0,0017 BNB das negociações.&#x20;
* As posições com faixas de preço que não cobrem o preço atual, portanto, inativas, não contribuirão para a negociação, nem receberão nenhuma taxa.

## Ganhando CAKE&#x20;

Para tornar ainda mais valioso ser um provedor de liquidez, você também pode colocar suas posições de liquidez para trabalhar, gerando um novo rendimento nos [Farms de CAKE](https://pancakeswap.finance/farms), enquanto ainda ganha recompensas de taxas de negociação.

## Exchange V2

### LP Tokens

<figure><img src="../../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

Por exemplo, se você deposita **CAKE** e **BNB** em uma pool de liquidez, recebe tokens **CAKE-BNB LP**.&#x20;

O número de tokens LP que você recebe representa sua parte na pool de liquidez CAKE-BNB.&#x20;

Você também pode resgatar seus fundos a qualquer momento removendo sua liquidez.&#x20;

## Ganhando taxas de negociação&#x20;

Sempre que alguém negocia na PancakeSwap, para cada hop (swap) em cada pool de liquidez da Exchange V2, o trader paga uma taxa fixa de 0,25%, **dos quais 0,17%** é adicionado de volta à pool de liquidez na forma de taxas de negociação.&#x20;

## Ganhando CAKE&#x20;

A antiga Exchange V2 será executada em paralelo com a nova Exchange V3. Portanto, alguns pares de negociação permanecerão na PancakeSwap Exchange V2 e terão seus Farms V2 correspondentes. Verifique as tags para identificar as versões da exchange.

## Impermanent Loss (Perda Impermanente)

Fornecer liquidez não é isento de riscos, pois você pode estar exposto a perdas impermanentes.\
[“](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)[Simplificando, a perda impermanente é a diferença entre holdar tokens em um AMM e holdar os tokens na sua carteira.” - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
