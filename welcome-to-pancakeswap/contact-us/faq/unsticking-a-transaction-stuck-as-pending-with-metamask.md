---
description: So entsperren Sie feststeckende ausstehende Transaktionen in MetaMask
---

# Feststeckende ausstehende Transaktionen in MetaMask beheben

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Wenn Ihre Transaktion in MetaMask im ausstehenden Zustand feststeckt und die Schaltfläche „Abbrechen" nicht hilft, müssen Sie möglicherweise diese Methode verwenden, um Ihren Rückstau zu bereinigen.

Diese Methode funktioniert, indem die feststeckende Transaktion im Wesentlichen durch eine andere Transaktion mit höherer Priorität überschrieben wird.

### **1. Benutzerdefinierten Transaktions-Nonce aktivieren**

1\. Öffnen Sie Ihr MetaMask-Plugin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Klicken Sie auf das farbige Kreissymbol oben rechts und klicken Sie im Dropdown-Menü auf **Einstellungen**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Wählen Sie im Einstellungsmenü **Erweitert** aus.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Scrollen Sie nach unten, bis Sie **Erweiterte Gas-Kontrollen** sehen. Schalten Sie diese auf EIN.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Scrollen Sie weiter in den erweiterten Einstellungen, bis Sie **Transaktions-Nonce anpassen** sehen. Schalten Sie diese auf EIN.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Ihre feststeckende Transaktion finden**

Wir werden nun die feststeckende Transaktion suchen und die „Nonce" notieren. Das ist eine Art Kennung, die wir später wiederverwenden werden.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Gehen Sie zurück zur Hauptseite von MetaMask. Suchen Sie im Reiter „Assets" den Token-Typ Ihrer feststeckenden Transaktion (in diesem Fall CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. Suchen Sie im Token-Menü Ihre **ausstehende** Transaktion im Warteschlangenbereich. Klicken Sie auf Ihre Transaktion, um weitere Details anzuzeigen.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Suchen Sie den Eintrag **Nonce** und notieren Sie diese Zahl.

### **3. Die feststeckende Transaktion überschreiben**

Nun erstellen wir eine neue Transaktion, um die feststeckende zu ersetzen. Wir passen die Nonce-Nummer so an, dass sie mit der übereinstimmt, die Sie sich gerade notiert haben.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. Erstellen Sie eine neue Transaktion, um Ihre feststeckende zu ersetzen. Erhöhen Sie diesmal die **Transaktionsgebühr**. Hier wurde sie von 9 auf 20 erhöht. Dadurch wird die Wahrscheinlichkeit erhöht, dass Ihre Transaktion in einen Block aufgenommen wird.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. Stellen Sie auf der Bestätigungsseite sicher, dass Ihr Gas-Preis nun den neuen, höheren Betrag anzeigt.

10\. Suchen Sie den Eintrag **CUSTOM NONCE** und ändern Sie die Nonce auf die Zahl, die Sie in Schritt 7 notiert haben. Klicken Sie nun auf „Bestätigen".

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Ihre neue Transaktion sollte nun in einen Block aufgenommen werden. Um dies zu überprüfen, öffnen Sie MetaMask und klicken Sie auf den Reiter **Aktivität**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Ihre abgeschlossene Transaktion sollte oben in Ihrer Aktivitätsliste erscheinen. Wenn sie immer noch orange als „Ausstehend" angezeigt wird, müssen Sie etwas länger warten oder den Vorgang mit einer noch höheren Transaktionsgebühr (Gas-Preis) wiederholen.

Da keine Wallet zwei Transaktionen mit derselben Nonce erstellen kann, wird Ihre feststeckende Transaktion storniert, sobald die Ersatztransaktion erfolgreich ist.<br>
