---
hidden: true
---

# Gauges-Abstimmungs-FAQ

### Ich habe eine aktive Position, warum kann ich nicht abstimmen? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Bitte stellen Sie sicher, dass Ihre Entsperrzeit mindestens 1 Woche nach dem Snapshot-Zeitpunkt der aktuellen Epoche liegt.

Wenn Ihre Position zum Snapshot-Zeitpunkt entsperrt wird, bedeutet das, dass Sie zum Snapshot-Zeitpunkt 0 veCAKE haben. Daher können Sie nicht abstimmen.



### Kann ich direkt nach der Einrichtung einer veCAKE-Position abstimmen?

Ja.

Sobald Ihre Position eingerichtet ist, können Sie Ihren CAKE sofort zur Abstimmung verwenden.

Jedoch:

* In den letzten 24 Stunden einer Epoche können keine Stimmen abgegeben werden.
* Sie können Ihre Abstimmungsentscheidung für einen bestimmten Gauge nicht häufiger als alle 10 Tage aktualisieren.
* Bitte stellen Sie sicher, dass Ihre Position nicht früher als zum Snapshot-Zeitpunkt oder zu diesem entsperrt wird.



### Kann ich mehr veCAKE oder Stimmen erhalten?

Ja, fügen Sie einfach mehr CAKE hinzu oder verlängern Sie Ihre Sperrposition.

Bitte beachten Sie, dass Sie nach dem Erwerb von mehr veCAKE durch Hinzufügen von CAKE oder Verlängern der Sperrdauer alle Gauges manuell aktualisieren müssen, indem Sie die Abstimmungsanfrage erneut einreichen.



### Warum haben sich die Abstimmungsergebnisse nach dem Auszählungszeitraum geändert?

Während des Auszählungszeitraums gibt die PancakeSwap Kitchen ihre Stimmen basierend auf verschiedenen Kennzahlen aller Gauges ab.

Das Ziel ist es:

* Sicherzustellen, dass wichtige Liquiditätspools eine wettbewerbsfähige Rendite auf ihre LP-Positionen erhalten
* Sicherzustellen, dass bestehende Syrup-Pool-Partnervereinbarungen erfüllt werden, bevor diese vollständig zum veCAKE-Gauge-Abstimmungssystem migriert werden
* Sicherzustellen, dass kleinere Farms, die nach dem Launch von veCAKE keine Stimmen erhalten haben, in der ersten Phase zumindest eine gewisse Zuteilung erhalten, begrenzt auf ihre aktuellen Emissionsniveaus.

Weitere Details finden Sie in diesem Vorschlag: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### Warum sinkt die Anzahl meiner Stimmen?

Weil wir beim Abstimmen über Gauges unsere veCAKE verwenden. Und der veCAKE-Saldo sinkt schrittweise mit der verbleibenden Sperrdauer.

Ihre Stimmen sinken bis auf 0, wenn Ihre veCAKE-Position entsperrt wird.

Um mehr Stimmen zu erhalten, erwerben Sie mehr veCAKE, indem Sie mehr CAKE zur Sperrung hinzufügen oder die Sperrdauer verlängern.



### Warum kann ich nach dem Erwerb von mehr veCAKE nicht für mehr Gauges abstimmen?

Beim Abstimmen über Gauges geben wir unsere Stimmen ab, indem wir festlegen, wie viel % unserer veCAKE an jeden Gauge gehen sollen.

Selbst wenn Sie mehr veCAKE erworben haben: Wenn Sie in den letzten 10 Tagen 100 % Ihrer veCAKE zugeteilt haben, können Sie die Entscheidung erst nach Ablauf der 10-tägigen Abkühlperiode ändern.



### Die Abstimmungsergebnisse wurden ausgezählt, warum ändert sich die Emissionsrate nicht?

Es dauert etwa 72 Stunden, bis die Abstimmungsergebnisse auf verschiedene Emissionsprodukte auf PancakeSwap angewendet werden. Die Chefs arbeiten weiterhin daran, diesen Prozess zu automatisieren, um die Verzögerung zu verkürzen und die Genauigkeit zu verbessern.



### Warum hat der Gauge, für den ich gestimmt habe, in der nächsten Epoche keine CAKE-Emissionen erhalten?

Whitelisted Gauges müssen Stimmen erhalten, die mindestens 1 CAKE pro Tag an Emissionen entsprechen, bevor sie CAKE erhalten können.
