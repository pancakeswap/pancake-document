# 🚜 Yield Farming

![](../../.gitbook/assets/yield-farms-header.png)

Farms de rendimento(Yield Farming) permite que os usuários ganhem CAKE enquanto apoiam a PancakeSwap fazendo stake de LP Tokens.

Confira nosso [Guia de Como usar farms](https://docs.pancakeswap.finance/v/portuguese-brazilian/produtos/yield-farming/how-to-use-farms) para começar a colher rendimentos.&#x20;

Saiba [Como encontrar os contratos inteligentes do Farm](https://docs.pancakeswap.finance/v/portuguese-brazilian/produtos/yield-farming)

{% hint style="warning" %}
Yield Farm pode dar melhores recompensas do que as Pools de Syrup, mas vem com o risco de **Perda Impermanente(Impermanent Loss)**. Não é tão assustador quanto parece, mas vale a pena aprender sobre o conceito antes de começar.&#x20;

Confira este ótimo [artigo sobre Perda Impermanente da Binance Academy](https://academy.binance.com/pt/articles/impermanent-loss-explained) para saber mais.
{% endhint %}

## Cálculo de Recompensas

Cálculo do APR de Yield Farm inclui ambos:

* **APR das recompensas do LP** ganhos através do fornecimento de liquidez e;
* **APR das recompensas base do Farm** ganhos pelo stake de LP Tokens no Farm.

Por quê? Porque quando você faz stake de seus tokens LP em um farm para ganhar CAKE, você ainda está fornecendo liquidez à pool de liquidez, então você também ganha recompensas  do LP!

![](<../../.gitbook/assets/Frame 1 (3).png>)

Então como calculamos essas coisas?

### Calculando APR das recompensas base do Farm

O **APR Base do Farm** é calculada de acordo com o multiplicador do farm e a quantidade total de liquidez no farm -- esta é a quantidade de CAKE distribuída para o farm.

### Calculando APR da recompensas do LP

Além disso, os farmers recebem **recompensas em LP** por fornecer liquidez. Aqui está um exemplo de cálculo de **recompensas de LP**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1\_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq\_cfiBriKcl)

No par WBNB/BUSD acima, vemos esses valores:

**Liquidez:** $387,42M\
**Volume 24H:** $96,97M\
**Volume 7D:** 709,73M

* Calcular taxas anuais
  * Use o volume de 24H para calcular **a proporção das taxas** de fornecedores de liquidez na pool (baseado no 0,17% da estrutura de taxa de trade):\
    $96,970,000\*0.17/100 = **$164,849**
  * A seguir, use aquela **proporção das taxas** para estimar as **taxas anuais** projetadas para serem ganhas pela pool (baseado no atual volume de 24h):\
    $164,849\*365 = **$60,169,885**
* Agora podemos usar as taxas anuais para calcular o **APR das recompensas de LP**: São **taxas anuais** divididas pela **liquidez:**\
  ($60,169,885/$387,420,000)\*100 = **15.53% APR das recompensas do LP**
