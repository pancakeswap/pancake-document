---
hidden: true
---

# Smart Router (V2)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap Smart Router è un algoritmo di routing che collega l'AMM e lo StableSwap (BNB Chain), e l'AMM e i market maker (Ethereum), per fornire liquidità e prezzi migliori. Utilizza un algoritmo di routing degli ordini intelligente che esegue scambi su più pool per trovare il miglior prezzo per i trader. Per ulteriori informazioni su StableSwap [clicca qui](/broken/pages/nNPogTZMxocdyFIBYbkE) e per l'integrazione con i Market Maker [clicca qui](../market-maker-integration.md).

La cucina distribuirà gradualmente coppie StableSwap per testare e migliorare ulteriormente il prodotto.

## Perché dovrei usare Smart Router per i miei Swap AMM?&#x20;

* Fai Swap delle tue stablecoin o di altre coppie con prezzi di asset simili in modo più efficiente con gli stessi passaggi di scambio.
* Fai Swap con i market maker, che possono offrire un'esecuzione migliore rispetto al normale AMM di PancakeSwap.
* Con la funzione StableSwap, lo Slippage di trading è inferiore rispetto al normale AMM.
* Le commissioni di trading di StableSwap sono inferiori rispetto al normale AMM.

## In Lavorazione&#x20;

* Interfaccia migliorata per l'output.
* Percorsi divisi per scambi più efficienti. Ad es. il Router invia il 50% della coppia su un percorso diverso per risparmiare sulle commissioni in base alla dimensione del trade e alla liquidità.&#x20;
