# 🌊 Pool di Liquidità

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

Nel nuovo Exchange V3, la liquidità verrà gestita sotto forma di posizioni non fungibili. Guadagnerai comunque una quota delle commissioni mentre fornisci liquidità.

Quando aggiungi il tuo token a una Pool di Liquidità riceverai token NFT da Liquidity Provider e condividerai le commissioni.

### **Posizioni di liquidità non fungibili**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

In V3, i provider di liquidità hanno ora più controllo su quale fascia di prezzo vogliono distribuire la loro liquidità. Quindi, quando aggiungi il tuo token a una Pool di Liquidità in V3, creerai una nuova posizione di liquidità non fungibile con le sue impostazioni uniche.

Pertanto, in V3, le posizioni di liquidità sono NFT. Tieni presente che questi NFT sono trasferibili e rappresentano la proprietà degli asset sottostanti e delle commissioni di trading guadagnate.

In V3, le commissioni di trading non verranno più automaticamente reinvestite nella posizione. Puoi richiederle manualmente su ciascuna delle pagine di dettaglio della posizione.

Puoi riscattare i tuoi fondi in qualsiasi momento rimuovendo la tua liquidità.

### **Liquidità attiva e fasce di prezzo**

In V3, i provider di liquidità possono configurare le loro posizioni per fornire liquidità solo quando il prezzo è all'interno di una determinata fascia. Se il prezzo di trading esce dalla fascia, la posizione sarà composta da un solo tipo di token della coppia e diventerà inattiva.

Le posizioni di liquidità inattive non parteciperanno al trading né guadagneranno commissioni di trading.

### **Liquidità concentrata**

In V3, poiché i provider di liquidità possono concentrare i loro depositi di token per fornire liquidità solo all'interno di una fascia di prezzo specifica. Con la stessa quantità di asset sottostanti, V3 può supportare scambi molto più grandi.

Risulta in un livello di liquidità relativa molto più elevato rispetto a V2. E i provider di liquidità possono guadagnare più commissioni di trading con la stessa quantità di capitale.

Ecco un esempio:

> Baller e Claire hanno entrambi fornito liquidità nella pool CAKE/USDT con asset token del valore di $1.000 USD. Il prezzo attuale di CAKE è 5 USDT.
>
> In modo simile a PancakeSwap v2, Baller ha fornito la sua liquidità sull'intera fascia di prezzo. Pertanto ha depositato tutto il suo capitale, 500 USDT e 100 CAKE.
>
> Claire utilizza la nuova funzionalità di liquidità concentrata in PancakeSwap v3 e ha creato una posizione con una fascia di prezzo da 2 a 12,5 USDT per CAKE. Ha depositato 185 USDT e 37 CAKE, per un totale di $370. Ora può spendere i restanti $630 altrove, come bloccare CAKE nella Syrup Pool per godere di un alto rendimento CAKE mentre riceve una serie di benefici dall'ecosistema PancakeSwap.
>
> Finché CAKE rimane all'interno della fascia di prezzo da 2 a 12,5, sia Baller che Claire riceveranno la stessa quantità di premi in commissioni di trading mentre Claire ha depositato molto meno capitale nella Pool di Liquidità.

### **Commissioni di trading**&#x20;

Fornire liquidità ti dà una ricompensa sotto forma di commissioni di trading quando le persone usano la tua Pool di Liquidità per completare gli Swap.

Ogni volta che qualcuno fa trading su PancakeSwap, per ogni hop (Swap) in ogni Pool di Liquidità di Exchange V3, a seconda del livello di commissione della Pool di Liquidità, il trader paga una commissione che va dallo 0,01% all'1%. Le aliquote e la ripartizione delle commissioni sono mostrate di seguito:

<details>

<summary>Commissioni di Trading (EVM)</summary>

| Componente Commissione / Livello di Commissione | 0,01% | 0,05% | 0,25% | 1%  |
| ----------------------------------------------- | ----- | ----- | ----- | --- |
| Liquidity Provider                              | 67%   | 66%   | 68%   | 68% |
| Burn CAKE                                       | 15%   | 15%   | 23%   | 23% |
| Treasury                                        | 18%   | 19%   | 9%    | 9%  |

Ad esempio, in una pool con livello di commissione dello 0,25%:

