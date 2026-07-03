# Infinity StableSwap

### Übersicht

Infinity StableSwap ist ein Pool-Typ innerhalb von [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity), optimiert für den Tausch von Assets, die nahe am gleichen Preis gehandelt werden sollten – wie Stablecoins (z. B. USDC/USDT) oder eng gekoppelte Assets (z. B. Wrapped-Token-Paare, Liquid-Staking-Token und Liquid-Restaking-Token).

Er wird durch einen StableSwap-Hook betrieben, der auf der Infinity-Architektur läuft und vom StableSwap-NG-Design von Curve inspiriert ist. Er ist derzeit auf BNB Chain verfügbar, mit Plänen zur Erweiterung auf weitere Chains in der Zukunft.

***

### Wie es funktioniert

Infinity StableSwap verwendet eine stabile Invarianzkurve – ein Hybrid zwischen konstanter Summe und konstantem Produkt:

* Nahe dem Peg → die Kurve verhält sich nahe der konstanten Summe, was zu sehr geringer Kursabweichung bei Trades rund um 1:1 führt.
* Weit vom Peg entfernt → die Kurve geht allmählich in Richtung konstantem Produkt über, was hilft, das Gleichgewicht wiederherzustellen und den Pool bei großen Ungleichgewichten oder Depeg-Ereignissen zu schützen.

Dies macht ihn besonders effektiv für stabile Paare, bei denen enge Bepreisung und geringe Kursabweichung am wichtigsten sind.

***

### Hauptmerkmale

Optimiert für Swaps nahe dem Peg: Geringe Kursabweichung bei Trades zwischen Assets, die voraussichtlich zum ungefähr gleichen Preis gehandelt werden.

Einfache Liquiditätsbereitstellung: Liquiditätsanbieter (LPs) hinterlegen beide Token proportional, ohne Preisspannen auswählen oder verwalten zu müssen – im Gegensatz zu CLAMM-Pools.

ERC-20-LP-Token: Ihre LP-Position wird als standardmäßiger ERC-20-Token dargestellt, wodurch er einfach mit Yield-Programmen, Points-Kampagnen und anderen DeFi-Protokollen verwendet werden kann.

Dynamische Gebühren: Gebühren können sich basierend auf den Pool-Gleichgewichtsbedingungen anpassen und belohnen Trades, die dazu beitragen, den Pool in Richtung Gleichgewicht zu bringen, während sie solche entmutigen, die das Ungleichgewicht verschlechtern.

Infinity-Routing-Unterstützung: Trades werden automatisch durch StableSwap-Pools geleitet, wenn diese den besten Preis bieten – keine zusätzlichen Schritte für Händler erforderlich.

Anpassbarer Amplifikationsparameter (A): Pool-Betreiber können den A-Parameter im Laufe der Zeit nach oben oder unten anpassen, um sich an veränderte Marktbedingungen anzupassen, mit Schutzmaßnahmen gegen abrupte Änderungen.

***

### Pool-Parameter

Das Verhalten von StableSwap-Pools wird durch eine kleine Anzahl von Parametern gesteuert, die typischerweise bei der Pool-Erstellung festgelegt werden.

#### Amplifikationskoeffizient (A)

Der A-Parameter steuert, wie eng der Pool den 1:1-Preispeg einhält.

| A-Wert    | Auswirkung                                                                                       |
| --------- | ------------------------------------------------------------------------------------------------ |
| Höheres A | Engere Kurve rund um den Peg; geringere Kursabweichung nahe 1:1; empfindlicher gegenüber Ungleichgewicht |
| Niedrigeres A | Lockerere Kurve; verhält sich eher wie ein Standard-Pool mit konstantem Produkt           |

Faustregel: Verwenden Sie ein höheres A für Assets mit einem starken, zuverlässigen Peg (z. B. USDC/USDT). Verwenden Sie ein niedrigeres A für Assets mit loserem oder volatilem Peg (z. B. einige LST-Paare).

Der A-Parameter kann vom Pool-Betreiber über einen definierten Zeitraum schrittweise nach oben oder unten angepasst werden. Änderungen werden schrittweise mit Schutzmaßnahmen angewendet, um Manipulation oder plötzliche Preisverschiebungen zu verhindern.

#### Off-Peg-Gebührenmultiplikator

