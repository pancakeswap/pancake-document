# Pottery FAQ

{% hint style="danger" %}
[Archiviert] Pottery – Stand 3. November 2023
{% endhint %}

## Warum brauchen wir Pottery, wenn wir bereits die Lotterie v2 haben?

Pottery ist ein völlig anderes Produkt als Lotterie v2. Es ist eine Kombination aus dem gesperrten CAKE-Pool und der Lotterie-Funktion, die Chainlinks Implementierung von VRF für echte, sichere Zufälligkeit nutzt. Durch die Teilnahme an Pottery verlieren Sie kein eingezahltes CAKE — Sie riskieren nur die Staking-Belohnungen des eingezahlten CAKE. Dieses Produkt ist für CAKE-Inhaber konzipiert, die risikoaverser sind, aber dennoch an einem Produkt dieser Art teilnehmen möchten. Es ist eine einfache, unterhaltsame und sichere Möglichkeit, eine Chance auf zusätzliches CAKE zu haben. Erfahren Sie mehr über [die Produktstruktur hier](https://docs.pancakeswap.finance/products/pottery).

## Ersetzt Pottery die ursprüngliche Lotterie v2?

Pottery ersetzt die ursprüngliche Lotterie v2 nicht. Diese beiden Produkte werden separat betrieben und geführt. Sie können an beiden teilnehmen!

## Wie hilft Pottery PancakeSwap und CAKE?

Acht Prozent (8 %) des jede Woche verteilten Preistopfs werden als Gebühren für die Verbrennung erhoben, was den Wert für CAKE aufbaut. Wir beabsichtigen, die Gebührenstruktur nach der Beta-Phase des Produkts entsprechend zu überprüfen und anzupassen.

## Was ist die Beta-Phase von Pottery für?

Aufgrund der Abläufe dieses neuen Produkts wie der Kreditaufnahme aus der Schatzkammer, dem Kohorten-Management und der Auslosung startet das Produkt in der Beta-Phase mit einer Einzahlungsobergrenze für jede Pottery, um sicherzustellen, dass alles reibungslos läuft. Nach der Beta-Phase können wir verschiedene Parameter basierend auf dem Betrieb und dem Community-Feedback überprüfen und anpassen, wie z. B. die Gebühren, die Häufigkeit jeder Kohorte, die Sperrdauer usw.

## Warum muss mein CAKE für 10 Wochen gesperrt werden?

Wenn Pottery einfach den Flexible-Staking-Pool nutzen könnte, wäre seine Produktstruktur viel einfacher — ähnlich wie Produkte wie PoolTogether und Moonpot. Die aktuelle Rendite aus dem Flexible-Staking-Pool ist jedoch nicht ausreichend, um einen bedeutungsvollem Preispool für die Auslosung zu erstellen. Daher wurde entschieden, das CAKE für eine moderate Dauer zu sperren, um die Belohnungen auszubalancieren, die zur Finanzierung des Preispools verwendet werden können. Mit mehr Betrieb und Community-Feedback können wir die Sperrdauer in der Zukunft überprüfen und anpassen.

## Warum kann ich nicht abheben?

Bitte beachten Sie, dass die Abhebe-Schaltfläche erst nach 10 Wochen ab dem Sperrdatum aufleuchtet und verfügbar ist. Das Datum für die Abhebung basiert auf 10 Wochen nach dem Sperrdatum und der Uhrzeit — 23:59 UTC am ersten Montag jedes Monats.

## Warum kann ich meine Einzahlung nicht einsehen?

Gelegentlich kann es aufgrund des Subgraph-Lesens zu Verzögerungen kommen — es wird ein Signal angezeigt, wenn Verzögerungen auftreten. Normalerweise sollte der richtige Betrag angezeigt werden, wenn Sie in 15 Minuten erneut nachsehen.

## Wie erfahre ich, ob ich bei der wöchentlichen Auslosung gewonnen habe?

Nach jeder Auslosung am Freitag um ca. Mittag UTC können Sie die Ergebnisse und Gewinner im Panel "Abgeschlossene Runden" einsehen. Eine weitere Möglichkeit zu überprüfen, ob Sie bei wöchentlichen Auslosungen gewonnen haben, ist das Claim-Panel, um zu sehen, ob es einen Preis zu beanspruchen gibt. Lesen Sie [diese Seite, wie Sie teilnehmen können](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery)!

## Was ist die Finanzierungsquelle des Preises?

Die Preispools werden durch die Staking-Belohnungen der Einzahlungen finanziert. Da die Staking-Belohnungen des CAKE-Lock-Staking-Pools jedoch nur nach der Sperrdauer — in diesem Fall 10 Wochen — verteilt werden, leiht sich der Contract für ein besseres Produkterlebnis und zur Ermöglichung der wöchentlichen Auslosungen direkt nach dem Einzahlungsdatum 80 % der geschätzten Gesamtstaking-Belohnungen der Kohorte aus dem CAKE-Treasury basierend auf der APR zum Zeitpunkt der Sperrung. Das geliehene CAKE wird für die Auszahlung bei jeder wöchentlichen Auslosung verwendet. Erfahren Sie mehr über [die Produktstruktur hier](https://docs.pancakeswap.finance/products/pottery)!

## Wenn ich gewinne, muss ich den Preis manuell einfordern?

Ja, Sie müssen auf die Claim-Schaltfläche im Claim-Panel auf der Pottery-Seite klicken.

## Wie häufig findet die Pottery statt?

Jede Pottery-Kohorte ist ab dem Freitag davor ab ca. 10:00 UTC für Einzahlungen geöffnet und schließt am ersten Montag jedes Monats um 23:59 UTC, sofern keine besonderen Regelungen und vorherige Ankündigungen erfolgen. Jede Kohorte wird 10 wöchentliche Auslosungen an 10 aufeinanderfolgenden Freitagen um Mittag UTC haben.

Die erste Pottery wird am 5. August 2022 geöffnet und am 8. August 2022 um 23:59 UTC gesperrt.

## Warum öffnet die Pottery-Einzahlung nur einmal im Monat?

Diese Regelung kombiniert die Einzahlung zur Weiterleitung an den gesperrten Staking-Pool, sodass der Pottery-Contract der Kohorte die Staking-Belohnungen der Einzahlung aus dem gesperrten Staking-Pool koordinieren kann. Mit mehr Betrieb und Community-Feedback können wir die Häufigkeit in der Zukunft überprüfen und anpassen.

## Was ist die Einzahlungsgrenze?

Es gibt eine Mindesteinzahlung von 1 CAKE. In der Beta-Phase des Produkts gibt es auch eine maximale Einzahlungsgrenze für jede Kohorte, die Sie im Einzahlungspanel einsehen können, wenn Sie die Einzahlung vornehmen. Dies soll sicherstellen, dass auf der Betriebsseite alles reibungslos läuft, einschließlich der Kreditaufnahme aus der Schatzkammer, dem gesperrten Staking und der Auslosung. Obwohl das Maximum, das Sie einzahlen können, die maximale Einzahlungsgrenze dieser Kohorte ist (wenn sonst niemand CAKE eingezahlt hat), würden Sie alle Preise gewinnen; das bedeutet jedoch auch, dass die endgültige Rendite dieselbe ist wie wenn Sie Ihr CAKE für 10 Wochen in den Lock-Staking-Pool einzahlen, aber Sie zahlen auch die Pottery-Gebühren.

## Warum brauchen wir das Kohortensystem? Warum fassen wir nicht alles zusammen?

Da Pottery mit dem Fixed-Term-Staking von CAKE interagiert, kann jede Einzahlung erst nach der Sperrdauer abgehoben werden. Wenn wir alle Einzahlungen zusammenfassen möchten, während wir nach der anfänglichen Sperrung weitere Einzahlungen hinzufügen und diese ebenfalls für 10 Wochen sperren können (ab dem Zeitpunkt der neuen Einzahlung), könnten die ursprünglichen Einzahler nicht rechtzeitig abheben.

## Was ist der SHARE-Token?

SHARE-Token werden generiert und verteilt, wenn Sie in die Pottery einzahlen. Sie repräsentieren und dienen als Nachweis für Ihren Anteil am Einzahlungspool.

Bei der Abhebung wird der SHARE-Token zurück an den Pottery-Contract übertragen und verbrannt.

## Wo kann ich Feedback zu diesem Produkt geben?

Bitte wenden Sie sich gerne an uns auf [Telegram](https://t.me/pancakeswap) oder [Discord](https://discord.gg/pancakeswap), wenn Sie noch Fragen zum Format haben oder Feedback haben, um dies weiter zu verbessern!
