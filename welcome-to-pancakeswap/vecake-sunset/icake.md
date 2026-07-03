---
description: veCAKE Staking und IFO-Zuteilungen
hidden: true
---

# iCAKE

### **Was ist das neue iCAKE?**

Nach dem Übergang zu veCAKE wird das neue iCAKE auf dem veCAKE-Guthaben basieren.

* Genau wie das alte iCAKE bestimmt es das maximale CAKE-Einzahlungslimit bei öffentlichen PancakeSwap IFO-Verkäufen. Wenn Sie beispielsweise 200 iCAKE haben, können Sie 200 CAKE in öffentlichen IFO-Verkäufen einsetzen.
* Die neue iCAKE-Zahl wird anhand des veCAKE-Guthabens am Ende jedes IFO berechnet. Daher haben Sie für jeden IFO unterschiedliche iCAKE-Zahlen.
* Da das veCAKE-Guthaben mit der verbleibenden Sperrzeit schrittweise abnimmt, wird auch Ihr iCAKE in zukünftigen IFOs mit Ihrem veCAKE-Guthaben sinken. Um Ihre iCAKE-Zahl aufrechtzuerhalten, fügen Sie dem Staking mehr CAKE hinzu oder verlängern/erweitern Sie Ihre Sperre.

**iCAKE ist KEIN neues Token, sondern eine numerische Kennzahl, die vom PancakeSwap IFO-System verwendet wird.**

### Wie wird iCAKE berechnet?

Die Anzahl Ihrer iCAKE basiert auf dem veCAKE-Guthaben am Ende jedes IFO, multipliziert mit einem vordefinierten Verhältnis.

veCAKE ist ein dynamisch berechneter Wert, der davon abhängt, wie viel CAKE Sie sperren und wie viel Zeit in der Sperre verbleibt. Weitere Informationen zur Berechnung von veCAKE finden Sie [hier](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Auf das veCAKE-Guthaben wird ein zusätzliches Verhältnis angewendet, das von der Kitchen für jeden IFO angepasst wird. Wenn das Verhältnis beispielsweise 2x beträgt und Sie am Ende des nächsten IFO 1 veCAKE haben, können Sie bis zu 2 CAKE einsetzen.

Beispiel:

* Sie haben 100 CAKE für 2 Jahre gesperrt.
  * Ihre verbleibende Sperrzeit beträgt: `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (Sekunden)
  * Die maximale Sperrzeit beträgt: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (Sekunden)
  * Zum aktuellen Zeitpunkt haben Sie: `100 * (62899200 / 126403199) ~= 49.76` veCAKE
* Der nächste IFO ist geplant; seine Endzeit liegt genau 1 Woche später, also `604800` Sekunden nach dem aktuellen Moment.
  * Zu diesem Zeitpunkt beträgt Ihre verbleibende Sperrzeit: `62899200 - 604800 = 62294400` (Sekunden)
  * Zu diesem Zeitpunkt haben Sie: `100 * (62294400 / 126403199) ~= 49.28` veCAKE
* Für diesen IFO ist das Verhältnis auf `3x` festgesetzt.
* Daher haben Sie für diesen IFO: `49.28 * 3 = 147.84` iCAKE, was bedeutet, dass Sie bis zu 147.84 CAKE im öffentlichen Verkauf einsetzen können.

### Wie kann ich die Anzahl meiner iCAKE überprüfen?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Sie können die Anzahl Ihrer iCAKE auf der IFO-Seite [hier](https://pancakeswap.finance/ifo) prüfen.

Bitte beachten Sie, dass Ihr iCAKE berechnet wird, wenn kein bevorstehender IFO vorhanden ist. In diesem Fall wird Ihr iCAKE anhand des veCAKE-Echtzeit-Guthabens berechnet, das sekündlich abnimmt.

Wenn ein bevorstehender IFO vorhanden ist, wird Ihr iCAKE anhand des veCAKE-Guthabens zum Snapshot-Zeitpunkt berechnet, der dem Ende des IFO entspricht. Ihr iCAKE wird sich nicht verringern oder ändern, bis der IFO endet.

### **Wie kann ich die Anzahl meiner iCAKE erhöhen?**

Sie können die Anzahl Ihrer iCAKE jederzeit erhöhen, indem Sie:

* Ihrer veCAKE-Staking-Position mehr CAKE hinzufügen.
* Ihre veCAKE-Staking-Position verlängern.

auf der [CAKE Staking-Seite](https://pancakeswap.finance/cake-staking)

### Was ist das „Verhältnis" bei der iCAKE-Berechnung?

Das Verhältnis ist ein zusätzlicher Kontrollfaktor, der bei der Berechnung von iCAKE auf das veCAKE-Guthaben angewendet wird.

Wenn das Verhältnis beispielsweise 2x beträgt und Sie am Ende des nächsten IFO 1 veCAKE haben, können Sie bis zu 2 CAKE einsetzen.

Zwischen den einzelnen IFOs wird die Kitchen das „Verhältnis" basierend auf verschiedenen Kennzahlen optimieren. Die Anpassung wird auf allen sozialen Kanälen veröffentlicht.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Sie können die aktuelle „Verhältnis"-Zahl für iCAKE-Berechnungen auf der [IFO-Seite](https://pancakeswap.finance/ifo) einsehen.
