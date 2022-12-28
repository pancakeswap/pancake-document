# 🔄 StableSwap

<figure><img src="../../.gitbook/assets/docs masthead.png" alt=""><figcaption></figcaption></figure>

StableSwap na PancakeSwap é um recurso para negociar pares de stable com uma slippage/derrapagem mais baixa com base em uma função de curva de slippage  invariável. Ele foi projetado para fazer swap de ativos específicos com preços próximos - como stablecoins em dólares (por exemplo, HAY, BUSD e USDT) ou tokens de staking líquidos (por exemplo, stkBNB e aBNBc).&#x20;

O StableSwap é uma implementação do AMM da Curve Finance na PancakeSwap. Ele adiciona a curva de soma constante invariável linear (x+y=k) no topo da fórmula do produto constante (x\*y=k) para manter os preços mais iguais, desde que a pool de liquidez não seja extremamente desequilibrada. Como resultado, como os StableSwaps são restritos a ativos com preços semelhantes, a impermanent loss não é tão preocupante (exceto em casos extremos de depeg) e a slippage/derrapagem é menor do que o AMM normal, que usa apenas a fórmula do produto constante.&#x20;

Quando você faz uma troca de token (negociação) no StableSwap, você paga uma taxa de 0,04% de taxas de negociação, que é menor do que os 0,25% normais no PancakeSwap AMM normal. A atribuição de taxas é dividida da seguinte forma:



* 50% para o LP como recompensa&#x20;
* 40% para recompra e queima de CAKE
* 10% para o tesouro da PancakeSwap&#x20;

| Pares de Stable | Taxas do Trade | Recompensas para o LP | Recompra de CAKE | Tesouro da PancakeSwap  |
| --------------- | -------------- | --------------------- | ---------------- | ----------------------- |
| USDT-BUSD       | 0.15%          | 0.075%                | 0.06%            | 0.015%                  |
| USDC-BUSD       | 0.15%          | 0.075%                | 0.06%            | 0.015%                  |
| USDC-USDT       | 0.15%          | 0.075%                | 0.06%            | 0.015%                  |
| HAY-BUSD        | 0.04%          | 0.02%                 | 0.016%           | 0.004%                  |

A Cozinha lançará gradualmente os pares StableSwap e revisará as taxas para testar e melhorar ainda mais o produto.

## Por que devo usar o StableSwap em vez do swap AMM normal?

* Faça swap de suas stablecoins ou outros pares de ativos com preços semelhantes com mais eficiência com os mesmo passos na negociação!&#x20;
* Com a função StableSwap, a slippage/derrapagem de negociação é menor do que o AMM normal, que usa apenas a fórmula do produto constante
* As taxas de negociação também são mais baixas em comparação com o AMM normal.

## Ainda Cozinhando

* Melhores guias sobre interface do usuário em relação a StableSwap e LPs estáveis
* Página de informações do StableSwap
* Adicionando pares de negociação de mais stables e o processo de migração de LPs existentes

## Linha do Tempo <a href="#timeline" id="timeline"></a>

* USDC-BUSD, USDT-BUSD, USDC-USDT fornecimento de liquidez liberada: **Nov 30 2022 11:00 UTC**
* Migração do Farm (Recopmensas de CAKE redirecionada dos farms de LP USDC-BUSD, USDT-BUSD, USDC-USDT para os Farms LP de Stable USDC-BUSD, USDT-BUSD, USDC-USDT): TBD

## Perguntas frequentes sobre o lançamento do Stablepool em 30 de novembro&#x20;

O que aconteceu com os novos Stablepools?&#x20;

* Encontramos um pequeno problema com o parâmetro de taxa&#x20;
* Isso resultou na incapacidade de remover liquidez em 50%/50% devido a taxas administrativas mais altas&#x20;

Principais atualizações:&#x20;

* Seus fundos estão seguros&#x20;
* Revertemos o FE e o revertemos para a versão anterior antes das novas pools&#x20;
* As taxas serão reembolsadas para todos os provedores de LP ativos na pool&#x20;
* Enquanto isso, os chefs estão trabalhando em uma solução. Depois de implantado, você poderá gerenciar seu LP de stable&#x20;
* A migração do farm será atrasada até que a correção seja implantada&#x20;

Continuaremos a fornecer atualizações aqui assim que pudermos.
