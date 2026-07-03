# Fonctionnalités Clés

### 1️⃣ Singleton

Dans PancakeSwap v3, chaque pool de Liquidité possédait son propre contrat, ce qui rendait la création de pools et les Swaps sur plusieurs pools plus coûteux.

Infinity résout ce problème en implémentant le modèle Singleton. Désormais, tous les pools résident dans un seul contrat appelé le PoolManager. Ce changement réduit les coûts de gas de création de pool jusqu'à 99% et rend les Swaps multi-hops (des Swaps passant par plusieurs pools) beaucoup moins coûteux en évitant les transferts de tokens inutiles.

#### ⚙️ **Comment ça fonctionne :**

* Les données de chaque pool sont stockées dans un contrat partagé à l'aide d'un identifiant de pool unique.
* La création d'un nouveau pool n'est plus qu'une mise à jour d'état, et non un déploiement de contrat complet.
* Les Swaps entre pools sont plus rapides et consomment moins de gas.<br>

Cette approche Singleton, combinée à d'autres optimisations comme Flash Accounting et ERC-6909, contribue à faire de PancakeSwap Infinity l'une des plateformes DEX les plus économes en gas disponibles aujourd'hui.

***

### ⚡️ Flash Accounting

Flash Accounting est une optimisation puissante de PancakeSwap Infinity qui contribue à réduire les frais de gas lors de transactions complexes telles que les Swaps multi-hops et les modifications de Liquidité.

Dans les versions antérieures (comme v3), les tokens étaient déplacés dans et hors de chaque pool à chaque étape d'une transaction. Cela entraînait des coûts de gas élevés, en particulier pour les Swaps multi-hops.

Avec Flash Accounting, cela n'est plus nécessaire. Au lieu de déplacer les tokens après chaque étape, PancakeSwap Infinity suit tous les mouvements de tokens en interne et n'effectue qu'un seul transfert final à la fin de l'ensemble de la transaction. Cela permet d'économiser beaucoup de gas.

#### ⚙️ **Comment ça fonctionne :**

* Lorsque vous interagissez avec Infinity (par ex., en effectuant un Swap ou en ajoutant de la Liquidité), le système calcule le solde net de tokens que vous devez ou recevez.
* Ces soldes nets de tokens sont stockés temporairement à l'aide du Transient Storage, une nouvelle fonctionnalité introduite avec la mise à niveau Cancun d'Ethereum (EIP-1153).
* Le Transient Storage est moins coûteux que le stockage traditionnel car il ne dure que le temps de la transaction — aucune écriture ou lecture permanente n'est nécessaire.

***

### 🪙 Prise en charge des Tokens Natifs

Avec l'introduction de l'architecture Singleton et du Flash Accounting, PancakeSwap Infinity prend désormais en charge les tokens de gas natifs (ex. BNB, ETH) directement dans les pools de Liquidité — plus besoin de les envelopper (wrap) ou de les désenvelopper (unwrap).

#### ✅ Points Clés

* **Pools de Tokens Natifs Directs :** Vous pouvez désormais créer des pools comme ETH/USDC, BNB/CAKE sans avoir besoin de WETH ou WBNB.
* **Économe en Gas :** Les transferts de tokens natifs sont \~50% moins coûteux que les transferts de tokens ERC-20, ce qui entraîne des coûts de gas réduits pour les Swaps et les actions de Liquidité.<br>

**Précédemment supprimé, maintenant réactivé :** La prise en charge des tokens natifs était absente dans les versions antérieures en raison de la complexité d'implémentation et de la fragmentation de la Liquidité.

***

### 📈 Courbes de Tarification Personnalisées

PancakeSwap Infinity donne aux développeurs le pouvoir de créer des modèles de tarification personnalisés pour les pools — allant au-delà du modèle traditionnel utilisé dans la plupart des AMMs.

{% hint style="success" %}
**Les développeurs peuvent créer de nouveaux comportements de Swap et des modèles de Liquidité entièrement nouveaux, adaptés à des types d'actifs ou des stratégies de trading spécifiques.**
{% endhint %}

#### 🔧 Que sont les Courbes de Tarification Personnalisées ?

Les courbes de tarification personnalisées permettent aux développeurs de :

* Contourner la logique native du gestionnaire de pool, en créant des pools avec des comportements de Swap définis sur mesure.
* Modifier la façon dont les montants de tokens sont calculés pour les Swaps ou les modifications de Liquidité.
* Intégrer des mécanismes de frais personnalisés, tels que :
  * Frais de retrait de Liquidité
  * Remises ou pénalités basées sur la stratégie

Tout cela est rendu possible grâce aux callbacks de hook before/after swap, qui peuvent intercepter et modifier dynamiquement les paramètres de Swap.

#### 🛠 Exemples de Cas d'Usage

* **Courbes StableSwap :** Concevoir des courbes plus plates autour d'un ratio de prix 1:1, réduisant l'impact sur le prix entre des actifs comme USDC et USDT.
* **RWAs :** Créer des comportements personnalisés pour différents types d'actifs à offre dynamique.
* **Frais au Niveau du Hook :** Facturer des frais uniques différents des frais au niveau du pool, comme des frais de développeur.
* **Modèles de Risque Personnalisés :** Ajuster la tarification pour refléter la volatilité, les données d'oracle ou des métriques externes.

