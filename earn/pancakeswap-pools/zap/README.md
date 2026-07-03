---
description: Aggiunta di liquidità in un solo clic
---

# Zap

### Cos'è Zap <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap è una funzione che ti permette di aggiungere liquidità con facilità. Con Zap, puoi fornire liquidità con qualsiasi token che hai in portafoglio, indipendentemente dai token richiesti nella pool. Imposta semplicemente la fascia di prezzo, scegli l'importo da fornire ed esegui. I tuoi token verranno bilanciati automaticamente per formare la posizione di liquidità, mentre vengono scambiati nel modo più efficiente, con il minore impatto sul prezzo e Slippage.

### Chain Supportate

* v3 - Tutte le pool su BNB Chain, pool selezionate su Ethereum e Arbitrum
* Infinity - Tutte le pool CLAMM (senza hook) su BNB Chain

### Come Usarlo <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Per ora, Zap supporta:

* 🆕 Qualsiasi token!
* Utilizzo di un singolo token
* 🆕 Utilizzo di due token
* 🆕 Oppure... utilizzo di più token (sì, può essere usato come raccoglitore di dust)

#### Iniziare <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Per usare Zap, vai semplicemente alla pagina Add Liquidity, seleziona la coppia di trading per cui vuoi fornire liquidità, il livello di commissione e la fascia di prezzo.

Poi seleziona l'importo del token che vuoi fornire come liquidità.

L'opzione Zap apparirà automaticamente quando uno o più token hanno saldo insufficiente.

Clicca il link per aprire il modale Zap.

#### Avviare lo Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Nel nuovo modale "Zap in" troverai i seguenti campi:

1. La coppia di trading su cui stai facendo Zap (fornendo liquidità).
2. Il/i token di deposito e gli importi da depositare. Puoi liberamente aggiungere o rimuovere token per lo Zap.
3. La fascia di prezzo della nuova posizione. Puoi anche cliccare le frecce per passare tra diverse visualizzazioni del prezzo.
4. Una ripartizione dettagliata di come la funzione Zap gestirà i tuoi token di deposito.
5. Un riepilogo delle statistiche che include:
   1. Valore stimato in USD per la nuova posizione di liquidità.
   2. Importo token stimato nella nuova posizione di liquidità.
   3. Fondi residui stimati in USD dopo lo Zap. Nella maggior parte dei casi dovrebbe essere 0. Se la Pool di Liquidità o i token hanno pochissima liquidità, questo valore potrebbe aumentare.
   4. L'impatto sul prezzo per gli Swap e i ribilanciamenti dei token durante lo Zap.
   5. L'impatto sul prezzo per l'aggiunta di liquidità e la costruzione della posizione.
   6. Commissione Zap. A seconda della coppia di liquidità, il tasso di commissione può variare.

{% hint style="warning" %}
Tieni presente che potresti dover riconfigurare l'importo da fare con Zap in base al tuo saldo disponibile. Se non hai saldo su uno dei token, rimuovilo.
{% endhint %}

{% hint style="info" %}
Potresti notare che le impostazioni da "Add V3 Liquidity" vengono automaticamente trasferite al modale Zap. Incluse le impostazioni dell'importo di deposito e della fascia di prezzo.
{% endhint %}

#### Avviare lo Zapping <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Infine clicca "Approve" e conferma nel popup del portafoglio per l'approvazione del token.

Poi clicca "Preview" per aprire il modale di conferma finale. Prima di procedere, ti invitiamo a rivedere tutte le statistiche e le stime mostrate nel modale di conferma finale. In particolare le cifre dell'impatto e il Slippage massimo.

Infine clicca "Add Liquidity" e conferma nel popup del tuo portafoglio.

Dopo la conferma della transazione, vedrai la tua nuova posizione nella pagina "My Position"

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Altre Impostazioni <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Se vuoi personalizzare ulteriormente la tua esperienza Zap, clicca semplicemente l'icona dell'ingranaggio in alto a destra. Nelle impostazioni puoi configurare:

* Il Slippage massimo durante lo Zap.
* La scadenza della transazione.
* Se usare la liquidità aggregata di KyberSwap per effettuare il ribilanciamento dei token. Disattivalo se vuoi fare trading solo nelle Pool di PancakeSwap.
* La modalità Degen può essere usata per eseguire Zap con Slippage molto elevato. Non è consigliata per casi d'uso normali, usala a tuo rischio e pericolo.

{% hint style="warning" %}
Tieni presente che le impostazioni di Slippage e Scadenza sono indipendenti dalla pagina Swap e Liquidità.
{% endhint %}

#### Zap in con due token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Ora puoi fare Zap della tua liquidità con due token. Questo è utile quando il tuo saldo disponibile non corrisponde alle impostazioni di prezzo e all'importo e al rapporto dei token richiesti. Fai semplicemente Zap, e il rapporto verrà ribilanciato automaticamente.

#### Zap in con molti token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Sì, funziona proprio come un raccoglitore di token dust. È adatto per ripulire i piccoli saldi nel tuo portafoglio e metterli in una posizione per iniziare a guadagnare dalle commissioni di trading.&#x20;
