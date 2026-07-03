# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### Was kann ich auf PancakeSwap auf anderen Blockchains tun?

Stellen Sie Liquidität bereit, handeln Sie und farmen Sie wie gewohnt. Wenn Sie bereits ein Multi-Chain-Nutzer sind, denken Sie daran, auch auf PancakeSwap auf anderen Blockchains, auf denen wir deployed haben (z. B. Ethereum), Liquidität bereitzustellen – denn wir bieten CAKE-Rewards auf BNB Smart Chain, sodass Sie noch mehr CAKE verdienen können, ohne Ihre Vermögenswerte zu bridgen!

### **Wird es weitere Paare geben?**

Ja, aber wir werden schrittweise vorgehen, um die Sicherheit der Nutzerfonds und die CAKE-Inflation zu gewährleisten. Teilen Sie uns in den Community-Chats mit, welche Ergänzungen Sie sich für PancakeSwap auf anderen Blockchains wünschen und auf welchen weiteren Blockchains PancakeSwap Ihrer Meinung nach eingesetzt werden sollte.

### **Warum sind die Gaskosten für das Staken von LP-Tokens hoch?**

Für die erstmalige Einrichtung wird eine kleine Menge des nativen Tokens (z. B. ETH auf Ethereum) benötigt. Daher sind die Kosten der ersten Transaktion etwas höher.

