# Caratteristiche Principali

### 1️⃣ Singleton

In PancakeSwap v3, ogni pool di liquidità aveva il proprio contratto, il che rendeva più costosi la creazione di pool e lo Swap su più pool.

Infinity risolve questo problema implementando il modello Singleton. Ora tutti i pool vivono all'interno di un singolo contratto chiamato PoolManager. Questa modifica riduce i costi di gas per la creazione dei pool fino al 99% e rende gli Swap multi-hop (Swap che passano attraverso più pool) molto più economici evitando trasferimenti di token non necessari.

#### ⚙️ **Come funziona:**

* I dati di ogni pool sono archiviati in un contratto condiviso usando un ID pool univoco.
* Creare un nuovo pool è ora solo un aggiornamento di stato, non un deployment completo del contratto.
* Lo Swap tra pool è più veloce e utilizza meno gas.<br>

Questo approccio Singleton, insieme ad altre ottimizzazioni come Flash Accounting e ERC-6909, aiuta a rendere PancakeSwap Infinity una delle piattaforme DEX più efficienti in termini di gas disponibili oggi.

***

### ⚡️ Flash Accounting

Flash Accounting è una potente ottimizzazione in PancakeSwap Infinity che aiuta a ridurre le commissioni di gas durante transazioni complesse come gli Swap multi-hop e le variazioni di liquidità.

Nelle versioni precedenti (come v3), i token venivano spostati dentro e fuori da ogni pool durante ogni fase di una transazione. Questo comportava costi di gas elevati, specialmente per gli Swap multi-hop.

Con Flash Accounting, questo non è più necessario. Invece di spostare token dopo ogni fase, PancakeSwap Infinity tiene traccia internamente di tutti i movimenti di token ed effettua un unico trasferimento finale alla fine dell'intera transazione. Questo risparmia molto gas.

#### ⚙️ **Come Funziona:**

* Quando interagisci con Infinity (es. facendo Swap o aggiungendo liquidità), il sistema calcola il saldo netto dei token che devi o che ricevi.
* Questi saldi netti di token vengono archiviati temporaneamente usando Transient Storage, una nuova funzionalità introdotta con l'aggiornamento Cancun di Ethereum (EIP-1153).
* Transient Storage è più economico dello storage tradizionale perché dura solo per la durata della transazione — non è necessaria alcuna scrittura o lettura permanente.

***

### 🪙 Supporto Token Nativi

Con l'introduzione dell'architettura Singleton e di Flash Accounting, PancakeSwap Infinity supporta ora i token gas nativi (es. BNB, ETH) direttamente nei pool di liquidità — senza più la necessità di wrapping e unwrapping.

#### ✅ Punti Salienti

* **Pool di Token Nativi Diretti:** Ora puoi creare pool come ETH/USDC, BNB/CAKE senza bisogno di WETH o WBNB.
* **Efficiente in termini di Gas:** I trasferimenti di token nativi sono \~50% più economici dei trasferimenti di token ERC-20, comportando costi di gas inferiori per gli Swap e le operazioni di liquidità.<br>

**Precedentemente Rimosso, Ora Riabilitato:** Il supporto dei token nativi era assente nelle versioni precedenti a causa della complessità di implementazione e della frammentazione della liquidità.

***

### 📈 Curve di Prezzo Personalizzate

PancakeSwap Infinity offre agli sviluppatori il potere di creare modelli di prezzo personalizzati per i pool — andando oltre il modello tradizionale usato nella maggior parte degli AMM.

{% hint style="success" %}
**Gli sviluppatori possono costruire comportamenti di Swap e modelli di liquidità completamente nuovi, adattati a specifici tipi di asset o strategie di trading.**
{% endhint %}

#### 🔧 Cosa Sono le Curve di Prezzo Personalizzate?

Le curve di prezzo personalizzate consentono agli sviluppatori di:

* Bypassare la logica nativa del pool manager, creando pool con comportamenti di Swap definiti su misura.
* Modificare il modo in cui gli importi dei token vengono calcolati per gli Swap o le modifiche di liquidità.
* Incorporare meccaniche di commissione personalizzate, come:
  * Commissioni di ritiro della liquidità
  * Rimborsi o penali basati sulla strategia

Tutto ciò è reso possibile dai callback degli hook before / after swap, che possono intercettare e modificare i parametri di Swap dinamicamente.

#### 🛠 Esempi di Casi d'Uso

* **Curve StableSwap:** Progetta curve più piatte intorno a un rapporto di prezzo 1:1, riducendo l'impatto sul prezzo tra asset come USDC e USDT.
* **RWA:** Crea comportamenti personalizzati per diversi tipi di asset con offerta dinamica.
* **Commissioni a Livello di Hook:** Applica commissioni uniche diverse da quelle a livello di pool, come commissioni per sviluppatori.
* **Modelli di Rischio Personalizzati:** Adatta i prezzi per riflettere la volatilità, i dati degli oracle o metriche esterne.

