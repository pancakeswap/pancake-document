# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Os Farms de Yield Farming permitem que os usuários ganhem CAKE enquanto apoiam a PancakeSwap fazendo Staking de LP Tokens.

Confira nosso [guia Como Usar os Farms](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) para começar a fazer farming.

Saiba [como encontrar contratos inteligentes dos Farms](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
O Yield Farming pode oferecer recompensas melhores do que os Syrup Pools, mas apresenta o risco de **Perda Impermanente**. Não é tão assustador quanto parece, mas vale a pena aprender o conceito antes de começar.

Confira este excelente [artigo sobre Perda Impermanente](https://academy.binance.com/en/articles/impermanent-loss-explained) da Binance Academy para saber mais.
{% endhint %}

## Cálculos de recompensa

Os cálculos de APR do Yield Farming incluem tanto:

* **APR de recompensas LP** ganho ao fornecer liquidez e;
* **APR de recompensas base do Farm** ganho fazendo Staking de LP Tokens no Farm.

Por quê? Porque quando você faz Staking dos seus LP tokens em um farm para ganhar CAKE, você ainda está fornecendo liquidez ao pool de liquidez, portanto também ganha recompensas LP!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Então como calculamos esses valores?

### Calculando o APR de Recompensa Base do Farm

O **APR Base do Farm** é calculado de acordo com o multiplicador do farm e a quantidade total de liquidez no farm — esse é o valor de CAKE distribuído ao farm.

### Calculando o APR de Recompensa LP

Além disso, os farmers recebem **recompensas LP** por fornecer liquidez. Aqui está um exemplo de cálculo das **recompensas LP**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

No par WBNB/BUSD acima, vemos estes valores:

**Liquidez:** $387,42M\
**Volume 24H:** $96,97M\
**Volume 7D:** 709,73M

* Calcular as taxas anuais
  * Use o volume de 24H para calcular a **participação nas taxas** dos provedores de liquidez no pool (baseado na estrutura de taxa de negociação de 0,17%):\
    $96.970.000\*0,17/100 = **$164.849**
  * Em seguida, use essa **participação nas taxas** para estimar as **taxas anuais projetadas** ganhas pelo pool (com base no volume atual de 24h):\
    $164.849\*365 = **$60.169.885**
* Agora podemos usar as taxas anuais para calcular o **APR de recompensas LP:** São as **taxas anuais** divididas pela **liquidez:**\
  ($60.169.885/$387.420.000)\*100 = **15,53% APR de recompensa LP**
