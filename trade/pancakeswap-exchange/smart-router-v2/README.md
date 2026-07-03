---
hidden: true
---

# Smart Router (V2)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap Smart Router ist ein Routing-Algorithmus, der den AMM und StableSwap (BNB Chain) sowie den AMM und Market Maker (Ethereum) verknüpft, um bessere Liquidität und bessere Preise zu bieten. Er verwendet einen intelligenten Order-Routing-Algorithmus, der Trades über mehrere Pools ausführt, um den besten Preis für Trader zu finden. Weitere Informationen zu StableSwap finden Sie [hier](/broken/pages/nNPogTZMxocdyFIBYbkE) und zur Market-Maker-Integration [hier](../market-maker-integration.md).

Die Kitchen wird StableSwap-Paare schrittweise einführen, um das Produkt weiter zu testen und zu verbessern.

## Warum sollte ich den Smart Router für meine AMM-Swaps verwenden?&#x20;

* Swappen Sie Ihre Stablecoins oder andere Paare mit ähnlichen Asset-Preisen effizienter mit denselben Handelsschritten.
* Swappen Sie gegen Market Maker, die möglicherweise eine bessere Ausführung als der normale PancakeSwap AMM bieten.
* Mit der StableSwap-Funktion ist die Trading-Kursabweichung geringer als beim normalen AMM.
* Die StableSwap-Trading-Gebühren sind im Vergleich zum normalen AMM niedriger.

## In Entwicklung&#x20;

* Verbesserte Benutzeroberfläche für die Ausgabe.
* Split-Routen für effizientere Trades. Z. B. leitet der Router 50% des Paares je nach Trade-Größe und Liquidität an eine andere Route weiter, um Gebühren zu sparen.&#x20;
