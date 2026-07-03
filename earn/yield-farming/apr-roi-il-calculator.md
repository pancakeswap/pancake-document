# APR/ROI/IL-Rechner

In V3-Liquidität und Farms können Sie dank der neuen nicht-fungiblen Liquidität und der anpassbaren Preisspannen für jede LP-Position einen individuellen LP-Gebühren-APR und Farm-APR für CAKE einsehen.

Um die Bereitstellung von Liquidität zu vereinfachen, stehen neue automatische APR-Anzeigen mit einem komplett neu gestalteten ROI-Rechner zur Verfügung – immer dann, wenn Sie Liquidität bereitstellen oder farmen.

## Automatische APR-Berechnung und -Anzeigen <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Während Sie Liquidität bereitstellen, reagiert die automatische APR-Anzeige auf Ihre Konfigurationsänderungen und berechnet den APR auf Basis Ihrer Einstellungen.

Wenn Sie beispielsweise Ihre Preisspanneneinstellungen enger fassen, steigt der APR in den meisten Fällen.

Bitte beachten Sie für LP-Gebühren-APRs:

* Die geschätzte Höhe der LP-Gebühren-Rewards variiert je nach gewählter Gebührenstufe; Gebühren-Rewards müssen manuell abgerufen und reinvestiert werden.
* APR-Werte werden anhand historischer Handelsvolumina berechnet, die vom Subgraph abhängig sind und Verzögerungen bei der Indexierung unterliegen können.

Für Farm-APRs:

* Die geschätzte Höhe der CAKE-Rewards basiert auf den aktuellen CAKE-Emissionen an die Farms. Diese können sich aufgrund künftiger Emissionsanpassungen ändern.

{% hint style="info" %}
Die Zahlen werden auf Basis der aktuellen Kurse und Pool-Bedingungen berechnet und können sich aufgrund verschiedener externer Variablen ändern. Es handelt sich ausschließlich um Schätzungen zur Ihrer Information, die keine garantierten Erträge darstellen.
{% endhint %}

Diese APR-Anzeige finden Sie unter:

* Seite „Liquidität hinzufügen" – zeigt den LP-Gebühren-APR
* Detailseite jeder bestehenden Liquiditätsposition – zeigt den LP-Gebühren-APR\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Farm-Seite, innerhalb der Position unter jeder Farm – zeigt den kombinierten APR mit LP-Gebühren und CAKE-Rewards\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Verbesserter ROI-Rechner <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Immer wenn Sie die automatischen APR-Anzeigen sehen, können Sie darauf klicken, um den neuen ROI-Rechner aufzurufen. Der neue ROI-Rechner wurde vollständig überarbeitet und um mehrere Funktionen erweitert, die auf die Bedürfnisse bei der Bereitstellung konzentrierter Liquidität und beim Farming in V3 zugeschnitten sind.

Gehen wir die einzelnen Abschnitte gemeinsam durch:

### Einlagebetrag, „Staked für" und „Compounding alle" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Diese drei Eingaben sind die Grundparameter, die auch im vorherigen ROI-Rechner vorhanden waren. Sie definieren:

1. Wie viele Vermögenswerte in die Liquiditätsposition eingebracht werden, in USD.
2. Wie lange diese Vermögenswerte in der Position gestakt bleiben.
3. Wie häufig Sie Rewards reinvestieren (Compounding).



⓵ **Einlagebetrag**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Sie können den Betrag in USD manuell eingeben oder die Schnellaktions-Schaltflächen nutzen, um schnell 100 $, 1.000 $ oder den maximalen verfügbaren Betrag basierend auf dem Token-Guthaben in Ihrer Wallet einzutragen.



⓶ **Staking-Dauer**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Sie können auswählen, wie lange die Vermögenswerte in der Liquiditätsposition gestakt bleiben: 1 Tag, 7 Tage, 30 Tage, 1 Jahr und 5 Jahre.

Die Rendite wird basierend auf Ihrer gewählten Staking-Dauer berechnet.



⓷ **Compounding**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Sie können auswählen, wie häufig Sie die von der Position generierten Rewards ernten und reinvestieren möchten. Zur Auswahl stehen: 12 Stunden, 1 Tag, 7 Tage und 30 Tage.

