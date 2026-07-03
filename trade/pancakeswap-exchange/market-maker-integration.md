---
hidden: true
---

# Market-Maker-Integration

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Market-Maker-Integration auf Ethereum

PancakeSwap ist mit Market Makern auf Ethereum und Binance Smart Chain integriert, um Tradern die Ausführung von Trades zu geringeren Kosten zu ermöglichen.

Zusätzlich zum AMM können Trades auf PancakeSwap nun an ausgewählte, auf einer Whitelist stehende Market Maker weitergeleitet werden, wenn diese eine bessere Ausführung als die aktuellen AMM-Preise bieten. Diese Weiterleitung erfolgt automatisch durch einen [Smart Router](smart-router-v2/), sodass Trades nur dann an Market Maker weitergeleitet werden, wenn diese aktiv bessere Preise anbieten. Dort, wo der AMM wettbewerbsfähiger ist, werden Trader zur Ausführung an die AMMs weitergeleitet.

Es gibt 2 Szenarien, in denen Market Maker auf PancakeSwap tätig sind.

**Szenario 1: Vorhandene AMM-Liquiditätspools**

Wenn PancakeSwap bereits Liquidität für ein bestimmtes Token-Paar (z. B. WETH/USDC) im AMM hat, fragt PancakeSwap Market Maker nach einem Angebot für denselben Trade. Der Smart Router von PancakeSwap leitet die Trade-Anfrage dann je nach aktuell bestem Preis entweder an den AMM oder an die Market Maker weiter.

**Szenario 2: Keine vorhandenen AMM-Liquiditätspools**

In einem solchen Szenario leitet der Smart Router den Trade automatisch an die Market Maker weiter. Dies hält Projekte jedoch nicht davon ab, anschließend ihren AMM-Liquiditätspool einzurichten und mit uns zusammenzuarbeiten, um dezentralisierte DEX-Liquidität aufrechtzuerhalten.

### Gebühren

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap erhebt von Tradern keine Gebühren für über uns ausgeführte Trades, die von Market Makern abgewickelt werden. PancakeSwap erhält jedoch **0,05%** **Trading-Gebühren** von Whitelist-Market-Makern für die von ihnen ausgeführten Volumina. PancakeSwap erhält eine reduzierte **Trading-Gebühr von 0,01%**, wenn die ausgeführten Trades zwischen Stablecoin-Paaren stattfinden. Bitte beachten Sie die nachfolgende Gebührenaufschlüsselung:<br>

<table><thead><tr><th width="178">Trades</th><th width="138">Trading-Gebühren</th><th width="182">PCS-Gebühr von MM</th><th width="147">CAKE-Burn</th><th align="center">PancakeSwap Treasury</th></tr></thead><tbody><tr><td>Überbrückte Coins aus anderen Netzwerken</td><td>Nicht zutreffend</td><td>0,25%</td><td>0,083%</td><td align="center">0,167%</td></tr><tr><td>Nicht-Stablecoin auf Ethereum (z. B. ETH/USDC)</td><td>Nicht zutreffend</td><td>0,05%</td><td>0,017%</td><td align="center">0,033%</td></tr><tr><td>Nicht-Stablecoin auf BSC (z. B. BNB/USDT)</td><td>Nicht zutreffend</td><td>0,05%</td><td>0,017% </td><td align="center">0,033%</td></tr><tr><td>Stablecoin zu Stablecoin auf Ethereum</td><td>Nicht zutreffend</td><td>0,01%</td><td>0,003%</td><td align="center">0,007%</td></tr></tbody></table>

#### Derzeit unterstützte Assets

Die folgenden Assets werden derzeit unterstützt und können sich je nach Market Maker erhöhen oder verringern:

**Auf Ethereum**

* **Hauptwährungen:** WETH, WBTC
* **Stablecoins:** USDT, USDC, DAI, BUSD
* **Andere beliebte ERC-20-Assets:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Auf Binance Smart Chain:**

* **Hauptwährungen:** BNB, ETH, BTCB
* Nicht-native BNB-Token: ARB, OP

Bitte beachten Sie, dass Market Maker im Gegensatz zu AMMs nicht in der Lage sind, beliebige Beträge zu handeln, und die Beträge, die sie bereit sind auszuführen, von ihrer eigenen Liquidität abhängen. Es ist nicht ungewöhnlich, dass sehr große Aufträge manchmal nicht vollständig erfüllt werden können. Wir empfehlen Nutzern, die Angebote sorgfältig zu prüfen, um sicherzustellen, dass jeder Trade den Preis und die Menge gemäß ihren Anforderungen widerspiegelt.

**Ausfallzeiten der Market Maker**

Von Market Makern wird nicht erwartet, dass sie rund um die Uhr Angebote stellen. Es gibt Situationen (z. B. wichtige Wirtschaftsereignisse, Systemaktualisierungen), in denen der Market Maker vorübergehend nicht verfügbar sein kann, um ein Angebot zu unterbreiten. Bitte beachten Sie, dass diese Token in diesen Zeiträumen einfach nicht handelbar sind. Wir empfehlen Nutzern, eine Weile zu warten, bis der Market Maker wieder online ist.

#### FAQ

**F.** Werden die Market Maker auf Aptos integriert?

**A.:** Möglicherweise. Wir starten die Market-Maker-Integration vorerst nur auf Ethereum und Binance Smart Chain, um die Liquidität für eine bessere Nutzererfahrung zu steigern. Wir werden andere Chains weiterhin beobachten.

**F.** Wie wird PancakeSwap Einnahmen erzielen, wenn es Nutzern keine Gebühr berechnet?

**A.:** PancakeSwap erhebt keine Gebühren von Nutzern, erhält jedoch eine kleine Provision von Market Makern und nutzt diese, um den CAKE-Rückkauf und -Burn zu finanzieren.

**F.** Werden Liquiditätsanbieter weiterhin LP-Gebühren verdienen?

**A.:** Ja, Liquiditätsanbieter werden weiterhin 0,17% Trading-Gebühren-Belohnung (LP-Gebühren) und Yield aus den CAKE-Farms verdienen.

**F.** Werden die Market Maker Liquidität zum AMM hinzufügen? Wird dies den APR senken?

**A.:** Market Maker verwalten ihre eigene, separate Liquidität und verdienen daher keinen APR aus Trades auf dem AMM. Nur LPs verdienen Gebühren und APRs durch die Bereitstellung von Liquidität für die AMM-Pools.

**F.** Ich stelle Liquidität auf Ethereum PancakeSwap bereit. Muss ich etwas unternehmen?

**A.:** Nein, Sie müssen nichts tun. Sie werden weiterhin LP-Gebühren für Trades verdienen, die über den AMM ausgeführt werden, und weiterhin den Yield in CAKE erhalten.

**F.** Wie kann jemand Market Maker werden?

**A.:** Wir prüfen und arbeiten mit Market Makern auf individueller Basis zusammen. Bitte wenden Sie sich direkt an uns oder über unsere Administratoren, wenn Sie Interesse an einer Zusammenarbeit haben.
