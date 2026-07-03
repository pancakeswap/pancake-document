# Agente di riferimento — Agente di liquidazione ordini/intenti

> Un agente Provider ERC-8183 che soddisfa un Job di swap-intent alla volta instralandolo tramite l'aggregazione PancakeSwap e consegnando il token target direttamente al Client.

### 0. Come si associa a ERC-8183

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) definisce un **Job** con tre ruoli e stati Open → Funded → Submitted → Terminal. L'**BNBAgent SDK** di BNB è l'implementazione attiva.

| Ruolo                                                     | In questo agente                                                                                                                  |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Client** (Agent-A)                                      | pubblica un intento di swap: "scambia X del token A → token B, consegnami ≥ `minOut`", mette in escrow l'input + una mancia      |
| **Provider** (Agent-B) — **questo è il nostro agente di riferimento** | quota tramite **aggregazione PancakeSwap** e, se può soddisfare/superare `minOut`, esegue lo swap e consegna il token B al Client |
| **Evaluator**                                             | verifica che il Client abbia ricevuto l'importo del token B ≥ `minOut`; rilascia la mancia (o rimborsa il Client)                 |

Il risultato è oggettivo ("il Client ha ricevuto ≥ `minOut`?"), il che è esattamente il motivo per cui questo si adatta a ERC-8183 mentre il ribilanciatore non si adattava.

***

### 1. Scopo e ambito sintetico

> Un agente **Provider** che soddisfa un Job di swap-intent alla volta instralandolo tramite l'aggregazione PancakeSwap e consegnando il token target direttamente al Client — e nient'altro.

***

### 2. Cosa l'agente è AUTORIZZATO a fare (allowlist delle capacità)

| # | Capacità                  | Superficie                                                  | Note                                                                       |
| - | ------------------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------- |
| A | Scoprire Job aperti       | BNBAgent SDK (registro ERC-8183)                            | Sola lettura; filtra verso Job di swap-intent che può servire              |
| B | Quotare un percorso       | **Aggregazione PancakeSwap** (Aggregator API / Smart Router) | Sola lettura; miglior prezzo su V3                                         |
| C | Accettare un Job          | BNBAgent SDK (Funded → committed)                           | Solo se la sua quota aggiornata ≥ `minOut` e la mancia ≥ soglia minima     |
| D | Eseguire lo swap          | Router PancakeSwap                                          | Input prelevato dall'escrow del Job; **destinatario dell'output = il Client**, in una transazione |
| E | Inviare il risultato      | BNBAgent SDK (→ Submitted)                                  | L'hash della transazione di liquidazione come prova                        |
| F | Riscuotere la mancia      | Escrow ERC-8183 / x402                                      | Solo dopo che l'Evaluator segna il Job come Terminal                       |

**L'output di ogni liquidazione va direttamente al Client. L'unico guadagno dell'agente è la mancia del Job.**

***

### 3. Guardrail rigidi (il requisito per essere inclusi)

| Guardrail                              | Regola                                                                                                                                                            |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Non accettare mai ciò che non puoi soddisfare** | Accetta un Job solo se una quota _aggiornata_ supera `minOut`. Se non può, lascia il Job Funded per un altro Provider.                                    |
| **Requotare all'esecuzione**           | Requota immediatamente prima di liquidare; annulla se il percorso non supera più `minOut` (nessuna quota obsoleta).                                               |
| **Liquidazione atomica**               | Prelievo-dall'escrow → swap → consegna al Client in **una transazione**, destinatario dell'output = Client. L'agente non deve mai detenere i fondi del Client attraverso un passaggio fallito. |
| **Slippage**                           | Slippage di esecuzione limitato; l'importo consegnato deve essere ancora ≥ `minOut` dopo lo slippage, altrimenti la transazione viene annullata. Mai `amountOutMin = 0`. |
| **Scadenza**                           | Scadenza breve sulla transazione di liquidazione (≤ 5 min); rispetta la scadenza del Job stesso.                                                                  |
| **Mancia minima / valore massimo**     | Non accettare Job con mancia sotto la soglia minima o sopra un limite di valore per Job.                                                                          |
| **Safelist dei token**                 | Serve solo Job i cui token sono nella lista token di PancakeSwap (anti-honeypot / token falsi).                                                                   |
| **Concorrenza singolo-Job (v1)**       | Soddisfa un Job alla volta; nessun over-commitment.                                                                                                               |
| **Precondizione gas**                  | Conferma che ci sia abbastanza BNB per l'intera liquidazione prima di accettare.                                                                                  |
| **Idempotente**                        | Non inviare mai due volte o ri-soddisfare un Job già Submitted/Terminal.                                                                                          |

