# Taxa Dinâmica no Modo Degen

O modo PancakeSwap Perpetuals Degen usa um modelo de taxas dinâmico. Esta taxa foi projetada para cobrar taxas pelo PnL e proteger os usuários de perdas.&#x20;

## Como funciona?

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

onde:&#x20;

* Pnl é o lucro ou perda da posição&#x20;
* shareRate é a taxa de participação, que é a porcentagem do nocional que é paga em taxas (15% como padrão)&#x20;
* Nocional é a quantidade de dinheiro usada para abrir a posição&#x20;
* closeMinRate é a taxa mínima de fechamento, que é o valor mais baixo que você pode pagar para fechar uma posição (0,03% como padrão)

**Exemplo:**&#x20;

Se você tiver uma posição com lucro de US$ 100, uma taxa de participação de 15% e um nocional de US$ 600, então a taxa de fechamento seria:&#x20;

Nível de taxa de fechamento = Máx. (100 \* 15% / 600, 0,03%) = 0,03%&#x20;

Nesse caso, a taxa de fechamento seria de 0,03%, a taxa mínima de fechamento.

Observação:&#x20;

A taxa de execução só será cobrada quando uma posição for aberta. É definido em 0,3 USD (BNB Chain) / 0,2 USD (Arbitrum), semelhante ao que está sendo cobrado ao negociar pares clássicos de negociação perpétua. Não há taxa de posição de abertura.&#x20;

Em caso de liquidação, a taxa de perda de líquido de 90% inclui taxa de fechamento.
