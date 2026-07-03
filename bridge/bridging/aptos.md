---
description: CAKE zwischen EVM-Chains und Aptos bridgen
---

# So funktioniert das Bridging – EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Der folgende Leitfaden verwendet BNB Chain als Beispiel für eine EVM-Chain. Dasselbe Vorgehen gilt auch für Ethereum.
{% endhint %}

## CAKE von BNB Smart Chain nach Aptos bridgen

1 – Stellen Sie sicher, dass Ihre Wallet sowohl BNB Smart Chain als auch Aptos Mainnet unterstützt. Oder dass Sie beide Wallets in Ihrem Browser installiert haben.

Öffnen Sie dann die [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 – Zunächst müssen wir unsere BNB Smart Chain Wallet verbinden.

Klicken Sie auf „Connect" und wählen Sie Ihre bevorzugte Wallet im Abschnitt „EVM". Bestätigen und genehmigen Sie anschließend das Pop-up Ihrer Wallet.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 – Dann müssen wir unsere Aptos-Wallet verbinden.

Wählen Sie im Wallet-Verbindungsdialog Ihre bevorzugte Wallet im Abschnitt „Aptos". Bestätigen und genehmigen Sie anschließend das Pop-up Ihrer Wallet.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 – Klicken Sie auf das „v" im oberen Token-Auswahlfeld und wählen Sie „CAKE".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 – Geben Sie die Anzahl der CAKE ein, die Sie nach Aptos bridgen möchten.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 – Falls Ihre Aptos-Wallet neu erstellt wurde und kein APT (Aptos Coin)-Guthaben aufweist, empfehlen wir, die Option „Gas on Destination" auf dem Standardwert zu belassen. Die Bridge zahlt eine kleine Menge APT in Ihre Wallet ein – nicht nur um Ihnen den Einstieg auf Aptos zu erleichtern, sondern auch weil Sie APT für Gas benötigen, um Ihre gebrückten CAKE zu registrieren und abzurufen.

Eine Änderung dieser Option kann dazu führen, dass der Bridging-Vorgang fehlschlägt.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 – Klicken Sie auf „Transfer", um die Bridging-Transaktion zu initiieren, und bestätigen Sie diese über das Bestätigungs-Pop-up Ihrer Wallet.

Bitte beachten Sie, dass je nach Zustand Ihrer BNB Smart Chain Wallet und Aptos-Wallet **mehrere** Wallet-Bestätigungen erforderlich sein können. Wenn Sie CAKE beispielsweise zum ersten Mal nach Aptos bridgen, müssen Sie:

* Die CAKE-Ausgabe im Bridging-Vertrag genehmigen (über Ihre BNB Smart Chain Wallet)
* CAKE registrieren (über Ihre Aptos-Wallet)

Weitere Details finden Sie in [dieser Übersicht](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 – Lehnen Sie sich zurück und entspannen Sie sich. Der Vorgang dauert in der Regel nur wenige Minuten. Sobald der Bridging-Vorgang abgeschlossen ist, wird CAKE in Ihre Aptos-Wallet eingezahlt. Den Fortschritt können Sie über den Fortschrittsbalken verfolgen.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## CAKE zum ersten Mal nach Aptos bridgen

Das Bridging von CAKE zu Aptos-Wallets erfordert Registrierungs- und Abruf-Transaktionen. Dies dient der Verbesserung der Nutzersicherheit und ist spezifisch für Aptos.

### **Wenn Sie bereits APT (Aptos Coin) in Ihrer Wallet haben:**

Sie werden aufgefordert, CAKE in Ihrer Aptos-Wallet zu registrieren, falls dies noch nicht geschehen ist. In diesem Fall ist keine zusätzliche Abruf-Transaktion erforderlich.

### **Wenn Sie kein APT (Aptos Coin) in Ihrer Wallet haben:**

Nachdem die Bridge-Transaktion abgeschlossen ist, müssen Sie Ihre CAKE manuell abrufen. Um die Gasgebühren für den Abruf zu decken, werden APT-Token aus Ihrer Quell-Wallet an Ihre Aptos-Wallet gesendet.

Diese Registrierungs- und Abrufschritte gelten nur beim ersten Mal, wenn Sie mit einem Token auf Aptos interagieren. Bei nachfolgenden Transfers desselben Tokens sind diese Schritte nicht mehr erforderlich.

Bevor Sie CAKE zum ersten Mal nach Aptos bridgen, stellen Sie sicher, dass Ihre Aptos-Adresse genügend APT für Gasgebühren hat. Weitere Details finden Sie in der Erklärung von Aptos hier: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## CAKE von Aptos nach BNB Smart Chain bridgen

1 – Stellen Sie sicher, dass Ihre Wallet sowohl BNB Smart Chain als auch Aptos Mainnet unterstützt. Oder dass Sie beide Wallets in Ihrem Browser installiert haben.

Öffnen Sie dann die [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 – Zunächst müssen wir unsere BNB Smart Chain Wallet verbinden.

Klicken Sie auf „Connect" und wählen Sie Ihre bevorzugte Wallet im Abschnitt „EVM". Bestätigen und genehmigen Sie anschließend das Pop-up Ihrer Wallet.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 – Dann müssen wir unsere Aptos-Wallet verbinden.

Wählen Sie im Wallet-Verbindungsdialog Ihre bevorzugte Wallet im Abschnitt „Aptos". Bestätigen und genehmigen Sie anschließend das Pop-up Ihrer Wallet.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 – Klicken Sie auf das „v" im oberen Token-Auswahlfeld und wählen Sie „CAKE". Klicken Sie dann auf den Doppelpfeil-Button in der Mitte der Seite, um die Bridging-Richtung umzukehren.

Stellen Sie sicher, dass das „Aptos"-Netzwerk im oberen Feld angezeigt wird.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 – Geben Sie die Anzahl der CAKE ein, die Sie zu BNB Smart Chain bridgen möchten.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 – Falls Ihre BNB Smart Chain Wallet neu erstellt wurde und kein BNB (Gas-Token)-Guthaben aufweist, empfehlen wir, die Option „Gas on Destination" auf dem Standardwert zu belassen. Die Bridge zahlt eine kleine Menge BNB in Ihre Wallet ein. Das hilft Ihnen, Ihren Einstieg auf BNB Smart Chain zu starten und das vielfältige PancakeSwap-Ökosystem zu erkunden.

7 – Klicken Sie auf „Transfer" und genehmigen Sie die Transaktionen über das Pop-up Ihrer Wallet.

8 – Lehnen Sie sich zurück und entspannen Sie sich. Der Vorgang dauert in der Regel nur wenige Minuten. Sobald der Bridging-Vorgang abgeschlossen ist, wird CAKE in Ihre BNB Smart Chain Wallet eingezahlt. Den Fortschritt können Sie über den Fortschrittsbalken verfolgen.
