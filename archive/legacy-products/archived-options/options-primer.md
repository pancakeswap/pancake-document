# Introduzione alle Opzioni



{% hint style="danger" %}
\[ARCHIVIATO] Options – A partire dall'11 marzo 2025\
Se hai ancora liquidità da prelevare, fallo immediatamente visitando https://www.stryke.xyz/en/trade.
{% endhint %}



## Cosa sono le Opzioni?

Le opzioni sono contratti derivati che forniscono all'acquirente il diritto, ma non l'obbligo, di acquistare (opzione call) o vendere (opzione put) un asset sottostante a un prezzo predeterminato (prezzo strike) entro un periodo specificato (data di scadenza).

## Tipi di Opzioni?

### Opzioni Call

Un'opzione call dà al detentore il diritto di acquistare l'asset sottostante al prezzo strike concordato alla data di scadenza o prima. I trader acquistano opzioni call quando prevedono che il prezzo dell'asset sottostante salirà. Questo consente loro di beneficiare di un potenziale apprezzamento del prezzo senza dover possedere direttamente l'asset sottostante.

> Un trader acquista un'opzione call su Bitcoin con un prezzo strike di $50.000 con scadenza tra un mese. Se il prezzo di Bitcoin supera $50.000 entro quel mese, l'investitore può esercitare l'opzione per acquistare Bitcoin a $50.000, traendo potenzialmente profitto dalla differenza di prezzo.

### Opzioni Put

Un'opzione put dà al detentore il diritto di vendere l'asset sottostante al prezzo strike concordato alla data di scadenza o prima. I trader acquistano opzioni put quando si aspettano che il prezzo dell'asset sottostante scenda. Questo consente loro di trarre profitto da potenziali ribassi di prezzo senza dover vendere allo scoperto l'asset sottostante. In genere le opzioni put vengono anche utilizzate per coprirsi dai rischi al ribasso dei portafogli d'investimento.

> Un trader acquista un'opzione put su Ethereum con un prezzo strike di $3.000 con scadenza tra due settimane. Se il prezzo di Ethereum scende sotto $3.000 entro quel periodo, il trader può esercitare l'opzione per vendere Ethereum a $3.000, mitigando così le potenziali perdite.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Posizioni in Opzioni

Per ogni tipo di opzione, esistono due potenziali posizioni:

### **Opzione Long (Acquirente dell'opzione)**&#x20;

Questa posizione comporta il pagamento di un premio anticipato per acquisire l'opzione. Se l'opzione finisce in profitto, il detentore riceve un regolamento.

### **Opzione Short (Scrittore/Venditore dell'opzione)**

