# Prognose FAQ

{% hint style="info" %}
Verwenden Sie die Seitenleiste, um schnell Antworten auf Ihre Fragen zu finden!
{% endhint %}

## A) Allgemeine Fragen

### **1. Welche Gebühren fallen an?**

3 % jedes Gesamttopfes einer Runde fließen in die Schatzkasse, von der 100 % für den Rückkauf und die Verbrennung von CAKE verwendet werden.

### 2. Wie wird die Auszahlung berechnet?

* Auszahlungsquote für den HOCH-Pool = Gesamtwert beider Pools ÷ Wert des HOCH-Pools
* Auszahlungsquote für den NIEDRIG-Pool = Gesamtwert beider Pools ÷ Wert des NIEDRIG-Pools

**Beispiel – 2 BNB auf „NIEDRIG" gesetzt, Ergebnis = „NIEDRIG":**

* NIEDRIG-Seite = 15 BNB, Gesamtpreispool = 150 BNB&#x20;
* NIEDRIG-Auszahlungsquote = 150 BNB / 15 BNB = 10x
* Auszahlungsbetrag = Auszahlungsquote × Position × (1 - Schatzkammergebühr)
  * Bei einem Einsatz von 2 BNB auf NIEDRIG: Auszahlung = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Gewinn = 19,4 − 2 = 17,4 BNB

### 3. Gibt es eine Frist, bis wann ich meine Gewinne einlösen muss?

Nein, Sie können Ihre Gewinne jederzeit in der Zukunft einlösen.

### 4. Was ist die Vertragsadresse für PancakeSwap Prediction?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Positionen und Ergebnisse

### 1. **Kann ich meine Position ändern oder entfernen?**

Nein. Sobald Sie eine Position eingegangen sind, können Sie die Richtung NICHT ändern, hinzufügen oder Ihre Position entfernen. Sie ist gesperrt – stellen Sie also sicher, dass Sie zu 100 % mit Ihrer Positionsrichtung zufrieden sind, bevor Sie bestätigen.&#x20;

### 2. Wann werden Märkte abgebrochen? Was passiert dann?

* **Wann:** Oracle- oder Backend-Dienstausfall oder andere außergewöhnliche Umstände.
* **Ergebnis:** Nutzer können 100 % ihres ursprünglichen Einsatzbetrags einfordern (keine Gebühr).

### 3. Das Ergebnis der Runde hat sich nach ihrem Ende geändert! Warum?

Manchmal kann das endgültige Ergebnis nach dem Abschluss einer Runde anders sein als das zuletzt während der Runde angezeigte Ergebnis. Wenn Sie beobachten, dass eine Runde auf „NIEDRIG" endet, kann es einige Sekunden später zu „HOCH" wechseln.

Dies liegt daran, dass wir den Oracle-Preisfeed verwenden, um das endgültige Ergebnis einer Runde zu bestimmen. Der Zeitraum zwischen dem Ende einer Runde und dem Start der nächsten beträgt 30 Sekunden, aber das Oracle aktualisiert sich alle 20 Sekunden. Es ist möglich, dass das Oracle während dieses kurzen Zeitraums ein Update sendet, während die Transaktion zum Auslösen der nächsten Runde verarbeitet wird. Dies kann dazu führen, dass das Ergebnis der vorherigen Runde scheinbar „umkippt".

### 4. Was sind gesperrter Kurs und Schlusskurs?

* **Gesperrter Kurs:** Kurs zu Beginn der LIVE-Phase.
* **Schlusskurs:** Kurs am Ende der Runde, der zur Bestimmung der Gewinner verwendet wird.

**Beispiel – Runde 400 (BNB Prognose):**

1. **12:00–12:05:** Einsatz platzieren → Nutzer setzt 0,1 BNB auf „HOCH"
2. **12:05–12:10:** Sperrphase → Gesperrter Kurs = 850 $
3. **12:10:** Abschlussphase → Schlusskurs = 860 $
4. **Ergebnis: „HOCH"**-Einsatz gewinnt

**Hinweise:**

* Der Oracle-Preis kann bis zu 20 Sekunden für die Aktualisierung benötigen.
* Haus gewinnt: Alle Einsätze gehen ans Haus

### 5. Welche Situationen gelten als HAUS-GEWINN?

**Szenarien:**

1. Es gibt keine gegnerischen Einsätze und der Nutzer verliert (z. B. setzt nur ein Nutzer auf HOCH und das Ergebnis = NIEDRIG)
2. Gesperrter Kurs = Schlusskurs

**Was passiert:**

* PancakeSwap nimmt 100 % des Pools; alle Gelder fließen in die CAKE-Verbrennung.
* Nutzer auf beiden Seiten verlieren ihren ursprünglichen Einsatzbetrag.

**Beispiel – keine gegnerischen Einsätze:**

* Nutzer A setzt auf HOCH, es gibt keine NIEDRIG-Einsätze, Ergebnis = NIEDRIG → Nutzer A verliert; 100 % der Gelder gehen in die Schatzkasse.
* Nutzer B setzt auf HOCH, es gibt keine NIEDRIG-Einsätze, Ergebnis = HOCH → Nutzer B erhält 97 % der Einlage zurück.



## C) Marktpausen

### 1. Was bedeutet es, wenn Märkte pausiert sind?

Märkte werden pausiert, wenn Bedingungen auftreten, die die Zuverlässigkeit des Vertrags beeinträchtigen. Wenn Märkte pausiert sind, finden in keinen Runden Einsätze statt.

### 2. Was führt dazu, dass der PancakeSwap Prediction-Markt pausiert?

Der Prognosemarkt wird unter folgenden Bedingungen pausiert:

