# 🔀 Cross-Chain Swaps

Cross-Chain Swaps ermöglichen es Nutzern, Token nahtlos zwischen verschiedenen Chains zu swappen – alles in einer einzigen, optimierten Transaktion.

Cross-Chain Swaps werden zwischen folgenden Chains unterstützt:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Transaktionen sind blitzschnell – sie werden in der Regel innerhalb von Sekunden bis unter einer Minute abgeschlossen.**
{% endhint %}

***

### 🔍 Funktionsweise

1. Der Nutzer wählt die Quell-/Ziel-Chain sowie die Quell-/Ziel-Token aus
2. Der PancakeSwap Router berechnet die effizienteste Route
3. Swaps werden unter Verwendung der PancakeSwap-Liquiditätspools (v2, v3, Infinity, StableSwaps) auf der Quell- und Ziel-Chain ausgeführt
4. Das Bridging erfolgt über unsere Partnerprotokolle: [Across](https://across.to/) (für EVM <> EVM), [Relay](https://relay.link/bridge) (für SOL <> EVM)

{% hint style="success" %}
**Cross-Chain Swaps sind für jeden Token mit ausreichender Liquidität auf beiden Chains verfügbar.**
{% endhint %}

***

### 💸 Gebühren

* **PancakeSwap erhebt keine Gebühren für Cross-Chain-Transaktionen.**
* Die Gebühren setzen sich zusammen aus:
  1. **Trading-Gebühr:** Anfallend für Swaps innerhalb von Liquiditätspools auf der Quell- und Ziel-Chain
  2. **Bridge-Gebühr:** An Relayer für das Bridging von Assets gezahlt

***

### 🎯 Was sind Intents?

Intents ermöglichen es Nutzern, ihr gewünschtes Ergebnis zu definieren, ohne sich um die Ausführung kümmern zu müssen.

Beispiele für Intents:

* „Swap 1 ETH auf Base für mindestens 3000 USDC auf Arbitrum"

Ohne Intents müsste ein Nutzer manuell:

* ETH zu Arbitrum bridgen
* Eine DEX mit dem besten ETH → USDC-Preis finden

{% hint style="success" %}
**Mit Intents übernimmt das System alles automatisch.**
{% endhint %}

**Vorteile des Intent-basierten Designs:**

* Nahtlose Nutzererfahrung
* Schnellere Transaktionszeiten
* Ein-Klick-, Einzeltransaktionen

***

### 🔐 Audits

Wir haben mehrere Audit-Runden mit renommierten Namen im Cross-Chain-Sicherheitsbereich durchgeführt:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
