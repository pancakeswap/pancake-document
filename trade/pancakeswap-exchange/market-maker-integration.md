---
hidden: true
---

# Integrazione con i Market Maker

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Integrazione con i Market Maker su Ethereum

PancakeSwap è integrato con i market maker su Ethereum e Binance Smart Chain per aiutare i trader a eseguire scambi a un costo inferiore.

Oltre all'AMM, gli scambi su PancakeSwap possono ora essere instradati verso market maker designati e inseriti in whitelist, se offrono un'esecuzione degli scambi migliore rispetto ai prezzi correnti dell'AMM. Questo routing viene gestito automaticamente da uno [Smart Router](smart-router-v2/) in modo che gli scambi vengano instradati verso i market maker solo quando stanno quotando prezzi migliori. Quando l'AMM è più competitivo, i trader verranno instradati verso gli AMM per l'esecuzione.

Esistono 2 scenari in cui i market maker operano su PancakeSwap.

**Scenario 1: Pool di liquidità AMM esistenti**

Se PancakeSwap ha già liquidità per un determinato token (ad es. WETH/USDC) nell'AMM, PancakeSwap chiederà ai market maker una quotazione per lo stesso scambio. Lo smart router di PancakeSwap instraderà quindi la richiesta di scambio verso l'AMM o i market maker a seconda di quale fonte di liquidità offre il prezzo migliore in un dato momento.

**Scenario 2: Nessun pool di liquidità AMM esistente**

In questo scenario, lo smart router instraderà automaticamente lo scambio verso i market maker. Tuttavia, questo non impedisce ai progetti di creare successivamente il proprio pool di liquidità AMM e di collaborare con noi per mantenere la liquidità DEX decentralizzata.

### Commissioni

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap non addebita ai trader alcuna commissione per gli scambi eseguiti tramite noi e dai market maker. Tuttavia, PancakeSwap riceve **0,05%** di **commissioni di trading** dai market maker inseriti in whitelist per i volumi da loro eseguiti. PancakeSwap riceve una **commissione di trading** ridotta dello **0,01%** se gli scambi eseguiti riguardano coppie di stablecoin. Consulta il dettaglio delle commissioni di seguito:<br>

<table><thead><tr><th width="178">Scambi</th><th width="138">Commissioni di Trading</th><th width="182">Commissione PCS dai MM</th><th width="147">Cake Burn</th><th align="center">Treasury PancakeSwap</th></tr></thead><tbody><tr><td>Coin con Bridge da altre reti</td><td>N/A</td><td>0.25%</td><td>0.083%</td><td align="center">0.167%</td></tr><tr><td>Non-stablecoin su Ethereum (es. ETH/USDC)</td><td>N/A</td><td>0.05%</td><td>0.017%</td><td align="center">0.033%</td></tr><tr><td>Non-stablecoin su BSC (es. BNB/USDT)</td><td>N/A</td><td>0.05%</td><td>0.017% </td><td align="center">0.033%</td></tr><tr><td>Stablecoin verso Stablecoin su Ethereum</td><td>N/A</td><td>0.01%</td><td>0.003%</td><td align="center">0.007%</td></tr></tbody></table>

#### Asset attualmente supportati

I seguenti asset sono attualmente supportati e potrebbero aumentare/diminuire a seconda dei market maker:

**Su Ethereum**

* **Principali:** WETH, WBTC
* **Stablecoin:** USDT, USDC, DAI, BUSD
* **Altri asset ERC-20 popolari:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Su Binance Smart Chain:**

* **Principali:** BNB, ETH, BTCB
* Token non nativi BNB: ARB, OP

Tieni presente che, a differenza degli AMM, i market maker non possono operare con qualsiasi importo e gli importi che sono disposti a eseguire dipendono dalla loro liquidità. Non è insolito che a volte gli ordini molto grandi non possano essere completamente evasi. Consigliamo agli utenti di esaminare attentamente le quotazioni per assicurarsi che ogni scambio rifletta il prezzo e la quantità in base alle proprie esigenze.

**Interruzioni dei market maker**

Non è previsto che i market maker quotino 24 ore su 24, 7 giorni su 7. Ci sono alcuni casi (ad es. eventi economici chiave, aggiornamenti di sistema) in cui il market maker potrebbe essere temporaneamente non disponibile a fornire una quotazione. Tieni presente che durante questi periodi, questi token semplicemente non saranno negoziabili, e consigliamo agli utenti di attendere prima che il market maker torni online.

#### FAQ

**D.** I market maker verranno integrati su Aptos?

**R:** Possibilmente. Al momento stiamo lanciando l'integrazione dei market maker solo su Ethereum e Binance Smart Chain per aumentare la liquidità e migliorare l'esperienza utente. Continueremo a monitorare le altre chain.

**D.** Come genererà entrate PancakeSwap se non addebita commissioni agli utenti?

**R:** PancakeSwap non addebiterà alcuna commissione agli utenti, ma riceverà una piccola commissione dai market maker e la utilizzerà per finanziare il riacquisto e la combustione di CAKE.

**D.** I fornitori di liquidità continueranno a guadagnare commissioni LP?

**R:** Sì, i fornitori di liquidità continueranno a guadagnare una ricompensa di commissione di trading dello 0,17% (commissioni LP) e rendimento sulle Farm CAKE.

**D.** I market maker aggiungeranno liquidità all'AMM? Ciò causerà un calo dell'APR?

**R:** I market maker mantengono la propria liquidità separata e pertanto non guadagneranno alcun APR dagli scambi sull'AMM. Solo gli LP guadagneranno commissioni e APR fornendo liquidità ai pool AMM.

**D.** Sto fornendo liquidità su PancakeSwap su Ethereum. Devo fare qualcosa?

**R:** No, non devi fare nulla. Continuerai a guadagnare le commissioni LP per gli scambi eseguiti tramite AMM e continuerai a ottenere rendimento in CAKE.

**D.** Come si può diventare un market maker?

**R:** Selezioniamo i market maker e collaboriamo con loro singolarmente. Contattaci direttamente o tramite i nostri amministratori se sei interessato a lavorare con noi.
