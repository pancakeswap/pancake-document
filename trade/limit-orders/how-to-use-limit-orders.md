---
hidden: true
---

# Come usare gli Ordini Limite

## Cosa sono gli Ordini Limite

Un ordine limite è uno strumento che consente agli utenti di acquistare o vendere asset a un prezzo specificato o migliore, anziché fare affidamento sul prezzo di mercato al momento dell'esecuzione. In un ordine limite, mentre il prezzo è garantito, l'esecuzione dell'ordine non lo è — gli ordini limite verranno eseguiti solo se il prezzo soddisfa i requisiti dell'ordine.

## Come impostare un ordine limite

1. Vai alla pagina Swap e seleziona l'opzione ordine limite cliccando su "LIMIT", oppure usa questo link: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Seleziona i token "Da" e "A" che desideri tradare. In questo esempio abbiamo scelto USDC e ETH rispettivamente, il che significa che vogliamo acquistare ETH con USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Inserisci l'importo che desideri tradare. Nota che il prezzo limite mostrerà il prezzo di mercato corrente che stimerà poi la quantità di output dei token di destinazione (ETH)
2. Imposta il prezzo limite desiderato. I trade verranno eseguiti SOLO quando il prezzo di mercato disponibile è migliore o uguale al prezzo limite. La quantità di output del token di destinazione si aggiornerà di conseguenza.

Nell'esempio seguente, desideriamo acquistare ETH quando il prezzo è $1.900 o migliore. La quantità di ETH ricevuta sarà uguale o superiore a 0,037 ETH. Solo le offerte uguali o migliori di questo importo saranno idonee a eseguire l'ordine. Questo importo tiene conto dei costi del gas e delle commissioni. &#x20;

{% hint style="info" %}
Nota importante: Poiché le commissioni vengono pagate dall'importo del token di output, il prezzo limite include le commissioni gas e di trading, quindi gli utenti dovrebbero tenerne conto quando impostano il prezzo. Ad esempio, le commissioni gas di un ordine molto piccolo possono totalizzare una percentuale molto grande dell'output dell'ordine, riflettendo un prezzo limite effettivo che non è competitivo con il prezzo di mercato spot.
{% endhint %}

3.  Premi "Place order". Controlla i dettagli del tuo ordine, accetta la dichiarazione di non responsabilità e premi "Confirm order".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Una volta completata la transazione, potrai vedere il tuo ordine nella sezione della cronologia degli ordini, sotto "Open orders". \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Gli ordini aperti possono essere cancellati in qualsiasi momento espandendo l'ordine e cliccando sul pulsante "Cancel Order".

Cose da considerare:

* Il tuo ordine potrebbe non essere eseguito se il prezzo di mercato disponibile è peggiore del prezzo limite che hai impostato.
* I trade si basano su un protocollo decentralizzato che utilizza taker off-chain che competono per eseguire gli ordini. Questi taker sono autorizzati a richiedere una commissione, che il protocollo rimuove dal taker vincente dai token di output.&#x20;
* I taker possono tenere conto delle commissioni gas per le tue transazioni quando impostano le loro commissioni, il che può comportare fluttuazioni negli importi delle commissioni.
* Quando si specifica un prezzo limite, gli utenti vedranno nell'UI la quantità minima di token di destinazione che riceveranno se l'ordine viene eseguito. Solo i taker che fanno offerte uguali o migliori di questo importo saranno idonei a eseguire l'ordine. Questo importo tiene conto dei costi del gas e delle commissioni di trading.
