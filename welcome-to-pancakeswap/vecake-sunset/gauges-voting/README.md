---
description: Usa il tuo veCAKE per votare e decidere come vengono distribuite le emissioni di CAKE
hidden: true
---

# Gauges Voting

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Cos'è un gauge?

Per capire il Gauges Voting, puoi pensare a qualsiasi prodotto che richiede emissioni di CAKE come a una serie di gauge. Questo include Farm, pool di ricompense settimanali CAKE, vault dei position manager, ecc.

I detentori di veCAKE possono ora usare il loro veCAKE come voti per decidere quale % di CAKE va a quale prodotto. Più veCAKE un gauge accumula tramite il Gauges Voting, maggiori saranno le emissioni di CAKE allocate al pool di Liquidità sottostante / vault del position manager.

{% hint style="info" %}
I voti in ogni epoch (E-0) determinano l'emissione di CAKE per l'epoch successiva (E+1), e queste modifiche entrano in vigore solo dopo la conclusione dell'epoch corrente.
{% endhint %}

#### Tipi di gauge

Esistono due tipi di gauge: "core" e "non-core". Le emissioni di CAKE ai primi sono controllate dal team, mentre la community influenza le emissioni ai pool "non-core" votando con veCAKE.

1. I gauge "core" includono coppie con token principali e stablecoin (WBTC, ETH, BNB, USDC, USDT, ecc.) - il team si assicurerà che queste coppie ricevano sufficienti ricompense CAKE poiché contribuiscono significativamente ai ricavi del protocollo
2. I gauge "non-core" rappresentano tutti gli altri gauge non classificati come gauge "core"

## Come votare?

### 1 - Comprendi il calendario di votazione

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Il voto sul peso dei gauge viene condotto ogni due settimane. L'inizio di un'epoch, come per la condivisione dei ricavi, è alle 00:00 UTC ogni giovedì pari.

Nell'esempio precedente:

* L'Epoch 1 inizia alle 00:00 UTC, 1°, giovedì della Settimana 1.
* L'Epoch 1 termina 2 settimane dopo, alle 00:00 UTC, 15°, giovedì della Settimana 3.
* Gli utenti possono votare durante il periodo dalle 00:00 UTC dall'1° al 14°.
* **NESSUN** voto può essere espresso durante il periodo dalle 00:00 UTC dal 14° al 15° poiché i voti vengono adeguati e conteggiati.
* I risultati delle votazioni verranno acquisiti in snapshot alle 00:00 UTC del 15°, al termine dell'Epoch 1.
* I risultati delle votazioni verranno applicati entro 72 ore dalla chiusura di un'epoch.

### 2 - Diventa idoneo

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Poiché veCAKE diminuisce gradualmente in base al tempo di blocco rimanente, i risultati delle votazioni verranno acquisiti tramite snapshot alla fine di ogni epoch. Questo include il numero totale di veCAKE e il veCAKE di ogni utente.

Nell'esempio precedente:

* I risultati dell'Epoch 1 saranno basati sui saldi di veCAKE alle 00:00 UTC del 15°.
* Gli utenti la cui posizione veCAKE si sblocca prima o uguale al 15° avranno un saldo di veCAKE pari a 0 al momento dello snapshot. Pertanto non hanno potere di voto per l'Epoch 1.

Pertanto, per diventare idoneo, devi ottenere una posizione veCAKE attiva che si sblocchi **DOPO** il momento di fine/snapshot dell'epoch corrente.

Nell'esempio precedente:

* Se vuoi votare nell'epoch 1, devi avere una posizione veCAKE che si sblocchi il 21° o successivamente, ovvero giovedì della settimana 3.

### 3 - Controlla i risultati di votazione correnti

Vai a "CAKE staking", scorri verso il basso e cerca la sezione "Gauges Voting", poi clicca su "Check Gauges".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Nella sezione in alto a sinistra puoi trovare:

* Il tuo veCAKE.
* Il momento dello snapshot e il termine del voto per l'epoch corrente.
* Il numero totale di ricompense CAKE da distribuire nella prossima epoch è basato sui risultati della votazione dell'epoch corrente.
* Il numero totale di voti veCAKE espressi.

In alto a destra puoi trovare un grafico a torta che rappresenta la % ricevuta da ciascun gauge.

In basso è presente un elenco completo di tutti i gauge votabili, con il numero di voti ricevuti e il % di peso previsto che stanno ottenendo nell'epoch corrente. C'è anche un campo "boost" e "caps" che dettaglia due importanti caratteristiche dei gauge. Continua a leggere per maggiori dettagli.

#### Boost dei gauge e limiti di emissione