In questa posizione, il venditore riceve un premio anticipato per emettere l'opzione. Tuttavia, se l'opzione finisce in profitto (per l'acquirente; basato sul prezzo sottostante, il prezzo strike e il tipo di opzione), il venditore è obbligato a pagare un regolamento.

## Opzioni Americane vs. Europee

* **Opzioni Americane:** Possono essere esercitate in qualsiasi momento prima della data di scadenza. Questa flessibilità le rende più preziose delle opzioni europee.
* **Opzioni Europee:** Possono essere esercitate solo alla data di scadenza. Sono generalmente meno costose delle opzioni americane a causa della loro mancanza di flessibilità.

## Quando usare le Opzioni?

Ecco alcuni esempi di casi d'uso:

1. **Speculazione:** Un investitore ritiene che il prezzo di Bitcoin aumenterà nel mese successivo. Acquista opzioni call su Bitcoin per trarre profitto dall'atteso rialzo del prezzo.
2. **Hedging:** Un validatore di criptovalute vuole coprirsi dai potenziali ribassi di prezzo di Ethereum. Acquista opzioni put su Ethereum per proteggersi dalle perdite se il prezzo scende sotto un certo livello.
3. **Generazione di reddito:** Un investitore crypto che detiene una grande quantità di Ether decide di scrivere opzioni call sui propri asset, guadagnando premi pur partecipando a potenziali movimenti di prezzo al rialzo.

## Prezzi delle Opzioni

Il pricing delle opzioni è complesso e coinvolge vari fattori, con il modello Black-Scholes come il più comunemente utilizzato.&#x20;

I fattori chiave che influenzano il pricing delle opzioni includono:

* **Prezzo dell'Asset Sottostante:** Il prezzo di mercato corrente dell'asset sottostante.
* **Prezzo Strike:** Il prezzo a cui il detentore dell'opzione può acquistare o vendere l'asset sottostante.
* **Volatilità:** Il grado di fluttuazioni di prezzo nell'asset sottostante.&#x20;
* **Tempo alla Scadenza:** Il tempo rimanente fino alla scadenza dell'opzione.
* **Tassi d'Interesse:** Il tasso di rendimento privo di rischio.

Il pricing delle opzioni determina il premio/commissione che uno scrittore riceve quando un trader di opzioni acquista la sua opzione. Gli scrittori di opzioni sono esposti al rischio di pagare un regolamento se le loro opzioni scadono In-The-Money o ITM (profittevole per l'acquirente). Pertanto, i premi che guadagnano dagli acquirenti devono riflettere equamente la probabilità di un evento ITM.

I premi delle opzioni CLAMM di PancakeSwap derivano dal modello Black-Scholes con le seguenti ipotesi:

* Si assume che il tasso privo di rischio sia zero.
* La volatilità è basata sulla volatilità storica a 30 giorni dell'asset sottostante [usata come proxy per la volatilità implicita (IV)].

Alcune eccezioni includono:

* IV di $ETH e $BTC è presa direttamente da Deribit se i prezzi strike corrispondono. Se i prezzi strike non corrispondono, i più vicini strike superiore e inferiore da Deribit vengono ponderati in base al grado di scostamento per impostare la IV.
* $ARB usa la volatilità storica beta-based a 30 giorni calcolando il prezzo strike effettivo dell'asset base rispetto a $ETH per estrapolare la IV, moltiplicata per il beta dell'asset base rispetto a $ETH.

Gli asset con alta volatilità avranno un premio più costoso rispetto agli asset con minore volatilità, poiché c'è un rischio maggiore per gli scrittori dell'opzione di scadere ITM.

## Regolamento delle Opzioni

### Condizioni di Regolamento

* Il regolamento è determinato in base alla moneyness dell'opzione alla scadenza.
* Il regolamento viene calcolato solo se l'opzione è In-The-Money (ITM) durante l'esercizio.

### Condizioni ITM

* **Opzione Call:** Se il Prezzo Spot al Regolamento > Prezzo Strike
* **Opzione Put:** Se il Prezzo Spot al Regolamento < Prezzo Strike

### Calcolo del Regolamento

* **Opzione Call:** #Opzioni \* (Prezzo Spot al Regolamento - Prezzo Strike)
* **Opzione Put:** #Opzioni \* (Prezzo Strike - Prezzo Spot al Regolamento)

### Moneyness

La moneyness si riferisce al valore intrinseco di un'opzione, determinato confrontando il suo prezzo strike con il suo prezzo spot al momento dell'esecuzione.

### Classificazione

1. Out-of-The-Money (OTM):
   1. Un'opzione è OTM se il prezzo spot al regolamento differisce dal prezzo strike e non c'è valore da scambiare se il regolamento avviene immediatamente.
   2. Condizioni:
      1. Opzione Call: Prezzo Spot < Prezzo Strike
      2. Opzione Put: Prezzo Spot > Prezzo Strike

{% hint style="info" %}
Un'opzione call su $ETH con un prezzo strike di $2.000 sarebbe OTM se il prezzo spot è $1.800 ($1.800 < $2.000 ovvero OTM).
{% endhint %}

2. At-The-Money (ATM):
   1. Un'opzione è ATM se il prezzo spot al regolamento è uguale al prezzo strike e non c'è valore da scambiare se il regolamento avviene immediatamente.
   2. Condizioni: Sia per le Opzioni Call che Put: Prezzo Spot = Prezzo Strike

{% hint style="info" %}
Sia un'opzione call che put su $ETH con un prezzo strike di $1.800 sarebbero ATM se il prezzo spot è anch'esso $1.800 ($1.800 = $1.800 ovvero ATM).
{% endhint %}

3. In-The-Money (ITM):
   1. Un'opzione è ITM se il prezzo spot al regolamento differisce dal prezzo strike e c'è valore da scambiare se il regolamento avvenisse immediatamente.
   2. Condizioni:
      1. Opzione Call: Prezzo Spot > Prezzo Strike
      2. Opzione Put: Prezzo Spot < Prezzo Strike

{% hint style="info" %}
Un'opzione call su $ETH con un prezzo strike di $1.600 sarebbe ITM se il prezzo spot è $1.800 ($1.800 > $1.600 ovvero ITM).
{% endhint %}

Il regolamento guadagnato dall'acquirente dell'opzione equivale al collaterale perso dallo scrittore dell'opzione. Il regolamento esclude il premio dell'opzione pagato, che viene considerato nel calcolo dei profitti o delle perdite per gli acquirenti e gli scrittori di opzioni.
