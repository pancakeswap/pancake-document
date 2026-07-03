# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Yield Farms ermöglichen es Nutzern, CAKE zu verdienen und PancakeSwap zu unterstützen, indem sie LP-Tokens staken.

Lesen Sie unsere [Anleitung zur Nutzung von Farms](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms), um mit dem Farming zu beginnen.

Erfahren Sie, [wie Sie Farm-Smart-Contracts finden](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Yield Farming kann bessere Erträge als Syrup Pools bieten, ist jedoch mit dem Risiko eines **Impermanent Loss** verbunden. Das klingt bedrohlicher als es ist, aber es lohnt sich, das Konzept zu verstehen, bevor Sie beginnen.

Lesen Sie diesen hervorragenden [Artikel über Impermanent Loss](https://academy.binance.com/en/articles/impermanent-loss-explained) von der Binance Academy, um mehr zu erfahren.
{% endhint %}

## Ertragsberechnungen

Die APR-Berechnungen für Yield Farms umfassen sowohl:

* **LP-Rewards APR**, der durch die Bereitstellung von Liquidität erzielt wird, als auch
* **Farm Base Rewards APR**, der durch das Staken von LP-Tokens in der Farm erzielt wird.

Warum? Wenn Sie Ihre LP-Tokens in einer Farm staken, um CAKE zu verdienen, stellen Sie weiterhin Liquidität für den Liquiditätspool bereit und erhalten daher ebenfalls LP-Rewards!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Wie werden diese Werte berechnet?

### Berechnung des Farm Base Reward APR

Der **Farm Base APR** wird anhand des Farm-Multiplikators und der Gesamtliquidität in der Farm berechnet – dies entspricht der Menge an CAKE, die der Farm zugeteilt wird.

### Berechnung des LP Reward APR

Darüber hinaus erhalten Farmer **LP-Rewards** für die Bereitstellung von Liquidität. Hier ein Beispiel zur Berechnung der **LP-Rewards**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

Im oben dargestellten WBNB/BUSD-Paar sehen wir folgende Werte:

**Liquidität:** $387,42 Mio.\
**Volumen 24H:** $96,97 Mio.\
**Volumen 7T:** 709,73 Mio.

* Jährliche Gebühren berechnen
  * Verwenden Sie das 24-Stunden-Volumen, um den **Gebührenanteil** der Liquiditätsanbieter im Pool zu berechnen (basierend auf der Handelsgebührenstruktur von 0,17 %):\
    $96.970.000 × 0,17 / 100 = **$164.849**
  * Verwenden Sie diesen **Gebührenanteil**, um die prognostizierten **jährlichen Gebühren** des Pools zu schätzen (basierend auf dem aktuellen 24-Stunden-Volumen):\
    $164.849 × 365 = **$60.169.885**
* Anhand der jährlichen Gebühren lässt sich nun der **LP Rewards APR** berechnen: Die **jährlichen Gebühren** geteilt durch die **Liquidität**:\
  ($60.169.885 / $387.420.000) × 100 = **15,53 % LP Reward APR**
