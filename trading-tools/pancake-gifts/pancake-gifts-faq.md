# FAQ di Pancake Gifts

Questa FAQ spiega come funziona Pancake Gifts internamente, cosa aspettarsi in diversi scenari e perché sono state fatte determinate scelte progettuali.

***

## 1. 🔐 Comportamento del codice regalo e accesso

### **1.1 Perché il codice regalo non viene memorizzato?**

Abbiamo **intenzionalmente scelto di non memorizzare** il codice regalo in:

* Archiviazione locale del frontend
* Database del backend

Questo protegge:

* La privacy degli utenti
* La sicurezza contro la compromissione del dispositivo
* Riscatti accidentali o dolosi del regalo

### **1.2 Posso rigenerare o recuperare il codice regalo in seguito?**

No. Il codice regalo:

* Viene mostrato **solo una volta** durante la creazione
* È incorporato nel **link** o nel **codice QR** generato
* **Non verrà visualizzato di nuovo** nell'interfaccia o nella cronologia

{% hint style="warning" %}
Se il codice viene perso e non hai salvato il link o il QR, il regalo non può essere riscattato manualmente. Per recuperare l'importo del tuo regalo, puoi annullarlo manualmente.
{% endhint %}

### **1.3 Il codice regalo sarà ancora incorporato nel link di condivisione o nel QR?**

Sì:

* Il link di condivisione include il codice regalo (es. `pancakeswap.finance/gift#code=xxxx`)
* Anche il codice QR incorpora il codice regalo, ma **non può essere rigenerato in seguito.**&#x20;

{% hint style="success" %}
**Suggerimento Pro:** Scarica l'immagine non appena viene generata
{% endhint %}

* I riscatti manuali richiedono il codice regalo effettivo — nessun fallback se il link/QR viene perso

## 2. 🎁 Stato del regalo e scadenza

### **2.1 Posso verificare se un regalo è stato riscattato, annullato o scaduto?**

Sì. La sezione **Cronologia regali** mostra:

* Stato: In attesa / Riscattato / Annullato / Scaduto / Non riscattabile
* Dettagli del regalo (token, importo, tipo, chain, timestamp)

### **2.2 Cosa succede quando un regalo scade?**

Se un regalo non viene riscattato entro la **finestra predefinita di 7 giorni**:

* L'**intero importo del regalo viene rimborsato** al portafoglio del creatore
* La **commissione gas fissa per il riscatto (\~$0,05) non viene restituita**

## 3. 🧠 Logica del riscatto e limitazioni

### **3.1 Gli utenti possono riscattare un regalo su una chain diversa da quella su cui è stato creato?**

No. Un regalo è **legato alla chain**:

* Un regalo creato su **BSC** deve essere riscattato su **BSC**
* Il gifting cross-chain non è attualmente supportato

## 4. ⛽ Commissioni gas e progettazione

### **4.1 Come viene stabilito l'importo fisso del gas per la creazione del regalo?**

Impostiamo un prezzo gas fisso basato sulle condizioni attuali della chain BNB (\~5 volte l'importo di Gas consigliato attualmente).

Questo buffer:

* Protegge dai picchi improvvisi del gas
* Garantisce che i regali rimangano riscattabili in condizioni di normale volatilità

\
Esempio

* **Attualmente consigliato: 0,1 Gwei** (vedi: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Pertanto, commissione gas fisso per il riscatto = 0,1 Gwei x 5 = 0,5 Gwei**


