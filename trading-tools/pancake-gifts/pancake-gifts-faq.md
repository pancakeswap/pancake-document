# Pancake Gifts FAQ

Diese FAQ erläutert, wie Pancake Gifts im Hintergrund funktioniert, was in verschiedenen Szenarien zu erwarten ist und warum bestimmte Designentscheidungen getroffen wurden.

***

## 1. 🔐 Geschenkcode-Verhalten und Zugriff

### **1.1 Warum wird der Geschenkcode nicht gespeichert?**

Wir speichern den Geschenkcode **absichtlich nicht** in:

* Frontend-Lokalspeicher
* Backend-Datenbanken

Dies schützt:

* die Privatsphäre der Nutzer
* die Sicherheit vor Gerätekompromittierung
* versehentliche oder böswillige Geschenkeinlösungen

### **1.2 Kann ich den Geschenkcode später neu generieren oder abrufen?**

Nein. Der Geschenkcode:

* wird **nur einmal** während der Erstellung angezeigt
* ist im generierten **Link** oder **QR-Code** eingebettet
* wird **nicht erneut** in der Benutzeroberfläche oder im Verlauf angezeigt

{% hint style="warning" %}
Wenn der Code verloren geht und Sie den Link oder QR nicht gespeichert haben, kann das Geschenk nicht manuell eingelöst werden. Um Ihren Geschenkbetrag zurückzuerhalten, können Sie es manuell stornieren.
{% endhint %}

### **1.3 Ist der Geschenkcode noch im Freigabelink oder QR eingebettet?**

Ja:

* Der Freigabelink enthält den Geschenkcode (z. B. `pancakeswap.finance/gift#code=xxxx`)
* Der QR-Code enthält ebenfalls den Geschenkcode, kann aber **nicht später neu generiert werden.**&#x20;

{% hint style="success" %}
**Profi-Tipp:** Laden Sie das Bild herunter, sobald es generiert wurde
{% endhint %}

* Manuelle Einlösungen erfordern den tatsächlichen Geschenkcode – kein Fallback, wenn der Link/QR verloren geht

## 2. 🎁 Geschenk-Status und Ablauf

### **2.1 Kann ich sehen, ob ein Geschenk eingelöst, storniert oder abgelaufen ist?**

Ja. Der Abschnitt **Geschenkverlauf** zeigt:

* Status: Ausstehend / Eingelöst / Storniert / Abgelaufen / Nicht einlösbar
* Geschenkdetails (Token, Betrag, Typ, Chain, Zeitstempel)

### **2.2 Was passiert, wenn ein Geschenk abläuft?**

Wenn ein Geschenk nicht innerhalb des Standard-**7-Tage-Fensters** eingelöst wird:

* Der **gesamte Geschenkbetrag wird** an die Wallet des Erstellers **zurückerstattet**
* Die feste **Einlösungsgas-Gebühr (\~0,05 $) wird nicht zurückgegeben**

## 3. 🧠 Einlöselogik und Einschränkungen

### **3.1 Können Nutzer ein Geschenk auf einer anderen Chain einlösen als der, auf der es erstellt wurde?**

Nein. Ein Geschenk ist **chain-gebunden**:

* Ein auf **BSC** erstelltes Geschenk muss auf **BSC** eingelöst werden
* Cross-Chain-Geschenke werden derzeit nicht unterstützt

## 4. ⛽ Gasgebühren und Design

### **4.1 Wie wird der feste Gasbetrag für die Geschenkerstellung festgelegt?**

Wir legen einen festen Gaspreis basierend auf den aktuellen BNB Chain-Bedingungen fest (\~5-fache des derzeit empfohlenen Gasbetrags).

Dieser Puffer:

* Schützt vor plötzlichen Gaspreisspitzen
* Stellt sicher, dass Geschenke unter normaler Volatilität einlösbar bleiben

\
Beispiel

* **Derzeit empfohlen: 0,1 Gwei** (siehe: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Daher feste Einlösungsgas-Gebühr = 0,1 Gwei x 5 = 0,5 Gwei**


