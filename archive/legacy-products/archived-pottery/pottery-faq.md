# FAQ di Pottery

{% hint style="danger" %}
\[Archiviato] Pottery – A partire dal 3 novembre 2023
{% endhint %}

## Perché abbiamo bisogno di Pottery se abbiamo già la Lotteria v2?

Pottery è un prodotto completamente diverso rispetto alla Lotteria v2. È una combinazione del pool CAKE bloccato e della funzione lotteria che utilizza l'implementazione VRF di Chainlink per una vera casualità sicura. Partecipando a Pottery, non perderai nessuno dei CAKE che depositi; rischi solo le ricompense di staking dei CAKE depositati. Questo prodotto è pensato per i detentori di CAKE più avversi al rischio ma che vogliono comunque partecipare a un prodotto di questo tipo. È un modo facile, divertente e sicuro per avere la possibilità di vincere qualche CAKE. Scopri di più sulla [struttura del prodotto qui](https://docs.pancakeswap.finance/products/pottery).

## Pottery sta sostituendo la Lotteria v2 originale?

Pottery non sostituisce la Lotteria v2 originale. Questi due prodotti vengono operati e gestiti separatamente. Puoi partecipare a entrambi!

## Come aiuta Pottery PancakeSwap e CAKE?

Otto percento (8%) del pot dei premi distribuito ogni settimana sarà addebitato come commissioni per il burn, accumulando valore per CAKE. Miriamo a rivedere e adeguare la struttura delle commissioni di conseguenza dopo la fase beta del prodotto.

## A cosa serve la fase beta di Pottery?

A causa delle operazioni di questo nuovo prodotto come il prestito dal treasury, la gestione delle coorti e le estrazioni. Il prodotto partirà nella fase beta con un deposito totale limitato per ogni Pottery per assicurarsi che tutto funzioni correttamente. Una volta superata la fase beta, potremmo rivedere e adeguare diversi parametri in base alle operazioni e ai feedback della community come le commissioni, la frequenza di ogni coorte, il periodo di blocco, ecc.

## Perché deve bloccare i miei CAKE per 10 settimane?

Se Pottery potesse semplicemente usare il pool di staking flessibile, la sua struttura del prodotto sarebbe molto più semplice — simile a prodotti come PoolTogether e Moonpot. Tuttavia, il rendimento attuale dal pool di staking flessibile non è sufficiente per produrre un pool premi significativo per le estrazioni. Quindi, la decisione è di bloccare i CAKE per una durata moderata per bilanciare le ricompense che possono essere usate per finanziare il pool premi. Con più operazioni e feedback della community, potremmo rivedere e adeguare la durata del blocco in seguito.

## Perché non riesco a prelevare?

Tieni presente che il pulsante di prelievo si illuminerà e sarà disponibile solo dopo 10 settimane dalla data di blocco. La data per il prelievo è basata su 10 settimane dopo la data e l'ora di blocco — 23:59 UTC il primo lunedì di ogni mese.

## Perché non riesco a visualizzare il mio deposito?

Potrebbe occasionalmente esserci un leggero ritardo a causa della lettura del Subgraph; ci sarà un segnale in caso di ritardi — solitamente dovrebbe mostrare l'importo corretto se controlli di nuovo tra 15 minuti.

## Come faccio a sapere se ho vinto nell'estrazione settimanale?

Dopo ogni estrazione il venerdì a circa mezzogiorno UTC, puoi visualizzare i risultati e i vincitori nel pannello Round Terminati. Un altro modo per verificare se hai vinto in una delle estrazioni settimanali è controllare nel pannello Richiedi se c'è qualche premio da rivendicare. Dai un'occhiata [a questa pagina su come partecipare](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery)!

## Qual è la fonte di finanziamento del premio?

I pool premi sono finanziati dalle ricompense di staking dei depositi. Tuttavia, poiché le ricompense di staking del pool di staking bloccato di CAKE vengono distribuite solo dopo la durata del blocco — 10 settimane in questo caso — per una migliore esperienza del prodotto e per facilitare le estrazioni settimanali subito dopo la data del deposito, il contratto prende in prestito l'80% del totale stimato delle ricompense di staking dalla coorte dal treasury CAKE in base all'APR al momento del blocco. I CAKE presi in prestito vengono usati per il pagamento di ogni estrazione settimanale. Scopri di più sulla [struttura del prodotto qui](https://docs.pancakeswap.finance/products/pottery)!

## Se vinco, devo rivendicare manualmente il premio?

Sì, dovrai cliccare il pulsante Rivendica nel pannello Richiedi sulla pagina Pottery.

## Con quale frequenza si svolge il Pottery?

Ogni coorte Pottery è aperta per il deposito il venerdì precedente a circa le 10:00 UTC e si chiude il primo lunedì di ogni mese alle 23:59 UTC, salvo disposizioni speciali e avvisi in anticipo. Ogni coorte avrà 10 estrazioni settimanali in 10 venerdì consecutivi a mezzogiorno UTC.

Il primo Pottery aprirà i depositi il 5 agosto 2022 e si bloccherà l'8 agosto 2022 alle 23:59 UTC.

## Perché il deposito Pottery è aperto solo una volta al mese?

Questo accordo combina il deposito da indirizzare al pool di staking bloccato, in modo che il contratto Pottery della coorte possa coordinare le ricompense di staking del deposito dal pool di staking bloccato. Con più operazioni e feedback della community, potremmo rivedere e adeguare la frequenza in seguito.

## Qual è il limite per il deposito?

C'è un deposito minimo di 1 CAKE. Nella fase beta del prodotto, ci sarà anche un limite massimo di deposito per ogni coorte che puoi vedere nel pannello Deposito quando stai effettuando il deposito. Questo per assicurarsi che tutto sul lato operativo, incluso il prestito dal treasury, lo staking bloccato e le estrazioni, funzioni correttamente. Mentre il massimo che puoi depositare è il limite massimo di deposito di quella coorte (se nessun altro ha depositato CAKE), vinceresti tutti i premi; tuttavia, ciò significa anche che il ritorno finale che otterrai è lo stesso che mettere i tuoi CAKE nel pool di staking bloccato per 10 settimane, ma pagherai anche le commissioni Pottery.

## Perché abbiamo bisogno del sistema delle coorti? Perché non raggruppiamo tutto insieme?

Poiché Pottery interagisce con lo staking a termine fisso di CAKE, qualsiasi deposito può essere prelevato solo dopo la durata del blocco. Se volessimo raggruppare tutti i depositi insieme, pur potendo aggiungere altri depositi dopo il blocco iniziale e bloccarli anch'essi per 10 settimane (dal momento del nuovo deposito), i depositanti iniziali non potrebbero prelevare in tempo.

## Cos'è il token SHARE?

I token SHARE vengono generati e distribuiti quando depositi nel pottery. Rappresenta e funge da credenziale della tua quota rispetto al pool di deposito.

Al momento del prelievo, il token SHARE verrà trasferito al contratto pottery e bruciato.

## Dove posso fornire feedback per questo prodotto?

Sentiti libero di contattarci su [Telegram](https://t.me/pancakeswap) o [Discord](https://discord.gg/pancakeswap) se non sei ancora sicuro del formato o se hai feedback per aiutarci a migliorarlo ulteriormente!
