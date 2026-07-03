# FAQ Swap

## Swap

### Cosa c'è di nuovo in Exchange V3?

* Liquidità concentrata — la Liquidità sarà concentrata nel range di prezzo più attivamente scambiato, il che significa:
  * Slippage di trading inferiore per i trader
  * Potenzialmente più ricompense in commissioni LP per i fornitori di Liquidità
* Una struttura di commissioni di trading flessibile — i fornitori di Liquidità possono scegliere tra più livelli di commissioni di trading quando creano coppie di Liquidità o forniscono Liquidità
* Range di prezzo personalizzabile — i fornitori di Liquidità possono anche scegliere quali range di prezzo vogliono fornire Liquidità
* Posizioni di Liquidità non fungibili — ogni posizione di Liquidità avrà il proprio ID univoco corrispondente alla sua configurazione (come il range di prezzo). Pertanto, potrai creare e mantenere più posizioni con la stessa coppia di trading ma con configurazioni e importi di Liquidità diversi
* Compatibilità con le versioni precedenti — Exchange v3 utilizzerà anche le coppie di Liquidità v2 legacy e StableSwap per fornire sempre il percorso di trading migliore
* Ordine limite integrato — gli utenti avanzati possono utilizzare il nuovo range di prezzo personalizzabile nella fornitura di Liquidità per creare effettivamente un ordine limite che convertirà tutti i token in quello desiderato quando il prezzo raggiunge il target



### Posso aggiungere i miei token a Exchange V3?

Chiunque può creare pool di Liquidità depositando Liquidità su V3.

Tuttavia, i seguenti token attualmente **NON** sono supportati:

* Token con commissione sul trasferimento
* Token con rebase

Per questi token, **NON** aggiungere Liquidità su Exchange V3. I tuoi asset potrebbero rimanere bloccati nella posizione di Liquidità.



### **Come mai la mia transazione non va a buon fine?**

PancakeSwap è un'applicazione DeFi che interagisce con il Portafoglio per completare transazioni on-chain per Swap, creazione di LP, Staking in Farm e Pool, ecc.

**Commissioni Gas**

