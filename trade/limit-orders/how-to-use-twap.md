# Come usare TWAP

## Cos'è TWAP?

TWAP (Time-weighted Average Price) è un tipo di ordine comune usato nel CeFi che suddivide un ordine in dimensioni di trade più piccole e le esegue a intervalli regolari. L'obiettivo principale di un ordine TWAP è ridurre l'impatto sul prezzo dell'ordine. Può essere utile anche se un utente vuole implementare una strategia di dollar-cost averaging (DCA) e acquistare un determinato token con cadenza regolare (ovvero una volta al mese).

Pertanto, TWAP è più indicato quando la dimensione dell'ordine è grande rispetto alla Liquidità disponibile, o quando un utente prevede un periodo di alta volatilità dei prezzi senza una chiara tendenza al rialzo o al ribasso.

## Come impostare un ordine TWAP?

1. Vai alla pagina Swap e seleziona l'opzione ordine TWAP cliccando su TWAP
2. Seleziona i token "Da" e "A" e inserisci l'importo che desideri tradare.
3. L'UI consente sia ordini dTWAP-market, che eseguono tutti i trade al prezzo di mercato disponibile, sia ordini dTWAP-limite, che eseguono i singoli trade solo se rientrano nel limite di prezzo impostato dall'utente. \
   In questo esempio abbiamo scelto di eseguire gli ordini TWAP al prezzo di mercato.
4. Successivamente, specifichiamo i parametri TWAP. Ci sono 3 parametri principali che controllano l'efficacia dell'ordine dTWAP:
   1. Totale trade: Consente all'utente di specificare il numero di trade individuali in cui verrà suddiviso il suo ordine. Lo slider dell'UI inizia con 1 trade e consente all'utente di aumentare il numero di trade individuali, oppure consente all'utente di inserire manualmente il totale dei trade nel campo di input direttamente.\
      Gli utenti dovrebbero notare che c'è un certo compromesso nella specificazione di questo parametro: più trade significa dimensioni di trade individuali più piccole, il che significa un impatto sul prezzo minore. Tuttavia, più trade significa anche più transazioni e commissioni gas totali più elevate.&#x20;
   2. Intervallo di Trade: Imposta il lasso di tempo tra ogni trade individuale. L'UI inizia con il minimo consentito (2 min), che lascia il tempo minimo per la guerra di offerte del taker e il regolamento del blocco tra ogni chunk. L'utente può impostarlo per qualsiasi durata desiderata. Un trade non verrà mai eseguito prima che trascorra questo tempo dopo il trade precedente.\
      Anche in questo caso gli utenti dovrebbero essere attenti nell'impostare questo parametro: intervalli più lunghi consentirebbero agli arbitraggisti una finestra più lunga per chiudere eventuali discrepanze di prezzo nei pool interessati e riportare le riserve all'equilibrio (in linea con il prezzo spot). Tuttavia, richiederebbe più tempo per eseguire l'ordine e aggiungerebbe incertezza al prezzo finale di esecuzione, specialmente in periodi di alta volatilità
   3. Durata Massima: Il tempo massimo durante il quale può essere eseguita la quantità totale di tutti i trade individuali che compongono l'ordine dTWAP completo. Dopo questa scadenza il trade scade, indipendentemente dagli importi effettivamente scambiati.\
      Nota che non tutti i chunk potrebbero essere eseguiti negli ordini limite, a seconda che il prezzo rimanga nei parametri impostati. \
      La durata predefinita raccomandata viene calcolata moltiplicando il numero di intervalli per l'intervallo di trade, e poi raddoppiando questo importo per fungere da buffer per consentire tempo sufficiente per l'attività on-chain. (nota che impostare una durata più breve rispetto alla durata predefinita sopra potrebbe risultare in un ordine parzialmente eseguito).

Come si può vedere, questi parametri offrono grande flessibilità nella personalizzazione di ogni ordine, tenendo conto di fattori come le condizioni di mercato, le commissioni gas correnti, ecc.

8. Premi "Place order". Controlla i dettagli del tuo ordine, accetta la dichiarazione di non responsabilità e premi "Confirm order".
9. Una volta elaborata la transazione, potrai vedere lo stato del tuo ordine nella sezione della cronologia degli ordini, sotto "Open orders".
10. Gli ordini aperti possono essere cancellati in qualsiasi momento espandendo l'ordine e cliccando sul pulsante "Cancel Order".

Cose da considerare

* Gli ordini vengono eseguiti in trade più piccoli nel corso di un periodo di tempo specificato e sono soggetti alle condizioni di mercato e ad altri rischi.
* Il tuo trade potrebbe essere eseguito a un prezzo significativamente diverso dal prezzo di mercato corrente (anche se non peggiore del tuo prezzo limite, se ne hai impostato uno), il che potrebbe comportare perdite significative. Se il prezzo di mercato disponibile è peggiore del prezzo limite che hai impostato, alcuni dei trade del tuo ordine potrebbero non essere eseguiti, risultando in un ordine parzialmente eseguito.
* I trade si basano su un protocollo decentralizzato che utilizza taker off-chain che competono per eseguire gli ordini. Questi taker sono autorizzati a richiedere una commissione, che il protocollo rimuove dal taker vincente dai token di output.&#x20;
* I taker possono tenere conto delle commissioni gas per le tue transazioni quando impostano le loro commissioni, il che può comportare fluttuazioni negli importi delle commissioni.

<br>
