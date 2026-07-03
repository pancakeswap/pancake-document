# FAQ Monad

#### 1. Quali livelli di commissione sono disponibili nei pool di Liquidità di PancakeSwap?

**Livelli di Commissione Supportati:**

* I seguenti livelli di commissione sono disponibili per i pool V3 (Liquidità concentrata): `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Per i pool V2 sono supportati solo pool con commissione dello 0,25%

#### 2. Chiunque può creare un pool?

Sì. La creazione di pool è permissionless, con alcune eccezioni:

* Può esistere un solo pool per una determinata combinazione di **coppia di token + livello di commissione** (es. può esistere un solo pool WMON <> USDC allo 0,05% in un determinato momento)

#### 3. Quanto tempo ci vuole perché un pool appena creato appaia?

* I pool appaiono tipicamente nell'elenco circa **5 minuti** dopo la creazione.
* Se non appare:
  * Usa la **barra di ricerca** per trovarlo manualmente.
  * I pool possono essere filtrati dall'elenco a causa di un basso **TVL**.

#### 4. Perché l'APR o il TVL del mio pool mostra ancora zero?

Questo è normale subito dopo la creazione di un nuovo pool:

* I dati di APR e TVL si popoleranno solo dopo che **almeno uno Swap** è avvenuto nel pool.
* Dopo uno Swap, queste metriche inizieranno a visualizzarsi entro circa **15 minuti**.

#### **5. Perché le mie transazioni a volte falliscono se il mio portafoglio ha meno di 10 MON?**

Monad ha una regola secondo cui ogni account dovrebbe mantenere un **buffer di sicurezza minimo di 10 MON**. Se il tuo saldo è basso e invii troppe transazioni troppo rapidamente, la rete potrebbe **smettere di accettarne di nuove**.

#### **6. Perché le prime 1–2 transazioni funzionano, ma quelle successive falliscono?**

Monad elabora i blocchi usando una visione leggermente "in ritardo" del tuo saldo. Quindi:

* La tua **prima** transazione di solito va bene.
* Anche la **seconda** potrebbe passare.
* Ma se invii **più transazioni in un breve periodo**, la rete pensa che potresti non avere abbastanza MON per pagare tutte le commissioni di gas.

Quindi **blocca** la transazione successiva. Questo è normale e fa parte del sistema di sicurezza.

#### **7. Perché sembra più restrittivo sugli smart account (portafogli contrattuali)?**

Gli smart account seguono **regole più rigide**:

* Devono **sempre** mantenere almeno **10 MON** mentre eseguono codice contrattuale.
* Se il tuo smart account ha meno di 10 MON, la transazione può **revertirsi immediatamente**, anche se gli EOA funzionano ancora per un paio di transazioni.

Ecco perché gli utenti con smart account riscontrano i fallimenti prima.

#### **8. Significa che non posso usare Monad con meno di 10 MON?**

Puoi _ancora_ usarlo, specialmente con un normale EOA — ma:

* Non inviare più transazioni consecutive.
* Aspetta qualche blocco tra le transazioni.
* Mantieni un po' di MON nel tuo portafoglio per evitare problemi.

#### **9. Come evito questi fallimenti?**

Suggerimenti semplici:

* Mantieni **10 MON o più** nel tuo portafoglio se possibile.
* Se hai poco MON, **distribuisci le tue transazioni** nel tempo (non inviarle in modo massiccio).
* Gli utenti con smart account dovrebbero mantenere **un po' più di 10 MON**, poiché le chiamate contrattuali usano gas extra.
