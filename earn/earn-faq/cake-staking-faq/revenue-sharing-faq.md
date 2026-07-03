---
hidden: true
---

# FAQ Condivisione dei Ricavi

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Come vengono calcolate le quote (rCAKE)? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

Ad ogni distribuzione settimanale, le quote di ciascun utente vengono ricalcolate in base a:

1. La quantità di CAKE bloccato che possiede
2. La durata di blocco rimanente del loro CAKE bloccato arrotondata verso il basso alle settimane, e il tempo massimo di blocco consentito (attualmente 52 settimane)

Ad esempio:

Se un utente ha 50 CAKE bloccati e il tempo di blocco rimanente è 10,3 settimane, allora l'utente ha `50 * (10 / 52 ) ~= 9,61` quote.

### Ho aggiornato la mia posizione; perché ho ancora 0 quote? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Le quote (rCAKE) vengono aggiornate ad ogni distribuzione settimanale alle 23:59 UTC ogni mercoledì. Torna dopo la prossima distribuzione settimanale per visualizzare le quote aggiornate.

### Perché le mie quote sono 0 nonostante abbia una posizione di Staking attiva? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Nel calcolo delle quote (rCAKE), la durata di blocco rimanente viene arrotondata verso il basso alle settimane. Pertanto per ricevere quote, devi assicurarti che la tua posizione di Staking si sblocchi non prima della prossima distribuzione.

Ad esempio, per ricevere quote per la distribuzione della settimana 1, devi:

* Unirti prima delle 23:59 UTC del 2 agosto.
* Avere una posizione di Staking CAKE a termine fisso attiva che si sblocchi dopo le 23:59 UTC del 9 agosto.

Se la tua posizione di Staking si sblocca prima delle 23:59 UTC del 9 agosto, riceverai 0 quote per la settimana 1.

### Posso partecipare a un periodo di distribuzione a metà settimana? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

No, come menzionato le quote vengono calcolate all'inizio del periodo di distribuzione alle 23:59 UTC ogni mercoledì. Pertanto riceverai quote a partire dalla prossima distribuzione e inizierai ad accumulare ricompense da allora.

### Come ricevo più quote? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Poiché le quote vengono calcolate in base alla quantità di CAKE e alla durata di blocco rimanente, per ricevere più quote puoi:

* Bloccare più CAKE
* Estendere la tua posizione di Staking

Nota che dopo aver aggiunto CAKE o esteso, le quote NON vengono aggiornate in tempo reale e vengono aggiornate solo ad ogni distribuzione settimanale.

### Devo aggiornare la mia posizione di Staking quando aggiungo altro CAKE o estendo lo Staking? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

No, dovrai iscriverti solo una volta. Tutte le operazioni successive sul Pool di Staking CAKE informeranno automaticamente il Pool di condivisione dei ricavi e aggiorneranno le tue quote alla prossima distribuzione settimanale.

### Perché le ricompense settimanali iniettate non corrispondono al 100% al volume visualizzato su vari tracker (come la pagina Info)?

Il numero di ricompense CAKE iniettate settimanalmente potrebbe non corrispondere al 100% con i numeri calcolati dal volume visualizzato su vari tracker. Molteplici fattori esterni possono influire sul numero di ricompense CAKE che possono essere convertite:

* Prezzo del token CAKE mentre la commissione di trading viene convertita ed elaborata
* Prezzi degli asset sottostanti mentre la commissione di trading viene convertita ed elaborata
* Per risparmiare gas e costi operativi, i ricavi delle blockchain diverse da BNB Chain vengono elaborati mensilmente. Verranno iniettati con un ritardo di un mese con media settimanale.
* Alcuni pair di trading potrebbero avere Liquidità insufficiente durante l'elaborazione della commissione di trading.
* Alcuni pair di trading potrebbero contenere token con logica personalizzata che impedisce l'elaborazione della loro commissione.

I Chefs stanno lavorando duramente per applicare strumenti e pratiche per garantire che possano essere elaborate e convertite più commissioni di trading generate in CAKE.
