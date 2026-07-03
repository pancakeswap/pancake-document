# FAQ di Prediction

{% hint style="info" %}
Usa la barra laterale per trovare rapidamente le risposte alle tue domande!
{% endhint %}

## A) Domande generali

### **1. Quali sono le commissioni?**

Il 3% del pot totale di ogni round andrà al treasury, di cui il 100% verrà utilizzato per riacquistare e bruciare CAKE.

### 2. Come viene calcolato il pagamento?

* Rapporto di pagamento per il Pool SU = Valore totale di entrambi i pool ÷ Valore del Pool SU
* Rapporto di pagamento per il Pool GIÙ = Valore totale di entrambi i pool ÷ Valore del Pool GIÙ

**Esempio - Scommessa 2 BNB "GIÙ", risultato = "GIÙ":**

* Lato GIÙ = 15 BNB, pool di premi totale = 150 BNB&#x20;
* Rapporto di pagamento GIÙ = 150 BNB / 15 BNB = 10x
* Importo del pagamento = Rapporto di pagamento × Posizione × (1 - Commissione del treasury)
  * Se scommetti 2 BNB su GIÙ, pagamento = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Profitto = 19,4 − 2 = 17,4 BNB

### 3. C'è un limite di tempo prima di poter riscuotere le mie vincite?

No, potrai riscuotere le tue vincite in qualsiasi momento in futuro.

### 4. Qual è l'indirizzo del contratto PancakeSwap Prediction?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Posizioni e risultati

### 1. **Posso modificare o rimuovere la mia posizione?**

No. Una volta inserita una posizione, NON puoi modificare la direzione, aggiungere o rimuovere la tua posizione. È bloccata, quindi assicurati di essere al 100% soddisfatto della direzione della tua posizione prima di confermare.&#x20;

### 2. Quando vengono annullati i mercati? Cosa succede allora?

* **Quando:** guasto dell'Oracle o del servizio backend, o altre circostanze straordinarie.
* **Risultato:** gli utenti possono riscuotere il 100% dell'importo della scommessa originale (nessuna commissione).

### 3. Il risultato del round è cambiato dopo la fine del round! Perché?

A volte, dopo la chiusura di un round, il risultato finale può essere diverso dall'ultimo risultato mostrato mentre il round era in corso. Se guardi un round terminare con "GIÙ", potrebbe sembrare che si trasformi in "SU" qualche secondo dopo.

Questo accade perché utilizziamo il feed di prezzi dell'Oracle per determinare il risultato finale di un round. Il periodo tra la fine di un round e l'inizio del successivo è di 30 secondi, ma l'Oracle si aggiorna ogni 20 secondi. È possibile che durante questo breve periodo l'Oracle invii un aggiornamento mentre la transazione per avviare il round successivo è in fase di mining. Questo può sembrare "ribaltare" il risultato del round precedente.

### 4. Cosa sono il Prezzo di blocco e il Prezzo di chiusura?

* **Prezzo di blocco:** prezzo all'inizio della fase LIVE.
* **Prezzo di chiusura:** prezzo alla fine del round, utilizzato per determinare i vincitori.

**Esempio – Round 400 (Prediction BNB):**

1. **12:00–12:05:** Inserimento scommessa → l'utente scommette 0,1 BNB su "SU"
2. **12:05–12:10:** Fase di blocco → Prezzo di blocco = $850
3. **12:10:** Fase di chiusura → Prezzo di chiusura = $860
4. **Risultato: la scommessa "SU"** vince

**Note:**

* Il prezzo dell'Oracle può impiegare fino a 20 secondi per aggiornarsi.
* Vittoria della casa: tutte le scommesse vanno alla Casa

### 5. Quali situazioni sono considerate una VITTORIA DELLA CASA?

**Scenari:**

1. Non esistono scommesse opposte e l'utente perde (ad es. solo un utente scommette SU e il risultato = GIÙ)
2. Prezzo di blocco = Prezzo di chiusura

**Cosa succede:**

* PancakeSwap prende il 100% del pool; tutti i fondi vanno alla combustione di CAKE.
* Gli utenti da entrambe le parti perdono l'importo iniziale della scommessa.

**Esempio - Nessuna scommessa opposta:**

* L'utente A scommette SU, non esistono scommesse GIÙ, risultato = GIÙ → L'utente A perde; il 100% dei fondi va al treasury.
* L'utente B scommette SU, non esistono scommesse GIÙ, risultato = SU → L'utente B recupera il 97% del deposito.



## C) Sospensioni del mercato

### 1. Cosa significa quando i mercati sono sospesi?

I mercati vengono sospesi quando ci sono condizioni che influenzano l'affidabilità del contratto. La sospensione dei mercati significa che non verranno accettate scommesse per nessun round.

### 2. Cosa causa la sospensione del mercato Prediction di PancakeSwap?

