# Perpetuals V2 Glossar

**Hier finden Sie alle im Futures Trading relevanten Begriffe mit ihren Definitionen.**

### **Perpetual Trading**

&#x20;Perpetuals, Perpetual Swaps oder Perps sind eine besondere Art von Terminkontrakten ohne Ablaufdatum.

### **Hebel**

Der Hebel ist ein Handelsmechanismus. Händler können ihn nutzen, um ihr Marktengagement zu erhöhen, indem sie weniger als den vollen Investitionsbetrag zahlen. Einfach ausgedrückt: Sie leihen sich Geld, um Ihre Investition zu hebeln.

### Orders

**Long:** Eine Long-Order eröffnen. Bei dieser Order kaufen Sie ein Asset und warten darauf, es zu verkaufen, wenn der Preis steigt. „Kaufen" und „Long" werden synonym verwendet.

**Short:** Eine Short-Order eröffnen. Bei dieser Order leihen Sie sich ein Asset, verkaufen es und hoffen, es zurückzukaufen, wenn der Preis fällt. „Verkaufen" und „Short" werden synonym verwendet.

**Limit Order:** Eine Limit Order ist eine Order zum Kauf oder Verkauf zu einem bestimmten Preis oder besser. Limit Orders sind nicht garantiert ausführbar.

**Market Order:** Eine Market Order ist eine Order zum Kauf oder Verkauf zum besten verfügbaren aktuellen Preis.

#### Positionsverwaltung

Nutzer können die Details ihrer eröffneten Positionen einsehen – zum Beispiel den Eröffnungspreis –, indem sie auf „Position" am unteren Rand der Handelsseite klicken. Sie können Details wie Eröffnungspreis, Anzahl der Positionen, aktuellen Preis und Zwangsliquidierungspreis einsehen.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Perp5.png" alt=""><figcaption></figcaption></figure>

**Positionsmodus**

PancakeSwap verwendet für jedes v2-Handelspaar einen isolierten Hebelmodus. Paare werden unabhängig voneinander betrieben:&#x20;

* Jedes Handelspaar ist eine isolierte Position; Nutzer können mehrere isolierte Positionen eröffnen.
* Jede Position (jedes Handelspaar) läuft unabhängig. Wenn Nutzer ihre Margin aufstocken müssen, müssen sie dies manuell tun, auch wenn in anderen separaten Positionen verfügbare Assets vorhanden sind. (ApolloX wird die automatische Aufstockung in Zukunft unterstützen.)
* Jede isolierte Handelsposition hat eine eigene Risikorate und einen eigenen Liquidierungspreis und wird einzeln abgerechnet.
* Das Liquidierungsrisiko ist für jedes Handelspaar isoliert. Wenn eine Position liquidiert wird, hat dies keinen Einfluss auf andere Positionen.

**Eine Position schließen**

Nutzer können ihre Positionen schließen, indem sie auf „Position schließen" klicken.

#### Gebühren und Kursabweichung

Weitere Informationen zu den Gebühren finden Sie auf der [Seite von Aster](https://docs.asterdex.com/product/asterex-simple/fees-and-slippage).
