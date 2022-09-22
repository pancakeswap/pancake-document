# 🔄 StableSwap

<figure><img src="../../.gitbook/assets/docs masthead.png" alt=""><figcaption></figcaption></figure>

StableSwap na PancakeSwap é um recurso para negociar pares de stable com uma slippage/derrapagem mais baixa com base em uma função de curva de slippage  invariável. Ele foi projetado para fazer swap de ativos específicos com preços próximos - como stablecoins em dólares (por exemplo, HAY, BUSD e USDT) ou tokens de staking líquidos (por exemplo, stkBNB e aBNBc).&#x20;

O StableSwap é uma implementação do AMM da Curve Finance na PancakeSwap. Ele adiciona a curva de soma constante invariável linear (x+y=k) no topo da fórmula do produto constante (x\*y=k) para manter os preços mais iguais, desde que a pool de liquidez não seja extremamente desequilibrada. Como resultado, como os StableSwaps são restritos a ativos com preços semelhantes, a impermanent loss não é tão preocupante (exceto em casos extremos de depeg) e a slippage/derrapagem é menor do que o AMM normal, que usa apenas a fórmula do produto constante.&#x20;

Quando você faz uma troca de token (negociação) no StableSwap, você paga uma taxa de 0,04% de taxas de negociação, que é menor do que os 0,25% normais no PancakeSwap AMM normal. A atribuição de taxas é dividida da seguinte forma:

* 0.02% para o LP como recompensa (50%)
* 0.016% para recompra e queima de CAKE (40%)
* 0.004% para o tesouro da PancakeSwap (10%)

No lançamento, a Cozinha lançará os pares de StableSwap gradualmente para testar e melhorar ainda mais o produto. O primeiro par a ser lançado será **HAY-BUSD**.

​[**HAY**](https://helio.money/) **** da Helio Protocol é uma stablecoin algorítmica totalmente descentralizada baseada no BNB como colateral. As razões pelas quais o par HAY-BUSD é selecionado como o primeiro são:

* Ser um dos primeiros grandes locais de negociação para a HAY absorver o volume extra
* Como o HAY foi lançado recentemente (meados de agosto de 2022) em comparação com outras stablecoins, o volume e o impacto operacional da transferência de liquidez são mais gerenciáveis para o lançamento do produto StableSwap
* Com base no progresso deste par e no feedback da comunidade, a Cozinha pode adicionar gradualmente outros pares de stable

## Por que devo usar o StableSwap em vez do swap AMM normal?

* Faça swap de suas stablecoins ou outros pares de ativos com preços semelhantes com mais eficiência com os mesmo passos na negociação!&#x20;
* Com a função StableSwap, a slippage/derrapagem de negociação é menor do que o AMM normal, que usa apenas a fórmula do produto constante
* As taxas de negociação também são mais baixas em comparação com o AMM normal.

## Quais são alguns dos recursos que a cozinha ainda está consertando e cozinhando?

* Melhores guias sobre interface do usuário em relação a StableSwap e LPs estáveis
* Página de informações do StableSwap
* Adicionando pares de negociação de mais stables e o processo de migração de LPs existentes

## Linha do Tempo <a href="#timeline" id="timeline"></a>

* Lançamento do StableSwap e fornecimento de liquidez HAY-BUSD habilitada: 22 de setembro de 2022 11:00 UTC&#x20;
* Migração do farm (recompensas de CAKE redirecionadas do Farm de LP de HAY-BUSD para Farm de LP de Stable de HAY-BUSD): 23 de setembro de 2022 11:00 UTC