Se una qualsiasi regola non può essere rispettata, **salta il Job** — non forzare mai una liquidazione.

***

### 4. Fuori ambito — l'agente NON DEVE

1. **Usare i fondi del Client per qualcosa di diverso dallo swap specificato.** Il destinatario dell'output è sempre il Client.
2. **Anticipare con il proprio inventario / assumere rischio di capitale.** v1 è **solo escrow-pull** — instrada l'input in escrow del Client; non esegue dall'proprio saldo.
3. **Instradare attraverso contratti non-PancakeSwap o non verificati**, o liquidare al di fuori dell'aggregazione PancakeSwap.
4. **Servire Job con token non in safelist**, o (v1) qualsiasi token scaled-UI / RWA (§5).
5. **Usare leva finanziaria, perp, margine o prestiti.**
6. **Inviare un risultato che non ha effettivamente soddisfatto** (nessuna attestazione falsa) o **valutare i propri Job** (conflitto di interessi).
7. **Chiamare qualsiasi funzione owner/admin** su PancakeSwap o sui contratti ERC-8183.
8. **Mantenere approvazioni di token permanenti** oltre una singola liquidazione; limita le approvazioni all'importo del Job.

***

### 5. Logica specifica di PancakeSwap (correttezza dell'applicazione)

* **Instrada tramite aggregazione PancakeSwap**, non un singolo pool — la migliore esecuzione su V2 / V3 / Stable è l'intera proposta di valore ("il miglior prezzo vince la mancia").
* **Consegna atomicamente al Client** impostando il `recipient` del router sull'indirizzo del Client; mai un processo in due fasi "swap verso sé stesso, poi trasferimento".
* **Freschezza della quota** — il prezzo on-chain si muove tra la scoperta e la liquidazione; requota all'esecuzione (guardrail §3).
* **`minOut` è in unità raw.** Per i **token scaled-UI / ERC-8056** (Binance Stock Tokens / equità RWA) raw ≠ visualizzato; una gestione errata consegna silenziosamente importi sbagliati. **Escludi i token scaled-UI da v1** finché l'ingegneria non conferma la gestione delle unità raw end-to-end.
* Il **minimo di slippage** sullo swap di liquidazione deve essere derivato in modo che l'importo _consegnato_ sia ≥ `minOut`, tenendo conto della divisione mancia/commissione.

***

### 6. Comportamento in caso di errore e recupero

* **La quota fallisce `minOut` all'esecuzione** → annulla prima/atomicamente con il prelievo dall'escrow; il Job rimane Funded per un altro Provider. Nessuno stato parziale.
* **Già Submitted/Terminal** → salta (idempotente).
* **La transazione di liquidazione viene annullata** → il Job rimane riscuotibile da altri; l'agente registra il fallimento e va avanti.
* **Fallimenti ripetuti su un Job** → metti in blacklist quel Job localmente e avvisa, invece di entrare in un ciclo di retry.

***

### 7. Punti di integrazione (la parte BNB / ERC-8183)

Questi sono forniti da BNB Agent Studio / BNBAgent SDK, non costruiti da PancakeSwap — ma la specifica dipende da essi:

* **Ciclo di vita del Job** (scopri Open → accetta Funded → Submitted → riscuoti) tramite BNBAgent SDK.
* **Identità del Provider** tramite ERC-8004.
* **Escrow + pagamento** tramite l'escrow ERC-8183 / x402.
* **Evaluator** — il predicato deve essere "il saldo del token B del Client è aumentato di ≥ `minOut`." Conferma con BNB **chi gestisce l'Evaluator** (neutrale/protocollo vs. Client) e che il predicato sia eseguibile on-chain.

***

### 8. Postura raccomandata v1 e decisioni aperte

1. **Solo escrow-pull, un Job alla volta, solo token-safelist, nessun token scaled-UI.** Superficie sicura minima da presentare al lancio.
2. **Conferma l'interfaccia di swap PancakeSwap** — l'**Aggregator (`aggr`) HTTP API** vs lo **Smart Router SDK**. La nota di Jerry dice "usa pcs aggr api"; è necessario confermare quale chiama l'agente, poiché cambia l'integrazione (e se la guida necessita di una sezione sull'aggregazione).
3. **Conferma il meccanismo di escrow** con BNB — il Provider può prelevare l'input in escrow del Client per instradare lo swap, e la consegna al Client è eseguibile come risultato?
4. **Conferma il proprietario dell'Evaluator e il predicato** (§7).

> Approvazione dell'ingegneria prima della presentazione: routing atomico escrow-pull → swap → consegna-al-Client; requota-all'esecuzione; matematica `minOut`-dopo-slippage; applicazione della safelist; gestione idempotente del Job.
