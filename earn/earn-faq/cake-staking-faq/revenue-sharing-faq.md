---
hidden: true
---

# Revenue-Sharing-FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Wie werden die Anteile (rCAKE) berechnet? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

Bei jeder wöchentlichen Ausschüttung werden die Anteile jedes Nutzers neu berechnet basierend auf:

1. Der Menge an gesperrtem CAKE, die er besitzt
2. Der verbleibenden Sperrdauer seines gesperrten CAKE, abgerundet auf Wochen, und der maximal zulässigen Sperrdauer (derzeit 52 Wochen)

Beispiel:

Wenn ein Nutzer 50 CAKE gesperrt hat und die verbleibende Sperrdauer 10,3 Wochen beträgt, hat der Nutzer `50 * (10 / 52) ~= 9,61` Anteile.

### Ich habe meine Position aktualisiert; warum habe ich noch 0 Anteile? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Anteile (rCAKE) werden bei jeder wöchentlichen Ausschüttung um 23:59 UTC jeden Mittwoch aktualisiert. Schauen Sie nach der nächsten wöchentlichen Ausschüttung erneut nach, um Ihre aktualisierten Anteile einzusehen.

### Warum sind meine Anteile 0, obwohl ich eine aktive Staking-Position habe? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Bei der Berechnung der Anteile (rCAKE) wird die verbleibende Sperrdauer auf Wochen abgerundet. Um Anteile zu erhalten, müssen Sie sicherstellen, dass Ihre Staking-Position nicht früher als zur nächsten Ausschüttung entsperrt wird.

Um beispielsweise Anteile für die Woche-1-Ausschüttung zu erhalten, müssen Sie:

* Vor 23:59 UTC, 2. August beitreten.
* Eine aktive Festlaufzeit-CAKE-Staking-Position haben, die später als 23:59 UTC, 9. August entsperrt wird.

Wenn Ihre Staking-Position vor 23:59 UTC, 9. August entsperrt wird, erhalten Sie für Woche 1 keine Anteile.

### Kann ich einem Ausschüttungszeitraum in der Mitte der Woche beitreten? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Nein, wie bereits erwähnt werden Anteile zu Beginn des Ausschüttungszeitraums um 23:59 UTC jeden Mittwoch berechnet. Daher erhalten Sie Anteile ab der nächsten Ausschüttung und beginnen ab dann, Rewards anzusammeln.

### Wie erhalte ich mehr Anteile? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Da Anteile basierend auf dem CAKE-Betrag und der verbleibenden Sperrdauer berechnet werden, können Sie mehr Anteile erhalten, indem Sie:

* Mehr CAKE sperren
* Ihre Staking-Position verlängern

Bitte beachten Sie, dass nach dem Hinzufügen von CAKE oder dem Verlängern die Anteile NICHT in Echtzeit aktualisiert werden und nur bei den wöchentlichen Ausschüttungen jeder Woche aktualisiert werden.

### Muss ich meine Staking-Position aktualisieren, wenn ich mehr CAKE hinzufüge oder das Staking verlängere? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

Nein, Sie müssen sich nur einmal anmelden. Alle nachfolgenden CAKE-Staking-Pool-Operationen informieren automatisch den Revenue-Sharing-Pool und aktualisieren Ihre Anteile bei den nächsten wöchentlichen Ausschüttungen.

### Warum stimmen die wöchentlich eingespeisten Rewards nicht zu 100 % mit dem Volumen überein, das auf verschiedenen Trackern (wie der Info-Seite) angezeigt wird?

Die wöchentlich eingespeiste Menge an CAKE-Rewards stimmt möglicherweise nicht zu 100 % mit den Zahlen überein, die aus dem auf verschiedenen Trackern angezeigten Volumen berechnet werden. Mehrere externe Faktoren können die Anzahl der konvertierbaren CAKE-Rewards beeinflussen:

* CAKE-Token-Preis während der Konvertierung und Verarbeitung der Handelsgebühr
* Preise der zugrunde liegenden Vermögenswerte während der Konvertierung und Verarbeitung der Handelsgebühr
* Zur Einsparung von Gas- und Betriebskosten werden Einnahmen von anderen Blockchains als BNB Chain monatlich verarbeitet. Sie werden mit einer einmonatigen Verzögerung und wöchentlichem Durchschnitt eingespeist.
* Einige Handelspaare können während der Verarbeitung der Handelsgebühr unzureichende Liquidität aufweisen.
* Einige Handelspaare können Token mit benutzerdefinierter Logik enthalten, die deren Gebührenverarbeitung verhindert.

Die Chefs arbeiten intensiv daran, Werkzeuge und Praktiken einzusetzen, um sicherzustellen, dass mehr generierte Handelsgebühren verarbeitet und in CAKE umgewandelt werden können.