Ein zusätzlicher Parameter, der die effektiven Gebühren anpasst, wenn sich der Pool vom Gleichgewicht entfernt. Er hilft, Trades zu entmutigen, die den Pool weiter aus dem Gleichgewicht bringen würden, und macht den Pool robuster während Marktbelastungen oder Depeg-Ereignissen.

#### Dynamische Gebühren

Eine Gebühr, die bei jedem Swap erhoben und an Liquiditätsanbieter ausgeschüttet wird. Infinity StableSwap unterstützt dynamische Gebühren – das bedeutet, dass die effektive Gebühr für einen bestimmten Trade variieren kann, je nach dem aktuellen Zustand des Pools (z. B. ob der Trade das Gleichgewicht verbessert oder verschlechtert).

***

### Infinity StableSwap vs. Classic StableSwap

Wenn Sie den bestehenden StableSwap von PancakeSwap bereits verwendet haben, finden Sie hier, was sich ändert – und was gleich bleibt.

| <p><br></p>                    | Classic StableSwap                                              | Infinity StableSwap                                                              |
| ------------------------------ | --------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Preiskurve                     | Stabile Invariante (Hybrid konstante Summe / konstantes Produkt) | Gleiche stabile Invarianzkurve, gleich geringe Kursabweichung nahe dem Peg      |
| ERC-20-LP-Token                | ✅ Ja                                                            | ✅ Ja                                                                             |
| Pool-Erstellung                | Aufwändig; erfordert manuelle Einrichtung durch das Team        | Genehmigungsfrei – jeder kann einen Pool erstellen                               |
| Swap-Gebühren                  | Fest pro Paar (z. B. 0,01 % für USDC/USDT)                     | Dynamische Gebühren – passen sich basierend auf dem Einfluss des Trades auf das Pool-Gleichgewicht an |
| Amplifikationsparameter (A)    | Statisch – einmalig festgelegt, kann nicht geändert werden      | Anpassbar – kann schrittweise im Laufe der Zeit nach oben oder unten angepasst werden |
| Off-Peg-Gebührenmultiplikator  | ❌ Nicht unterstützt                                             | ✅ Unterstützt – hilft, den Pool bei Depeg-Ereignissen zu schützen                |
| Gaseffizienz                   | Standard                                                        | Verbessert – profitiert von Infinitys Singleton und Flash Accounting             |

#### Was gleich bleibt

* Die Kernpreiskurve und das Verhalten mit geringer Kursabweichung nahe dem Peg bleiben unverändert.

#### Was neu und besser ist

* Genehmigungsfreie Pool-Erstellung: Pools können ohne manuelle Team-Einrichtung genehmigungsfrei erstellt werden.
* Dynamische Gebühren schützen LPs: Anstelle einer einzigen festen Gebühr kann die Gebühr pro Trade angepasst werden, je nachdem, ob der Trade das Pool-Gleichgewicht verbessert oder verschlechtert – wodurch der Pool in volatilen Bedingungen widerstandsfähiger wird.
* Anpassbarer A-Parameter: Der Amplifikationskoeffizient kann im Laufe der Zeit angepasst werden, wenn sich die Marktbedingungen ändern, anstatt für immer bei der Bereitstellung festgelegt zu sein.

***

### Häufig gestellte Fragen

Welche Assets sind für Infinity StableSwap geeignet?

Assets, die voraussichtlich nahe am gleichen Preis gehandelt werden: Stablecoins (USDC, USDT, BUSD usw.), Wrapped-Äquivalente desselben Assets (z. B. WBTC/cbBTC) und ausgewählte Liquid-Staking-Token / Liquid-Restaking-Token (LST/LRT)-Paare, bei denen die Peg-Volatilität gering ist.

<br>

Wie unterscheidet sich Infinity StableSwap vom alten PancakeSwap StableSwap?

Infinity StableSwap ist als Hook auf PancakeSwap Infinity implementiert, was bedeutet, dass er alle Infrastrukturvorteile von Infinity erbt, einschließlich niedrigerer Gaskosten durch Singleton und Flash Accounting sowie eines flexibleren Gebührensystems. Er unterstützt auch neue Funktionen wie dynamische Gebühren und anpassbare Amplifikation, die der Legacy-StableSwap nicht bot.

<br>

Muss ich meine Position im Laufe der Zeit verwalten?