1. Der Prognosevertrag konnte den Preis vom ChainLink Oracle nicht abrufen, weil das Oracle den Preis zum Zeitpunkt des Rundenabschlusses nicht gepostet hatte.
2. Der Prognosevertrag konnte eine Aktion (eine Runde beenden oder einen Preis vom Oracle abrufen) nicht ausführen, weil die Transaktion länger als 15 Blöcke im Mempool steckte.
3. PancakeSwap hat entschieden, die Prognose für diesen Markt / diesen Vermögenswert einzustellen.

### 3. Was passiert mit meiner Position, wenn der Markt pausiert?

Wenn die Märkte pausieren, während Sie eine offene Position haben, stehen Ihre Gelder zur Rückforderung bereit, genauso wie Sie normalerweise Ihre Gewinne einfordern würden.

Um Gelder zurückzufordern, müssen Sie einige Gasgebühren bezahlen. Wir können Sie nicht für die Gasgebühren entschädigen. Bitte berücksichtigen Sie dieses geringe Risiko vor der Teilnahme.

### 4. Wann werden die Märkte nach einer Pause wieder aufgenommen?

Die Märkte werden wieder aufgenommen, wenn ein Administrator (einer der Köche) den Markt manuell wieder aktiviert.



## D) Fehlerbehebung und Einlösungen

### 1. Wie kann ich frühere Gewinne aus dem CAKEUSD-Markt auf BNB Chain einlösen?&#x20;

* Gehen Sie zu [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Prüfen Sie den Verlauf-Reiter für historische Rundengewinne

### 2. Warum kann ich meine Gewinne nicht in meiner Wallet sehen?

Wenn Sie Gewinne einlösen, erscheinen diese möglicherweise nicht wie gewohnt in den Transaktionsprotokollen Ihrer Wallet.\
Das liegt daran, dass sie einen anderen Transaktionstyp verwenden: Interne Transaktionen.\
Geben Sie Ihre Wallet-Adresse in BscScan ein und prüfen Sie dann den Reiter „Interne Txns", um zu bestätigen, dass sie angekommen sind.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Warum werden die Ergebnisse meiner Runde nicht angezeigt?

Es gibt einen Puffer von 15 Blöcken pro Runde, der nach dem Ende einer Runde zu Verzögerungen von bis zu 45 Sekunden führen kann.\
Dieser Puffer berücksichtigt, dass wir möglicherweise nicht in der Lage sind, sofort zuverlässig einen Preis abzurufen und eine Runde zu beenden: Verschiedene Blockchain-Faktoren beeinflussen die Geschwindigkeit, mit der Transaktionen im Netzwerk bestätigt werden.

### 4. Ich kann meine Gewinne nicht einlösen. Was soll ich tun?

Stellen Sie sicher, dass Sie genügend BNB in Ihrer Wallet haben, um die Gasgebühren zu bezahlen. Sie benötigen etwas BNB, um den Smart Contract auszulösen.

### **5. Was, wenn ich Gewinne nicht über die Website einlösen kann?**

Möglicherweise können Sie Ihre Gewinne direkt über den Vertrag einlösen. Folgen Sie den Schritten in den 3 Registerkarten unten.

{% tabs %}
{% tab title="Check rounds you played" %}
So überprüfen Sie den Verlauf der gespielten Runden

1. Gehen Sie zur BscScan-Seite des [Prognosevertrags](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (z. B. BNBUSD).
2. Scrollen Sie nach unten zu „8. getUserRounds".
3. Geben Sie Ihre Wallet-Adresse unter „user(address)" ein.
4. Setzen Sie „cursor(uint256)" auf 0 und „size(uint256)" auf 1000.
5. Tippen Sie auf „Query"
6. Runden, an denen Sie teilgenommen haben, werden unten in der ersten Zeile angezeigt. (nach „uint256\[]:")
{% endtab %}

{% tab title="Check if you can claim" %}
Überprüfen Sie zunächst, ob Sie tatsächlich aus der gespielten Runde einlösen können.

1. Gehen Sie zur BscScan-Seite des [Prognosevertrags](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (z. B. BNBUSD) und gehen Sie zum Lesen-Reiter
2. Scrollen Sie nach unten zu „4. claimable".
3. Geben Sie die Runden-ID, die Sie prüfen möchten, unter „epoch(uint256)" ein.
4. Geben Sie Ihre Wallet-Adresse unter „user(address)" ein.
5. Tippen Sie auf „Query"
6. Wenn eine Runde einlösbar ist, wird „true" angezeigt.
7. Wenn das Ergebnis „false" ist, wiederholen Sie bitte die obigen Schritte mit „19. refundable".&#x20;
8. Hinweis: ⬆️ Wenn Sie sehen, dass eine Runde für sowohl „4. claimable" als auch „19. refundable" „false" zurückgibt, aber auf der Website angezeigt wird, wurde sie wahrscheinlich bereits eingelöst und die Website aktualisiert sich verzögert.
{% endtab %}

{% tab title="Claim from a round" %}
So lösen Sie ein

1. Gehen Sie zur BscScan-Seite des [Prognosevertrags](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (z. B. BNBUSD) und gehen Sie zum Schreiben-Reiter
2. Tippen Sie auf „🔴 Connect to Web3"
3. Verbinden Sie sich mit MetaMask oder WalletConnect.
4. Scrollen Sie nach unten zu „3. claim"
5.  Geben Sie die Rundennummer, die Sie einlösen möchten, in diesem Format ein, einschließlich der \[]-Klammern: `[12345]`&#x20;

    Wenn Sie mehrere Runden gleichzeitig einlösen möchten, trennen Sie die Runden durch ein Komma: `[12345,12346,12347]`
6. Tippen Sie auf „Write"
7. In der Wallet bestätigen&#x20;
{% endtab %}
{% endtabs %}
