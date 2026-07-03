# 📈 Analytics (Pagina Info)

## Pagina Info&#x20;

Visualizza il sito di analytics nativo di PancakeSwap qui: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Tutti i dati delle metriche principali provengono dall'Indexer interno di PCS, che a sua volta raccoglie dati dagli eventi attivati quando il contratto viene chiamato.&#x20;

Per la dimensione della data nell'indexer interno di PancakeSwap, utilizziamo l'ora internazionale standard (UTC) per le statistiche giornaliere. Pertanto, quando l'asse orizzontale sulla Dashboard mostra una data, rappresenta la data nell'ora internazionale standard (UTC).<br>

## Metriche Principali

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume (Volume di Trading):** Monitoriamo i dati giornalieri per ogni coppia di trading e i dati di trading giornalieri per ogni token. Il volume di trading giornaliero è determinato moltiplicando il volume di trading di ogni token per il giorno per il suo prezzo.

**Total Value Locked:** Ottieni tutti i pool dall'Indexer interno e leggi il reserve\_usd o total\_value\_locked\_usd da ogni pool.&#x20;

**Prezzo:** Nell'Indexer interno di PCS, utilizziamo diversi pool di base per calcolare i prezzi relativi agli USD. Il pool principale è il pool di trading in stablecoin, dove utilizziamo il pool di trading con il volume più alto come pool di base e calcoliamo il prezzo USD della stablecoin in base al peso del volume di trading. Inoltre, il pool di trading del token base rispetto alla stablecoin della chain è considerato anch'esso un pool di base per fornire il prezzo in USD.

_I token che non sono nella whitelist o non sono abbinati a token nella whitelist sono esclusi da questi calcoli._

<br>
