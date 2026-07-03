# FAQ Solana

### Pool V3 – Domande Frequenti (FAQ)

#### 1. Quali livelli di commissione sono disponibili?

**Livelli di Commissione Supportati:**\
I seguenti livelli di commissione sono disponibili per i pool V3 (Liquidità concentrata):

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Distribuzione delle Commissioni (si applica a tutti i livelli):**

* 84% ai fornitori di Liquidità (LP)
* 16% al protocollo
  * 8% viene bruciato
  * 8% va al treasury del protocollo

#### 2. Chiunque può creare un pool?

Sì. La creazione di pool è permissionless, con alcune eccezioni:

* Può esistere un solo pool per una determinata combinazione di **coppia di token + livello di commissione** (es. può esistere un solo pool SOL<> USDC allo 0,1% in un determinato momento)
* Al momento sono supportati solo **token SPL** e token **Token-2022** selezionati.

#### 3. Quanto tempo ci vuole perché un pool appena creato appaia?

* I pool appaiono tipicamente nell'elenco circa **5 minuti** dopo la creazione.
* Se non appare:
  * Usa la **barra di ricerca** per trovarlo manualmente.
  * I pool possono essere filtrati dall'elenco a causa di un basso **TVL**.

#### 4. Perché l'APR o il TVL del mio pool mostra ancora zero?

Questo è normale subito dopo la creazione di un nuovo pool:

* I dati di APR e TVL si popoleranno solo dopo che **almeno uno Swap** è avvenuto nel pool.
* Dopo uno Swap, queste metriche inizieranno a visualizzarsi entro circa **15 minuti**.

#### 5. Come aggiungo un token personalizzato per creare un pool?

Per aggiungere un nuovo token:

* Nell'interfaccia di creazione del pool, apri il selettore di token.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Incolla l'indirizzo del token nella barra di ricerca.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* Clicca su **"Aggiungi Token"**.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* Il token sarà ora ricercabile nell'elenco.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* Per gestire i token:
  * Clicca su **"Visualizza Elenco Token"**.
  *   Attiva o disattiva diversi elenchi, incluso l'**Elenco Token Aggiunti dall'Utente**, che include i token aggiunti manualmente.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Perché la mia prima transazione su Solana sembra più costosa?

Solana usa gli **Associated Token Account (ATA)** per gestire i saldi dei token per ogni portafoglio. Quando interagisci con un token per la prima volta, il tuo portafoglio deve creare un ATA, che comporta un costo iniziale una tantum (pagato in SOL).

* Questo costo di creazione dell'ATA è richiesto dal protocollo Solana e non è specifico di PancakeSwap.
* Se l'ATA viene successivamente chiuso, il **SOL originale utilizzato può essere rimborsato** al tuo portafoglio.
