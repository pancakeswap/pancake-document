# 🔀 Swaps Cross-chain

Les Swaps Cross-chain permettent aux utilisateurs d'échanger des tokens entre différentes chaînes de manière fluide — le tout en une seule transaction simplifiée.

Les Swaps Cross-chain sont pris en charge entre :

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Les transactions sont ultra-rapides — elles se terminent généralement en quelques secondes à moins d'une minute.**
{% endhint %}

***

### 🔍 Comment ça fonctionne

1. L'utilisateur sélectionne les chaînes Source / Destination et les tokens correspondants
2. Le routeur PancakeSwap calcule la route la plus efficace
3. Les Swaps sont exécutés en utilisant les pools de Liquidité de PancakeSwap (v2, v3, Infinity, StableSwaps) sur les chaînes source et destination
4. Le Bridging est géré via nos protocoles partenaires : [Across](https://across.to/) (pour EVM <> EVM), [Relay](https://relay.link/bridge) (pour SOL <> EVM)

{% hint style="success" %}
**Les Swaps Cross-chain sont disponibles pour tout token disposant d'une Liquidité suffisante sur les chaînes source et destination.**
{% endhint %}

***

### 💸 Frais

* **PancakeSwap ne facture aucun frais pour les transactions Cross-chain.**
* Les frais comprennent :
  1. **Frais de Trading :** Appliqués pour les Swaps dans les pools de Liquidité sur les chaînes source et destination
  2. **Frais de Bridge :** Payés aux relayeurs pour le Bridging des actifs

***

### 🎯 Que sont les Intents ?

Les Intents permettent aux utilisateurs de définir le résultat souhaité sans se préoccuper de la manière dont il est atteint.

Exemples d'Intents :

* « Échanger 1 ETH sur Base contre au moins 3000 USDC sur Arbitrum »

Sans les Intents, un utilisateur devrait manuellement :

* Bridger l'ETH vers Arbitrum
* Trouver un DEX offrant le meilleur prix ETH → USDC

{% hint style="success" %}
**Avec les Intents — le système gère tout automatiquement.**
{% endhint %}

**Avantages de la conception basée sur les Intents :**

* Expérience utilisateur fluide
* Temps de transaction plus rapides
* Transactions en un seul clic

***

### 🔐 Audits

Nous avons mené plusieurs cycles d'audit avec des noms reconnus dans le domaine de la sécurité cross-chain :

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
