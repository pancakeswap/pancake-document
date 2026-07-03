# Infinity StableSwap

### Panoramica

Infinity StableSwap è un tipo di pool all'interno di [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) ottimizzato per lo Swap di asset che dovrebbero essere scambiati a un prezzo simile — come le stablecoin (ad es. USDC/USDT) o gli asset con peg ravvicinati (ad es. coppie di token wrapped, token di Staking liquido e token di restaking liquido).

È alimentato da un hook StableSwap che gira sull'architettura Infinity, ispirato al design StableSwap NG di Curve. È attualmente disponibile su BNB Chain, con piani per espandersi ad altre chain in futuro.

***

### Come Funziona

Infinity StableSwap utilizza una curva invariante stabile — un ibrido tra somma costante e prodotto costante:

* Vicino al peg → la curva si comporta come una curva a somma costante, risultando in uno Slippage molto basso per i trade attorno a 1:1.
* Lontano dal peg → la curva transisce gradualmente verso il prodotto costante, il che aiuta a ripristinare l'equilibrio e protegge il pool durante grandi squilibri o eventi di depeg.

Questo lo rende particolarmente efficace per le coppie stabili in cui i prezzi stretti e lo Slippage basso sono più importanti.

***

### Caratteristiche Principali

Ottimizzato per gli Swap vicino al peg: Slippage basso per i trade tra asset che si prevede vengano scambiati approssimativamente allo stesso prezzo.

Fornitura di Liquidità semplice: I fornitori di Liquidità (LP) depositano entrambi i token proporzionalmente senza dover selezionare o gestire range di prezzi — a differenza dei pool CLAMM.

Token LP ERC-20: La tua posizione LP è rappresentata come token ERC-20 standard, rendendolo facile da utilizzare con programmi di yield, campagne di punti e altri protocolli DeFi.

Commissioni dinamiche: Le commissioni possono adeguarsi in base alle condizioni di equilibrio del pool, premiando i trade che aiutano a ripristinare il pool verso l'equilibrio e scoraggiando quelli che peggiorano lo squilibrio.

Supporto al routing Infinity: I trade vengono instradati automaticamente attraverso i pool StableSwap quando offrono il prezzo migliore — nessun passaggio aggiuntivo richiesto per i trader.

Parametro di Amplificazione (A) regolabile: Gli operatori del pool possono aumentare o diminuire gradualmente il parametro A nel tempo per adattarsi alle mutevoli condizioni di mercato, con salvaguardie per evitare cambiamenti bruschi.

***

### Parametri del Pool

Il comportamento del pool StableSwap è governato da un piccolo insieme di parametri, tipicamente impostati al momento della creazione del pool.

#### Coefficiente di Amplificazione (A)

Il parametro A controlla quanto strettamente il pool segue il peg di prezzo 1:1.

| Valore A   | Effetto                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------- |
| A più alto | Curva più stretta attorno al peg; Slippage inferiore vicino a 1:1; più sensibile allo squilibrio |
| A più basso | Curva più larga; si comporta più come un pool standard a prodotto costante               |

Regola generale: Usa un A più alto per asset con un peg forte e affidabile (ad es. USDC/USDT). Usa un A più basso per asset con peg più ampi o volatili (ad es. alcune coppie LST).

Il parametro A può essere aumentato o diminuito gradualmente dall'operatore del pool in un periodo di tempo definito. Le modifiche vengono applicate gradualmente con salvaguardie per evitare manipolazioni o improvvisi spostamenti di prezzo.

#### Moltiplicatore di Commissione Off-Peg

Un parametro aggiuntivo che regola le commissioni effettive quando il pool si allontana dall'equilibrio. Aiuta a scoraggiare i trade che squilibrerebbero ulteriormente il pool e rende il pool più robusto durante lo stress di mercato o gli eventi di depeg.

#### Commissioni Dinamiche

