---
description: Bridge CAKE tra chain EVM e Aptos
---

# Come Fare il Bridge – EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
La guida seguente usa BNB Chain come esempio di chain EVM. Lo stesso processo può essere applicato a Ethereum.
{% endhint %}

## Bridge CAKE da BNB Smart Chain ad Aptos

1 - Assicurati che il tuo portafoglio supporti sia BNB Smart Chain che Aptos Mainnet. Oppure assicurati di avere entrambi i portafogli installati nel tuo browser.

Poi apri il [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Per prima cosa, dobbiamo collegare il nostro portafoglio BNB Smart Chain.

Clicca su "Connect" e scegli il portafoglio che preferisci nella sezione "EVM". Poi conferma e approva nel popup del portafoglio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Poi, dobbiamo collegare il nostro portafoglio Aptos.

Nel modale di connessione portafoglio, scegli il portafoglio che preferisci nella sezione "Aptos". Poi conferma e approva nel popup del portafoglio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Clicca sulla "v" nel campo di selezione token in alto e scegli "CAKE".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Inserisci il numero di CAKE che vuoi trasferire tramite Bridge ad Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Se il tuo portafoglio Aptos è stato appena creato e non ha saldo APT (Aptos Coin). Ti consigliamo di lasciare l'opzione "gas on destination" al valore predefinito. Il Bridge depositerà una piccola quantità di APT nel tuo portafoglio, non solo per aiutarti ad iniziare il tuo percorso su Aptos, ma avrai anche bisogno di APT per il gas per registrare e richiedere il tuo CAKE trasferito.

Modificare questa opzione potrebbe causare il fallimento del Bridging.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Clicca su "Transfer" per avviare la transazione di Bridging e conferma tramite il popup di conferma del portafoglio.

Tieni presente che, a seconda delle condizioni del tuo portafoglio BNB Smart Chain e del portafoglio Aptos, potresti dover approvare **più** conferme del portafoglio. Ad esempio, se stai facendo il Bridge di CAKE su Aptos per la prima volta, dovrai:

* Approvare la spesa di CAKE sul contratto di Bridging (dal tuo portafoglio BNB Smart Chain)
* Registrare CAKE (dal tuo portafoglio Aptos)

Per maggiori dettagli consulta [questa spiegazione dettagliata](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 - Siediti e rilassati. Dovrebbero volerci solo pochi minuti. Una volta completato il Bridging, CAKE sarà depositato nel tuo portafoglio Aptos. Puoi monitorare il progresso tramite la barra di avanzamento.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Bridge di CAKE su Aptos per la Prima Volta

Il Bridge di CAKE verso portafogli Aptos richiede transazioni di registrazione e richiesta. Questo viene fatto per migliorare la sicurezza degli utenti ed è specifico di Aptos.

### **Se hai già APT (Aptos Coin) nel tuo portafoglio:**

Ti verrà chiesto di registrare CAKE sul tuo portafoglio Aptos se non è ancora registrato. In questo caso non è necessaria alcuna transazione di richiesta aggiuntiva.

### **Se non hai APT (Aptos Coin) nel tuo portafoglio:**

Al termine della transazione Bridge, dovrai richiedere manualmente il tuo CAKE. Per coprire le commissioni gas per la richiesta, i token APT verranno inviati al tuo portafoglio Aptos dal tuo portafoglio di origine.

Questi passaggi di registrazione e richiesta si applicano solo la prima volta che interagisci con un token su Aptos. I trasferimenti successivi dello stesso token non richiederanno queste azioni.

Prima di fare il Bridge di CAKE su Aptos per la prima volta, assicurati che il tuo indirizzo Aptos abbia abbastanza APT per le commissioni gas. Per maggiori dettagli, consulta la spiegazione di Aptos qui: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Bridge CAKE da Aptos a BNB Smart Chain

1 - Assicurati che il tuo portafoglio supporti sia BNB Smart Chain che Aptos Mainnet. Oppure assicurati di avere entrambi i portafogli installati nel tuo browser.

Poi apri il [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Per prima cosa, dobbiamo collegare il nostro portafoglio BNB Smart Chain.

Clicca su "Connect" e scegli il portafoglio che preferisci nella sezione "EVM". Poi conferma e approva nel popup del portafoglio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Poi, dobbiamo collegare il nostro portafoglio Aptos.

Nel modale di connessione portafoglio, scegli il portafoglio che preferisci nella sezione "Aptos". Poi conferma e approva nel popup del portafoglio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Clicca sulla "v" nel campo di selezione token in alto e scegli "CAKE". Poi clicca il pulsante con la doppia freccia al centro della pagina per invertire la direzione del Bridging.

Assicurati che la rete "Aptos" sia nel campo in alto.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - Inserisci il numero di CAKE che vuoi trasferire tramite Bridge a BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - Se il tuo portafoglio BNB Smart Chain è stato appena creato e non ha saldo BNB (token gas). Ti consigliamo di lasciare l'opzione "gas on destination" al valore predefinito. Il Bridge depositerà una piccola quantità di BNB nel tuo portafoglio. Ti aiuterà ad iniziare il tuo percorso su BNB Smart Chain ed esplorare il vivace ecosistema PancakeSwap.

7 - Clicca su "Transfer" e approva le transazioni dal popup del tuo portafoglio.

8 - Siediti e rilassati. Dovrebbero volerci solo pochi minuti. Una volta completato il Bridging, CAKE sarà depositato nel tuo portafoglio BNB Smart Chain. Puoi monitorare il progresso tramite la barra di avanzamento.