Pertanto, la prima cosa è **assicurarti di avere abbastanza BNB per pagare la commissione gas** delle transazioni on-chain. In genere, le commissioni gas fluttuano in base al numero di transazioni in coda; se ci sono più transazioni, potrebbe essere necessaria una commissione gas più alta per far passare la transazione. Su BNB Smart Chain, la commissione gas varia tipicamente da qualche centesimo a un dollaro USD in BNB. Scopri di più sulle [commissioni gas qui](https://academy.binance.com/en/glossary/gas).

**Commissioni di Transazione**

Se la tua azione di Swap ancora non va a buon fine e mostra un errore che ti chiede di rivedere lo Slippage — potresti voler verificare se i token che stai cercando di scambiare hanno **commissioni e restrizioni sulle transazioni**.

Non è raro che i token su BNB Smart Chain includano una **commissione di transazione** nei loro contratti; di solito queste commissioni potrebbero essere utilizzate per il burn, per finanziare un treasury di un progetto di fair launch — ad esempio, questo [token APX ha una tassa dell'1% su ogni transazione](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) per l'invio a un indirizzo di burn, in modo che più transazioni significhino più burning, aumentando il valore per i detentori di APX.

Con la commissione di transazione, che sia inclusiva (una parte dell'importo dello Swap viene inviata altrove rispetto al tuo indirizzo, quindi l'output è inferiore al previsto per l'input stimato) o esclusiva (che richiede un trasferimento aggiuntivo dal tuo indirizzo per inviare token extra, quindi l'input è superiore al previsto per l'output stimato), influisce sugli importi di input e output che accetti per firmare la transazione. In molti casi, la transazione non può soddisfare i requisiti di input e output a causa della tassa.

**Swap con Commissioni di Transazione**

Prima di fare lo Swap di qualsiasi token, assicurati di aver visitato il loro sito web per capire se hanno un meccanismo di commissione di transazione (o _tassa_ come molti progetti la chiamano). Se c'è, assicurati di impostare uno Slippage sufficiente per accomodare la commissione di transazione — ad es. se c'è una commissione di transazione del 5%, il tuo Slippage dovrà essere impostato ad almeno il 5% più il normale Slippage di trading a seconda del tuo importo di trading e della Liquidità del token, diciamo 5,5%-6%.

In alcuni casi estremi, incluse alcune truffe, alcuni token hanno persino un blocco sulla maggior parte o su tutti i trasferimenti on-chain, o consentono solo a certi indirizzi di vendere; in tal caso è impossibile fare lo Swap del token con successo. Informati sul token che stai cercando di scambiare e sii consapevole di eventuali commissioni e restrizioni!



### La nuova interfaccia di Swap utilizza la Liquidità v2 o StableSwap?

Sì. Il nuovo Swap v3 utilizza la Liquidità da PancakeSwap v3, v2 e StableSwap per ottenere il percorso di trading migliore.



### Cos'è il routing diviso?

In Swap v3, il tuo trade potrebbe essere suddiviso in più percorsi per eseguire il tuo trade al tasso migliore.

Per visualizzare maggiori dettagli su come viene instradato il tuo trade, tocca il pulsante "v" nella sezione "Percorso" per espandere e visualizzare i dettagli.

Scopri di più [qui](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Come personalizzare o disabilitare determinate fonti di Liquidità?

Il nuovo Swap v3 utilizza la Liquidità da PancakeSwap v3, v2 e StableSwap per ottenere il percorso di trading migliore. Tuttavia, puoi personalizzare o disabilitare determinate fonti di Liquidità se non vuoi che il tuo trade venga instradato attraverso di esse.

Quando visualizzi un percorso di trading, clicca sul pulsante "Personalizza Routing". Oppure clicca sul pulsante ⚙️ nell'angolo in alto a destra dell'interfaccia di Swap e scegli "Personalizza Routing".

Nel popup "Personalizza Routing", puoi scegliere quale fonte di Liquidità vuoi utilizzare. Oppure disabilitare completamente i multihop.

Nota: disabilitare i multihop potrebbe portare a un aumento dello Slippage o a un tasso di trading peggiore su coppie di trading specifiche. Procedi con cautela.

Scopri di più [qui](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Liquidità

### Cosa sono i livelli di commissione e come scegliere quello corretto?

In Exchange v3, quando fornisci Liquidità, puoi scegliere tra diverse commissioni di trading (0,01%, 0,05%, 0,25% e 1%) per la stessa coppia di token.

Ad esempio, per CAKE-BNB, potrebbe esserci una coppia allo 0,25%, il che significa che è in vigore una commissione di trading dello 0,25% per ogni trade. Tuttavia, alcuni fornitori di Liquidità potrebbero scegliere di fornire Liquidità a una coppia di trading CAKE-BNB con un tasso di commissione dello 0,05%, offrendo un preventivo migliore e attirando più volume di trading.

Non esiste una risposta "corretta" su quale configurazione di commissioni di trading scegliere. Dipende dai token all'interno della coppia di trading. Di solito, i token volatili dovrebbero avere una commissione di trading più alta per compensare meglio la perdita impermanente causata dalla volatilità. D'altra parte, token come le stablecoin hanno movimenti di prezzo più piccoli e perdite impermanenti più basse, quindi la loro commissione di trading dovrebbe essere inferiore.

Quando selezioni una coppia di token, l'interfaccia "Aggiungi Liquidità" sceglierà automaticamente il livello di commissione più popolare per te.



### Perché i miei due token di deposito non hanno lo stesso valore in USD?

In Exchange V3, gli asset sottostanti in una posizione di Liquidità non avranno sempre un valore uguale in USD. Dipenderà dalle impostazioni del range di prezzo di una posizione e dal prezzo corrente della coppia.

In realtà, se la tua posizione va fuori range, tutti i token verranno convertiti in un unico asset. Inoltre, puoi fornire Liquidità a un range di prezzo che non copre il prezzo corrente e depositare un solo asset. Continua a leggere per saperne di più ⬇️



### Cosa succede se la mia posizione di Liquidità va fuori range?

Non guadagnerai ricompense in commissioni di trading se il prezzo corrente esce dal range di prezzo definito nella tua posizione.

Inoltre, tutti i token verranno convertiti in un unico asset a seconda della direzione della condizione di prezzo.

Ad esempio, se una posizione di CAKE/BUSD è configurata con un range di prezzo da 3 BUSD per CAKE a 5 BUSD per CAKE, tutti gli asset nella posizione verranno convertiti in BUSD se il prezzo di CAKE è uguale o superiore a 5 BUSD per CAKE, e viceversa.

Nota che se il prezzo torna nel range, inizierai di nuovo a ricevere ricompense in commissioni di trading. Non sono necessarie azioni aggiuntive.



### È meglio fornire sempre Liquidità con un range più piccolo?

Fornire Liquidità a un range di prezzo più piccolo aiuterà a concentrare la tua Liquidità in un range di prezzo specifico, aumentando la tua quota relativa rispetto alla Liquidità totale all'interno del range di prezzo, guadagnando potenzialmente più ricompense in commissioni di trading.

Tuttavia, tieni presente che solo le posizioni di Liquidità attive guadagneranno ricompense in commissioni di trading dai trade. Ciò significa che guadagnerai ricompense solo quando il prezzo di trading corrente è all'interno del range di prezzo definito nella posizione di Liquidità.



### Esistono modi per regolare automaticamente la mia posizione in modo che sia sempre nel range e guadagni ricompense sulle commissioni?

PancakeSwap v3 supporta il deposito di Liquidità con un solo clic tramite Zap, disponibile su BNB Chain e Ethereum.



### Qual sarà la ripartizione delle commissioni di trading per Exchange v3?

|                    | 0,01% | 0,05% | 0,25% | 1%  |
| ------------------ | ----- | ----- | ----- | --- |
| Fornitore di Liquidità | 67%   | 66%   | 68%   | 68% |
| Burn CAKE          | 15%   | 15%   | 23%   | 23% |
| Treasury           | 18%   | 19%   | 9%    | 9%  |

### Le ricompense in commissioni LP vengono composte automaticamente come in Exchange v2?

No.

In Exchange v3 dovrai riscattare manualmente le ricompense in commissioni di trading. Puoi farlo dalla pagina dei dettagli della posizione. Puoi trovare tutte le tue posizioni di Liquidità v3 nella pagina della Liquidità.



### Cosa influenza l'APR delle commissioni LP?

In Exchange v3, l'APR delle ricompense in commissioni LP può variare tra le posizioni di Liquidità. Si basa sui seguenti fattori:

* Volume di trading\
  \- più volume genera più ricompense in commissioni
* Livello di commissione della coppia di Liquidità\
  \- un livello di commissione più alto genera più ricompense in commissioni dai singoli trade
* Il numero di token depositati\
  \- più token nella posizione si traduce in una quota relativa maggiore rispetto alla Liquidità attiva totale, che ottiene più ricompense in commissioni dai trade
* Il range di prezzo selezionato\
  \- un range di prezzo più piccolo consente una concentrazione più alta per la stessa quantità di token depositati, il che si traduce in una quota relativa maggiore rispetto alla Liquidità attiva totale e ottiene più ricompense in commissioni dai trade
* La quantità di Liquidità attualmente attiva\
  \- se ci sono più utenti che depositano e concentrano la loro Liquidità con lo stesso range del tuo, guadagnerai meno commissioni di trading a causa di una quota relativa inferiore rispetto al totale
* Se la posizione di Liquidità è attiva\
  \- solo le posizioni di Liquidità attive guadagneranno ricompense in commissioni di trading



### Posso fornire Liquidità v2?

Fornire Liquidità v2 non è più consigliabile. Raccomandiamo di utilizzare la Liquidità v3 per sfruttare le nuove funzionalità e migliorare l'efficienza.

Se vuoi procedere con l'aggiunta di Liquidità v2:

* Se la coppia di token non ha un pool v3, o ha più Liquidità in v2 rispetto al pool più grande in v3, comparirà un pulsante "Aggiungi Liquidità V2". Clicca semplicemente per passare all'aggiunta di Liquidità v2
* In alternativa, usa `/v2` nell'URL per utilizzare sempre la fornitura di Liquidità v2



### Perché non posso aggiungere Liquidità a una coppia che ho appena creato?

A causa di un bug dell'Exchange V2 legacy (presente in ogni fork di UniSwap V2), non potrai aggiungere Liquidità a una coppia usando la normale interfaccia di Liquidità di PancakeSwap e le sue chiamate al contratto se una coppia è:

* Creata chiamando `createPair` su FactoryV2 senza depositare Liquidità iniziale e coniare i token LP iniziali
* Successivamente, uno dei token nella coppia è stato trasferito manualmente nel contratto pool chiamando `sync`

{% hint style="info" %}
Recentemente, è stato rilevato un numero crescente di tali attacchi su PancakeSwap Exchange V2 su BNB Chain.

Raccomandiamo vivamente di utilizzare la nostra interfaccia per creare la coppia di trading per il tuo token aggiungendo la Liquidità iniziale con la creazione della coppia.
{% endhint %}

Mentre i Chefs lavorano su una soluzione per risolvere questo problema, ecco una guida passo per passo per risolverlo usando BscScan:

#### Individua l'indirizzo del pool e la sua pagina BscScan

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Se la tua coppia è interessata, vedrai il link alla pagina BscScan per la coppia/pool di trading nel messaggio di errore.

In alternativa, puoi andare su Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), andare su "Read Contract", "6. getPair", inserire l'indirizzo dei due token nella tua coppia di trading e cliccare su "Query". Dovresti vedere l'indirizzo della coppia nel campo di ritorno.

#### Controlla quale token è stato depositato e trasferisci l'altro token nel pool manualmente

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

Dal campo del saldo dei token su BscScan, puoi verificare quale token è stato depositato nel pool. Di solito, dovrebbe essere il token accoppiato. (Come WBNB, USDT, ecc...)

Una volta confermato, devi trasferire manualmente l'altro asset nel contratto pool. Puoi farlo nell'app Portafoglio che preferisci inserendo l'indirizzo del pool come destinatario.

Puoi trasferire qualsiasi importo, ma poiché si tratta effettivamente di "donare" asset a un pool, starai trasferendo i tuoi asset in una posizione di Liquidità senza coniare token di Liquidità. Quindi raccomandiamo di mantenere questo importo al minimo.

{% hint style="warning" %}
IMPORTANTE: Una volta trasferito il token, devi chiamare immediatamente `sync()` sul pool.
{% endhint %}

Puoi farlo andando sulla pagina BscScan per la coppia di trading, andando su "Write Contract", "8. Sync" e cliccando il pulsante "Write". Dovrai connettere il tuo Portafoglio prima di eseguire la transazione.

Una volta confermata la transazione, puoi aggiungere la Liquidità successiva sull'interfaccia di PancakeSwap.

#### Cosa fare se voglio definire il prezzo di lancio?

Devi regolare il pool al prezzo di lancio durante il trasferimento del token e la correzione del pool.

L'importo da trasferire può essere calcolato usando:

* `tokenInside`: il token che è già stato trasferito nel pool. Di solito dovrebbe essere il token accoppiato. (Come WBNB, USDT, ecc...)
* `tokenToSend`: il token che sta per essere inviato al pool. Di solito dovrebbe essere il tuo token di progetto
* `tokenInside.price`: il prezzo USD di tokenInside
* `tokenToSend.price`: il prezzo USD di tokenToSend (il prezzo di lancio)
* `pool`: il pool V2

Con la seguente formula:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Se il risultato è inferiore a 0 (di solito accade quando il prezzo di lancio è molto grande, potresti dover prima depositare più `tokenInside` nel pool)



### Come gestire LP stabile e LP v2 legacy?

Puoi gestirli come di consueto andando alla pagina [Liquidità](https://pancakeswap.finance/liquidity).



### Perché devo reimpostare l'approvazione su USDT prima di abilitare/approvare?

Quando si opera sulla mainnet di Ethereum, il token USDT segue una logica diversa per la gestione delle approvazioni e dell'allowance dei token.

Pertanto, quando le allowance di spesa sono troppo basse, è necessario reimpostare l'approvazione prima di impostarne una nuova.
