# FAQ

1. **In cosa si differenzia Infinity da PancakeSwap V3?**\
   Infinity aggiunge nuove funzionalità come hook programmabili, più [tipi di pool](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (come LBAMM e CLAMM), e risparmio di gas. Tuttavia, i meccanismi principali di Swap e di fornitura di liquidità sono ampiamente simili a v3, ad eccezione di alcune differenze minori nei pool LBAMM per la fornitura di liquidità.\
   <br>
2.  **Qual è la differenza tra LBAMM e CLAMM?**

    1. **LBAMM (Liquidity Book AMM):** Usa bin di liquidità, ognuno dei quali detiene liquidità a diversi livelli di prezzo. I LP possono fornire liquidità su più bin; gli Swap vengono eseguiti a un singolo livello di prezzo all'interno di un bin.
    2. **CLAMM (Concentrated Liquidity AMM):** Permette agli utenti di fornire liquidità all'interno di intervalli di prezzo personalizzati, come in PancakeSwap V3.

    \
    Per maggiori dettagli, visita [qui](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **Come posso riscuotere le mie ricompense Farm e perché sono limitate a ogni 8 ore?**\
   Puoi riscuotere le ricompense Farm dalle tue posizioni di liquidità cliccando sul pulsante "Harvest". Infinity consente la riscossione in batch di tutte le posizioni Farm attive, risparmiando sui costi di gas. Le ricompense vengono calcolate ed elaborate ogni 8 ore per ottimizzare i costi di gas e il calcolo. \
   \
   Per maggiori dettagli sul meccanismo di farming, visita [qui](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **Come funzionano gli hook di Infinity?**\
    Gli hook sono estensioni di smart contract personalizzabili che aggiungono funzionalità extra a un pool. Possono attivare azioni aggiuntive durante gli Swap o gli eventi di liquidità — ad esempio, regolando le commissioni, offrendo sconti o applicando altra logica.<br>

    Gli hook vengono associati a un pool al momento della sua creazione. Nella maggior parte dei casi, **gli utenti non devono effettuare alcun passaggio aggiuntivo**. Finché fai Swap o fornisci liquidità come di consueto, beneficerai automaticamente della logica dell'hook se si applica a quel pool.<br>

    👉 **Puoi visualizzare gli hook attivi e i loro dettagli nella pagina di ogni pool nella sezione "Funzionalità del Pool".**\
    <br>
5.  **Perché non ho ricevuto commissioni al momento del ritiro della mia posizione da un pool LBAMM?**\
    Nei pool LBAMM (Liquidity Book AMM), le commissioni vengono aggiunte automaticamente ai tuoi bin di liquidità attivi. Questo significa che:

    1. Quando ritiri la tua posizione, le commissioni guadagnate sono incluse negli importi totali di token che stai ritirando.
    2. A differenza degli AMM tradizionali, non esiste un saldo separato di "commissioni da riscuotere" — è tutto incluso nel valore della tua posizione.

    \
    Se non hai notato token aggiuntivi al momento del ritiro, potrebbe essere perché:

    1. La tua posizione potrebbe aver subito più perdite impermanenti rispetto alle commissioni raccolte a causa dei movimenti di prezzo durante la durata della tua posizione.
    2. La tua liquidità non era in bin attivi dove si sono verificati scambi.
