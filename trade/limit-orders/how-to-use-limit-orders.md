---
hidden: true
---

# So verwenden Sie Limit Orders

## Was sind Limit Orders?

Eine Limit Order ist ein Tool, das es Nutzern ermöglicht, Assets zu einem bestimmten Preis oder besser zu kaufen oder zu verkaufen, anstatt auf den Marktpreis zum Zeitpunkt der Ausführung angewiesen zu sein. Bei einer Limit Order ist zwar der Preis garantiert, nicht jedoch die Ausführung der Order – Limit Orders werden nur ausgeführt, wenn der Preis die Orderbedingungen erfüllt.

## So richten Sie eine Limit Order ein

1. Gehen Sie zur Swap-Seite und wählen Sie die Limit-Order-Option, indem Sie auf „LIMIT" klicken, oder verwenden Sie diesen Link: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Wählen Sie die „Von"- und „Zu"-Token, die Sie handeln möchten. In diesem Beispiel haben wir USDC und ETH gewählt, was bedeutet, dass wir ETH mit USDC kaufen möchten.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Geben Sie den Betrag ein, den Sie handeln möchten. Beachten Sie, dass der Limitpreis den aktuellen Marktpreis anzeigt, der dann die geschätzte Ausgabemenge der Ziel-Token (ETH) berechnet.
2. Legen Sie den gewünschten Limitpreis fest. Trades werden NUR ausgeführt, wenn der verfügbare Marktpreis besser als oder gleich dem Limitpreis ist. Die Ausgabemenge der Ziel-Token wird entsprechend aktualisiert.

Im folgenden Beispiel möchten wir ETH kaufen, wenn der Preis 1.900 $ oder besser ist. Die erhaltene ETH-Menge beträgt mindestens 0,037 ETH. Nur Gebote in Höhe dieses Betrags oder besser sind zur Ausführung der Order berechtigt. Dieser Betrag berücksichtigt Gaskosten und Gebühren.&#x20;

{% hint style="info" %}
Wichtiger Hinweis: Da die Gebühren vom Ausgabe-Token-Betrag abgezogen werden, beinhaltet der Limitpreis die Gas- und Handelsgebühren. Nutzer sollten dies bei der Festlegung des Preises berücksichtigen. Beispielsweise können die Gasgebühren einer sehr kleinen Order einen sehr hohen Prozentsatz des Order-Outputs ausmachen, was einen tatsächlichen Limitpreis widerspiegelt, der nicht mit dem Spotmarktpreis konkurrenzfähig ist.
{% endhint %}

3.  Klicken Sie auf „Order platzieren". Überprüfen Sie Ihre Orderdetails, akzeptieren Sie den Haftungsausschluss und klicken Sie auf „Order bestätigen".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Sobald die Transaktion abgeschlossen ist, können Sie Ihre Order im Bestellverlauf unter „Offene Orders" einsehen. \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Offene Orders können jederzeit storniert werden, indem Sie die Order erweitern und auf die Schaltfläche „Order stornieren" klicken.

Zu berücksichtigende Punkte:

* Ihre Order wird möglicherweise nicht ausgeführt, wenn der verfügbare Marktpreis schlechter als der von Ihnen festgelegte Limitpreis ist.
* Die Trades basieren auf einem dezentralen Protokoll, das Off-Chain-Taker verwendet, die miteinander konkurrieren, um Orders auszuführen. Diese Taker sind berechtigt, eine Gebühr zu verlangen, die das Protokoll für den gewinnenden Taker von den Ausgabe-Token abzieht.&#x20;
* Taker können Gasgebühren für Ihre Transaktionen berücksichtigen, wenn sie ihre Gebühren festlegen, was zu Schwankungen bei den Gebührenbeträgen führen kann.
* Bei der Angabe eines Limitpreises sehen Nutzer in der Oberfläche den Mindestbetrag der Ziel-Token, den sie bei Ausführung der Order erhalten. Nur Taker, die Gebote in Höhe dieses Betrags oder besser abgeben, sind zur Ausführung der Order berechtigt. Dieser Betrag berücksichtigt Gaskosten und Handelsgebühren.
