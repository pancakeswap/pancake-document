# ♾️ PancakeSwap Infinity

> Si vous êtes développeur ou si vous recherchez une documentation technique détaillée, veuillez consulter ce doc [https://developer.pancakeswap.finance/](https://developer.pancakeswap.finance/)

**PancakeSwap Infinity** est la dernière version de l'AMM PancakeSwap, conçue pour rendre le trading décentralisé plus rapide, moins coûteux et plus flexible. Elle repose sur une architecture modulaire qui permet une plus grande personnalisation et prend en charge différents types de pools de trading et de modèles de tarification.

Avec Infinity, les développeurs peuvent créer de nouvelles fonctionnalités plus facilement grâce aux « hooks » — de petits fragments de code qui s'exécutent lors d'actions clés du cycle de vie d'un pool. Cela permet des cas d'usage tels que des oracles personnalisés, des pools à frais dynamiques, des fonctionnalités avancées de trading et de gestion de Liquidité, et bien plus encore.&#x20;

Comparé à PancakeSwap v3, Infinity est plus économe en gas et pérenne. En découplant les fonctions fondamentales comme la comptabilité et la logique de trading, il permet l'intégration transparente de nouvelles courbes de tarification avec des capacités de hook — permettant au protocole d'évoluer sans nécessiter de redéploiement.

### ⭐️ Fonctionnalités Clés

1. Singleton
2. Flash Accounting
3. Hooks
4. Prise en charge des Tokens Natifs
5. Courbes de Tarification Personnalisées
6. ERC-6909
7. `donate()`

{% hint style="success" %}
**Open-source :** [PancakeSwap Infinity](https://github.com/pancakeswap/infinity-core) est publié sous licence open-source, encourageant les développeurs à innover, personnaliser et collaborer librement.
{% endhint %}
