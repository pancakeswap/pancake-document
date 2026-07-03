# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

Il CLAMM consente ai fornitori di liquidità di allocare il proprio capitale all'interno di **intervalli di prezzo specifici**. Questo porta a:

* **Maggiore efficienza del capitale**: Più liquidità ai prezzi di trading attivi.
* **Liquidità più profonda**: Migliore esecuzione per i trader.
* **Gestione attiva degli LP**: Gli LP devono adeguare le posizioni al movimento dei prezzi.
* **Maggiore potenziale di perdita impermanente** per le posizioni fuori intervallo.

{% hint style="info" %}
CLAMM opera sulla formula del prodotto costante (X \* Y = K). Ogni posizione di liquidità è non-fungibile e rappresentata come un NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM o "Bin Pool")

LBAMM implementa **bin di prezzo discreti**, ognuno dei quali detiene liquidità a un livello di prezzo specifico. LBAMM segue la **formula della somma costante (X + Y = K).**



**Caratteristiche principali:**

* Scambi con **impatto sul prezzo pari a 0** all'interno di un bin.
* **Liquidità fungibile** (la liquidità all'interno di ogni bin è un token ERC-20).
* **Costi di gas inferiori** per la modifica delle posizioni LP.
* **Supporto per diverse forme di liquidità** (es. asimmetrica, uniforme).
* Più adatto a coppie a **bassa volatilità** per via della curva di prezzo piatta per bin.

> 🥞 **PancakeSwap è il primo protocollo a offrire pool LBAMM con hook.**

{% hint style="success" %}
Sia i pool CLAMM che LBAMM supportano gli **hook**, che consentono agli sviluppatori di personalizzare il comportamento del pool. I tipi di pool sono estendibili tramite nuovi Pool Manager, che possono essere aggiunti senza la ridistribuzione del protocollo.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Funzionalità</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Curva di Prezzo</strong></td><td>Prodotto Costante (X * Y = K)</td><td>Somma Costante (X + Y = K)</td></tr><tr><td><strong>Token di Liquidità</strong></td><td>Non-fungibile (NFT)</td><td>Fungibile (ERC-20 per bin)</td></tr><tr><td><strong>Ideale Per</strong></td><td>Coppie sia ad alta che a bassa volatilità</td><td>Coppie a bassa volatilità</td></tr><tr><td><strong>Vantaggi</strong></td><td><ol><li>Efficienza del capitale</li><li>Efficiente in termini di gas su ampio/intero intervallo</li><li>Ampiamente adottato</li></ol></td><td><ol><li>Impatto sul prezzo 0 all'interno del bin</li><li>Gestione LP più economica</li><li>Forme di liquidità flessibili</li></ol></td></tr><tr><td><strong>Supporto Hook</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Commissioni

PancakeSwap Infinity supporta un sistema di commissioni flessibile ed estensibile tramite impostazioni di commissione Statica e Dinamica. Questa configurazione offre sia ai creatori di pool che agli LP potenti strumenti per ottimizzare diverse strategie di trading e profili di rischio.

#### 🔁 Commissioni Dinamiche

* Le Commissioni Dinamiche vengono determinate in tempo reale tramite contratti hook.
* Queste commissioni possono fluttuare in base a fattori esterni come volatilità, volume di trading, stato dell'utente (es. possesso di CAKE) o qualsiasi logica personalizzata codificata nell'hook.
* I pool con commissioni dinamiche devono abilitare l'impostazione al momento della creazione del pool e associare un hook in grado di modificare le commissioni tramite `beforeSwap`.
* Una volta inizializzato un pool, il tipo di commissione (dinamica o statica) è immutabile.

Le commissioni dinamiche offrono la massima flessibilità e ottimizzano le strutture delle commissioni sia per gli LP che per gli swapper in base alle condizioni di mercato.

#### 📌 Commissioni Statiche

* I pool a Commissione Statica hanno una commissione fissa impostata durante la creazione del pool.
* Queste commissioni non possono essere modificate dopo l'inizializzazione del pool.
* Adatte per casi d'uso più semplici o dove è importante la prevedibilità della struttura delle commissioni.<br>

**🔒 Limiti Massimi delle Commissioni:**

* Pool CLAMM: Fino al 100% (principalmente per casi d'uso specializzati o sperimentali)
* Pool LBAMM: Limitato al 10%<br>

**🏛 Commissione del Protocollo (per pool a commissione statica):**

* PancakeSwap applica una commissione di protocollo sui pool Infinity
* 33% della commissione LP, con un massimo dello 0,4%

| **Commissione LP** | **Commissione Protocollo** |
| ------------------ | -------------------------- |
| 1%                 | 0,33%                      |
| 2%                 | 0,4% (limite massimo)      |
| Pool a Commissione Dinamica | 0%              |

#### 🛠️ Note di Configurazione per i Creatori di Pool

* Quando si inizializza un pool tramite PoolManager, il creatore deve scegliere:
  * Se il pool usa una commissione statica o dinamica
  * Se un contratto hook è associato (richiesto per le commissioni dinamiche)

Queste impostazioni sono permanenti e definiscono il comportamento del pool per tutta la sua durata.