Darüber hinaus fallen beim Cross-Chain-Farming weitere Gebühren (hauptsächlich Gaskosten) an. Lesen Sie [diesen](faq.md#are-there-any-fees-when-i-do-crosschain-farming) dedizierten Abschnitt für weitere Informationen.

### **Warum dauert das Staken und Unstaken 30 Minuten?**

Alle Cross-Chain-Transaktionen dauern etwa 30 Minuten. Dies hat folgende Gründe:

* Transaktionen müssen sowohl auf der Farming-Blockchain (z. B. Ethereum) als auch auf der BNB Chain ausgeführt werden.
* Die Übermittlung von Cross-Chain-Nachrichten nimmt Zeit in Anspruch.
* Um die Sicherheit zu gewährleisten und sicherzustellen, dass alle Daten zwischen den verschiedenen Blockchains synchronisiert und konsistent sind.

### **Wo befinden sich meine geernteten CAKE-Rewards?**

Ihre geernteten CAKE werden auf BNB Smart Chain verteilt. Bitte wechseln Sie in Ihrer Wallet das Blockchain-Netzwerk, um Ihr CAKE-Guthaben zu prüfen.

### **Ich kann nicht ernten, weil meine Wallet das Wechseln zwischen verschiedenen Blockchains nicht unterstützt!**

Bitte versuchen Sie, eine andere Wallet-App zu verwenden, die Multi-Chain und Chain-Switching unterstützt.

Bitte beachten Sie, dass das Staken und Unstaken von LP-Tokens alle verdienten CAKE ebenfalls auf Ihre Wallet auf BNB Smart Chain ausschüttet. Wenn Sie keine andere Wallet-App verwenden möchten, können Sie einfach mehr staken oder eine kleine Menge an LP-Tokens unstaken, um Ihre verdienten CAKE zu ernten.

### Fallen beim Crosschain Farming Gebühren an?

Im Gegensatz zum nativen Farming auf BNB Chain sind beim Farming auf anderen Blockchains Cross-Chain-Aktivitäten erforderlich. Folgende Gebühren entstehen dabei:

**1 – Gaskosten für die Erstellung eines Proxy-Contracts**

Für das Cross-Chain-Farming muss auf der BNB Chain ein Proxy-Contract erstellt werden. Die Gaskosten für die Erstellung des Proxy-Contracts sind in der Transaktion enthalten.

Diese Gebühr wird nur einmalig bei der ersten „Stake"-Transaktion erhoben.

**2 – Gaskosten für Aufrufe auf BNB Chain**

Wenn Nutzer LP-Tokens ein- oder auszahlen, führt ein Executor Transaktionen im Namen der Nutzer auf der BNB Chain durch. Die Gaskosten für diese Aufrufe sind in der Transaktion enthalten.

Diese Gebühr wird bei jeder Ein- und Auszahlungstransaktion erhoben.

**3 – Gaskosten für Aufrufe auf anderen Blockchains**

Wenn Nutzer LP-Tokens abheben, führt ein Executor die abschließenden Transaktionen durch, um die LP-Tokens auf anderen Blockchains (z. B. Ethereum) freizugeben. Die Gaskosten für diese Aufrufe sind in der Transaktion enthalten.

Diese Gebühr wird nur bei Auszahlungstransaktionen erhoben.

**4 – Cross-Chain-Messaging-Gebühr**

Wir nutzen einen von Celer betriebenen Message-Bus für die Weiterleitung unserer Cross-Chain-Nachrichten. Daher wird eine Nachrichtengebühr basierend auf der Byte-Länge der Nachricht erhoben.

Diese Gebühr wird bei jeder Stake-Transaktion erhoben. Bei Unstake-Transaktionen wird diese Gebühr zweimal erhoben, da aus Sicherheitsgründen eine bidirektionale Kommunikation zwischen BNB Chain und anderen Blockchains erforderlich ist.

```
messagingFee = feeBase + message.length * feePerByte;
```

Die Variablen in der Formel finden Sie im Message-Bus-Contract:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 – Der Starter-Fond**

Dies ist keine „Gebühr" im eigentlichen Sinne.

Für jeden neuen Nutzer, der mit dem PancakeSwap Cross-Chain-Farming beginnt, hinterlegen wir bei der ersten „Stake"-Transaktion 0,005 BNB in seiner BNB-Chain-Wallet. Der entsprechende Betrag in nativen Token der Farming-Chain (z. B. ETH auf Ethereum) wird zum Marktpreis gemäß dem Preisorakel von der Einzahlungstransaktion abgezogen.

Dies soll Nutzern den Einstieg in das BNB-Chain-Ökosystem erleichtern. Wir verstehen, wie frustrierend es ist, alle geernteten CAKE zu besitzen, aber das lebhafte PancakeSwap-Ökosystem nicht erkunden zu können, ohne auf anderem Wege BNB für Gas zu beschaffen.

Diese Gebühr wird nur einmalig bei der ersten „Stake"-Transaktion erhoben.

### Woher stammen die Emissionen?

_Aktualisiert am 10. Oktober 2022_

Derzeit haben die Chefs 0,0189 CAKE pro Block vom CAKE-Pool auf alle Crosschain-Farms umgeleitet.

Hier ist die Emissionsaufschlüsselung:

<table><thead><tr><th width="249"></th><th>Multiplikator</th><th>CAKE pro Block</th></tr></thead><tbody><tr><td><strong>CAKE Pool</strong></td><td>-</td><td><strong>8,9811</strong></td></tr><tr><td><strong>Alle Crosschain Farms</strong></td><td>-</td><td><strong>0,0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0,5x</td><td>0,0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0,2x</td><td>0,0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0,2x</td><td>0,0042</td></tr></tbody></table>

### Was passiert bei Einzahlung, Ernte und Auszahlung?

PancakeSwap Crosschain Farming funktioniert wie die Nutzung eines „Stellvertreter"-LP-Tokens für das Farming auf BNB Chain mit demselben PancakeSwap MasterChef. Die CAKE-Rewards werden auf BNB Chain berechnet und verteilt, kontrolliert und gesichert durch denselben MasterChef-Contract.

#### Bei der Einzahlung:

1. Nutzer beantragen die Einzahlung von LP-Tokens auf Farming-Blockchains (z. B. Ethereum).
2. LP-Tokens werden an Farming-Vault-Contracts übertragen.
3. Der Celer-Message-Bus wird genutzt, um die „Einzahlungs"-Nachricht an BNB Chain zu übermitteln.
4. Ein Executor auf BNB Chain prägt dieselbe Menge an Farming-Tokens als „Stellvertreter" und zahlt sie dann in die Farms ein.

#### Beim Ernten:

Da CAKE-Rewards auf BNB Chain berechnet und verteilt werden, können Nutzer ihre CAKE-Rewards mit einer einzigen BNB-Chain-Transaktion beanspruchen, ohne Cross-Chain-Operationen durchführen zu müssen.

#### Bei der Auszahlung:

1. Nutzer beantragen die Auszahlung von LP-Tokens auf Farming-Blockchains (z. B. Ethereum).
2. Der Celer-Message-Bus wird genutzt, um die „Auszahlungs"-Nachricht an BNB Chain zu übermitteln.
3. Ein Executor auf BNB Chain zieht die Farming-Tokens aus den Farms ab, verbrennt diese Token, überträgt die verdienten CAKE an die Nutzer und nutzt den Celer-Message-Bus, um die Bestätigungsnachricht zurück an die ursprüngliche Farming-Blockchain zu senden.
4. Ein Executor auf der Farming-Blockchain bestätigt alles und gibt dann die LP-Tokens aus den Vault-Contracts frei.
