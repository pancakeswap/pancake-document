# Options-Grundlagen



{% hint style="danger" %}
[ARCHIVIERT] Options – Stand 11. März 2025\
Wenn Sie noch Liquidität abzuheben haben, tun Sie dies bitte sofort unter https://www.stryke.xyz/en/trade.
{% endhint %}



## Was sind Optionen?

Optionen sind Derivat-Contracts, die dem Käufer das Recht, aber nicht die Verpflichtung geben, ein zugrundeliegendes Vermögenswert zu einem vorher festgelegten Preis (Ausübungspreis) innerhalb eines bestimmten Zeitraums (Ablaufdatum) zu kaufen (Call-Option) oder zu verkaufen (Put-Option).

## Arten von Optionen

### Call-Optionen

Eine Call-Option gibt dem Inhaber das Recht, das zugrundeliegende Vermögenswert zum vereinbarten Ausübungspreis am oder vor dem Ablaufdatum zu kaufen. Händler kaufen Call-Optionen, wenn sie einen Preisanstieg des zugrundeliegenden Vermögenswerts erwarten. Dies ermöglicht es ihnen, von potenziellem Preisanstieg zu profitieren, ohne das zugrundeliegende Vermögenswert direkt besitzen zu müssen.

> Ein Händler kauft eine Call-Option auf Bitcoin mit einem Ausübungspreis von 50.000 USD, die in einem Monat abläuft. Wenn der Bitcoin-Preis innerhalb dieses Monats über 50.000 USD steigt, kann der Anleger die Option ausüben, um Bitcoin zu 50.000 USD zu kaufen und möglicherweise von der Preisdifferenz zu profitieren.

### Put-Optionen

Eine Put-Option gibt dem Inhaber das Recht, das zugrundeliegende Vermögenswert zum vereinbarten Ausübungspreis am oder vor dem Ablaufdatum zu verkaufen. Händler kaufen Put-Optionen, wenn sie einen Preisrückgang des zugrundeliegenden Vermögenswerts erwarten. Dies ermöglicht es ihnen, von potenziellen Preisrückgängen zu profitieren, ohne das zugrundeliegende Vermögenswert leer zu verkaufen. Typischerweise werden Put-Optionen auch zur Absicherung gegen Abwärtsrisiken in Anlageportfolios eingesetzt.

> Ein Händler kauft eine Put-Option auf Ethereum mit einem Ausübungspreis von 3.000 USD, die in zwei Wochen abläuft. Wenn der Ethereum-Preis innerhalb dieses Zeitraums unter 3.000 USD fällt, kann der Händler die Option ausüben, um Ethereum zu 3.000 USD zu verkaufen und dadurch potenzielle Verluste abzumildern.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Optionspositionen

Für jede Art von Option gibt es zwei mögliche Positionen:

### **Long-Option (Optionskäufer)**&#x20;

Bei dieser Position wird eine Vorab-Prämie gezahlt, um die Option zu erwerben. Wenn die Option im Gewinn endet, erhält der Inhaber eine Abrechnung.

### **Short-Option (Optionsschreiber/Verkäufer)**

Bei dieser Position erhält der Verkäufer eine Vorab-Prämie für die Ausgabe der Option. Wenn die Option jedoch im Gewinn endet (für den Käufer; basierend auf dem Basispreis, dem Ausübungspreis und der Art der Option), ist der Verkäufer verpflichtet, eine Abrechnung zu zahlen.

## Amerikanische vs. Europäische Optionen

* **Amerikanische Optionen:** Können jederzeit vor dem Ablaufdatum ausgeübt werden. Diese Flexibilität macht sie wertvoller als europäische Optionen.
* **Europäische Optionen:** Können nur am Ablaufdatum ausgeübt werden. Sie sind im Allgemeinen günstiger als amerikanische Optionen aufgrund ihrer mangelnden Flexibilität.

## Wann sollten Optionen eingesetzt werden?

Hier sind einige Beispiel-Anwendungsfälle:

1. **Spekulation:** Ein Anleger glaubt, dass der Bitcoin-Preis im nächsten Monat steigen wird. Er kauft Call-Optionen auf Bitcoin, um vom erwarteten Preisanstieg zu profitieren.
2. **Absicherung:** Ein Kryptowährungs-Validator möchte sich gegen potenzielle Preisrückgänge bei Ethereum absichern. Er kauft Put-Optionen auf Ethereum, um sich gegen Verluste zu schützen, falls der Preis unter ein bestimmtes Niveau fällt.
3. **Einkommensgenerierung:** Ein Krypto-Anleger, der eine große Menge Ether hält, entscheidet sich, Call-Optionen auf seine Bestände zu schreiben, Prämien zu verdienen und gleichzeitig an potenziellen Aufwärtsbewegungen teilzuhaben.

## Options-Preisgestaltung

Die Options-Preisgestaltung ist komplex und umfasst verschiedene Faktoren, wobei das Black-Scholes-Modell am häufigsten verwendet wird.&#x20;

Wesentliche Faktoren, die die Options-Preisgestaltung beeinflussen:

