# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### Cosa dovrei fare su PancakeSwap su altre blockchain?

Fornisci Liquidità, fai trading e farming come hai sempre fatto. Se sei già un utente multichain, ricordati di fornire Liquidità su PancakeSwap sulle altre blockchain su cui siamo stati deployati (come Ethereum), poiché abbiamo ricompense CAKE su BNB Smart Chain per te, permettendoti di guadagnare ancora più CAKE senza fare Bridging di quegli asset!

### **Ci saranno altri pair?**

Sì, ma procederemo per fasi per garantire di dare priorità alla sicurezza dei fondi degli utenti e all'inflazione di CAKE. Facci sapere nelle chat della community cosa pensi dovrebbe essere aggiunto a PancakeSwap su altre blockchain, e su quali altre blockchain dovremmo deployare PancakeSwap.

### **Perché il costo del gas per lo Staking degli LP Token è alto?**

Una piccola quantità di token nativo (ad esempio, ETH su Ethereum) è richiesta per la configurazione iniziale. Quindi la prima transazione sarà leggermente costosa.

Inoltre, ci sono altre commissioni (principalmente costi del gas) coinvolte nel farming cross-chain. Consulta [questa](faq.md#are-there-any-fees-when-i-do-crosschain-farming) sezione dedicata per saperne di più.

### **Perché lo Staking e l'unstaking richiedono 30 minuti per completarsi?**

Tutte le transazioni cross-chain richiedono circa 30 minuti per completarsi. Questo perché:

* Le transazioni devono essere eseguite sia sulla blockchain di farming (come Ethereum) che sulla BNB Chain.
* La consegna dei messaggi cross-chain richiede tempo.
* Per garantire la sicurezza e che tutti i dati siano sincronizzati e coerenti tra le diverse blockchain.

### **Dove sono le mie ricompense CAKE raccolte?**

I tuoi CAKE raccolti saranno distribuiti su BNB Smart Chain. Cambia la rete blockchain nel tuo portafoglio per verificare il saldo di CAKE.

### **Non riesco a raccogliere perché il mio portafoglio non supporta il cambio tra diverse blockchain!**

Prova a usare un'app portafoglio diversa che supporti il multichain e il cambio di rete.

Nota che lo Staking e l'unstaking degli LP Token raccoglieranno anche tutti i CAKE guadagnati nel tuo portafoglio su BNB Smart Chain. Quindi, se non vuoi usare un'app portafoglio diversa, metti semplicemente in Staking di più, o togli una piccola quantità di LP Token per raccogliere i tuoi CAKE guadagnati.

### Ci sono commissioni quando faccio Crosschain Farming?

A differenza del farming nativo su BNB Chain, fare farming su altre blockchain richiede attività cross-chain. Ecco le commissioni coinvolte:

**1 - Commissione gas per la creazione di un contratto proxy**

È necessario creare un contratto proxy su BNB Chain per il farming cross-chain. Il costo del gas per la creazione del contratto proxy è incluso nella transazione.

Questa commissione viene addebitata una sola volta alla prima transazione di "stake".

**2 - Commissione gas per le chiamate su BNB Chain**

Quando gli utenti depositano o prelevano LP Token, un executor eseguirà transazioni per conto degli utenti su BNB Chain. Il costo del gas per queste chiamate è incluso nella transazione.

Questa commissione viene addebitata in ogni transazione di deposito o prelievo.

**3 - Commissione gas per le chiamate su altre blockchain**

Quando gli utenti prelevano LP Token, un executor eseguirà le transazioni finali per rilasciare gli LP Token su altre blockchain (come Ethereum). Il costo del gas per queste chiamate è incluso nella transazione.

Questa commissione viene addebitata solo nelle transazioni di prelievo.

**4 - Commissione di messaggistica cross-chain**

Utilizziamo un message bus alimentato da Celer per instradare i nostri messaggi cross-chain. Pertanto viene inclusa una commissione per i messaggi basata sulla lunghezza in byte del messaggio.

Questa commissione viene addebitata in ogni transazione di stake. Nelle transazioni di unstake, questa commissione viene addebitata due volte poiché è necessaria una comunicazione bidirezionale tra BNB Chain e altre blockchain per garantire la sicurezza.

```
messagingFee = feeBase + message.length * feePerByte;
```

Puoi trovare le variabili nella formula nel contratto del message bus:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - Il fondo iniziale**

Non è strettamente una "commissione".&#x20;

Per ogni nuovo utente che inizia a fare Crosschain Farming su PancakeSwap, nella prima transazione di "stake", depositeremo 0,005 BNB nel suo portafoglio BNB Chain. La quantità corrispondente di token nativi sulla chain di farming (come ETH su Ethereum) verrà addebitata dalla transazione di deposito, usando il tasso di mercato fornito dall'oracolo dei prezzi.

Questo serve ad aiutare gli utenti a iniziare il loro percorso su BNB Chain con facilità. Comprendiamo quanto sia frustrante avere tutti i CAKE raccolti ma non poter esplorare il vivace ecosistema PancakeSwap senza trovare un altro modo per ottenere BNB per il gas.

Questa commissione viene addebitata una sola volta alla prima transazione di "stake".

### Da dove provengono le emissioni?&#x20;

_aggiornato il 10 ottobre 2022_

Per ora, i Chefs hanno dirottato 0,0189 CAKE per blocco dal pool CAKE a tutti i farm crosschain.&#x20;

Ecco il dettaglio delle emissioni:

<table><thead><tr><th width="249"></th><th>Moltiplicatore</th><th>CAKE per blocco</th></tr></thead><tbody><tr><td><strong>CAKE Pool</strong></td><td>-</td><td><strong>8.9811</strong></td></tr><tr><td><strong>Tutti i Farm Crosschain</strong></td><td>-</td><td><strong>0.0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0.5x</td><td>0.0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0.2x</td><td>0.0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0.2x</td><td>0.0042</td></tr></tbody></table>

### Cosa succede durante il deposito, la raccolta e il prelievo?

Il farming crosschain di PancakeSwap è come usare un LP Token "sostitutivo" per fare farming su BNB Chain, con lo stesso MasterChef di PancakeSwap. Le ricompense CAKE vengono calcolate e distribuite su BNB Chain, controllate e gestite dallo stesso contratto MasterChef.

#### Al deposito:

1. Gli utenti richiedono il deposito di LP Token sulle blockchain di farming (come Ethereum).
2. Gli LP Token vengono trasferiti ai contratti vault di farming.
3. Il message bus di Celer viene utilizzato per consegnare il messaggio di "deposito" a BNB Chain.
4. Un executor su BNB Chain conia la stessa quantità di token farming come "sostitutivi" e li deposita nei Farm.

#### Alla raccolta:

Poiché le ricompense CAKE vengono calcolate e distribuite su BNB Chain, gli utenti possono richiedere le proprie ricompense CAKE con una singola transazione su BNB Chain senza necessità di operazioni cross-chain.

#### Al prelievo:

1. Gli utenti richiedono il prelievo di LP Token sulle blockchain di farming (come Ethereum).
2. Il message bus di Celer viene utilizzato per consegnare il messaggio di "prelievo" a BNB Chain.
3. Un executor su BNB Chain preleva i token farming dai Farm, brucia quei token, trasferisce i CAKE guadagnati agli utenti e utilizza il message bus di Celer per consegnare il messaggio di conferma alla blockchain di farming originale.
4. Un executor sulla blockchain di farming conferma tutto e rilascia quindi gli LP Token dai contratti vault.
