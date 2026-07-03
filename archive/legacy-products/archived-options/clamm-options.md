# CLAMM Options

{% hint style="danger" %}
\[ARCHIVIATO] Options – A partire dall'11 marzo 2025\
Se hai ancora liquidità da prelevare, fallo immediatamente visitando https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



Le CLAMM Options presentano un approccio innovativo al trading di opzioni on-chain, offrendo ai fornitori di liquidità una piattaforma per capitalizzare sulla liquidità v3 di PancakeSwap. Questo consente loro di utilizzare la liquidità sia per i pool di liquidità v3 che per vendere opzioni, guadagnando commissioni di trading AMM standard, premi sulle opzioni e ricompense aggiuntive, mentre i trader possono utilizzare questa liquidità per acquistare opzioni in stile americano su vari token.

Realizzato dal team di Stryke (ex Dopex), il protocollo di opzioni CLAMM introduce un sistema efficiente di doppia fornitura di liquidità per i trader di opzioni (acquirenti) e i pool v3 di PancakeSwap.

Ecco un quadro strutturato di come funzionano le CLAMM Options:

1. Gli LP che aggiungono liquidità alle CLAMM Options contribuiscono contemporaneamente al pool v3 di PancakeSwap designato all'interno del loro intervallo di prezzo scelto.
2. Quando un trader di opzioni (acquirente) avvia una posizione, la liquidità viene estratta dal pool v3 per facilitare la vendita delle opzioni. Il rispettivo LP diventa quindi un venditore di opzioni e riceve un premio.
3. La liquidità non utilizzata dagli acquirenti di opzioni risiede nel pool v3 di PancakeSwap, potenzialmente guadagnando commissioni di trading.
4. Il payoff dalla vendita di opzioni e dalla fornitura di liquidità in un pool v3 rispecchia la stessa perdita impermanente, garantendo agli utenti un rischio non superiore rispetto al metodo convenzionale di aggiungere liquidità ai pool v3.
5. Gli LP affrontano alcuni rischi, poiché la liquidità potrebbe rimanere inutilizzata a causa della minore domanda di acquisto di opzioni. Inoltre, poiché la liquidità viene aggiunta al pool in un intervallo inattivo, potrebbe non guadagnare alcuna commissione.

Le opzioni CLAMM in stile americano di PancakeSwap debutteranno sulla chain Arbitrum, offrendo flessibilità con diverse durate di scadenza che vanno da 1 ora a 24 ore.

| **Mercati**                | ARB/USDC, ETH/USDC e wBTC/USDC    |
| -------------------------- | --------------------------------- |
| **Tipi di opzioni**        | Call e Put                        |
| **Prezzi strike**          | Basati sui tick del pool v3       |
| **Durate di scadenza**     | 1H, 2H, 6H, 12H e 24H            |

**Condizioni di esercizio:** Gli utenti possono esercitare le posizioni prima della chiusura per evitare che le opzioni in-the-money scadano senza valore. L'auto-esercizio può essere abilitato per realizzare automaticamente i profitti alla scadenza, evitando ulteriori azioni.

### Guida passo per passo

Ecco la guida passo per passo su come usare le CLAMM Options di PancakeSwap.

**Per i Trader:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Per gli LP:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
