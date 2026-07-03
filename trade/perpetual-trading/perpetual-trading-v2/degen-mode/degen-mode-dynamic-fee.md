# Taxa Dinâmica do Degen Mode

O PancakeSwap Perpetuals Degen Mode usa um modelo de taxa dinâmica. Esta taxa é projetada para cobrar taxas baseadas em PnL e proteger os usuários de perdas.\
**Como funciona?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

onde:

* Pnl é o lucro ou perda na posição
* shareRate é a taxa de participação, que é o percentual do nocional pago em taxas (15% por padrão)
* Notional é o valor monetário usado para abrir a posição
* closeMinRate é a taxa mínima de fechamento de posição, que é o valor mínimo que você pode pagar para fechar uma posição (0,03% por padrão)

\
**Exemplo:**

Se você tem uma posição com lucro de $100, uma taxa de participação de 15% e um nocional de $600, então a taxa de fechamento seria:

Taxa de fechamento = Max(100 \* 15% / 600, 0,03%) = 0,03%

Neste caso, a taxa de fechamento seria de 0,03%, a taxa mínima de fechamento.<br>

Nota:

A taxa de execução só será cobrada quando uma posição é aberta. Está definida em 0,3 USD (BNB Chain) / 0,2 USD (Arbitrum) / 0,01 USD (opBNB) / 0,3 USD (Base), semelhante ao que é cobrado ao negociar pares de trading perpétuo clássico. Não há taxa de abertura de posição.

No caso de Liquidação, a taxa de perda líquida de 90% inclui a taxa de fechamento.