Nein. Im Gegensatz zu CLAMM müssen Sie keine Preisspannen festlegen oder anpassen. Ihre Liquidität ist immer über die gesamte Kurve aktiv, sodass kein Risiko besteht, dass Ihre Position „außerhalb der Spanne" gerät.

<br>

Kann ich Liquidität mit nur einem Token bereitstellen?

Ja, Einzel-Token-Einzahlungen werden unterstützt.

<br>

Wie funktionieren dynamische Gebühren?

Bei Infinity StableSwap kann die Swap-Gebühr pro Trade variieren, je nachdem, wie der Trade das Pool-Gleichgewicht beeinflusst. Trades, die dazu beitragen, den Pool wieder in Richtung Gleichgewicht zu bringen, können niedrigere effektive Gebühren zahlen, während Trades, die das Ungleichgewicht verschlechtern, höhere Gebühren zahlen können. Dies soll LPs schützen und gesündere Pool-Bedingungen aufrechterhalten.



***



## Einen Infinity StableSwap-Pool erstellen



Infinity StableSwap-Pools sind genehmigungsfrei – jeder kann einen erstellen, ohne die Genehmigung des PancakeSwap-Teams zu benötigen.

<br>

### Schritt für Schritt

1\. Gehen Sie zur Farm/Liquiditäts-Seite und klicken Sie auf „Pool erstellen".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Wählen Sie „StableSwap-Pool" aus den Pool-Typ-Optionen aus.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Wählen Sie das Token-Paar für Ihren Pool aus (z. B. USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Pool-Parameter

| Parameter                  | Funktion                                                                                                                            |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Swap-Gebühr                | Gebühr, die bei jedem Swap erhoben und an LPs ausgezahlt wird. Standard ist 0,01 % für eng stabile Paare.                          |
| A (Amplifikation)          | Steuert, wie eng die Kurve den Peg einhält. Höher = geringere Kursabweichung nahe 1:1, aber empfindlicher gegenüber Ungleichgewicht. |
| Off-Peg-Gebührenmultiplikator | Erhöht Gebühren, wenn der Pool aus dem Gleichgewicht gerät, und entmutigt Trades, die das Ungleichgewicht verschlechtern.          |
| Gleitender Durchschnittszeitraum | Zeitfenster zur Berechnung des gleitenden Durchschnittspreises für dynamische Gebührenanpassungen.                            |

⚠️ Stellen Sie Parameter sorgfältig ein. Falsche Parameter – insbesondere ein sehr hohes A bei einem locker gekoppelten Asset – können das Risiko für LPs erhöhen. Wenn Sie unsicher sind, verwenden Sie die Voreinstellung für Ihren Asset-Typ und vermeiden Sie Änderungen der erweiterten Einstellungen.

<br>

Wählen Sie eine Pool-Parameter-Voreinstellung – diese legt automatisch die empfohlenen Parameter für Ihren Asset-Typ fest. Sie können diese dennoch manuell über den Erweitert-Schalter anpassen.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Voreinstellung                          | A    | Off-Peg-Gebührenmultiplikator | Gleitender Durchschnittszeitraum (Sekunden) |
| --------------------------------------- | ---- | ----------------------------- | ------------------------------------------- |
| Fiat-einlösbare Stablecoins             | 1000 | 10                            | 600                                         |
| Krypto-besicherte Stablecoins           | 100  | 12,5                          | 600                                         |
| Liquid-Restaking-Token                  | 500  | 10                            | 600                                         |

<br>

&#x20; Unsicher, welche Sie wählen sollen?&#x20;

* Verwenden Sie „Fiat-einlösbare Stablecoins" für Paare wie USDC/USDT.
* Verwenden Sie „Krypto-besicherte Stablecoins" für algorithmische oder krypto-besicherte Stablecoins.
* Verwenden Sie „Liquid-Restaking-Token" für LRT-Paare wie stkBNB/WBNB.

<br>

5\. Geben Sie den Einzahlungsbetrag ein, um die anfängliche Liquidität zu starten. Beide Token-Beträge müssen gleich sein (z. B. 1 USDC und 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Klicken Sie auf „Pool-Vorschau", überprüfen Sie Ihre Einstellungen, aktivieren Sie das Bestätigungsfeld und klicken Sie dann auf „Pool erstellen".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
