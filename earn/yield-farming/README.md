# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

I Yield Farm permettono agli utenti di guadagnare CAKE supportando PancakeSwap tramite lo Staking di LP Token.

Consulta la nostra [guida su come usare i Farm](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) per iniziare con il farming.

Scopri [come trovare gli smart contract dei Farm](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Il Yield Farming può offrire ricompense migliori rispetto ai Syrup Pool, ma comporta il rischio di **Impermanent Loss**. Non è così spaventoso come sembra, ma vale la pena capirne il concetto prima di iniziare.

Dai un'occhiata a questo ottimo [articolo sull'Impermanent Loss](https://academy.binance.com/en/articles/impermanent-loss-explained) di Binance Academy per saperne di più.
{% endhint %}

## Calcolo delle ricompense

I calcoli dell'APR dei Yield Farm includono entrambi:

* **APR delle ricompense LP** guadagnato fornendo Liquidità e;
* **APR delle ricompense base del Farm** guadagnato mettendo in Staking gli LP Token nel Farm.

Perché? Perché quando metti in Staking i tuoi LP Token in un Farm per guadagnare CAKE, stai comunque fornendo Liquidità al Pool di Liquidità, quindi guadagni anche le ricompense LP!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Allora come calcoliamo queste cifre?

### Calcolo dell'APR base del Farm

L'**APR base del Farm** viene calcolato in base al moltiplicatore del Farm e alla quantità totale di Liquidità nel Farm -- questo è l'ammontare di CAKE distribuito al Farm.

### Calcolo dell'APR delle ricompense LP

Oltre a ciò, i farmer ricevono **ricompense LP** per aver fornito Liquidità. Ecco un esempio di calcolo delle **ricompense LP**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

Nel pair WBNB/BUSD qui sopra, vediamo questi valori:

**Liquidità:** $387.42M\
**Volume 24H:** $96.97M\
**Volume 7D:** 709.73M

* Calcola le commissioni annue
  * Usa il volume delle 24H per calcolare la **quota delle commissioni** dei fornitori di Liquidità nel Pool (basata sulla struttura delle commissioni di trading dello 0,17%):\
    $96.970.000\*0,17/100 = **$164.849**
  * Successivamente, usa quella **quota delle commissioni** per stimare le **commissioni annue** proiettate guadagnate dal Pool (basate sul volume attuale delle 24h):\
    $164.849\*365 = **$60.169.885**
* Ora possiamo usare le commissioni annue per calcolare l'**APR delle ricompense LP:** Si tratta delle **commissioni annue** divise per la **Liquidità:**\
  ($60.169.885/$387.420.000)\*100 = **15,53% APR ricompense LP**
