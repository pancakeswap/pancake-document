---
description: CAKE zwischen Ethereum, BNB Chain, Aptos und vielen weiteren Chains bridgen
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging zu/von EVMs (Neue Seite): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging zu/von Aptos (V1 Bridge): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## Was ist Bridging in der Kryptowelt?

* Bridging bezeichnet in der Kryptowelt den Vorgang, Vermögenswerte zwischen verschiedenen Blockchain-Netzwerken zu übertragen.
* Es verbessert die Interoperabilität und ermöglicht den Transfer von Daten und Vermögenswerten zwischen verschiedenen Netzwerken.

\
Hier sind einige Gründe, weshalb Sie möglicherweise Bridging nutzen möchten:

* Andere Kryptowährungs-Token kaufen
* Ein NFT prägen, das nur auf einem bestimmten Netzwerk verfügbar ist
* Geld sparen durch günstigere Transaktionen
* Eine dApp nutzen, die nur auf einem anderen Netzwerk verfügbar ist

***

## CAKE, ein Multi-Chain-Token

Mit unserer Multi-Chain-Expansion und -Bereitstellung ist CAKE nun ein Multi-Chain-Token, der auf BNB Chain heimisch ist, aber auch auf Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB und Aptos verfügbar ist.

CAKE auf einer der anderen Chains entspricht CAKE auf BNB Smart Chain. Er kann jederzeit zwischen diesen Chains im Verhältnis 1:1 und ohne jegliche CAKE-Gebühr gebrückt werden.

**Bitte beachten Sie, dass es nur ein CAKE gibt.** Es gibt keine verschiedenen Versionen von CAKE auf unterschiedlichen Chains. Der Gesamtvorrat an CAKE über alle Blockchains hinweg ist auf 400 Mio. begrenzt, wie in diesem [Abstimmungsvorschlag](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5) beschrieben.

***

## Was ist die PancakeSwap Bridge?

Die PancakeSwap Bridge ist ein praktisches, integriertes Tool, mit dem Sie Vermögenswerte direkt über die PancakeSwap-Oberfläche zwischen verschiedenen Blockchains verschieben können. Anstatt externe Bridge-Seiten aufzurufen, können Sie unterstützte Token zwischen Chains wie BNB Chain, Ethereum, Base, Arbitrum und weiteren bridgen – alles an einem Ort.

Die PancakeSwap Bridge wird von vertrauenswürdigen Drittanbietern betrieben und fungiert als **Aggregator**, der die beste Route basierend auf Preis, Geschwindigkeit und Zuverlässigkeit auswählt.

Informationen zum Bridging von CAKE finden Sie in den Tutorials und FAQ der folgenden Abschnitte.

***

## 🔗 Funktionsweise

### Bridging über Aggregatoren

Die PancakeSwap Bridge fungiert als intelligente Schicht über vertrauenswürdigen Bridge-Protokollen von Drittanbietern. Wenn Sie eine Bridge-Übertragung initiieren, überprüft PancakeSwap:

* Mehrere integrierte Bridges auf optimale Routen
* Sendet Ihre Transaktion an den ausgewählten Anbieter

Bridging ist non-custodial – Ihre Vermögenswerte werden nicht über das Custody von PancakeSwap abgewickelt. Übertragungen werden direkt von den Bridge-Anbietern verwaltet.

### Unterstützte Bridge-Anbieter

Derzeit integrieren wir:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Hinweis: Jeder Anbieter verfügt über unterschiedliche Bridging-Mechanismen, unterstützte Chains, Gebühren und Limits.

***

### Unterstützte Chains und Token

#### Derzeit unterstützte Chains

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (V1-Seite)

#### Für das Bridging verfügbare Token

Verfügbare Token variieren je nach Chain und Route. Zu den gängigen unterstützten Token gehören (unter anderem):

* CAKE
* USDT
* USDC
* ETH

***

#### Einschränkungen & Ausschlüsse

Einige Token werden aufgrund von Bridge-Einschränkungen oder Liquiditätsproblemen möglicherweise nicht unterstützt. Diese wurden für eine optimale Nutzererfahrung herausgefiltert. Beispiele:

**Für cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Für deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Die oben genannten sind lediglich Beispiele. Die tatsächlich verfügbaren Token pro Chain werden direkt in der Bridge-Benutzeroberfläche angezeigt._

***

### 💸 Gebühren und Kosten

#### Bridge-Gebühren

* Werden vom jeweiligen Bridge-Anbieter erhoben
* Umfassen typischerweise eine geringe Gebühr pro Übertragung
* Werden klar angezeigt, bevor Sie Ihre Bridge bestätigen

***

#### Gaskosten

* Sie zahlen Gasgebühren auf der **Quell-Chain**, um die Transaktion zu initiieren
* Einige Anbieter erfordern möglicherweise auch Gas auf der **Ziel-Chain**
* **Tipp:** Halten Sie immer native Token (z. B. ETH, BNB) auf beiden Seiten der Bridge bereit

***

#### Mindestbeträge & Einschränkungen

Einige Bridge-Routen setzen voraus:

* **Mindest- und Höchstbeträge für das Bridging** (z. B. mindestens 10 USDC)
* **Unterstützte Token-Dezimalstellen oder -Formate** (z. B. nur ERC-20-Token)

Die Benutzeroberfläche erkennt und zeigt ungültige Übertragungen automatisch an.

***

### ⏳ Transaktionszeiten & Nachverfolgung

#### Wie lange dauert Bridging?

Bridge-Übertragungen werden in der Regel innerhalb weniger **Minuten** abgeschlossen, abhängig von:

* Quell- und Ziel-Chains
* Netzwerkauslastung
* Effizienz des Bridge-Anbieters

#### Ihre Übertragung verfolgen

Nach dem Absenden können Sie den Transaktionsstatus über die anbieterspezifischen Explorer einsehen:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Wenn eine Transaktion längere Zeit feststeckt, prüfen Sie den entsprechenden Explorer oder wenden Sie sich über unsere [sozialen Kanäle](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) an unsere Administratoren für [Hilfe](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Tipps vor dem Bridging

* **Halten Sie Gas-Token auf beiden Chains bereit** (z. B. ETH + BNB)
* **Starten Sie mit kleinen Beträgen**, wenn Sie zum ersten Mal bridgen
* Vermeiden Sie Bridging in Zeiten hoher Chain-Auslastung (kann zu höheren Gasgebühren führen)
* Bestätigen Sie die Token-Kompatibilität auf beiden Chains
* Überprüfen Sie immer Quell- und Zielnetzwerke

***

### Zusätzlich: CAKE Omni-Chain Fungible Token (OFT) Adressen

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
