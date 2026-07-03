# 🍯 \[Archiviato] Pottery

{% hint style="danger" %}
\[Archiviato] Pottery – A partire dal 3 novembre 2023
{% endhint %}

Pottery combina il lock-staking di CAKE con elementi di lotteria per darti la possibilità di vincere un rendimento più elevato sul tuo deposito di CAKE! È facile e sicuro poiché riceverai sempre indietro almeno tutti i CAKE che depositi.

## Specifiche:

* Deposita CAKE nella pagina Pottery con un minimo di 1 CAKE&#x20;
* Il deposito si chiude il primo lunedì di ogni mese per una diversa coorte Pottery (23:59 UTC di quel lunedì) ed è aperto dal venerdì precedente a circa le 10:00 UTC, salvo disposizioni speciali annunciate in anticipo (il primo Pottery si chiude l'8 agosto 2022 alle 23:59 UTC)
* Durante la fase beta del prodotto, c'è un limite al deposito totale di CAKE per ogni coorte Pottery (il limite massimo di deposito è 600.000 CAKE)
* I CAKE depositati verranno indirizzati al pool di lock-staking e bloccati per dieci (10) settimane. L'80% del totale delle ricompense di staking sarà inviato al pool Pottery per l'estrazione, il 20% sarà riservato per il tuo prelievo&#x20;
* Per ogni coorte Pottery (una al mese), ci saranno dieci (10) estrazioni settimanali ogni venerdì (a mezzogiorno UTC) a partire dal deposito, producendo otto (8) vincitori a settimana; un indirizzo può vincere più di uno degli otto slot vincenti ogni settimana \*
* Più è grande il tuo deposito rispetto al pool complessivo, maggiore è la possibilità di vincere; i vincitori possono rivendicare il loro premio subito dopo ogni estrazione&#x20;
* Ogni coorte Pottery conduce l'estrazione separatamente&#x20;
* Solo dopo 10 settimane dalla data di blocco della coorte Pottery, puoi prelevare i tuoi CAKE&#x20;
* Pottery usa l'implementazione VRF di Chainlink per una vera casualità sicura

## Coorte Pottery&#x20;

Il venerdì prima del primo lunedì di ogni mese, una coorte Pottery sarà aperta per depositare CAKE e parteciparvi per le successive 10 settimane. Questo accordo combina il deposito da indirizzare al pool di staking bloccato, in modo che il contratto Pottery della coorte possa coordinare le ricompense di staking del deposito dal pool di staking bloccato.

Ogni data di deposito e blocco sarà una coorte separata — una per ogni mese — ad esempio tutti i depositi del 5 settembre 2022 saranno in una coorte, tutti i depositi del 3 ottobre 2022 saranno in un'altra coorte.

Mentre le estrazioni possono avvenire contemporaneamente per diverse coorti, i pool premi per ogni coorte sono separati per essere equi.

![(Solo a scopo illustrativo, la data effettiva di blocco della coorte per il primo Pottery è stata fissata all'8 agosto 2022)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

Ad esempio, ci sono 2 estrazioni separate il 9 settembre 2022, una per la coorte dell'1 agosto come sesta estrazione settimanale e un'altra per la coorte del 5 settembre come prima estrazione settimanale. Se la coorte dell'1 agosto ha un totale di 100.000 CAKE depositati e la coorte del 5 settembre ha un totale di 300.000 CAKE depositati, il premio settimanale per la coorte dell'1 agosto proverrà solo dalle ricompense di staking di quei 100.000 CAKE, mentre il premio settimanale per la coorte del 5 settembre proverrà solo dalle ricompense di staking di quei 300.000 CAKE. Se hai depositato CAKE solo nella coorte dell'1 agosto, hai la possibilità di vincere il premio settimanale il 9 settembre in base alle ricompense di staking di 100.000 CAKE. Se hai depositato CAKE in entrambe le coorti dell'1 agosto e del 5 settembre, hai la possibilità di vincere entrambi i premi settimanali il 9 settembre.

#### Perché abbiamo bisogno del sistema delle coorti? Perché non raggruppiamo tutto insieme?

Poiché Pottery interagisce con lo staking a termine fisso di CAKE, qualsiasi deposito può essere prelevato solo dopo la durata del blocco. Se volessimo raggruppare tutti i depositi insieme, pur potendo aggiungere altri depositi dopo il blocco iniziale e bloccarli anch'essi per 10 settimane, i depositanti iniziali non potrebbero prelevare in tempo.

## **Finanziamento dei Premi e Allocazione delle Ricompense di Staking**

I depositi vengono raggruppati in coorti mensili per una più efficiente gestione delle ricompense di staking, anch'esse raggruppate per ogni coorte. Le ricompense di staking vengono utilizzate per finanziare il pool premi e alcune ricompense di staking per il deposito nel Pottery.

L'80% delle ricompense di staking sarà destinato a finanziare il pool premi per le 10 estrazioni settimanali e il restante 20% sarà riservato come ricompense di staking quando prelevi il tuo deposito CAKE dopo 10 settimane.

Tuttavia, poiché le ricompense di staking del pool di staking bloccato di CAKE vengono distribuite solo dopo la durata del blocco — 10 settimane in questo caso — per una migliore esperienza del prodotto e per facilitare le estrazioni settimanali subito dopo la data del deposito, il contratto prende in prestito l'80% del totale stimato delle ricompense di staking dalla coorte dal treasury CAKE in base all'APR al momento del blocco. I CAKE presi in prestito vengono usati per il pagamento di ogni estrazione settimanale.

Alla fine delle 10 settimane, quando le ricompense vengono distribuite dal pool di staking, il treasury CAKE verrà rimborsato per primo, poi il resto verrà reindirizzato al vault per consentire agli utenti di prelevare insieme al loro deposito iniziale nella coorte.

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEF6IySHEmy1P1k5S3W_pPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Ad esempio, se la coorte Pottery dell'1 agosto 2022 ha attratto 100.000 CAKE in depositi totali, il ritorno stimato per 10 settimane di staking bloccato è di circa 3.674 CAKE. Il contratto prenderà in prestito l'80%, ovvero circa 2.940 CAKE, per il pool premi per le 10 estrazioni settimanali, ovvero 294 CAKE in premi totali per ogni estrazione settimanale al netto delle commissioni.

È importante notare che le ricompense e l'APR alla fine della durata dal deposito possono cambiare nel corso delle 10 settimane in base agli altri depositi e ai loro periodi di blocco nel pool CAKE bloccato; potrebbe esserci una piccola deviazione dalle percentuali specificate (+/- 10%).

Tutte le ricompense di staking al netto delle commissioni saranno restituite ai depositanti tramite il pool premi o ricompense. Se l'APR effettivo è inferiore all'APR stimato al momento del blocco, significa che più ricompense vengono distribuite ai depositanti durante le estrazioni settimanali e meno per la parte delle ricompense di staking. Se l'APR effettivo è superiore all'APR stimato al momento del blocco, meno ricompense vengono distribuite tramite le estrazioni settimanali e più vengono riservate come ricompense di staking disponibili per il prelievo. In ultima analisi, il valore atteso è lo stesso.

## **Come Vincere – Calcolo delle Probabilità**

Le probabilità vengono calcolate in base alla quota dell'importo del deposito rispetto alla dimensione totale del deposito della coorte. In parole semplici, più CAKE depositi, maggiore è la possibilità di vincere ogni estrazione settimanale. Ad esempio, se hai depositato 10.000 CAKE e il deposito totale della coorte è 100.000 CAKE, c'è il 10% di possibilità che tu vinca a ogni estrazione settimanale.

Ogni indirizzo può vincere più di 1 degli 8 slot vincenti ogni settimana.

Nel caso estremo, se tutti i 100.000 CAKE della coorte vengono depositati da te, vincerai tutti i premi di ogni estrazione settimanale. Tuttavia, ciò significa che il ritorno finale che otterrai è lo stesso che mettere 100.000 CAKE nel pool di staking bloccato per 10 settimane, ma pagherai anche le commissioni Pottery.

## **Rischi – Importante!**

Hai la garanzia di recuperare il 100% di ciò che hai depositato in 10 settimane. Tuttavia, puoi _solo_ prelevare il tuo deposito CAKE dopo 10 settimane di blocco, senza altro modo per prelevare anticipatamente.

Partecipando al Pottery, rischi le ricompense di staking, insieme ad altre utilità del CAKE bloccato come iCAKE e vCAKE. Nel caso in cui non vinci nulla dalle 10 estrazioni settimanali, avresti perso l'80% delle ricompense di staking che avresti dovuto ottenere se avessi bloccato i tuoi CAKE nel pool di staking per 10 settimane.

Partecipa in base alla tua propensione al rischio: una volta depositati i CAKE, non c'è nulla che chiunque possa fare per aiutarti a prelevare anticipatamente.

## **Commissioni**

Otto percento (8%) del pot dei premi distribuito ogni settimana sarà addebitato come commissioni per il burn. Miriamo a rivedere e adeguare la struttura delle commissioni di conseguenza dopo la fase beta del prodotto.

## **Pronto a partecipare?**

Se hai capito bene la struttura del prodotto, i rischi e le commissioni, consulta questa pagina su [come partecipare](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) dall'interfaccia web di PancakeSwap e altre [FAQ di Pottery](https://docs.pancakeswap.finance/products/pottery/pottery-faq)!


