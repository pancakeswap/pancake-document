---
description: >-
  So lösen Sie alle ausstehenden Transaktionen, die in Ihrem MetaMask
  festhängen
---

# Hängende ausstehende Transaktionen in MetaMask beheben

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Wenn Ihre Transaktion in Metamask auf „Ausstehend“ (Pending) hängt und die Schaltfläche „Cancel“ nicht hilft, müssen Sie möglicherweise diese Methode verwenden, um Ihren Rückstau aufzulösen.

Diese Methode funktioniert, indem die hängende Transaktion im Grunde durch eine andere Transaktion mit höherer Priorität überschrieben wird.

### **1. Benutzerdefinierte Transaktions-Nonce aktivieren**

1\. Öffnen Sie Ihr MetaMask-Plugin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Klicken Sie oben rechts auf das bunte Kreissymbol und wählen Sie im Dropdown-Menü **Settings**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Wählen Sie im Settings-Menü **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Scrollen Sie nach unten, bis Sie **Advanced gas controls** sehen. Schalten Sie diese Option auf ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Scrollen Sie in den Advanced-Einstellungen weiter, bis Sie **Customize transaction nonce** sehen. Schalten Sie auch diese Option auf ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Ihre hängende Transaktion finden**

Wir suchen nun die hängende Transaktion und notieren uns die „Nonce“. Das ist eine Art Kennung, die wir später wiederverwenden.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Gehen Sie zurück zur Startseite von MetaMask. Suchen Sie im Tab „Assets“ den Token-Typ Ihrer hängenden Transaktion (in diesem Fall CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. Suchen Sie im Menü des Tokens Ihre **Pending**-Transaktion im Bereich Queue. Klicken Sie auf Ihre Transaktion, um weitere Details zu sehen.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Suchen Sie den Eintrag **Nonce** und notieren Sie sich diese Zahl.

### **3. Die hängende Transaktion überschreiben**

Nun erstellen wir eine neue Transaktion, die die hängende ersetzt. Wir passen die Nonce-Zahl so an, dass sie mit der soeben notierten übereinstimmt.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Erstellen Sie eine neue Transaktion, um Ihre hängende Transaktion zu ersetzen. Erhöhen Sie diesmal die **Transaction Fee**. Hier haben wir sie von 9 auf 20 erhöht. Dadurch wird es wahrscheinlicher, dass Ihre Transaktion in einen Block aufgenommen wird.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Stellen Sie auf der Bestätigungsseite sicher, dass Ihr Gas Price nun auf dem neuen, höheren Wert steht.

11\. Suchen Sie den Eintrag **CUSTOM NONCE** und ändern Sie die Nonce auf die Zahl, die Sie sich in Schritt 8 notiert haben. Klicken Sie nun auf Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Ihre neue Transaktion sollte nun in einen Block aufgenommen werden. Öffnen Sie zur Kontrolle MetaMask und klicken Sie auf den Tab **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Ihre abgeschlossene Transaktion sollte ganz oben in Ihrer Activity-Liste erscheinen. Wenn dort in Orange noch „Pending“ steht, müssen Sie etwas länger warten oder den Vorgang mit einer noch höheren Transaktionsgebühr (Gas Price) wiederholen.

Da kein Wallet zwei Transaktionen mit derselben Nonce erstellen kann, wird Ihre hängende Transaktion storniert, sobald die von Ihnen erstellte Ersatztransaktion erfolgreich ist.<br>
