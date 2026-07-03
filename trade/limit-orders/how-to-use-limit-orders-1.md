# So verwenden Sie Limit Orders

Gebührengenerierende Limit Orders auf PancakeSwap funktionieren anders als herkömmliche Limit Orders. Wenn ein Nutzer eine Limit Order platziert, stellt er dem PancakeSwap Infinity-Pool effektiv **einseitige Liquidität** bereit.

Wenn sich der Marktpreis bewegt, können Swaps im Pool die Liquidität des Nutzers nutzen. In diesem Fall werden die hinterlegten Token vollständig in die Ausgabe-Token umgewandelt, und der Nutzer erhält:

* Die Ausgabe-Token, und
* Die aus Swaps verdienten Handelsgebühren, die gegen seine Liquidität ausgeführt wurden.

***

**Beispiel: BNB gegen USDT verkaufen**

* **Aktueller Preis im BNB/USDT-Pool:** 600 USDT pro BNB
* **Ziel-/Limitpreis des Nutzers:** 700 USDT pro BNB

Ablauf:

1. Der Nutzer setzt eine Limit Order, um BNB bei 700 USDT zu verkaufen.
2. Sein BNB wird in das Tick eingelegt, das dem Preis von 700 USDT pro BNB im Pool am nächsten liegt.
3. Wenn der externe Marktpreis 700 USDT erreicht, passt sich der Pool-Preis an (aufgrund von Arbitrage-Möglichkeiten / besserem Pricing).
4. Zu diesem Zeitpunkt wird das BNB des Nutzers in USDT umgetauscht.
5. Während dieses Prozesses verdient der Nutzer Gebühren aus jedem Swap, der seine Liquidität verbraucht.
6. Sobald die Liquidität vollständig verbraucht ist, werden die umgewandelten USDT (plus Gebühren) automatisch abgehoben und an die Wallet des Nutzers gesendet.

***

### Schritt-für-Schritt-Anleitung

Wählen Sie ein Token-Paar (z. B. BNB/CAKE) und den Betrag, den Sie verkaufen/kaufen möchten.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Legen Sie Ihren Ziel-/Limitpreis fest.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Platzieren Sie die Limit Order und klicken Sie auf „Bestätigen". Liquidität wird in Ihrem Namen in das Tick platziert, das dem Limitpreis am nächsten liegt.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Sobald der Pool-Preis Ihr Ziel erreicht, wird Ihre Order ausgeführt. Die gewünschten Ausgabe-Token plus Gebühren werden automatisch abgehoben und an Ihre Wallet gesendet.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Orderstatus

Sie können Ihren Orderstatus anzeigen, indem Sie hier klicken.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Ihre Order kann sich in einem der folgenden Zustände befinden:**

| Status             | Beschreibung                                                                                            |
| ------------------ | ------------------------------------------------------------------------------------------------------- |
| Ausstehend         | Wartet darauf, dass der Preis Ihr Ziel erreicht                                                         |
| Ausgeführt         | Order ausgeführt und Mittel an Ihre Wallet gesendet                                                     |
| Teilweise ausgeführt | Nur ein Teil Ihrer Order wurde ausgeführt. Sie halten beide Token (z. B. Teil BNB, Teil USDT)         |
| Storniert          | Sie haben die Order storniert. Alle Ihre Mittel werden Ihnen zurückgegeben.                             |

### FAQ

**F: Muss ich Gebühren zahlen, um eine Limit Order zu platzieren?**

A: Nein. Stattdessen verdienen Sie 0,1 % an Handelsgebühren, wenn Ihre Order ausgeführt wird.

**F: Kann ich Orders für beliebige Paare platzieren?**

A: Beim Launch werden nur ausgewählte Paare unterstützt. Weitere Paare werden später hinzugefügt.

**F: Was ist die Mindestordergröße?**

A: 50 $. Dies verhindert winzige Orders, die zu übermäßigen Gaskosten führen könnten.&#x20;

**F: Was passiert, wenn nur ein Teil meiner Order ausgeführt wird?**

A: Sie halten beide Token. Sie können jederzeit stornieren und beide Token plus verdiente Gebühren abheben.

**F: Meine Order wurde ausgeführt, aber ich habe noch keine Mittel in meiner Wallet erhalten?**

A: In sehr seltenen Szenarien kann dies vorkommen, aber Ihre Mittel sind immer sicher. Verwenden Sie einfach die Schaltfläche „Abheben" in der Orderdetails-Oberfläche, um die Mittel manuell einzufordern.