{% hint style="info" %}
Dans les versions AMM précédentes (ex. PancakeSwap v2/v3), la logique de tarification était codée en dur et rigide. L'architecture de PancakeSwap Infinity débloque la possibilité de créer des pools plus efficaces en capital et plus adaptés.
{% endhint %}

#### 🔍 Flexibilité pour les Développeurs

* Les développeurs peuvent déployer des contrats hook personnalisés pour remplacer la logique de tarification.
* Les callbacks de hook tels que `beforeSwap` et `afterSwap` permettent un contrôle total sur la façon dont les deltas de tokens sont calculés et appliqués.

***

### 🧮 ERC-6909 : Comptabilité Multi-Tokens Efficace

PancakeSwap Infinity adopte [ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), un standard de token léger et économe en gas conçu pour la comptabilité interne de plusieurs tokens au sein d'un seul contrat. Il remplace de nombreuses opérations ERC-20 traditionnelles par des primitives de mint et de burn — entraînant des économies de gas significatives et des flux de transactions simplifiés.

#### ⚙️ Comment ça fonctionne

Plutôt que de déplacer les tokens dans et hors du protocole à chaque interaction, les tokens ERC-6909 représentent des soldes internes :

* Mint : Lorsque les utilisateurs déposent des tokens ou effectuent un échange, ils peuvent choisir de recevoir des tokens ERC-6909 comme créances.
* Burn : Plus tard, au lieu de transférer à nouveau des tokens ERC-20, les utilisateurs peuvent simplement brûler ces tokens ERC-6909 pour régler les soldes ou financer de nouvelles opérations.

Ce modèle réduit considérablement le besoin de transferts de tokens externes, qui entraînent généralement des coûts de gas plus élevés et interagissent avec une logique tierce (ex. les vérifications de liste noire d'USDC).

#### 🪙 Avantages de ERC-6909

<table><thead><tr><th width="262.9921875">Fonctionnalité</th><th width="497.7421875">Avantage</th></tr></thead><tbody><tr><td>✅ Créances de Solde Interne</td><td>Pas besoin de transférer des tokens à plusieurs reprises entre l'utilisateur et le contrat</td></tr><tr><td>✅ Mint/Burn Économe en Gas</td><td>Surcharge constante quel que soit le token, aucun appel de contrat externe</td></tr><tr><td>✅ Plus Simple que ERC-1155</td><td>Taille de code réduite, pas de callbacks, pas d'exigences de transfert groupé</td></tr><tr><td>✅ Prise en Charge Multi-Tokens</td><td>Un seul contrat peut suivre plusieurs types de tokens avec des soldes isolés</td></tr><tr><td>✅ Compatible avec PoolManager</td><td>Élimine les approbations et transferts ERC-20 redondants</td></tr></tbody></table>

#### 🚀 Cas d'Usage

* **Traders à haute fréquence :** Évitez les transferts coûteux en gas et interagissez directement en utilisant les soldes internes.
* **Gestionnaires de Liquidité :** Ouvrez et fermez des positions plus efficacement sans mouvements de tokens excessifs.

#### 💡 Points Importants

* Les utilisateurs optent pour le flux ERC-6909 lorsqu'ils n'ont pas besoin de régler immédiatement les transferts de tokens.
* Les soldes internes peuvent être consolidés et réglés en net ultérieurement, offrant aux utilisateurs avancés un plus grand contrôle et une plus grande flexibilité.

***

### 💸 Méthode Donate

La méthode `donate()` permet aux utilisateurs d'inciter directement les fournisseurs de Liquidité in-range au sein d'un pool en faisant des dons de tokens. Cette méthode s'appuie sur le système de comptabilité des frais du pool pour faciliter les paiements, garantissant que seuls les tokens du pool sont pris en charge.

#### 🔹 Fonctionnalités Clés :

* **Paiements Directs aux LPs :** Les dons sont faits directement aux fournisseurs de Liquidité, récompensant ceux qui maintiennent la Liquidité dans la plage active du pool.
* **Prend en Charge Uniquement les Tokens du Pool :** La méthode `donate()` ne prend en charge que les dons dans les tokens du pool, car elle exploite le système de comptabilité des frais pour assurer une distribution correcte.
* **Ouverte à Tous les Utilisateurs :** N'importe quel utilisateur peut appeler la méthode `donate()`, permettant à quiconque d'inciter la fourniture active de Liquidité.

Bien que la méthode `donate()` soit un outil puissant pour inciter les LPs, les donateurs doivent être conscients que leurs dons peuvent faire l'objet de frontrunning de la part d'autres utilisateurs. Cela peut se produire lorsqu'un utilisateur ajoute rapidement de la Liquidité au pool juste avant qu'un don soit effectué, recevant ainsi une partie des fonds donnés.

Pour prévenir le frontrunning, les donateurs peuvent avoir besoin d'envisager des stratégies supplémentaires lors de la conception de leurs mécanismes de don, telles que :

* S'assurer que les dons se produisent d'une manière qui minimise la possibilité de frontrunning opportuniste.
* Ajouter des délais temporels ou des conditions spécifiques (en utilisant les callbacks de hook before/after donate) qui garantissent que les dons ne sont pas exploités de cette façon.