Die Rendite und der APY werden basierend auf Ihrer Wahl berechnet. Wenn Sie Ihre Position nicht reinvestieren möchten, deaktivieren Sie das Kontrollkästchen auf der linken Seite.

{% hint style="info" %}
In V3 müssen LP-Gebühren und verdiente CAKE manuell geerntet und reinvestiert werden.
{% endhint %}

### &#x20;⓸ Historischer Preis <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Dies ist ein reiner Anzeigebereich zur Referenz der historischen Preisentwicklung des ausgewählten Paares.

Sie können die historischen Preisbewegungen in verschiedenen Zeitrahmen nachvollziehen – etwa wie stark der Preis üblicherweise schwankt – und daraus geeignete Preisspanneneinstellungen ableiten, die eine Balance zwischen höherem APR und geringerem Risiko eines Impermanent Loss bieten.

* MIN – Mindestpreis
* MAX – Höchstpreis
* AVG – Durchschnittspreis
* CURRENT – Aktueller Preis

{% hint style="info" %}
Das Preisdiagramm verwendet ausschließlich Daten aus dem tatsächlichen V3-Paar. Preisdaten vor der Einführung von V3 sind daher nicht verfügbar. Die vier Preiskennzahlen beziehen sich auf den aktuell ausgewählten Zeitraum und ändern sich entsprechend der Auswahl.
{% endhint %}

### ⓹ Preisspanne <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

In diesem Bereich können Sie prüfen, wie viel Liquidität in verschiedenen Preisspannen hinterlegt ist, und die Preisspanne festlegen, für die Sie Liquidität bereitstellen möchten.

Unterhalb des Titels finden Sie das Verteilungsdiagramm. Je höher die Liquiditätsmenge, desto höher ist der Balken im Diagramm.

Sie können Ihre Preisspanneneinstellungen auf folgende Arten ändern:

* Ziehen Sie die beiden Griffe im Diagramm, um die Mindest- und Höchstpreisgrenze zu erhöhen oder zu verringern.
* Verwenden Sie den Bereich zwischen den beiden Griffen, um die ausgewählte Spanne zu verschieben.
* Klicken Sie auf die + und – Schaltflächen bei den Min- und Max-Preisfeldern.
* Klicken Sie auf die Zahlen in den Preisfeldern und geben Sie diese manuell ein.

So navigieren Sie im Verteilungsdiagramm:

1. Verwenden Sie die Lupenschaltflächen mit Plus und Minus, um hinein- und herauszuzoomen.
2. Ziehen Sie die X-Achse (unten), um nach links und rechts zu verschieben.

Um Liquidität für die gesamte Preisspanne bereitzustellen, klicken Sie auf „Full Range".

### ⓺ Preisrichtung umkehren, um Preise mit anderer Basis anzuzeigen <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Bei manchen Token-Paaren ist es einfacher und intuitiver, Preise mit bestimmten Basis-Token anzuzeigen. Beim BNB/USDT-Paar bevorzugen die meisten Nutzer beispielsweise die Anzeige „Wie viele USDT pro BNB" und nicht umgekehrt.

Sie können die Preisanzeige ganz einfach umkehren. Klicken Sie dazu auf die Schaltfläche neben „Preise anzeigen in:", um die Basis zwischen den beiden Token des Paares zu wechseln.

### ⓻ Einstellungen importieren und exportieren (anwenden) <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Wenn Sie den ROI-Rechner im Fenster „Liquidität hinzufügen" öffnen oder eine bestehende Position aufrufen, werden die folgenden Einstellungen automatisch importiert, sodass Sie diese nicht erneut eingeben müssen:

1. Der Betrag der einzubringenden Vermögenswerte
2. Die Preisspanne
3. Die ausgewählte Gebührenstufe

Wenn Sie die Konfiguration im ROI-Rechner abgeschlossen haben, können Sie auf „Einstellungen anwenden" klicken, um die Einstellungen aus dem Rechner direkt in das Fenster „Liquidität hinzufügen" zu übertragen – ohne diese manuell abgleichen zu müssen.

### ⓼ Farm-Rewards und APR berechnen <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Farm-Rewards werden in die Berechnungen einbezogen, wenn Sie den ROI-Rechner auf der „Farm"-Seite aufrufen.

Sie können die Detailbereiche erweitern, um eine Aufschlüsselung der Rewards anzuzeigen.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
