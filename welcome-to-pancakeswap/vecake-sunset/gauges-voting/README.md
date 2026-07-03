---
description: Nutzen Sie Ihr veCAKE, um abzustimmen und zu entscheiden, wie CAKE-Emissionen verteilt werden
hidden: true
---

# Gauges Voting

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Was ist ein Gauge?

Um das Gauges Voting zu verstehen, können Sie sich alle Produkte, die CAKE-Emissionen benötigen, als eine Reihe von Gauges vorstellen. Dazu gehören Farms, der wöchentliche CAKE-Belohnungspool, Positionsmanager-Vaults usw.

veCAKE-Inhaber können ihr veCAKE nun als Stimmen nutzen, um zu entscheiden, wie viel Prozent des CAKE an welches Produkt fließt. Je mehr veCAKE ein Gauge durch Gauges Voting ansammelt, desto mehr CAKE-Emissionen werden dem zugrunde liegenden Liquiditätspool / Positionsmanager-Vault zugeteilt.

{% hint style="info" %}
Die Stimmen in jeder Epoche (E-0) bestimmen die CAKE-Emissionen für die nächste Epoche (E+1), und diese Änderungen treten erst nach Abschluss der aktuellen Epoche in Kraft.
{% endhint %}

#### Gauge-Typen

Es gibt zwei Arten von Gauges – „Core" und „Non-Core". CAKE-Emissionen an erstere werden von der Kitchen kontrolliert, während die Community die Emissionen an „Non-Core"-Pools durch Abstimmungen mit veCAKE beeinflusst.

1. „Core"-Gauges umfassen Paare mit wichtigen Token und Stablecoins (WBTC, ETH, BNB, USDC, USDT usw.) – die Kitchen stellt sicher, dass diese Paare ausreichende CAKE-Belohnungen erhalten, da sie wesentlich zu den Einnahmen des Protokolls beitragen.
2. „Non-Core"-Gauges repräsentieren alle anderen Gauges, die nicht als „Core"-Gauges klassifiziert sind.

## Wie wird abgestimmt?

### 1 – Abstimmungsplan verstehen

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Die Gauges-Gewichtungsabstimmung findet alle zwei Wochen statt. Der Beginn einer Epoche, wie auch beim Revenue Sharing, ist jeden geraden Donnerstag um 00:00 Uhr UTC.

Im obigen Beispiel:

* Epoche 1 beginnt am 00:00 Uhr UTC, 1., Donnerstag in Woche 1.
* Epoche 1 endet 2 Wochen später, am 00:00 Uhr UTC, 15., Donnerstag in Woche 3.
* Nutzer können vom 1. bis zum 14. ab 00:00 Uhr UTC abstimmen.
* **KEINE** Stimmen können vom 14. bis zum 15. ab 00:00 Uhr UTC abgegeben werden, da die Stimmen angepasst und ausgezählt werden.
* Die Abstimmungsergebnisse werden am 15. um 00:00 Uhr UTC als Snapshot erfasst. Ende von Epoche 1.
* Abstimmungsergebnisse werden innerhalb von 72 Stunden nach Abschluss einer Epoche angewendet.

### 2 – Berechtigung erlangen

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Da veCAKE entsprechend der verbleibenden Sperrzeit schrittweise abnimmt, werden die Abstimmungsergebnisse am Ende jeder Epoche per Snapshot erfasst. Dies umfasst die Gesamtmenge an veCAKE sowie das veCAKE jedes Nutzers.

Im obigen Beispiel:

* Die Ergebnisse für Epoche 1 basieren auf den veCAKE-Guthaben am 15. um 00:00 Uhr UTC.
* Nutzer, deren veCAKE-Position vor oder am 15. entsperrt wird, haben zum Snapshot-Zeitpunkt ein veCAKE-Guthaben von 0. Sie haben daher keine Stimmrechte für Epoche 1.

Um berechtigt zu sein, müssen Sie eine aktive veCAKE-Position besitzen, die **SPÄTER** als der Endzeit-/Snapshot-Zeitpunkt der aktuellen Epoche entsperrt.

Im obigen Beispiel:

* Wenn Sie in Epoche 1 abstimmen möchten, müssen Sie eine veCAKE-Position haben, die am 21. oder später entsperrt wird, also am Donnerstag in Woche 3.

### 3 – Aktuelle Abstimmungsergebnisse prüfen

Navigieren Sie zu „CAKE staking", scrollen Sie nach unten und suchen Sie den Bereich „Gauges Voting", dann klicken Sie auf „Check Gauges".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Im oberen linken Bereich finden Sie:

* Ihr veCAKE.
* Den Snapshot-Zeitpunkt und das Abstimmungsende für die aktuelle Epoche.
* Die Gesamtanzahl der CAKE-Belohnungen, die in der nächsten Epoche auf Grundlage der Abstimmungsergebnisse aus der aktuellen Epoche verteilt werden.
* Die Gesamtmenge der abgegebenen veCAKE-Stimmen.

Oben rechts finden Sie ein Kreisdiagramm, das den prozentualen Anteil jedes erhaltenen Gauge darstellt.

Unten befindet sich eine vollständige Liste aller Abstimmungs-Gauges mit der Anzahl der erhaltenen Stimmen und dem erwarteten prozentualen Gewicht, das sie in der aktuellen Epoche erhalten. Es gibt auch ein „Boost"- und ein „Caps"-Feld, das zwei wichtige Gauge-Eigenschaften beschreibt. Lesen Sie weiter für weitere Details.

#### Gauge Boost und Emissionsobergrenzen

Um sicherzustellen, dass CAKE-Belohnungen an die produktivsten Gauges gehen, kann auf jeden Gauge ein Boost und/oder eine Emissionsobergrenze angewendet werden. Beide Eigenschaften können gleichzeitig bestehen.