Per garantire che le ricompense CAKE vadano ai gauge più produttivi, a ciascun gauge può essere applicato un boost e/o un limite di emissione. Le due caratteristiche possono coesistere.

Il Boost del gauge è un moltiplicatore applicato al numero di voti ricevuti da un gauge, che va da 1x a 2,5x (i gauge per i pool V3 sono limitati a 2x). Questo serve a incentivare i voti e la Liquidità per le coppie di trading importanti.

Il limite di emissione è un limite massimo sul % di peso che un gauge può ricevere, che va dal 2% al 20%. Questo serve a promuovere l'equità nell'allocazione e a prevenire abusi del sistema dei gauge.

Ad esempio:

* Un gauge ha 10 voti, boost 2x e limite del 15%. Il voto totale è 100.
* Dopo aver applicato il boost, questo gauge avrà 20 voti, peso del 20% sul totale (100).
* Tuttavia, poiché ha un limite del 15%, il % finale di ricompense CAKE che questo gauge riceverà nella prossima epoch verrà adeguato al 15%.

#### Come vengono determinati il Boost dei gauge e i limiti di emissione?

Durante il processo di candidatura di un gauge, chiediamo ai candidati di proporre il valore del moltiplicatore di boost e il % del limite di emissione che desiderano assegnare al gauge. Questi devono essere votati dai detentori di veCAKE, insieme all'intera candidatura del gauge.

L'opzione predefinita per tutti i gauge è il moltiplicatore 1,00x e il limite di emissione del 5%. Possono essere modificati con proposte future.

{% hint style="info" %}
Tieni presente che i risultati delle votazioni vengono aggiornati settimanalmente. I numeri vengono calcolati in base ai saldi di veCAKE alle 00:00 UTC del prossimo giovedì.
{% endhint %}

### 4 - Aggiungi i gauge da votare

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Per votare su un gauge, scorri verso il basso e cerca la sezione "My Votes". Clicca su "Add Gauge".

Nella finestra popup puoi aggiungere gauge alla tua lista di voti cliccando sull'icona blu "+". Puoi trovare i risultati di votazione correnti nell'elenco, insieme a boost e limiti.

Per individuare rapidamente un gauge, puoi usare i filtri per filtrare i gauge per blockchain, livelli di commissione e tipi di Liquidità. Oppure digita il ticker del token nel campo di ricerca.

### 5 - Seleziona quanto % di veCAKE votare per ciascun gauge

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Dopo aver aggiunto i gauge, puoi selezionare quale % del tuo veCAKE destinare a ciascun gauge.

Questo perché:

* veCAKE diminuisce gradualmente con il tempo di blocco rimanente. È impraticabile stimare e calcolare quanti veCAKE esatti votare.
* È scomodo rivivotare ad ogni epoch successiva. Pertanto, il Gauges Voting è progettato per mantenere le tue decisioni di voto in tutte le epoch successive fino a quando non ne esprimi una nuova.

Nell'esempio precedente:

* Al momento, ho 2,62 veCAKE.
* Ho deciso di allocare l'80% a CAKE-BNB, ovvero 2,10 veCAKE al momento.
* Il 20% a USDC-ETH, ovvero 0,52 veCAKE, sempre al momento.
* Il mio totale veCAKE diminuirà gradualmente con il tempo di blocco rimanente. Al momento dello snapshot, potrei avere meno veCAKE, ma la mia decisione di suddivisione 80%–20% verrà comunque applicata ai risultati finali.
* Inoltre, questa decisione 80%–20% verrà applicata a ogni epoch successiva fino a quando non la aggiornerò esprimendo una nuova richiesta di voto. Oppure fino a quando il mio veCAKE non scenderà a 0 per via dello sblocco.

Dopo aver confermato la tua decisione, clicca su "Submit vote" e conferma nel tuo Portafoglio.

### 6 - Aggiorna i tuoi voti

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Dopo che il tuo voto è stato inviato, puoi vedere i tuoi voti aggiornati in "Current Votes" e il veCAKE rimanente aggiornato.

Tieni presente che la decisione di voto per ciascun gauge può essere aggiornata solo ogni 10 giorni. Una volta inviata una richiesta di voto, tutti i gauge votati saranno soggetti a un periodo di attesa di 10 giorni prima che tu possa inviare un'altra richiesta di aggiornamento.

Per aggiornare la tua decisione di voto, modifica il % di percentuale e invia nuovamente.

{% hint style="info" %}
Tieni presente che dopo aver ottenuto più veCAKE aggiungendo CAKE o estendendo il tempo di blocco, devi aggiornare manualmente tutti i gauge reinviando la richiesta di voto.

Il periodo di attesa di 10 giorni si applica indipendentemente dal fatto che tu abbia modificato le tue decisioni di %.
{% endhint %}
