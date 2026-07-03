# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

Le CLAMM permet aux fournisseurs de Liquidité d'allouer leur capital dans des **plages de prix spécifiques**. Cela conduit à :

* **Une meilleure efficacité du capital** : Plus de Liquidité aux prix de trading actifs.
* **Une Liquidité plus profonde** : Meilleure exécution pour les traders.
* **Une gestion LP active** : Les LPs doivent ajuster leurs positions lorsque les prix évoluent.
* **Un risque de perte impermanente plus élevé** pour les positions hors plage.

{% hint style="info" %}
Le CLAMM fonctionne selon la formule du produit constant (X \* Y = K). Chaque position de Liquidité est non fongible et représentée sous forme de NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM ou « Bin Pool »)

Le LBAMM implémente des **bins de prix discrets**, chacun contenant de la Liquidité à un niveau de prix spécifique. Le LBAMM suit la **formule de la somme constante (X + Y = K).**



**Caractéristiques clés :**

* Échanges à **0 impact sur le prix** au sein d'un bin.
* **Liquidité fongible** (la Liquidité dans chaque bin est un token ERC-20).
* **Coûts de gas inférieurs** pour ajuster les positions LP.
* **Prise en charge de différentes formes de Liquidité** (ex. asymétrique, uniforme).
* Plus adapté aux paires à **faible volatilité** en raison de la courbe de tarification plate par bin.

> 🥞 **PancakeSwap est le premier protocole à proposer des pools LBAMM avec des hooks.**

{% hint style="success" %}
Les pools CLAMM et LBAMM prennent tous deux en charge les **hooks**, qui permettent aux développeurs de personnaliser le comportement des pools. Les types de pools sont extensibles via de nouveaux Gestionnaires de Pools, qui peuvent être ajoutés sans redéploiement du protocole.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Fonctionnalité</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Courbe de Tarification</strong></td><td>Produit Constant (X * Y = K)</td><td>Somme Constante (X + Y = K)</td></tr><tr><td><strong>Token de Liquidité</strong></td><td>Non fongible (NFT)</td><td>Fongible (ERC-20 par bin)</td></tr><tr><td><strong>Idéal Pour</strong></td><td>Paires à forte/faible volatilité</td><td>Paires à faible volatilité</td></tr><tr><td><strong>Avantages</strong></td><td><ol><li>Efficacité du capital</li><li>Économe en gas pour les plages larges/complètes</li><li>Largement adopté</li></ol></td><td><ol><li>0 impact sur le prix dans un bin</li><li>Gestion LP moins coûteuse</li><li>Formes de Liquidité flexibles</li></ol></td></tr><tr><td><strong>Prise en Charge des Hooks</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Frais

PancakeSwap Infinity prend en charge un système de frais flexible et extensible via des paramètres de frais Statiques et Dynamiques. Cette configuration donne aux créateurs de pools et aux LPs des outils puissants pour optimiser différentes stratégies de trading et profils de risque.

#### 🔁 Frais Dynamiques

* Les Frais Dynamiques sont déterminés en temps réel via des contrats hook.
* Ces frais peuvent fluctuer en fonction de facteurs externes tels que la volatilité, le volume de trading, le statut de l'utilisateur (ex. détention de CAKE) ou toute logique personnalisée codée dans le hook.
* Les pools avec des frais dynamiques doivent activer ce paramètre lors de la création du pool et attacher un hook capable de modifier les frais via `beforeSwap`.
* Une fois qu'un pool est initialisé, le type de frais (dynamique ou statique) est immuable.

Les frais dynamiques offrent une flexibilité maximale et optimisent les structures de frais pour les LPs et les traders en fonction des conditions du marché.

#### 📌 Frais Statiques

* Les pools à Frais Statiques ont des frais fixes définis lors de la création du pool.
* Ces frais ne peuvent pas être modifiés après l'initialisation du pool.
* Adaptés aux cas d'usage plus simples ou lorsque la prévisibilité de la structure des frais est importante.<br>

**🔒 Plafonds de Frais Maximum :**

* Pools CLAMM : Jusqu'à 100% (principalement pour des cas d'usage spécialisés ou expérimentaux)
* Pools LBAMM : Plafonné à 10%<br>

**🏛 Frais de Protocole (pour les pools à frais statiques) :**

* PancakeSwap applique des frais de protocole sur les pools Infinity
* 33% des frais LP, plafonné à 0,4%

| **Frais LP**           | **Frais de Protocole** |
| ---------------------- | ---------------------- |
| 1%                     | 0,33%                  |
| 2%                     | 0,4% (plafonné)        |
| Pool à Frais Dynamiques | 0%                    |

#### 🛠️ Notes de Configuration pour les Créateurs de Pools

* Lors de l'initialisation d'un pool via PoolManager, le créateur doit choisir :
  * Si le pool utilise des frais statiques ou dynamiques
  * Si un contrat hook est attaché (requis pour les frais dynamiques)

Ces paramètres sont permanents et définissent le comportement du pool tout au long de sa durée de vie.
