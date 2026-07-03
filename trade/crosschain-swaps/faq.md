# ❓ FAQ

### 1. Come funziona la tolleranza allo Slippage per gli Swap Cross-chain?

Per gli Swap Cross-chain, la percentuale di tolleranza allo Slippage selezionata viene applicata in modo indipendente agli Swap sia sulla chain di origine che su quella di destinazione.

**Esempio:**

* Swap BNB su BNB Chain verso ARB su Arbitrum
* Tolleranza allo Slippage impostata all'1%
* Il percorso potrebbe essere:
  1. Swap BNB → USDC su BNB Chain
  2. Bridge USDC da BNB Chain ad Arbitrum tramite Across
  3. Swap USDC → ARB su Arbitrum
* In questo caso, la tolleranza allo Slippage dell'1% si applica separatamente a:
  * Lo Swap su BNB Chain
  * Lo Swap su Arbitrum

Questo ti protegge da movimenti di prezzo eccessivi su entrambe le fasi della transazione, mantenendo il processo di Bridging non influenzato dalle impostazioni di Slippage.

### 2. Cosa succede se la mia transazione fallisce?

Se il tuo Swap Cross-chain incontra un problema in qualsiasi fase, ecco come viene gestito:

1.  **Fallimento dello Swap/Transazione sulla Chain di Origine**

    ➝ Riceverai immediatamente il tuo token originale sulla chain di origine.
2.  **Fallimento della Transazione Bridge**

    ➝ Across elaborerà un rimborso entro 90 minuti - 2 ore, e riceverai l'asset con Bridge sulla chain di origine. Relay invece elabora il rimborso in circa un minuto in tali scenari tra SOL <> EVM.
3.  **Fallimento dello Swap sulla Chain di Destinazione**

    ➝ Riceverai l'asset con Bridge sulla chain di destinazione, senza lo Swap finale verso il tuo token di destinazione.

{% hint style="info" %}
**Nota:** Puoi sempre controllare lo stato delle tue transazioni tramite la scheda della cronologia delle transazioni nell'interfaccia di WalletConnect.
{% endhint %}

### 3. I miei Swap Cross-chain sono protetti da MEV?

MEV Guard è supportato solo su BNB Chain quando gli Swap vengono avviati direttamente da un portafoglio connesso con MEV Guard abilitato.

* Se il tuo Swap Cross-chain include uno Swap su BNB Chain come chain di origine, e hai MEV Guard abilitato, quello Swap sarà protetto da MEV.
* Se BNB Chain è la chain di destinazione, lo Swap viene eseguito dal relayer/sistema di Bridging e non sarà protetto da MEV, poiché non è avviato dal tuo portafoglio connesso.

{% hint style="info" %}
**Nota:** Altre chain come Arbitrum e Base attualmente non supportano la protezione MEV Guard su PancakeSwap.
{% endhint %}

### 4. Posso fare Swap di stablecoin tra chain diverse?

Sì — puoi fare Swap e Bridge di stablecoin come USDC, USDT e DAI direttamente tra qualsiasi chain supportata.

Hai due opzioni:

1.  **Bridge Diretto:**

    Fai il Bridge di stablecoin supportate (come USDC, USDT, ecc.) direttamente da una chain all'altra.
2.  **Swap verso Altri Token:**

    Puoi anche fare lo Swap di una stablecoin verso qualsiasi altro token supportato sulla chain di destinazione utilizzando i pool di liquidità di PancakeSwap — prima o dopo il Bridging.

{% hint style="info" %}
**Nota:** Le stablecoin supportate per il Bridge diretto possono variare a seconda della chain.
{% endhint %}

### 5. I miei Swap utilizzeranno PCSX?

No — PCSX non è supportato per gli Swap Cross-chain.

Gli Swap Cross-chain su PancakeSwap vengono instradati esclusivamente attraverso:

* **I pool di liquidità di PancakeSwap** (v2, v3, Infinity, StableSwap) per gli Swap on-chain, e
* **I protocolli Across & Relay** per il Bridging degli asset tra chain.

PCSX non può essere utilizzato per facilitare o instradare alcuna parte di una transazione di Swap Cross-chain.

### 6. Esiste un limite minimo o massimo sull'importo dello Swap?

Sì — alle transazioni Cross-chain si applicano sia limiti minimi che massimi.

* **Limite Massimo:**\
  Dipende dalla liquidità di Bridge disponibile per il token e la chain selezionati. Questo valore può fluttuare in tempo reale in base alle condizioni della rete e della liquidità.
* **Limite Minimo:**\
  Impostato per garantire che sia economicamente conveniente per i relayer elaborare la transazione Bridge.

{% hint style="info" %}
**Nota:** I limiti esatti di minimo e massimo variano a seconda del token Bridge. Se l'importo della tua transazione è al di fuori dell'intervallo consentito, l'interfaccia mostrerà un messaggio di errore chiaro e ti chiederà di modificare l'importo.
{% endhint %}
