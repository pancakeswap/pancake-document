---
hidden: true
---

# FAQ Farming

### Perché ci sono più APR?

In V3, puoi concentrare i tuoi asset mentre fornisci Liquidità per aumentare la tua quota rispetto alla Liquidità totale disponibile, guadagnando una % più alta di ricompense.&#x20;

Pertanto, a seconda delle impostazioni dell'intervallo di prezzo della posizione, ogni posizione di Liquidità avrà il proprio APR sulle commissioni LP e il proprio APR di farming.

L'APR globale viene calcolato con la quantità totale di ricompense CAKE in USD, divisa per la quantità totale di asset nelle posizioni attive attualmente in Staking nel Farm. Quindi l'APR di farming globale è solo un riferimento generico e non rappresenterà gli APR individuali per ciascuna posizione.

Per visualizzare il tuo APR di farming, controlla le tue posizioni elencate sotto ogni Farm.

###

### Cosa succede se la mia posizione di Liquidità esce dall'intervallo mentre è in Staking nel Farm?

In V3, solo le posizioni di Liquidità attive (in range) guadagneranno CAKE dai Farm.

La posizione smetterà di ricevere ricompense CAKE quando il prezzo esce dall'intervallo.

Se il prezzo torna nell'intervallo, la posizione inizierà di nuovo a ricevere ricompense CAKE. Non sono necessarie azioni aggiuntive da parte degli utenti in Staking.



### Esistono modi per regolare automaticamente la mia posizione in modo che sia sempre nell'intervallo e guadagni ricompense sulle commissioni?

PancakeSwap v3 supporta il deposito di Liquidità con un clic tramite Zap, disponibile su BNB Chain e Ethereum.



### È meglio fare sempre farming con una posizione di Liquidità con un intervallo più piccolo?

Fornire Liquidità a un intervallo di prezzo più piccolo aiuterà a concentrare la tua Liquidità, aumentando le tue quote relative rispetto alla Liquidità totale nell'intervallo di prezzo, guadagnando potenzialmente più ricompense CAKE.

Tuttavia, tieni presente che solo le posizioni di Liquidità attive guadagneranno ricompense CAKE. Ciò significa che guadagnerai ricompense solo quando il prezzo di trading attuale è all'interno dell'intervallo di prezzo definito nella posizione di Liquidità.

Se devi regolare l'intervallo di prezzo della tua posizione, dovrai fare unstake, rimuovere la Liquidità e creare una nuova posizione con l'intervallo di prezzo aggiornato. Tieni presente che gli aggiustamenti frequenti non sono sempre la strategia più ottimale poiché realizzano l'Impermanent Loss e costano una certa quantità di gas per completare più transazioni.



### Quante posizioni posso mettere in Staking in un singolo Farm?

Non c'è un limite massimo di posizioni che puoi mettere in Staking in un Farm.

Ma tieni presente che dovrai spendere gas per raccogliere manualmente da ciascuna posizione. Tieni sempre in considerazione il costo del gas nelle operazioni di rendimento.



### Con quale frequenza dovrei raccogliere le mie ricompense?

La frequenza con cui raccogli le tue ricompense dipende da te, ma è utile ricordare che c'è una piccola commissione coinvolta nella raccolta. Puoi vedere questa commissione nel tuo portafoglio quando confermi dopo aver cliccato "Harvest"**.**

Questo mostra la commissione per la raccolta come appare nel portafoglio MetaMask. Portafogli diversi mostreranno le informazioni in modo leggermente diverso. Considera di lasciare che le tue ricompense crescano per un po' in modo da pagare commissioni meno spesso.



### E se voglio modificare la mia posizione mentre è in Staking nel Farm?

Mentre sei in Staking nel Farm, puoi aggiungere o rimuovere Liquidità senza fare unstaking. Individua semplicemente la posizione di Liquidità che vuoi modificare, clicca sul suo titolo/ID e dovresti vedere la pagina di dettaglio della posizione dove puoi usare i pulsanti "Aggiungi" e "Rimuovi".

Se vuoi regolare le configurazioni dell'intervallo di prezzo di una posizione di Liquidità, dovrai fare unstake dal Farm, rimuovere tutta la Liquidità e ricreare una nuova posizione aggiungendo Liquidità.



### Cosa influenza l'APR del Farming?

In Farm v3, l'APR delle ricompense CAKE può variare tra le posizioni di Liquidità. Si basa sui seguenti fattori:

* Tasso di emissione CAKE ai Farm\
  \- più CAKE genererà un rendimento più alto per tutti i Farm. Leggi di più nella [nostra pagina Tokenomics](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)
* Moltiplicatore del Farm\
  \- i Farm con un moltiplicatore più alto otterranno più CAKE proporzionalmente a tutti i Farm. Nota che i Farm v3 e v2 + StableSwap usano due set separati di moltiplicatori. E i Farm su Ethereum e BNB Chain usano anche due set separati di moltiplicatori.
* Il numero di token depositati nella posizione\
  \- più token nella posizione si traduce in una quota relativa maggiore rispetto alla Liquidità attiva totale nel Pool del Farm e ottiene più ricompense CAKE
* L'intervallo di prezzo selezionato\
  \- un intervallo di prezzo più piccolo consente una concentrazione più alta per la stessa quantità di token depositati, il che si traduce in una quota relativa maggiore rispetto alla Liquidità attiva totale nel Pool del Farm, e ottiene più ricompense CAKE
* La quantità di Liquidità attualmente attiva\
  \- se ci sono più utenti che depositano e concentrano la loro Liquidità con lo stesso intervallo del tuo, guadagnerai meno ricompense CAKE a causa di una quota relativa minore rispetto al totale
* Se la posizione di Liquidità è attiva\
  \- solo le posizioni di Liquidità attive guadagneranno ricompense CAKE dal Farm



### Perché sto vedendo un popup "Aggiorna posizioni"?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Poco dopo il lancio di V3, i Chefs hanno implementato un aggiornamento sui Farm per rendere i calcoli delle ricompense più accurati e affidabili. Se stai vedendo questo popup, significa che alcune delle tue posizioni richiedono un aggiornamento.

Clicca semplicemente "Aggiorna tutto" e conferma nel popup del tuo portafoglio.

Nota che i Chefs stanno anche applicando questo aggiornamento ai dati storici di Staking tra il lancio di Farm V3 e quando questo aggiornamento viene implementato. Se ci sono ricompense CAKE extra, verranno inviate al tuo portafoglio tramite airdrop prima del 1° maggio 2023.



### Perché un Farm 2x in V3 ha meno APR di un Farm 1x in V2?

Prima di tutto, quando si confrontano gli APR, è necessario assicurarsi che la Liquidità totale in Staking tra i due Farm sia uguale.

Oltre a ciò, ora abbiamo più gruppi di Farm che hanno il proprio flusso di emissioni CAKE. E ogni gruppo di Farm condivide set separati di moltiplicatori.

Un singolo Farm riceverà emissioni CAKE in base a:

* A = CAKE totale al secondo/blocco per il gruppo di Farm a cui appartiene
* B = Numero totale di moltiplicatori all'interno del gruppo a cui appartiene
* C = Il moltiplicatore che possiede

`CAKE per blocco/secondo = C / B * A`

I numeri sopra riportati si trovano in ciascuno dei contratti [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I).



### Posso usare bCAKE nei Farm v3?

Sì

bCAKE per i Farm V3 arriverà molto presto dopo il deployment di PancakeSwap Farm V3. Resta sintonizzato.