* **Basispreis:** Der aktuelle Marktpreis des zugrundeliegenden Vermögenswerts.
* **Ausübungspreis:** Der Preis, zu dem der Optionsinhaber das zugrundeliegende Vermögenswert kaufen oder verkaufen kann.
* **Volatilität:** Das Ausmaß der Preisschwankungen des zugrundeliegenden Vermögenswerts.&#x20;
* **Restlaufzeit:** Die verbleibende Zeit bis zum Ablauf der Option.
* **Zinssätze:** Der risikofreie Renditesatz.

Die Options-Preisgestaltung bestimmt die Prämie/Gebühr, die ein Schreiber erhält, wenn ein Optionshändler seine Option kauft. Options-Schreiber sind dem Risiko ausgesetzt, bei ITM-Ablauf ihrer Optionen (vorteilhaft für den Käufer) eine Abrechnung zahlen zu müssen. Daher müssen die von Käufern verdienten Prämien die Wahrscheinlichkeit eines ITM-Ereignisses fair widerspiegeln.

PancakeSwap CLAMM-Options-Prämien werden aus dem Black-Scholes-Modell mit folgenden Annahmen abgeleitet:

* Der risikofreie Zinssatz wird als null angenommen.
* Die Volatilität basiert auf der 30-Tage-historischen Volatilität des Basiswerts [verwendet als Proxy für implizite Volatilität (IV)].

Einige Ausnahmen umfassen:

* Die IV von $ETH und $BTC wird direkt von Deribit übernommen, wenn Ausübungspreise übereinstimmen. Wenn Ausübungspreise nicht übereinstimmen, werden die nächsten oberen und unteren Ausübungen von Deribit basierend auf dem Grad der Abweichung gewichtet, um die IV festzulegen.
* $ARB verwendet die 30-Tage-Beta-basierte historische Volatilität, indem der effektive Ausübungspreis des Basisvermögenswerts gegen $ETH berechnet wird, um die IV zu extrapolieren, die dann mit dem Beta des Basisvermögenswerts gegen $ETH multipliziert wird.

Vermögenswerte mit hoher Volatilität hätten eine teurere Prämie als Vermögenswerte mit geringerer Volatilität, da für Schreiber das Risiko größer ist, dass die Option ITM abläuft.

## Options-Abrechnung

### Abrechnungsbedingungen

* Die Abrechnung wird auf Basis der Geldwertigkeit der Option bei Ablauf bestimmt.
* Die Abrechnung wird nur berechnet, wenn die Option bei Ausübung im Geld (ITM) ist.

### ITM-Bedingungen

* **Call-Option:** Wenn der Spotpreis bei Abrechnung > Ausübungspreis
* **Put-Option:** Wenn der Spotpreis bei Abrechnung < Ausübungspreis

### Abrechnungsberechnung

* **Call-Option:** Anzahl der Optionen \* (Spotpreis bei Abrechnung - Ausübungspreis)
* **Put-Option:** Anzahl der Optionen \* (Ausübungspreis - Spotpreis bei Abrechnung)

### Geldwertigkeit

Die Geldwertigkeit bezieht sich auf den inneren Wert einer Option, der durch den Vergleich ihres Ausübungspreises mit ihrem Spotpreis zum Zeitpunkt der Ausführung bestimmt wird.

### Klassifizierung

1. Aus dem Geld (OTM):
   1. Eine Option ist OTM, wenn der Spotpreis bei Abrechnung vom Ausübungspreis abweicht und bei sofortiger Abrechnung kein Wert ausgetauscht werden soll.
   2. Bedingungen:
      1. Call-Option: Spotpreis < Ausübungspreis
      2. Put-Option: Spotpreis > Ausübungspreis

{% hint style="info" %}
Eine $ETH-Call-Option mit einem Ausübungspreis von 2.000 USD wäre OTM, wenn der Spotpreis 1.800 USD beträgt (1.800 USD < 2.000 USD, d. h. OTM).
{% endhint %}

2. Am Geld (ATM):
   1. Eine Option ist ATM, wenn der Spotpreis bei Abrechnung gleich dem Ausübungspreis ist und bei sofortiger Abrechnung kein Wert ausgetauscht werden soll.
   2. Bedingungen: Sowohl Call- als auch Put-Optionen: Spotpreis = Ausübungspreis

{% hint style="info" %}
Sowohl eine $ETH-Call-Option als auch eine Put-Option mit einem Ausübungspreis von 1.800 USD wären ATM, wenn der Spotpreis ebenfalls 1.800 USD beträgt (1.800 USD = 1.800 USD, d. h. ATM).
{% endhint %}

3. Im Geld (ITM):
   1. Eine Option ist ITM, wenn der Spotpreis bei Abrechnung vom Ausübungspreis abweicht und bei sofortiger Abrechnung ein Wert ausgetauscht werden soll.
   2. Bedingungen:
      1. Call-Option: Spotpreis > Ausübungspreis
      2. Put-Option: Spotpreis < Ausübungspreis

{% hint style="info" %}
Eine $ETH-Call-Option mit einem Ausübungspreis von 1.600 USD wäre ITM, wenn der Spotpreis 1.800 USD beträgt (1.800 USD > 1.600 USD, d. h. ITM).
{% endhint %}

Die vom Optionskäufer verdiente Abrechnung entspricht dem Sicherheitsverlust des Optionsschreibers. Die Abrechnung schließt die gezahlte Optionsprämie aus, die bei der Berechnung von Gewinnen oder Verlusten für Optionskäufer und -schreiber berücksichtigt wird.
