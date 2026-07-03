# Hooks

{% hint style="info" %}
Se sei uno sviluppatore o stai cercando documentazione tecnica dettagliata per sviluppare un hook, visita [qui](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Gli hook sono potenti componenti aggiuntivi che permettono agli sviluppatori di estendere e personalizzare il comportamento dei pool di liquidità in PancakeSwap Infinity. Pensali come "plugin" o "widget" che aggiungono nuove funzionalità ai pool di liquidità.

#### 🔍 Cosa Sono gli Hook?

* Gli hook sono smart contract esterni creati da chiunque — sviluppatori, protocolli o membri della community — e associati ai pool di liquidità per migliorare o modificarne il comportamento.
* Ogni pool può avere un solo hook associato, ma un singolo hook può servire molti pool.
* Gli hook possono eseguire codice personalizzato prima o dopo azioni chiave come:
  * Inizializzazione di un pool
  * Swap
  * Aggiunta/rimozione di liquidità
  * Donazione<br>

**⛓️ Come Funzionano gli Hook:**

* Un hook viene selezionato durante la creazione del pool e non può essere modificato in seguito.
* Un contratto hook si attiva su azioni specifiche (Swap, aggiunta di liquidità, ecc.) ed esegue la logica prima o dopo tali azioni, come definito nel contratto.
* Ad esempio, un hook potrebbe:
  * Offrire sconti sulle commissioni di Swap ai detentori di CAKE
  * Applicare commissioni personalizzate e distribuire ricompense
  * Abilitare nuova logica di Swap come StableSwap o ordini in stile TWAMM<br>

#### ⚙️ Callback degli Hook

Gli hook possono essere attivati in dieci momenti specifici. Gli sviluppatori possono scegliere quali implementare:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Questi consentono di implementare comportamenti altamente personalizzabili e modulari tramite gli hook.

#### 🔧 Due Tipi di Hook

**Tipo 1: Nessuna Autorizzazione Richiesta**

Questi hook vengono eseguiti automaticamente e non richiedono l'autorizzazione dell'utente. Vengono attivati da azioni come Swap o variazioni di liquidità.



Esempi:

* Commissioni Dinamiche: Regola le commissioni di Swap in base alla volatilità del mercato
* Rimborsi delle Commissioni: Offri sconti agli utenti che detengono CAKE o che effettuano volumi elevati di trading



Flusso Esempio (Sconto Commissioni CAKE):

1. Un utente avvia uno Swap.
2. L'hook verifica il saldo di CAKE dell'utente tramite il callback `beforeSwap`.
3. Se l'utente detiene abbastanza CAKE secondo le soglie definite, ottiene uno sconto del 50% sulle commissioni del pool.
4. Il resto della transazione procede normalmente.<br>

{% hint style="success" %}
Questi hook non richiedono un'interfaccia speciale o interazioni aggiuntive. I vantaggi vengono applicati automaticamente.
{% endhint %}

**Tipo 2: Autorizzazione Utente Richiesta**

Questi hook richiedono che gli utenti interagiscano direttamente con essi, forniscano autorizzazione e potrebbe essere necessario trasferire fondi, spesso per creare o gestire posizioni.



Esempi:

* Ordini Limite: Esegui uno Swap solo quando viene raggiunto il prezzo target.
* TWAMM: Suddividi gli ordini grandi in pezzi più piccoli per un'esecuzione migliore.
* Gestione Attiva della Liquidità: Gestisci automaticamente le posizioni LP per rendimenti ottimali.



Flusso Esempio (Hook per Ordini Limite):

1. L'utente interagisce direttamente con il contratto hook (non tramite la normale interfaccia di Swap).
2. Inserisce i dettagli come prezzo limite, coppia di token, importo.
3. L'hook emette un token ricevuta che rappresenta l'ordine.
4. Successivamente, quando il prezzo del pool raggiunge il target, l'hook esegue l'ordine tramite afterSwap.
5. L'utente può restituire il token ricevuta per riscuotere gli asset scambiati.

{% hint style="info" %}
Questi hook spesso richiedono un'interfaccia personalizzata e gli utenti devono fidarsi e approvare il contratto hook per detenere i loro fondi.
{% endhint %}

#### 🚀 Casi d'Uso e Innovazione

Gli hook sbloccano possibilità illimitate, tra cui:

* AMM personalizzati (es. curve per stablecoin)
* Ricompense di liquidity mining
* Strategie di trading automatizzate, gestione della liquidità
* Ordini limite on-chain, altri tipi di ordini
* Prezzi dinamici e aggiustamenti delle commissioni
* Strategie LP che migliorano il rendimento<br>

Con gli hook, gli sviluppatori possono costruire un'esperienza DeFi completamente nuova utilizzando l'infrastruttura esistente di PancakeSwap Infinity — accelerando lo sviluppo e riducendo i costi.