Il mercato di previsione si sospenderà nelle seguenti condizioni:

1. Il contratto di previsione non è riuscito a ottenere il prezzo dall'Oracle ChainLink perché l'Oracle non aveva pubblicato il prezzo nel momento in cui il round era terminato.
2. Il contratto di previsione non è riuscito a eseguire un'azione (terminare un round o ottenere un prezzo dall'Oracle) perché la transazione era bloccata nel mempool per più di 15 blocchi.
3. PancakeSwap ha deciso di interrompere la previsione per quel mercato / asset.

### 3. Cosa succede alla mia posizione se il mercato si sospende?

Se i mercati si sospendono mentre hai una posizione attiva, i tuoi fondi saranno disponibili per essere recuperati, allo stesso modo in cui normalmente riscuoteresti le tue vincite.

Per recuperare i fondi, dovrai pagare alcune commissioni gas. Non possiamo compensarti per le commissioni gas, quindi tieni presente questo piccolo rischio prima di partecipare.

### 4. Quando riprenderanno i mercati dopo la sospensione?

I mercati riprenderanno quando un amministratore (uno dei cuochi) riprenderà manualmente il mercato.



## D) Risoluzione dei problemi e riscossione

### 1. Come riscuoto le vincite passate dal mercato CAKEUSD su BNB Chain?&#x20;

* Vai su [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Controlla la scheda cronologia per le vincite dei round precedenti

### 2. Perché non riesco a vedere le mie vincite nel mio portafoglio?

Quando riscuoti le vincite, potrebbero non apparire nei log delle transazioni del tuo portafoglio come al solito.\
Questo perché utilizzano un tipo diverso di transazione: le transazioni interne.\
Inserisci l'indirizzo del tuo portafoglio su BscScan, poi controlla la scheda "Internal Txns" per confermare che siano arrivate.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Perché i risultati del mio round non vengono mostrati?

C'è un buffer di 15 blocchi per ogni round, che può causare ritardi fino a 45 secondi dopo la fine di un round.\
Questo buffer è per far fronte al fatto che potremmo non essere in grado di recuperare un prezzo in modo affidabile e terminare un round immediatamente: vari fattori blockchain influenzano la velocità con cui le transazioni vengono confermate sulla rete.

### 4. Non riesco a riscuotere le mie vincite, cosa devo fare?

Assicurati di avere abbastanza BNB nel tuo portafoglio per pagare le commissioni gas. Avrai bisogno di un po' di BNB per attivare lo smart contract.

### **5. Cosa fare se non riesco a riscuotere le vincite dal sito web?**

Potresti essere in grado di riscuotere le tue vincite direttamente dal contratto. Segui i passaggi nelle 3 schede qui sotto.

{% tabs %}
{% tab title="Check rounds you played" %}
Come controllare la cronologia dei round a cui hai partecipato

1. Vai alla pagina BscScan del [contratto Prediction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ad es. BNBUSD).
2. Scorri fino a "8. getUserRounds".
3. Digita l'indirizzo del tuo portafoglio sotto "user(address)".
4. Imposta "cursor(uint256)" a 0 e "size(uint256)" a 1000.
5. Clicca "Query"
6. I round a cui hai partecipato appariranno di seguito nella prima riga. (dopo "uint256\[]:")
{% endtab %}

{% tab title="Check if you can claim" %}
Prima, controlla se dovresti effettivamente poter riscuotere dal round a cui hai partecipato.

1. Vai alla pagina BscScan del [contratto Prediction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ad es. BNBUSD) e vai alla scheda Read
2. Scorri fino a "4. claimable".
3. Digita l'id del round che vuoi controllare sotto "epoch(uint256)".
4. Digita l'indirizzo del tuo portafoglio sotto "user(address)".
5. Clicca "Query"
6. Se un round è riscuotibile, mostrerà "true".
7. Se il risultato è "false", ripeti i passaggi precedenti e prova con "19. refundable".&#x20;
8. Nota: ⬆️ Se vedi che un round restituisce "false" sia per "4. claimable" che per "19. refundable", ma viene mostrato sul sito web, probabilmente è già stato riscosso e il sito web è in ritardo.
{% endtab %}

{% tab title="Claim from a round" %}
Come riscuotere

1. Vai alla pagina BscScan del [contratto Prediction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ad es. BNBUSD) e vai alla scheda Write
2. Clicca "🔴 Connect to Web3"
3. Usa MetaMask o WalletConnect per connetterti.
4. Scorri fino a "3. claim"
5.  Digita il numero del round che vuoi riscuotere in questo formato, incluse le parentesi \[]: `[12345]`&#x20;

    Se vuoi riscuotere da più round contemporaneamente, separa i round con una virgola in questo modo: `[12345,12346,12347]`
6. Clicca "Write"
7. Conferma nel portafoglio&#x20;
{% endtab %}
{% endtabs %}
