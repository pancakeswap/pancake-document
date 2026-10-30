# Shared Inventory Hook

Le Shared Inventory Hook (SIH) officiel de PancakeSwap est conçu pour permettre à un seul pool de capital de faire du market-making sur tous les pools qui partagent ses tokens, au lieu d'immobiliser une liquidité distincte dans chacun. Il offre aux traders des cotations plus profondes et un price impact plus faible, tout en permettant aux fournisseurs de liquidité de déployer moins de capital pour la même couverture.

Conçu par l'équipe centrale de PancakeSwap, ce hook est taillé pour les émetteurs d'actifs et les teneurs de marché qui souhaitent coter plusieurs paires on-chain sans fragmenter leur inventaire.

#### 🔍 Pourquoi un Shared Inventory ?

Fournir de la liquidité à plusieurs paires de la manière conventionnelle implique d'immobiliser un capital dédié dans des pools séparés, dont la majeure partie reste inactive entre les trades. SIH conserve au contraire un solde par token et ne l'injecte comme liquidité que lorsqu'un swap en a besoin ; le même capital peut ainsi soutenir tous les pools qui partagent ce token.

#### 📊 En quoi est-ce différent des autres modèles ?

La liquidité concentrée conventionnelle exige d'engager la totalité du capital dans un seul pool. Les autres approches inter-pools, comme les couches de règlement à soldes virtuels, se situent généralement en dehors de l'AMM lui-même, de sorte que la liquidité peut ne pas être visible comme profondeur de pool on-chain ni routée directement par les agrégateurs.

La liquidité de SIH entre dans le pool PancakeSwap Infinity CLAMM et en sort via le hook à chaque swap ; elle apparaît donc comme une véritable profondeur de pool que les routeurs peuvent voir et exécuter.

#### ⚙️ Fonctionnement

* **Injection just-in-time (JIT)**\
  Avant chaque swap, le hook mint une position de liquidité concentrée configurée dans le pool ; une fois le swap exécuté, il la burn et règle le résultat net. La position n'existe que pendant la durée d'un seul swap, et le solde est libre de servir immédiatement le pool suivant qui en a besoin.
* **Un solde, plusieurs pools**\
  L'inventaire correspond au solde de tokens du hook lui-même, il n'y a aucun dépôt par pool. Tout token destiné à être utilisé dans plus d'un pool est partagé entre tous ces pools.

{% hint style="success" %}
Cela dissocie la profondeur cotée par un pool du capital que celui-ci détient directement : un hook financé peut coter une liquidité profonde et resserrée sur plusieurs pools qui partagent un token.
{% endhint %}

* **Hook configurable**\
  Pour chaque pool qu'il dessert, le hook conserve une configuration indépendante et ajustable de la fourchette de prix et de la profondeur. Déplacer la bande ne nécessite qu'une mise à jour de configuration, ce qui permet de recentrer facilement les cotations autour d'un prix de référence mouvant.

#### 📌 Points clés

* Un seul solde de tokens partagé soutient tous les pools qui utilisent ce token. Ajouter un nouveau pool ne mobilise aucun capital supplémentaire.
* Entièrement on-chain et composable : la liquidité de SIH est une véritable profondeur de pool, routable aussi bien par PancakeSwap que par des agrégateurs tiers.
* Les traders bénéficient de cotations plus profondes et d'un price impact plus faible sur les gros montants ; les opérateurs perçoivent les mêmes frais de trading avec une fraction du capital conventionnel.
