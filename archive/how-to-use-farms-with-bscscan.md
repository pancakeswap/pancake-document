# So verwenden Sie Farms mit BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Da mehrere Schritte erforderlich sind, kann die Nutzung von Farms mit PancakeSwap zunächst einschüchternd wirken. Diese Anleitung führt Sie durch die direkte Nutzung des Farms-Contracts über BscScan.

{% hint style="warning" %}
Bitte beachten Sie, dass die Interaktion mit Contracts über BscScan für Anfänger nicht empfohlen wird. Wenn Sie sich nicht sicher fühlen, empfehlen wir stattdessen die [Anleitung zur Verwendung von Farms](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms).
{% endhint %}

## Farm-Prozess-ID finden

Um korrekt mit dem Farming-Smart-Contract zu interagieren, benötigen Sie die passende Prozess-ID (PID) für Ihr LP-Paar. Derzeit ist der einfachste Weg, diese zu finden, die Prüfung auf GitHub.

1\. Öffnen Sie den [PancakeSwap-Website-Farms-Code auf GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Strg**/**Cmd** + **F** und suchen Sie nach Ihrem Paar nach Ticker (nicht nach Projektname). Zum Beispiel 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Notieren oder kopieren Sie die PID-Nummer — in diesem Fall 389 — an einem leicht zugänglichen Ort. Sie werden diese später benötigen.

## LP-Token über BscScan einzahlen

Das Einzahlen von LP-Token über BscScan umfasst einige Schritte. Wir haben diese in Teilschritte unterteilt, um die Nachverfolgung zu erleichtern.

### Adresse des Haupt-Staking-Contracts ermitteln

Die Adresse des Haupt-Staking-Contracts lautet: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Wenn Sie dies bestätigen möchten, besuchen Sie die [PancakeSwap: Haupt-Staking-Contract BscScan-Seite](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Sie sehen die Adresse oben links. Klicken Sie auf das **Seiten-Symbol**, um diese in die Zwischenablage zu kopieren. Sie werden diese in Kürze benötigen.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Den Contract für Ihr LP-Token öffnen

Sie müssen den Smart Contract für das LP-Token genehmigen, das Sie einer Farm zuweisen möchten, bevor Sie es verwenden können.

### Aus dem Quellcode

1\. Öffnen Sie zunächst [farms.ts auf GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Strg**/**Cmd** + **F** und suchen Sie nach Ihrem Paar nach Ticker (nicht nach Projektname). Zum Beispiel 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Wenn Sie den Code für das gesuchte LP-Paar gefunden haben, suchen Sie nach der Adresse nach "56:". Dies ist Ihre Contract-Adresse.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Über die Benutzeroberfläche

1\. Besuchen Sie zunächst die [PancakeSwap-Farms-Seite](https://pancakeswap.finance/farms) und suchen Sie nach Ihrem gewählten Paar über das Feld "SUCHE" oben rechts. In diesem Beispiel verwenden wir CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Klicken Sie auf **Details**, um die Zeile zu erweitern und mehr Informationen anzuzeigen.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Klicken Sie auf **Contract anzeigen**, um den Smart Contract auf BscScan zu öffnen.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Genehmigung für den LP-Token-Contract erteilen

Da Sie nun den Contract Ihres LP-Tokens auf BscScan geöffnet haben, genehmigen Sie nun die Ausgabe Ihrer LP-Token in der Farm.

1\. Gehen Sie auf der LP-Token-Contract-Seite zu **Contract** und dann zu **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klicken Sie auf **Connect to Web3**, um MetaMask zu verbinden.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Bestätigen Sie die Verbindung.

3\. Unter Funktion 1, "approve", sehen Sie "spender:address". Fügen Sie die zuvor in die Zwischenablage kopierte Adresse des Haupt-Staking-Contracts ein.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Sie müssen auch den Betrag der LP-Token genehmigen, den der Contract ausgeben kann. Im Wertfeld müssen Sie den Betrag in Wei eingeben. Sie können den [BscScan Unit Converter](https://www.bscscan.com/unitconverter) verwenden, um Ihren Betrag einfach in Wei umzurechnen. Hier verwenden wir 5 CAKE-BUSD LP-Token.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Sie können auch `-1` als Wert verwenden, um eine unbegrenzte Ausgabegenehmigung zu erteilen. Das bedeutet nicht, dass Sie standardmäßig alles ausgeben, sondern nur, dass Ihre Wallet eine Transaktion beliebiger Größe mit diesem Contract zulässt.
{% endhint %}

6\. Klicken Sie auf **Write** und bestätigen Sie die Aktion in Ihrer MetaMask-Wallet. Sie können nun LP-Token bis zu dem genehmigten Betrag in der Farm hinterlegen.

### LP-Token mit dem Haupt-Staking-Contract-Smart-Contract einzahlen

Da der Haupt-Staking-Contract nun zum Ausgeben Ihrer LP-Token genehmigt ist, ist es Zeit, eine Einzahlung vorzunehmen.

1\. Gehen Sie zurück auf der [PancakeSwap: Haupt-Staking-Contract BscScan-Seite](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) zu **Contract** und dann zu **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klicken Sie auf **Connect to Web3**, um MetaMask zu verbinden.

3\. Scrollen Sie zu Funktion 2, "deposit", und geben Sie Ihre PID in das Feld "\_pid" ein.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Wenn Sie Ihre PID nicht notiert haben, erfahren Sie im Abschnitt **Farm-Prozess-ID finden** weiter oben auf dieser Seite, wie Sie diese ermitteln.

4\. Unter \_pid sehen Sie "\_amount". Geben Sie den Betrag für den LP-Contract ein, den Sie zuvor genehmigt haben.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Überprüfen Sie die Informationen und klicken Sie auf **Write**. Bestätigen Sie Ihre Aktion in MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Sie können bestätigen, dass Ihre Einzahlung erfolgreich war, indem Sie auf **Ihre Transaktion anzeigen** klicken.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Aus einem Pool abheben

Das Abheben Ihrer LP-Token aus einem Pool ist dem Einzahlen sehr ähnlich. Der Unterschied liegt darin, mit welcher Funktion Sie interagieren.

1\. Gehen Sie zurück auf der [PancakeSwap: Haupt-Staking-Contract BscScan-Seite](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) zu **Contract** und dann zu **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klicken Sie auf **Connect to Web3**, um MetaMask zu verbinden.

3\. Scrollen Sie ganz nach unten zu Funktion 15, "withdraw", und geben Sie Ihre PID in das Feld "\_pid" ein.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Wenn Sie Ihre PID nicht notiert haben, erfahren Sie im Abschnitt **Farm-Prozess-ID finden** weiter oben auf dieser Seite, wie Sie diese ermitteln.

4\. Unter \_pid sehen Sie "\_amount". Geben Sie den LP-Betrag ein, den Sie aus dem Pool abheben möchten.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Überprüfen Sie die Informationen und klicken Sie auf **Write**. Bestätigen Sie Ihre Aktion in MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Sie können bestätigen, dass Ihre Abhebung erfolgreich war, indem Sie auf **Ihre Transaktion anzeigen** klicken.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Notfall-Abhebung durchführen**

‌Die Verwendung der Notfall-Abhebungsfunktion ermöglicht es Ihnen, alle Ihre Gelder aus einem Pool zu ziehen, wenn kein anderer Weg funktioniert.

{% hint style="danger" %}
**Die Nutzung der Notfall-Abhebungsfunktion führt zum Verlust Ihrer CAKE-Belohnungen!**

Das PancakeSwap-Team empfiehlt dringend, diese Funktion zu vermeiden, sofern Sie nicht offiziell vom PancakeSwap-Team dazu aufgefordert werden oder Sie sich sehr gut mit der Interaktion mit Smart Contracts auskennen und den zugrundeliegenden Code verstehen.
{% endhint %}

‌1. Gehen Sie auf der [PancakeSwap: Haupt-Staking-Contract BscScan-Seite](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) zu **Contract** und dann zu **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klicken Sie auf **Connect to Web3**, um MetaMask zu verbinden.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Scrollen Sie nach unten zu Funktion 4, "emergencyWithdraw", und geben Sie Ihre PID in das Feld "\_pid" ein.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Wenn Sie Ihre PID nicht notiert haben, erfahren Sie im Abschnitt **Farm-Prozess-ID finden** weiter oben auf dieser Seite, wie Sie diese ermitteln.

5\. Überprüfen Sie die Informationen und klicken Sie auf **Write**. Bestätigen Sie Ihre Aktion in MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Sie können bestätigen, dass Ihre Abhebung erfolgreich war, indem Sie auf **Ihre Transaktion anzeigen** klicken.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
