# Arbitrum

Il 31 agosto 2023, PancakeSwap Perpetuals lancerà il Programma di Ricompense di Trading V2 su Arbitrum. Gli utenti che mettono in Staking [ALP nel Syrup Pool CAKE](https://pancakeswap.finance/pools?chain=arb) su Arbitrum possono godere di moltiplicatori di potenziamento. Inoltre, non c'è periodo di maturazione per le ricompense guadagnate in questo programma. Gli utenti possono riscattare le loro ricompense USDC in qualsiasi momento. I dettagli sono i seguenti:

Orario di inizio: 31 agosto 2023, 08:00 (UTC)

Periodo di Attività (Epoch): Ogni giovedì dalle 08:00:00 UTC al giovedì successivo alle 07:59:59, per una durata di 1 settimana

Orario di Distribuzione delle Ricompense: Ogni ciclo è dalle 00:00 (UTC) alle 23:59 (UTC) giornaliero. Le ricompense vengono emesse ogni giovedì intorno alle 08:00 (UTC). Dopo l'aggiornamento del livello dell'utente, le ricompense verranno calcolate e distribuite. Gli utenti devono riscattare le loro ricompense entro 30 giorni dall'emissione. In caso contrario, la piattaforma revocherà le ricompense.&#x20;

Importo della ricompensa: Per le prime 5 settimane, il 25% delle commissioni di trading (in USDC). Questo pool di premi verrà poi distribuito in base ai livelli.

Regole dell'attività: Gli utenti che fanno trading su PancakeSwap Perpetuals V2 su Arbitrum si qualificheranno per il pool di premi

### Ripartizione dei Livelli

Ogni giovedì alle 08:00:00 UTC, calcoliamo i dati di trading dall'ultimo giovedì alle 08:00:00 UTC a questo giovedì alle 07:59:59 e quindi aggiorniamo il Livello dell'utente in base alle regole del Livello. Le regole del Livello sono le seguenti (la configurazione è supportata):

<table><thead><tr><th width="161">Livello</th><th width="249.33333333333331">Descrizione</th><th>Peso</th></tr></thead><tbody><tr><td>Diamond</td><td>Volume di trading dell'Epoch >=1M USD</td><td>5</td></tr><tr><td>Gold</td><td>Volume di trading dell'Epoch >=500K USD</td><td>3</td></tr><tr><td>Silver</td><td>Volume di trading dell'Epoch >=250K USD</td><td>1</td></tr></tbody></table>

**Nota: I criteri dei livelli e i pesi sono soggetti a modifiche in base alla Liquidità del pool e all'attività di trading complessiva sulla piattaforma**

Le ricompense verranno distribuite equamente tra tutti gli utenti che si qualificano per un determinato livello

### Formula di calcolo delle Ricompense di Trading:&#x20;

Al termine di ogni ciclo di ricompense di trading, il volume di trading effettivo dell'utente in quel ciclo verrà calcolato per determinare il peso e l'importo delle ricompense USDC.

La formula per il numero di ricompense specifiche è: r = min{R \* W/Sum(Wi), R \* 20%\}, i parametri sono i seguenti:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Importo della ricompensa USDC da estrarre dall'utente per l'epoch corrente</td></tr><tr><td>R</td><td>La ricompensa dell'epoch corrente R=(valore USDC della commissione ETH + valore USDC della commissione DAI + valore USDC della commissione BTC + commissione USDC)*0,25, di cui l'1% di commissione Swap deve essere detratto al momento del regolamento, ad esempio: quando la commissione ETH settimanale è 1 e il Prezzo ETH è 2.000, la commissione ETH per il valore USDC = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Peso corrispondente al livello dell'utente</td></tr><tr><td>Sum(Wi)</td><td>Punteggio di peso totale di tutti gli utenti. Wi rappresenta il peso di qualsiasi utente, e sum(Wi) rappresenta la somma dei punteggi di peso di tutti gli utenti.</td></tr></tbody></table>

* La quota massima di entrate per utente è limitata al 20% dei ricavi riservati al programma

Termini e Condizioni

* A causa della differenza nelle commissioni di trading per ogni coppia di trading su V2, le ricompense ricevute dagli utenti possono variare anche se i loro volumi di trading effettivi sono gli stessi.
* Le ricompense da distribuire per ogni ciclo verranno archiviate nel seguente indirizzo contratto:&#x20;
* PancakeSwap/ApolloX si riserva il diritto di interpretazione finale per questa attività.



Avvertenza sul Rischio: Il trading di crypto futures comporta un rischio sostanziale. Tutte le attività di trading vengono eseguite a tua discrezione e a tuo rischio. Le informazioni qui contenute non devono essere considerate come consigli finanziari o di investimento da parte di PancakeSwap/ApolloX. PancakeSwap/ApolloX non sarà responsabile per eventuali perdite che potrebbero derivare dall'uso di PancakeSwap/ApolloX.

<br>
