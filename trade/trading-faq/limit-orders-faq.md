# FAQ

{% hint style="info" %}
Verwenden Sie die Seitenleiste, um schnell Antworten auf Ihre Fragen zu finden!
{% endhint %}

## Limit Orders und TWAP

Bitte lesen Sie die von Orbs bereitgestellten FAQ:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (eingestellt)

### Warum kann ich meine Orders nicht finden?

Limit Orders V2 sind nun eingestellt. Bitte verwenden Sie diesen Link:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Warum wurde meine Order nicht ausgeführt?

Limit Orders werden ausgeführt, wenn sie ihren gewünschten Preis erreichen. Aufgrund von Gasschwankungen kann der tatsächliche Ausführungspreis jedoch vom in der Oberfläche angegebenen Preis abweichen. Normalerweise sollten Ausführungspreis und gewünschter Preis nahezu identisch sein. Bei besonders kleinen Orders (ca. unter 1.000 $) kann der Ausführungspreis jedoch etwas höher sein, um Gebühren zu berücksichtigen.&#x20;

Daher wird Ihre Order möglicherweise nicht ausgeführt, weil:

* Die gesamte Order zum gewünschten Preis und Betrag aufgrund des Preiseinflusses nicht erfüllt werden konnte.
* Einer der Token in der Limit Order eine Übertragungsgebühr hat (siehe unten).

**Bitte prüfen Sie vor dem Aufgeben einer Order die Angabe des tatsächlichen Ausführungspreises in der Oberfläche.**

{% hint style="info" %}
Bitte beachten Sie: Die Tabelle mit dem Bestellverlauf bezieht die Daten aus dem Subgraph und kann leicht verzögerte Informationen anzeigen.
{% endhint %}

### Kann ich eine Limit Order für Token mit Übertragungsgebühr aufgeben?

**Nein.** Token mit einer Übertragungsgebühr sollten nicht mit Limit Orders verwendet werden. Handeln Sie auf eigenes Risiko.

### Wie stelle ich die Kursabweichung bei Limit Orders ein?

Kursabweichung ist bei Limit Orders nicht relevant. Sie geben den Eingabebetrag an (z. B. 1.000 CAKE) und den Ausgabebetrag (z. B. 20 BNB). Limit Orders garantieren, dass Sie bei Erreichen des gewünschten Preises für das Paar nicht weniger als den angegebenen Ausgabebetrag (20 BNB) für Ihren Eingabebetrag (1.000 CAKE) erhalten. **Beachten Sie, dass Token mit Übertragungsgebühr nicht mit Limit Orders verwendet werden sollten** (siehe oben).

### Der tatsächliche Ausführungspreis zeigt „wird nie ausgeführt". Was bedeutet das?

Das bedeutet im Wesentlichen, dass Sie versuchen, eine sehr kleine Menge an Token zu tauschen, bei der nicht genügend Token vorhanden sind, um die Gasgebühr zu decken. Im Allgemeinen müssen Sie den Betrag im Eingabefeld erhöhen, um diesen Fehler zu beheben.&#x20;

### Gibt es ein Ablaufdatum für meine Limit Orders?

Offene Orders haben ein Ablaufdatum von 90 Tagen. Nach dem Ablauf Ihrer Order wird diese möglicherweise nie ausgeführt. Bitte stornieren Sie Ihre Order nach Ablauf.&#x20;

Eine anpassbare Ablaufdatumsfunktion ist für die nahe Zukunft geplant.

### Warum kann ich keine Limit Orders unterhalb des Marktpreises erstellen?

Um unterhalb des Marktpreises zu verkaufen, benötigen Sie **Stop-Limit-Orders**, keine Limit Orders. Die Stop-Limit-Orders-Funktion wird in Kürze verfügbar sein.

### Ich habe eine Order aufgegeben, sie erscheint nicht in der Ordertabelle oder ist im Status „Ausstehend" stecken geblieben.

Der Bestellverlauf stammt aus dem Subgraph und kann daher leicht verzögerte Informationen anzeigen. Normalerweise dauern Verzögerungen im schlimmsten Fall nicht länger als ein paar Minuten. Bitte beachten Sie den Subgraph-Indikator in der unteren rechten Ecke der Bestellverlaufstabelle.
