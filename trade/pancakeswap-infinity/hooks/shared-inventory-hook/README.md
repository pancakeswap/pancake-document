# Shared Inventory Hook

Lo Shared Inventory Hook (SIH) ufficiale di PancakeSwap è progettato per consentire a un unico pool di capitale di fare market-making su ogni pool che condivide i suoi token, invece di bloccare liquidità separata in ciascuno. Offre ai trader quotazioni più profonde e un price impact inferiore, permettendo ai fornitori di liquidità di impiegare meno capitale a parità di copertura.

Sviluppato dal core team di PancakeSwap, questo hook è pensato per gli emittenti di asset e i market maker che vogliono quotare più coppie on-chain senza frammentare il proprio inventario.

#### 🔍 Perché Shared Inventory?

Fornire liquidità a più coppie nel modo convenzionale significa bloccare capitale dedicato in pool separati, per lo più inattivo tra uno scambio e l'altro. SIH invece mantiene un solo saldo per token e lo inietta come liquidità solo quando uno swap ne ha bisogno, così lo stesso capitale può sostenere ogni pool che condivide quel token.

#### 📊 In cosa è diverso dagli altri modelli?

La liquidità concentrata convenzionale richiede di impegnare l'intero capitale in un singolo pool. Altri approcci cross-pool, come i layer di regolamento a saldo virtuale, in genere si trovano al di fuori dell'AMM stesso, dove la liquidità potrebbe non essere visibile come profondità di pool on-chain né instradata direttamente dagli aggregator.

La liquidità di SIH entra ed esce dal pool PancakeSwap Infinity CLAMM tramite l'hook a ogni swap, quindi appare come vera profondità di pool che i router possono vedere e con cui possono eseguire gli ordini.

#### ⚙️ Come funziona

* **Iniezione just-in-time (JIT)**\
  Prima di ogni swap, l'hook crea (mint) nel pool una posizione di liquidità concentrata configurata; dopo l'esecuzione dello swap, la brucia (burn) e regola il risultato netto. La posizione esiste solo per la durata di un singolo swap, quindi il saldo è libero di servire subito il pool successivo che ne ha bisogno.
* **Un saldo, molti pool**\
  L'inventario è il saldo di token dell'hook stesso, non c'è alcun deposito per singolo pool. Qualsiasi token che debba essere usato in più di un pool viene condiviso tra tutti.

{% hint style="success" %}
Questo separa la profondità quotata da un pool dal capitale che il pool detiene direttamente: un hook finanziato può quotare liquidità profonda e stretta su un numero di pool che condividono un token.
{% endhint %}

* **Hook configurabile**\
  Per ogni pool che serve, l'hook mantiene una configurazione indipendente e regolabile per intervallo di prezzo e profondità. Spostare la banda richiede solo un aggiornamento della configurazione, rendendo semplice ricentrare le quotazioni attorno a un prezzo di riferimento in movimento.

#### 📌 Punti chiave

* Un unico saldo di token condiviso sostiene ogni pool che usa quel token. Aggiungere un nuovo pool non richiede nuovo capitale.
* Completamente on-chain e componibile: la liquidità di SIH è vera profondità di pool, instradabile sia da PancakeSwap sia da aggregator di terze parti.
* I trader ottengono quotazioni più profonde e un price impact inferiore sulle dimensioni; gli operatori guadagnano le stesse commissioni di trading con una frazione del capitale convenzionale.
