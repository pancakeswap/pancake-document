# FAQ

### Ho bloccato i miei CAKE o migrato la mia posizione nel pool CAKE. Perché ho ancora 0 quote? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Le quote vengono aggiornate ad ogni distribuzione settimanale alle 00:00 UTC ogni giovedì.

Le ricompense si accumulano ogni volta che hai completato lo Staking per un'epoch intera.&#x20;

Le epoch sono periodi di 7 giorni, che iniziano ogni giovedì alle 00:00 UTC. Ad esempio, se metti in Staking di martedì, la tua prima epoch inizierà giovedì. Una volta completato lo Staking fino al giovedì successivo, potrai riscuotere le tue ricompense da quel giovedì al giovedì successivo, ovvero l'epoch 1.

Torna a controllare ogni giovedì per i numeri di ricompensa aggiornati.

### Perché le mie quote/ricompense sono 0 nonostante abbia una posizione di Staking attiva? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Nel calcolo delle ricompense, la durata del blocco rimanente viene arrotondata per difetto alle settimane. Pertanto, per ricevere quote, devi assicurarti che la tua posizione di Staking si sblocchi non prima del giovedì successivo alle 00:00 UTC.

Ad esempio, la settimana 1 inizia alle 00:00 UTC, giovedì 1 gen. Per ricevere ricompense per la distribuzione della settimana 1, devi:

* Iscriverti prima delle 00:00 UTC, 1 gen.
* Avere una posizione di Staking veCAKE attiva, che si sblocchi uguale o dopo le 00:00 UTC, 15 gen. (giovedì della settimana 3)

Tieni presente che se la tua posizione di Staking si sblocca alle 00:00 UTC, 8 gen (giovedì della settimana 2), riceverai comunque 0 ricompense per la settimana 1, poiché il tuo saldo di veCAKE scenderà a zero alle 00:00 UTC, 8 gen.

### Posso iscrivermi a un periodo di distribuzione a metà settimana? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

No, come indicato, le ricompense possono iniziare ad accumularsi solo quando sei già in Staking all'inizio dell'epoch, ovvero ogni settimana alle 00:00 UTC, giovedì.&#x20;

### Come faccio a ricevere più ricompense? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Poiché le tue quote nei pool vengono calcolate in base al saldo di veCAKE al momento della distribuzione, ovvero alle 00:00 UTC del prossimo giovedì, per ricevere più ricompense aumenta semplicemente il tuo saldo di veCAKE:

* Bloccando più CAKE nella posizione di Staking veCAKE
* Rinnovando la tua posizione di Staking

Tieni presente che dopo aver aggiunto CAKE o esteso la posizione, le tue quote si aggiorneranno solo all'inizio della prossima epoch, ovvero alle 00:00 UTC del giovedì successivo.

### Perché le ricompense settimanali iniettate non corrispondono al 100% al volume mostrato su vari tracker (come la pagina Info)? Perché le ricompense settimanali del pool CAKE non corrispondono al 100% ai risultati del Gauges Voting?

Il numero di ricompense CAKE iniettate settimanalmente potrebbe non corrispondere al 100% ai numeri calcolati dal volume mostrato su vari tracker. Molteplici fattori esterni possono influenzare il numero di ricompense CAKE che possono essere convertite:

* Il prezzo del token CAKE mentre la commissione di trading viene convertita ed elaborata
* I prezzi degli asset sottostanti mentre la commissione di trading viene convertita ed elaborata
* Per risparmiare gas e costi operativi, i ricavi provenienti da blockchain diverse da BNB Chain vengono elaborati mensilmente. Verranno iniettati con un ritardo di un mese con una media settimanale.
* Alcune coppie di trading potrebbero avere Liquidità insufficiente durante l'elaborazione della commissione di trading.
* Alcune coppie di trading potrebbero contenere token con logica personalizzata che impedisce l'elaborazione delle loro commissioni.
* Ritardi nelle transazioni dovuti alle prestazioni delle infrastrutture e dei sistemi di supporto.

Il team sta lavorando intensamente per applicare strumenti e pratiche che consentano di elaborare e convertire in CAKE un maggior numero di commissioni di trading generate.
