# FAQ Solana Farming

### 1. Come funziona il Farming SOL?

* Il Farming V3 è **basato su campagne**, il che significa che i Farm sono attivi solo per una durata prestabilita.
* Durante la campagna:
  * I token ricompensa vengono distribuiti **ogni secondo** alle **posizioni di Liquidità attive**.
  * L'APR del farming verrà mostrato nella pagina della lista Pool e nella pagina Le mie posizioni
* Dopo la fine della campagna:
  1. **Non verranno distribuite altre ricompense**.
  2. **L'APR del farming non verrà più mostrato** nella pagina della lista Pool e nella pagina Le mie posizioni
  3. Il Farm diventa **inattivo**, ma può essere riavviato dal creatore aggiungendo altre ricompense.

### 2. Devo mettere in Staking il mio LP NFT per guadagnare ricompense di farming?

* **Non è richiesto alcuno Staking**.
* Finché la tua posizione di Liquidità è **attiva (in range)** in un Pool con un Farm attivo, guadagnerai ricompense automaticamente.

### 3. Esistono potenziatori del Farm?

* **No**, i Farm V3 **non** supportano alcun meccanismo di potenziamento.
* Le ricompense si basano esclusivamente sulla tua quota di Liquidità attiva nel Pool.

### 4. Possono essere creati più Farm per lo stesso Pool?

* **No**, può esistere solo **un Farm per pair di token e livello di commissione**.

### 5. Come vengono configurati i Farm SOL?

#### A. Token ricompensa

* È possibile assegnare fino a **3 diversi token ricompensa** per Farm.
* Una volta impostati, i tipi di token ricompensa **non possono essere modificati**.
* Il creatore del Farm può:
  * **Aggiungere** i token ricompensa allocati.
  * **Estendere la durata del farming** dopo la fine della campagna.

#### B. Durata della campagna

* Le campagne devono durare un minimo di **7 giorni** e un massimo di **90 giorni**.

### 6. Un Farm può essere modificato dopo la creazione?

I creatori del Farm possono modificare i seguenti parametri **dopo la creazione del Farm**:

1. Tasso di distribuzione delle ricompense (al secondo)
2. Data di fine campagna
3. Aggiungere un token ricompensa e il corrispondente importo di ricompensa (solo se inizialmente sono stati assegnati meno di 3 token)