{% hint style="info" %}
Nelle versioni AMM precedenti (es. PancakeSwap v2/v3), la logica di prezzo era hardcoded e rigida. L'architettura di PancakeSwap Infinity sblocca la capacità di costruire pool più efficienti in termini di capitale e personalizzati.
{% endhint %}

#### 🔍 Flessibilità per gli Sviluppatori

* Gli sviluppatori possono distribuire contratti hook personalizzati per sovrascrivere la logica di prezzo.
* I callback degli hook come beforeSwap e afterSwap consentono il pieno controllo su come i delta dei token vengono calcolati e applicati.

***

### 🧮 ERC-6909: Contabilità Multi-Token Efficiente

PancakeSwap Infinity adotta [ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), uno standard token leggero ed efficiente in termini di gas progettato per la contabilità interna di più token all'interno di un singolo contratto. Sostituisce molte operazioni ERC-20 tradizionali con primitive di mint e burn — portando a significativi risparmi di gas e flussi di transazione semplificati.

#### ⚙️ Come Funziona

Invece di spostare token dentro e fuori dal protocollo ad ogni interazione, i token ERC-6909 rappresentano saldi interni:

* Mint: Quando gli utenti depositano token o effettuano uno scambio, possono scegliere di ricevere token ERC-6909 come crediti.
* Burn: In seguito, invece di trasferire nuovamente token ERC-20, gli utenti possono semplicemente bruciare questi token ERC-6909 per regolare i saldi o finanziare nuove operazioni.

Questo modello riduce drasticamente la necessità di trasferimenti di token esterni, che tipicamente comportano costi di gas più elevati e interagiscono con logica di terze parti (es. i controlli di blacklisting di USDC).

#### 🪙 Vantaggi di ERC-6909

<table><thead><tr><th width="262.9921875">Funzionalità</th><th width="497.7421875">Vantaggio</th></tr></thead><tbody><tr><td>✅ Crediti di Saldo Interno</td><td>Non è necessario trasferire token ripetutamente tra utente e contratto</td></tr><tr><td>✅ Mint/Burn Efficiente in termini di Gas</td><td>Overhead costante indipendentemente dal token, nessuna chiamata a contratti esterni</td></tr><tr><td>✅ Più Semplice di ERC-1155</td><td>Dimensione del codice ridotta, nessun callback, nessun requisito di trasferimento in batch</td></tr><tr><td>✅ Supporto Multi-Token</td><td>Un singolo contratto può tracciare più tipi di token con saldi isolati</td></tr><tr><td>✅ Integrazione Fluida con PoolManager</td><td>Elimina approvazioni e trasferimenti ERC-20 ridondanti</td></tr></tbody></table>

#### 🚀 Casi d'Uso

* **Trader ad alta frequenza:** Evita trasferimenti ad alto costo di gas e interagisci direttamente usando saldi interni.
* **Gestori di liquidità:** Apri e chiudi posizioni in modo più efficiente senza movimenti eccessivi di token.

#### 💡 Note Importanti

* Gli utenti optano per il flusso ERC-6909 quando non hanno bisogno di regolare immediatamente i trasferimenti di token.
* I saldi interni possono essere consolidati e regolati in modo netto in seguito, offrendo agli utenti avanzati maggiore controllo e flessibilità.

***

### 💸 Metodo Donate

Il metodo `donate()` consente agli utenti di incentivare direttamente i fornitori di liquidità nell'intervallo attivo all'interno di un pool donando token. Questo metodo si basa sul sistema di contabilità delle commissioni del pool per facilitare i pagamenti, garantendo che siano supportati solo i token del pool.

#### 🔹 Caratteristiche Principali:

* **Pagamenti Diretti agli LP:** Le donazioni vengono effettuate direttamente ai fornitori di liquidità, premiando coloro che mantengono la liquidità nell'intervallo attivo del pool.
* **Supporta Solo i Token del Pool:** Il metodo `donate()` supporta solo le donazioni nei token del pool, poiché sfrutta il sistema di contabilità delle commissioni per garantire una corretta distribuzione.
* **Aperto a Tutti gli Utenti:** Qualsiasi utente può chiamare il metodo `donate()`, consentendo a chiunque di incentivare la fornitura attiva di liquidità.

Sebbene il metodo `donate()` sia uno strumento potente per incentivare gli LP, i donatori devono essere consapevoli che le loro donazioni potrebbero subire frontrunning da parte di altri utenti. Ciò può verificarsi quando un utente aggiunge rapidamente liquidità al pool subito prima che venga effettuata una donazione, ricevendo una parte dei fondi donati.

Per prevenire il frontrunning, i donatori potrebbero dover considerare strategie aggiuntive nella progettazione dei loro meccanismi di donazione, come:

* Assicurarsi che le donazioni avvengano in modo da minimizzare la possibilità di frontrunning opportunistico.
* Aggiungere ritardi temporali o condizioni specifiche (usando i callback before / after donate degli hook) che garantiscano che le donazioni non vengano sfruttate in questo modo.