Una commissione addebitata su ogni Swap, pagata ai fornitori di Liquidità. Infinity StableSwap supporta commissioni dinamiche — ovvero la commissione effettiva su un dato trade può variare a seconda dello stato corrente del pool (ad es. se il trade migliora o peggiora l'equilibrio).

***

### Infinity StableSwap vs. Classic StableSwap

Se hai già utilizzato lo StableSwap esistente di PancakeSwap, ecco cosa cambia — e cosa rimane uguale.

| <p><br></p>                       | Classic StableSwap                                              | Infinity StableSwap                                                             |
| --------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Curva di prezzo                   | Invariante stabile (ibrido somma costante / prodotto costante)  | Stessa curva invariante stabile, stesso Slippage basso vicino al peg            |
| Token LP ERC-20                   | ✅ Sì                                                            | ✅ Sì                                                                            |
| Creazione del pool                | Pesante sul lato operativo; richiede configurazione manuale dal team | Permissionless — chiunque può creare un pool                               |
| Commissioni di Swap               | Fisse per coppia (ad es. 0,01% per USDC/USDT)                  | Commissioni dinamiche — si adeguano in base all'effetto del trade sull'equilibrio del pool |
| Parametro di Amplificazione (A)   | Statico — impostato una volta, non può essere modificato        | Regolabile — può essere aumentato o diminuito gradualmente nel tempo            |
| Moltiplicatore di commissione off-peg | ❌ Non supportato                                           | ✅ Supportato — aiuta a proteggere il pool durante gli eventi di depeg           |
| Efficienza gas                    | Standard                                                        | Migliorata — beneficia del Singleton e del Flash Accounting di Infinity         |

#### Cosa rimane uguale

* La curva di prezzo principale e il comportamento a basso Slippage vicino al peg rimangono invariati.

#### Cosa c'è di nuovo e di meglio

* Creazione Permissionless del Pool: I pool possono essere creati in modo permissionless senza richiedere la configurazione manuale del team.
* Le commissioni dinamiche proteggono gli LP: Invece di una singola commissione fissa, la commissione può adeguarsi per trade in base al fatto che il trade aiuti o danneggi l'equilibrio del pool — rendendo il pool più resiliente durante le condizioni volatili.
* Parametro A adattabile: Il coefficiente di amplificazione può essere regolato nel tempo al cambiare delle condizioni di mercato, invece di essere bloccato per sempre al momento del deployment.

***

### Domande Frequenti

Quali asset sono adatti a Infinity StableSwap?

Asset che si prevede vengano scambiati a un prezzo simile: stablecoin (USDC, USDT, BUSD, ecc.), equivalenti wrapped dello stesso asset (ad es. WBTC/cbBTC), e select token di Staking liquido / token di restaking liquido (coppie LST/LRT) dove la volatilità del peg è bassa.

<br>

In cosa differisce Infinity StableSwap dal vecchio StableSwap di PancakeSwap?

Infinity StableSwap è implementato come un hook su PancakeSwap Infinity, il che significa che eredita tutti i benefici infrastrutturali di Infinity, inclusi costi gas inferiori tramite Singleton e Flash Accounting, e un sistema di commissioni più flessibile. Supporta anche nuove funzionalità come commissioni dinamiche e amplificazione regolabile che il precedente StableSwap non offriva.

<br>

Devo gestire la mia posizione nel tempo?

No. A differenza di CLAMM, non devi impostare o regolare range di prezzi. La tua Liquidità è sempre attiva sull'intera curva, quindi non c'è rischio che la tua posizione vada "fuori range".

<br>

Posso fornire Liquidità con un solo token?

Sì, i depositi con un singolo token sono supportati.

<br>

Come funzionano le commissioni dinamiche?

In Infinity StableSwap, la commissione di Swap può variare per trade in base all'effetto del trade sull'equilibrio del pool. I trade che aiutano a riportare il pool verso l'equilibrio possono pagare commissioni effettive inferiori, mentre i trade che peggiorano lo squilibrio possono pagare commissioni più alte. Questo è progettato per proteggere gli LP e mantenere condizioni di pool più sane.



***



## Creare un Pool Infinity StableSwap



I pool Infinity StableSwap sono permissionless — chiunque può crearne uno senza richiedere l'approvazione del team di PancakeSwap.

<br>

### Passo per Passo

1\. Vai alla pagina Farm/Liquidità e clicca su Crea Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Seleziona Pool StableSwap dalle opzioni di tipo di pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Seleziona la coppia di token per il tuo pool (ad es. USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Parametri del Pool

| Parametro                      | Cosa fa                                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| Commissione di Swap            | Commissione addebitata su ogni Swap, pagata agli LP. Il valore predefinito è 0,01% per coppie stabili strette.      |
| A (Amplificazione)             | Controlla quanto strettamente la curva segue il peg. Più alto = Slippage inferiore vicino a 1:1, ma più sensibile allo squilibrio. |
| Moltiplicatore Commissione Off-Peg | Scala le commissioni quando il pool si allontana dall'equilibrio, scoraggiando i trade che peggiorano lo squilibrio. |
| Tempo di Media Mobile          | Finestra temporale utilizzata per calcolare il prezzo medio mobile per le regolazioni delle commissioni dinamiche.  |

⚠️ Imposta i parametri con attenzione. Parametri errati — specialmente un A molto alto su un asset con peg poco stretto — possono aumentare il rischio per gli LP. In caso di dubbi, usa il preset per il tuo tipo di asset ed evita di modificare le impostazioni Avanzate.

<br>

Scegli un Preset dei Parametri del Pool — questo imposta automaticamente i parametri consigliati per il tuo tipo di asset. Puoi comunque regolarli manualmente tramite il toggle Avanzato.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                                | A    | Moltiplicatore Commissione Off-Peg | Tempo di Media Mobile (secondi) |
| ------------------------------------- | ---- | ---------------------------------- | -------------------------------- |
| Stablecoin Riscattabili in Fiat       | 1000 | 10                                 | 600                              |
| Stablecoin Collateralizzate in Crypto | 100  | 12,5                               | 600                              |
| Token di Restaking Liquido            | 500  | 10                                 | 600                              |

<br>

&#x20; Non sai quale scegliere?

* Usa Stablecoin Riscattabili in Fiat per coppie come USDC/USDT
* Usa Stablecoin Collateralizzate in Crypto per stablecoin algo o supportate da crypto
* Usa Token di Restaking Liquido per coppie LRT come stkBNB/WBNB.

<br>

5\. Inserisci l'importo del deposito per fornire la Liquidità iniziale. Entrambi gli importi dei token devono essere uguali (ad es. 1 USDC e 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Clicca su Anteprima Pool, controlla le tue impostazioni, seleziona la casella di conferma, quindi clicca su Crea Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
