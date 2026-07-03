---
hidden: true
---

# FAQ Votazione Gauges

### Ho una posizione attiva, perché non posso votare? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Assicurati che il tuo tempo di sblocco sia uguale o successivo a 1 settimana dopo il momento dello snapshot dell'epoch corrente.&#x20;

Se la tua posizione si sblocca al momento dello snapshot, significa che hai 0 veCAKE al momento dello snapshot. Pertanto non puoi votare.



### Posso votare subito dopo aver impostato una posizione veCAKE?

Sì.

Una volta impostata la tua posizione, puoi usare il tuo cake per votare immediatamente.

Tuttavia:

* Non è possibile esprimere voti nelle ultime 24 ore di un'epoch.
* Non puoi aggiornare la tua decisione di voto su un gauge specifico più frequentemente di ogni 10 giorni.
* Assicurati che la tua posizione non si sblocchi prima o al momento dello snapshot.



### Posso ottenere più veCAKE o voti?

Sì, aggiungi semplicemente più CAKE o estendi la tua posizione di blocco.

Nota che dopo aver ottenuto più veCAKE aggiungendo CAKE o estendendo il tempo di blocco, devi aggiornare manualmente ogni gauge inviando nuovamente la richiesta di voto.



### Perché i risultati della Votazione sono cambiati dopo il periodo di conteggio?

Durante il periodo di conteggio, la PancakeSwap Kitchen esprime i suoi voti basandosi su varie metriche di tutti i gauge.&#x20;

L'obiettivo è:

* Garantire che ai Pool di Liquidità principali venga fornito un rendimento competitivo sulle loro posizioni LP
* Garantire che gli accordi esistenti con i partner Syrup Pool vengano rispettati prima di migrarli completamente al sistema di Votazione veCAKE per i gauge
* Garantire che i Farm più piccoli che non hanno ricevuto voti dopo il lancio di veCAKE ricevano almeno una certa allocazione nel rollout iniziale, limitata ai loro livelli di emissione attuali.

Consulta questa proposta per ulteriori dettagli: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### Perché i miei numeri di voto stanno diminuendo?

Perché quando votiamo sui gauge, votiamo usando il nostro veCAKE. E il saldo veCAKE diminuisce gradualmente con il tempo di blocco rimanente.&#x20;

I tuoi voti diminuiranno fino a 0 allo sblocco della tua posizione veCAKE.

Per ottenere più voti, acquisisci più veCAKE aggiungendo più CAKE al blocco, o estendendo il blocco.



### Dopo aver ottenuto più veCAKE, perché non riesco a votare per più gauge?

Quando votiamo sui gauge, esprimiamo i nostri voti definendo quanta % del nostro veCAKE va a ciascun gauge.

Pertanto, anche se hai ottenuto più veCAKE, se hai allocato il 100% del tuo veCAKE nei precedenti 10 giorni, non puoi cambiare la decisione fino alla fine del periodo di cooldown di 10 giorni.



### I risultati della Votazione sono stati conteggiati, perché il tasso di emissione non sta cambiando?

Ci vogliono circa 72 ore per applicare i risultati della Votazione ai vari prodotti di emissione su PancakeSwap. I Chefs continueranno ad automatizzare questo processo per ridurre il divario e migliorare la precisione.



### Perché il gauge per cui ho votato non ha ricevuto emissioni CAKE nella prossima epoch?

I gauge in whitelist devono ricevere voti corrispondenti a un minimo di 1 CAKE al giorno in emissioni prima di poter ricevere qualsiasi CAKE.
