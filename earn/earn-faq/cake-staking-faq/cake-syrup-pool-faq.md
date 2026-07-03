---
hidden: true
---

# CAKE Syrup Pool FAQ

## FAQ

### Welche Sperrdauer kann ich wählen?

Sie können zwischen 1 und 52 Wochen wählen. Was bevorzugen Sie?

### Welche Variablen beeinflussen die neuen CAKE-Syrup-Pool-Renditen in % (flexible und Festlaufzeit-Staking-Optionen)?

Da flexible Staking- und Festlaufzeit-Staking-Optionen Teil desselben Pools sind, beeinflussen folgende Variablen die Rendite (APR/APY) beider:

* Gesamt-CAKE, der im flexiblen Staking und im Festlaufzeit-Staking gestakt ist (die Summe beider). Je mehr CAKE gestakt wird, desto niedriger der APR/APY.
* Gesamt-CAKE, der im Festlaufzeit-Staking gesperrt ist. Je mehr CAKE gesperrt ist, desto mehr Yield-Boosts entstehen, was zu weniger CAKE-Rewards für andere (insbesondere flexibles Staking) führt.
* Die durchschnittliche Sperrdauer aller im Festlaufzeit-Staking gesperrten CAKE. Wenn die durchschnittliche Sperrdauer zunimmt, sinkt der APR/APY.

### Kann ich die Rewards während der Sperrzeit ernten?

Nein. Sie können die Rewards erst ernten, wenn die Sperrdauer abgelaufen ist. Dies liegt sowohl an der von uns angebotenen Rendite als auch an den technischen Umsetzungen.

### Kann ich die Sperrdauer verlängern?

Ja. Das Verlängern der Sperrdauer fügt Ihrer **anfänglichen Sperrdauer** mehr Zeit hinzu. Bitte beachten Sie beim Verlängern Ihrer Sperrdauer:

Neue verlängerte Sperrdauer = anfängliche Sperrdauer + hinzugefügte Dauer

### Kann ich mein CAKE über den Contract aus dem Festlaufzeit-Staking entfernen, wenn ich meine Meinung ändere?

Nein. Ihr CAKE kann zu keinem Zeitpunkt aus dem Festlaufzeit-Staking entfernt oder abgehoben werden, bis Ihre Sperrdauer endet und Ihr CAKE entsperrt wird.

### Was ist der „CAKE gesperrt"-Betrag?

Der „CAKE gesperrt"-Betrag ist das anfänglich gesperrte CAKE-Guthaben eines Nutzers zuzüglich der bisher verdienten CAKE-Rewards.

CAKE gesperrt = Anfänglich gesperrtes CAKE-Guthaben + CAKE-Rewards

Beim Hinzufügen von mehr CAKE zum Festlaufzeit-Staking ist der „zu sperrende CAKE"-Betrag das anfänglich gesperrte CAKE-Guthaben des Nutzers, die bisherigen CAKE-Rewards und der hinzuzufügende CAKE.

### Kann sich der Festlaufzeit-Staking-CAKE-Pool-APR ändern, nachdem ich mein CAKE gesperrt habe?

Ja, der Festlaufzeit-Staking-CAKE-Pool-APR ist variabel, genau wie bei den alten CAKE-Pools. Der Festlaufzeit-Staking-CAKE-Pool-APR ist nicht fest und hängt ab von:

* Gesamt-CAKE im CAKE-Pool (die Summe aus flexiblem und Festlaufzeit-Staking).
* Der durchschnittlichen Sperrdauer aller im Festlaufzeit-Staking gesperrten CAKE.
* Einem Yield-Boost (ähnlich einem Multiplikator), der aus der anfänglichen Sperrdauer eines Nutzers berechnet wird. Je länger Sie Ihr CAKE sperren, desto höher der Yield-Boost.

Wenn Sie beispielsweise Ihr CAKE für 52 Wochen sperren, ist Ihr Yield-Boost größer als bei einer Sperrung für 26 Wochen. Der Yield-Boost steigt linear, je länger Sie Ihr CAKE sperren.

