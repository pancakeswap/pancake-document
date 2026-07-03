# Farm

Il farming su PancakeSwap Infinity è un modo semplice ed efficiente in termini di gas per guadagnare ricompense di liquidità senza dover mettere in Staking i propri LP Token. Una volta aggiunta liquidità a un pool idoneo, le ricompense iniziano ad accumularsi automaticamente.

#### ⚙️ Come Funziona

Ecco una rapida panoramica di come il sistema traccia e distribuisce le ricompense:<br>

**✅ Nessuno Staking Richiesto**

* Tieni semplicemente la tua posizione LP nel tuo portafoglio.
* Non è necessario bloccare i tuoi asset o interagire con smart contract aggiuntivi.
* Inizi a guadagnare ricompense automaticamente quando aggiungi liquidità.

#### 📈 Distribuzione delle Ricompense

* Solo le posizioni nell'intervallo attivo (quelle che forniscono liquidità attiva) ricevono ricompense.
* Le ricompense sono proporzionali alle commissioni guadagnate dalla tua posizione durante ogni periodo, chiamato epoch.

#### ⏳ Cos'è un Epoch?

* Un epoch è una finestra temporale fissa — attualmente impostata a 8 ore.
* Le ricompense vengono calcolate e distribuite dopo ogni epoch.
* Gli epoch sono attualmente programmati alle 00:00, 08:00 e 16:00 UTC.

***

#### 🔄 Processo di Farming e Riscossione

1. **Tracciamento delle Posizioni:** Il sistema backend monitora le tue posizioni LP su tutte le Farm.
2. **Calcolo delle Ricompense:** Alla fine di ogni epoch,
   1. Il sistema calcola le tue ricompense in base alla tua liquidità e alle commissioni generate.
   2. Elabora le ricompense in un albero di Merkle e invia una radice di Merkle a uno smart contract.
3. **Periodo di Contestazione:**
   1. Dopo la pubblicazione della radice di Merkle, inizia il periodo di contestazione di 1 ora.
   2. Durante il periodo di contestazione:
      1. Le ricompense appena calcolate non possono essere riscosso.
      2. Le ricompense degli epoch precedenti rimangono disponibili per la riscossione.
      3. Strumenti di verifica automatici e gestiti dalla community controllano l'accuratezza dei dati pubblicati. Se vengono rilevate discrepanze, può essere sollevata una contestazione per prevenire distribuzioni errate.
4. **Riscossione delle Ricompense:**
   1. Una volta terminato il periodo di contestazione, puoi riscuotere le tue ricompense per l'ultimo epoch.
   2. Tutte le ricompense in sospeso su tutte le Farm possono essere riscuote in un'unica transazione efficiente in termini di gas.
5. **Le Ricompense Non Riscuote si Accumulano:**
   1. Qualsiasi ricompensa non riscossa si accumula agli epoch successivi. Ogni aggiornamento incorpora le ricompense precedenti, garantendo che nessun guadagno vada perso o scada.

{% hint style="info" %}
Intervalli di liquidità più ristretti portano generalmente a guadagni più elevati, ma aumentano la probabilità che una posizione esca dall'intervallo e diventi non idonea alle ricompense.
{% endhint %}

#### 🌱 Riepilogo

✅ Nessuno Staking\
✅ Riscossione efficiente in termini di gas\
✅ Aggiornamenti regolari delle ricompense\
✅ Processo di contestazione equo e trasparente\
✅ Le ricompense si accumulano finché non sei pronto a riscuoterle
