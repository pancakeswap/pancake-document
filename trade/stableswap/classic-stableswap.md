# Classic StableSwap

O Classic StableSwap é uma implementação do AMM da Curve Finance no PancakeSwap. Ele adiciona a curva de soma constante linear (x+y=k) sobre a fórmula de produto constante (x\*y=k) para manter os preços mais iguais enquanto o Pool de Liquidez não estiver extremamente desequilibrado. Como resultado, como os StableSwaps são restritos a ativos com preços semelhantes, a perda impermanente não é uma grande preocupação (exceto em casos extremos de depeg) e o Slippage é menor do que no AMM normal que usa apenas a fórmula de produto constante.

Ao realizar um Swap (negociação) no StableSwap, você pagará taxas de negociação menores do que os 0,25% habituais no AMM normal do PancakeSwap. A distribuição das taxas é a seguinte:

* 50% para o LP como recompensas&#x20;
* 40% para recompra e queima de CAKE&#x20;
* 10% para o Tesouro PancakeSwap

## Taxas do Stableswap

As taxas para os pares estão detalhadas na tabela abaixo:

<table><thead><tr><th width="150">Par Estável</th><th width="132">Taxas de Negociação</th><th width="118.33333333333331">Recompensas LP</th><th width="124">Recompra de CAKE</th><th>Tesouro PancakeSwap</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-USDT</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>HAY-BUSD</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>HAY-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>axlUSDC-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>BNBx-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>stkBNB-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr></tbody></table>

A equipe gradualmente lançará pares StableSwap e revisará as taxas para testar e melhorar ainda mais o produto.

## Por que devo usar o StableSwap em vez do Swap AMM normal?

* Troque suas stablecoins ou outros pares com preços de ativos semelhantes de forma mais eficiente com os mesmos passos de negociação&#x20;
* Com a função StableSwap, o Slippage de negociação é menor do que no AMM normal&#x20;
* As taxas de negociação do StableSwap são menores em comparação com o AMM normal
