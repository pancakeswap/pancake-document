# Hook a Commissione Dinamica

L'Hook a Commissione Dinamica ufficiale di PancakeSwap è progettato per creare uno scambio di valore più equo tra i Fornitori di Liquidità e i Trader. Protegge gli LP da perdite impermanenti (IL) eccessive mantenendo al contempo un mercato efficiente per i trader.

Costruito dal team principale di PancakeSwap, questo hook è studiato specificamente per offrire un'alternativa intelligente e adattiva ai tradizionali modelli a commissione fissa.

#### 🔍 Perché le Commissioni Dinamiche?

Le grandi operazioni di arbitraggio causano una maggiore divergenza dei prezzi nei pool, aumentando l'IL per gli LP. Il nostro modello a commissione dinamica applica commissioni proporzionalmente più elevate sulle operazioni di arbitraggio più grandi per compensare questo rischio — lasciando comunque abbastanza margine per gli arbitraggisti di guadagnare e mantenere i prezzi allineati.

#### 📊 In Cosa si Differenzia dagli Altri Modelli?

Altri modelli in passato hanno utilizzato dati storici per stimare la volatilità e altri fattori per regolare le commissioni. Tuttavia:

* I dati storici sono un indicatore ritardato e potrebbero non prevedere accuratamente la volatilità futura.
* Gli eventi di mercato esterni (come cambiamenti normativi o variazioni economiche) possono rendere inaffidabili le tendenze passate.
* I modelli complessi con molti parametri rischiano l'overfitting — performano bene sui dati passati ma male su condizioni nuove e inedite.

Il nostro approccio è più semplice, adattivo e basato sul comportamento di trading in tempo reale.

#### ⚙️ Come Funziona

* **Non prevediamo la volatilità o altri fattori macro**\
  Il nostro modello trae invece vantaggio intrinsecamente dal comportamento degli arbitraggisti in diversi regimi di mercato:
  * **Alta volatilità:** Più operazioni di arbitraggio di dimensioni maggiori → Commissioni più alte per gli LP, che coprono una quota maggiore dell'IL.
  * **Bassa volatilità:** Operazioni meno frequenti e più piccole → L'IL è naturalmente più bassa, ma gli LP guadagnano comunque commissioni più alte rispetto a un modello a commissione fissa.
* **Il nostro modello utilizza**
  * Un prezzo del pool con peso esponenziale per rilevare le operazioni di arbitraggio.
  * Una curva di commissione esponenziale basata sull'impatto sul prezzo di ogni Swap.
  * Un limite massimo di commissione del 5% per mantenere l'equità per i trader.

{% hint style="success" %}
Questo garantisce che le commissioni scalino dinamicamente con l'impatto del trade adattandosi automaticamente alle mutevoli condizioni di mercato.
{% endhint %}

* **Incentivi Bilanciati**\
  Gli arbitraggisti mantengono ancora circa il 50% dei loro profitti dopo le commissioni dinamiche, assicurando che siano motivati a mantenere i prezzi del pool in linea con il mercato.

#### 📌 Punti Chiave

* Nessuna dipendenza da previsioni di volatilità o altri fattori macro.
* Si adatta automaticamente alla volatilità del mercato in base al comportamento di trading effettivo.
* Protegge gli LP dall'IL su base per-Swap.
* Mantiene forti incentivi per gli arbitraggisti a colmare i divari di prezzo.
* Avvantaggia i trader con liquidità più profonda e commissioni base più basse.