### Kann ich weiterhin an IFOs teilnehmen, wenn mein CAKE im Festlaufzeit-Staking-Pool gesperrt ist, oder muss ich mehr CAKE kaufen?

Nein, eine separate Menge CAKE ist erforderlich. Festlaufzeit-Staking ermöglicht jedoch den Zugang zu IFO-Public-Sales. Lesen Sie mehr zu [iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md).

### Kann ich abstimmen, wenn mein CAKE im Festlaufzeit-Staking-Pool gesperrt ist?

Ja! Lesen Sie mehr zu [vCAKE](../../../welcome-to-pancakeswap/vecake-sunset/archive-vecake/vecake.md).

### Kann ich sowohl den flexiblen Staking-CAKE-Pool als auch den Festlaufzeit-Staking-CAKE-Pool gleichzeitig nutzen?

Ja, wenn Sie Festlaufzeit-CAKE-Staking betreiben, erscheint automatisch ein flexibler CAKE-Staking-Nebenpool für Sie zur Auswahl.

### Gibt es eine Gebühr für die Umwandlung von flexibel gestakeltem CAKE in Festlaufzeit-Staking?

Nein. Es gibt keine zusätzlichen Gebühren für das Verschieben von CAKE vom flexiblen Staking zum Festlaufzeit-Staking, nur Gasgebühren.

### Was passiert am Ende der Sperrdauer? Was bedeutet „After Burning"?

{% hint style="warning" %}
**After Burning verbrennt die zukünftigen CAKE-Rewards sowie die bereits verdienten CAKE-Rewards.** Um den Verlust bereits verdienter CAKE-Rewards zu vermeiden, empfehlen wir, am Ende Ihrer Staking-Sperrzeit eine neue Festlaufzeit-Staking-Periode zu beginnen oder Ihr CAKE in flexibles Staking umzuwandeln.
{% endhint %}

Wenn Ihre Festlaufzeit-Staking-Periode endet und Ihr CAKE entsperrt wird, haben Sie 7 Tage Zeit, eine von zwei Optionen zu wählen:

* Sperren Sie Ihr CAKE, um eine neue Festlaufzeit-Staking-Periode zu beginnen\
  oder
* Wandeln Sie Ihr gestaktes CAKE in flexibles Staking um (keine 72-stündige Abhebungsgebühr).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20before%20after%20burning.png)

Während dieser 7 Tage verdienen Sie weiterhin CAKE.

Nach 7 Tagen, wenn Sie keine der beiden Optionen gewählt haben, tritt Ihr gestaktes CAKE in den sogenannten „After Burning"-Modus ein. **Im „After Burning"-Modus werden Ihre CAKE-Rewards (einschließlich der bereits verdienten Rewards) schrittweise verbrannt.** Der Prozentsatz der verbrannten CAKE-Rewards steigt linear über den 90-tägigen „After Burning"-Zeitraum, bis er 100 % erreicht, was bedeutet, dass alle CAKE-Rewards verbrannt werden.

Um keine CAKE-Rewards zu verlieren, empfehlen wir, am Ende Ihrer Staking-Sperrzeit eine neue Festlaufzeit-Staking-Periode zu beginnen oder Ihr CAKE in flexibles Staking umzuwandeln.

Hier ein Beispiel:

> Johannes hat 100 CAKE für 52 Wochen gestakt, während seiner Staking-Periode 50 CAKE verdient, und die Staking-Periode ist nun abgelaufen.
>
> Er hat dann keine Maßnahmen ergriffen, und seine Position ist in den „After Burning"-Modus gewechselt.
>
> Während des 90-tägigen After-Burning-Zeitraums werden alle 50 CAKE, die er verdient hat, schrittweise verbrannt, zusammen mit allen neu verdienten CAKE.
>
> Nach 90 Tagen werden die tatsächlich verdienten Rewards 0 betragen. Die 100 CAKE, die er ursprünglich eingezahlt hat, sind jedoch nicht davon betroffen.
>
> Beginnen Sie eine neue Festlaufzeit-Staking-Periode oder wechseln Sie zu flexiblem Staking – und machen Sie es nicht wie Johannes.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20after%20burning%20started.png)
