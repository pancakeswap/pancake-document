# Hooks

{% hint style="info" %}
Si vous êtes développeur ou si vous recherchez une documentation technique détaillée sur le développement d'un hook, veuillez consulter [cette page](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Les hooks sont des extensions puissantes qui permettent aux développeurs d'étendre et de personnaliser le comportement des pools de Liquidité dans PancakeSwap Infinity. Considérez-les comme des « plugins » ou des « widgets » qui ajoutent de nouvelles fonctionnalités aux pools de Liquidité.

#### 🔍 Que sont les Hooks ?

* Les hooks sont des contrats intelligents externes créés par n'importe qui — développeurs, protocoles ou membres de la communauté — et attachés à des pools de Liquidité pour améliorer ou modifier leur comportement.
* Chaque pool ne peut avoir qu'un seul hook attaché, mais un même hook peut servir plusieurs pools.
* Les hooks peuvent exécuter du code personnalisé avant ou après des actions clés telles que :
  * L'initialisation d'un pool
  * Un Swap
  * L'ajout/suppression de Liquidité
  * Un Don (Donate)<br>

**⛓️ Comment fonctionnent les hooks :**

* Un hook est sélectionné lors de la création du pool et ne peut pas être modifié ultérieurement.
* Un contrat hook se déclenche sur des actions spécifiques (Swap, ajout de Liquidité, etc.) et exécute une logique avant ou après ces actions telle que définie dans le contrat.
* Par exemple, un hook pourrait :
  * Offrir des réductions sur les frais de Swap aux détenteurs de CAKE
  * Facturer des frais personnalisés et distribuer des récompenses
  * Activer une nouvelle logique de Swap comme des stableswaps ou des ordres de style TWAMM<br>

#### ⚙️ Callbacks de Hooks

Les hooks peuvent être déclenchés à dix moments spécifiques. Les développeurs peuvent choisir ceux qu'ils souhaitent implémenter :

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Ces callbacks permettent d'implémenter un comportement hautement personnalisable et modulaire via les hooks.

#### 🔧 Deux Types de Hooks

**Type 1 : Aucune Autorisation Requise**

Ces hooks s'exécutent automatiquement et ne nécessitent pas d'autorisation de l'utilisateur. Ils sont déclenchés par des actions comme les Swaps ou les modifications de Liquidité.



Exemples :

* Frais Dynamiques : Ajustement des frais de Swap en fonction de la volatilité du marché
* Remises sur Frais : Offrir des réductions aux utilisateurs détenteurs de CAKE ou effectuant des volumes élevés



Exemple de Flux (Remise sur Frais CAKE) :

1. Un utilisateur initie un Swap.
2. Le hook vérifie son solde de CAKE via le callback hook `beforeSwap`.
3. Si l'utilisateur détient suffisamment de CAKE selon les seuils définis, il bénéficie d'une réduction de 50% sur les frais du pool.
4. Le reste de la transaction se déroule normalement.<br>

{% hint style="success" %}
Ces hooks ne nécessitent pas d'interface spéciale ni d'interaction supplémentaire. Les avantages sont appliqués automatiquement.
{% endhint %}

**Type 2 : Autorisation Utilisateur Requise**

Ces hooks nécessitent que les utilisateurs interagissent directement avec eux, fournissent une autorisation et peuvent nécessiter le transfert de fonds, souvent pour créer ou gérer des positions.



Exemples :

* Ordres Limites : Exécuter un Swap uniquement lorsque le prix cible est atteint.
* TWAMM : Fractionner de grands ordres en plus petits morceaux pour une meilleure exécution.
* Gestion Active de Liquidité : Gérer automatiquement les positions LP pour des rendements optimaux.



Exemple de Flux (Hook d'Ordre Limite) :

1. L'utilisateur interagit directement avec le contrat hook (pas via l'interface de Swap habituelle).
2. Il saisit des détails comme le prix limite, la paire de tokens, le montant.
3. Le hook émet un token de reçu représentant l'ordre.
4. Plus tard, lorsque le prix du pool atteint la cible, le hook exécute l'ordre via `afterSwap`.
5. L'utilisateur peut retourner le token de reçu pour réclamer les actifs échangés.

{% hint style="info" %}
Ces hooks nécessitent souvent une interface personnalisée et les utilisateurs doivent faire confiance au contrat hook et l'approuver pour qu'il détienne leurs fonds.
{% endhint %}

#### 🚀 Cas d'Usage et Innovation

Les hooks ouvrent des possibilités illimitées, notamment :

* AMMs personnalisés (par ex., courbes stablecoin)
* Récompenses de liquidity mining
* Stratégies de trading automatisées, gestion de Liquidité
* Ordres limites on-chain, autres types d'ordres
* Tarification dynamique et ajustements des frais
* Stratégies LP d'optimisation du rendement<br>

Grâce aux hooks, les développeurs peuvent créer une toute nouvelle expérience DeFi en utilisant l'infrastructure existante de PancakeSwap Infinity — accélérant le développement et réduisant les coûts.