* Tra tutte le posizioni di liquidità attive (in-range), ci sono un totale di 10 CAKE e 10 BNB token.
* Qualcuno scambia 1 CAKE per 1 BNB.
* Qualcun altro scambia 1 BNB per 1 CAKE.
* I provider di liquidità che sono nella fascia e forniscono liquidità attiva hanno guadagnato un totale di 0,0017 CAKE e 0,0017 BNB dagli scambi.
* Le posizioni con fasce di prezzo che non coprono il prezzo corrente, quindi inattive, non contribuiranno al trading né guadagneranno commissioni.

</details>

<details>

<summary><strong>Commissioni di trading (Solana)</strong></summary>

**Livelli di Commissione Pool CLMM V3 disponibili:**\
0,01%, 0,02%, 0,03%, 0,04%, 0,05%, 0,1%, 0,15%, 0,16%, 0,18%, 0,2%, 0,25%, 0,4%, 0,6%, 0,8%, 1%, 2%, 3%, 4%

**Nota:** La **distribuzione delle commissioni rimane la stessa** per tutti i livelli di commissione.

| Componente Commissione            | % del Totale Commissioni Swap | Descrizione                                                                  |
| --------------------------------- | ----------------------------- | ---------------------------------------------------------------------------- |
| **LP (Liquidity Provider)**       | 84%                           | Guadagnata dagli LP che forniscono liquidità nella fascia di prezzo attiva   |
| **Burn**                          | 8%                            | Rimossa permanentemente per ridurre la fornitura di CAKE                     |
| **Treasury**                      | 8%                            | Allocata al treasury del protocollo PancakeSwap                              |

**Esempio: Distribuzione delle Commissioni in una Pool CAKE/SOL allo 0,25%**

1. **Configurazione della Pool:** Liquidità attiva totale: 10 CAKE e 10 SOL (posizioni in-range).
2. **Avvengono gli Swap:**
   * L'utente A scambia 1 CAKE → 1 SOL.
   * L'utente B scambia 1 SOL → 1 CAKE.
3. **Commissioni Totali Raccolte:**
   * 0,25% per trade × 2 trade = **0,005 CAKE + 0,005 SOL**.
4. **Distribuzione delle Commissioni:**
   * **84% agli LP:** 0,0042 CAKE + 0,0042 SOL
   * **8% al Burn:** 0,0004 CAKE + 0,0004 SOL
   * **8% al Treasury:** 0,0004 CAKE + 0,0004 SOL
5. **Guadagni degli LP:**
   * Solo gli **LP in-range** guadagnano commissioni. Le commissioni vengono distribuite proporzionalmente in base alla quota di ciascun LP.
   * Gli **LP fuori fascia** **non guadagnano** commissioni.

</details>

### **Guadagnare CAKE**

Per rendere ancora più conveniente essere un provider di liquidità, puoi anche mettere al lavoro le tue posizioni di liquidità per generare nuovo rendimento nelle [CAKE Farms](https://pancakeswap.finance/liquidity/pools), continuando al contempo a guadagnare premi dalle commissioni di trading.

***

## Exchange V2

### LP Token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Ad esempio, se depositi **CAKE** e **BNB** in una Pool di Liquidità, riceverai token **CAKE-BNB LP**.

Il numero di LP token che ricevi rappresenta la tua quota della Pool di Liquidità CAKE-BNB.

Puoi anche riscattare i tuoi fondi in qualsiasi momento rimuovendo la tua liquidità.

### **Guadagnare commissioni di trading**

Ogni volta che qualcuno fa trading su PancakeSwap, per ogni hop (Swap) in ogni Pool di Liquidità di Exchange V2, il trader paga una commissione fissa dello 0,25%, **di cui lo 0,17%** viene aggiunto alla Pool di Liquidità sotto forma di commissioni di trading.

### **Guadagnare CAKE**

Il vecchio Exchange V2 continuerà a funzionare in parallelo con il nuovo Exchange V3. Quindi, alcune coppie di trading rimarranno su PancakeSwap Exchange V2 e avranno le loro Farm V2 corrispondenti. Controlla i tag per identificare le versioni dell'exchange.



## Impermanent Loss

Fornire liquidità non è privo di rischi, poiché potresti essere esposto all'impermanent loss.

["In parole semplici, l'impermanent loss è la differenza tra tenere token in un AMM e tenerli nel tuo portafoglio." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