Gauge Boost ist ein Multiplikator, der auf die Anzahl der Stimmen angewendet wird, die ein Gauge erhält, und liegt zwischen 1x und 2,5x (Gauges für V3-Pools sind auf 2x begrenzt). Dies soll Stimmen und Liquidität für wichtige Handelspaare fördern.

Die Emissionsobergrenze ist eine maximale Obergrenze für den prozentualen Anteil, den ein Gauge erhalten kann, und liegt zwischen 2 % und 20 %. Dies fördert die Fairness bei der Zuteilung und verhindert Missbrauch des Gauge-Systems.

Beispiel:

* Ein Gauge hat 10 Stimmen, 2x Boost und 15 % Obergrenze. Die Gesamtstimmen betragen 100.
* Nach Anwendung des Boosts hat dieser Gauge 20 Stimmen, ein Gewicht von 20 % gegenüber der Gesamtzahl (100).
* Da er jedoch eine 15 %-Obergrenze hat, wird der endgültige Prozentsatz der CAKE-Belohnungen, die dieser Gauge in der nächsten Epoche erhält, auf 15 % angepasst.

#### Wie werden Gauge Boost und Emissionsobergrenzen bestimmt?

Während des Gauge-Bewerbungsverfahrens bitten wir Antragsteller, den Wert des Boost-Multiplikators und den Prozentsatz der Emissionsobergrenze vorzuschlagen, den sie dem Gauge zuweisen möchten. Diese müssen zusammen mit der gesamten Gauge-Bewerbung von veCAKE-Inhabern abgestimmt werden.

Die Standardoption für alle Gauges ist ein 1,00x-Multiplikator und eine 5 %-Emissionsobergrenze. Diese können durch zukünftige Vorschläge geändert werden.

{% hint style="info" %}
Bitte beachten Sie, dass die Abstimmungsergebnisse wöchentlich aktualisiert werden. Die Zahlen werden anhand der veCAKE-Guthaben am kommenden Donnerstag um 00:00 Uhr UTC berechnet.
{% endhint %}

### 4 – Gauges zur Abstimmung hinzufügen

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Um für einen Gauge zu stimmen, scrollen Sie nach unten und suchen Sie den Bereich „My Votes". Klicken Sie auf „Add Gauge".

Im Popup-Fenster können Sie Gauges zu Ihrer Abstimmungsliste hinzufügen, indem Sie auf das blaue „+"-Symbol klicken. In der Liste finden Sie die aktuellen Abstimmungsergebnisse sowie Boost und Caps.

Um einen Gauge schnell zu finden, können Sie nach Blockchains, Gebührenstufen und Liquiditätstypen filtern oder den Token-Ticker in das Suchfeld eingeben.

### 5 – Prozentualen veCAKE-Anteil für jeden Gauge festlegen

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Nachdem Sie die Gauges hinzugefügt haben, können Sie auswählen, wie viel Prozent Ihres veCAKE an jeden Gauge gehen soll.

Dies liegt daran:

* veCAKE nimmt mit der verbleibenden Sperrzeit schrittweise ab. Es ist unpraktisch, die genaue Anzahl der abzustimmenden veCAKE zu schätzen und zu berechnen.
* Es ist umständlich, in jeder kommenden Epoche erneut abzustimmen. Daher ist das Gauges Voting so konzipiert, dass Ihre Abstimmungsentscheidungen in alle kommenden Epochen übertragen werden, bis Sie eine neue abgeben.

Im obigen Beispiel:

* Im Moment habe ich 2,62 veCAKE.
* Ich habe beschlossen, 80 % für CAKE-BNB zuzuweisen, was momentan 2,10 veCAKE entspricht.
* 20 % für USDC-ETH, was momentan 0,52 veCAKE entspricht.
* Mein gesamtes veCAKE wird mit der verbleibenden Sperrzeit schrittweise abnehmen. Zum Snapshot-Zeitpunkt habe ich möglicherweise weniger veCAKE, aber meine Entscheidung für die 80 %–20 %-Aufteilung wird trotzdem auf die Endergebnisse angewendet.
* Darüber hinaus wird diese 80 %–20 %-Entscheidung auf jede kommende Epoche angewendet, bis ich sie durch eine neue Abstimmungsanfrage aktualisiere. Oder bis mein veCAKE durch Entsperren auf 0 sinkt.

Nachdem Sie Ihre Entscheidung bestätigt haben, klicken Sie auf „Submit vote" und bestätigen Sie in Ihrer Wallet.

### 6 – Ihre Stimmen aktualisieren

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Sobald Ihre Stimme abgegeben wurde, sehen Sie, wie Ihre Stimmen unter „Current Votes" aktualisiert werden, und das verbleibende veCAKE wird aktualisiert.

Bitte beachten Sie, dass die Abstimmungsentscheidung für jeden Gauge nur alle 10 Tage aktualisiert werden kann. Sobald Sie eine Abstimmungsanfrage einreichen, wird für alle abgestimmten Gauges eine 10-tägige Abkühlphase aktiviert, bevor Sie eine weitere Anfrage zur Aktualisierung einreichen können.

Um Ihre Abstimmungsentscheidung zu aktualisieren, ändern Sie den Prozentwert und reichen Sie die Abstimmung erneut ein.

{% hint style="info" %}
Bitte beachten Sie, dass Sie nach dem Erwerb von mehr veCAKE durch Hinzufügen von CAKE oder Verlängerung der Sperrzeit alle Gauges manuell aktualisieren müssen, indem Sie die Abstimmungsanfrage erneut einreichen.

Die 10-tägige Abkühlphase gilt unabhängig davon, ob Sie Ihre prozentualen Entscheidungen geändert haben.
{% endhint %}
