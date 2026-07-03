# Hook de Frais Dynamiques

Le Hook de Frais Dynamiques officiel de PancakeSwap est conçu pour créer un échange de valeur plus équitable entre les Fournisseurs de Liquidité et les Traders. Il protège les LPs contre une perte impermanente (IL) excessive tout en maintenant l'efficacité du marché pour les traders.

Développé par l'équipe principale de PancakeSwap, ce hook est spécifiquement conçu pour offrir une alternative intelligente et adaptative aux modèles de frais fixes conventionnels.

#### 🔍 Pourquoi des Frais Dynamiques ?

Les grandes opérations d'arbitrage provoquent une plus grande divergence de prix dans les pools, augmentant l'IL pour les LPs. Notre modèle de frais dynamiques facture des frais proportionnellement plus élevés sur les grandes opérations d'arbitrage pour compenser ce risque — tout en laissant suffisamment de marge aux arbitragistes pour réaliser des profits et maintenir les prix alignés.

#### 📊 En quoi est-ce différent des autres modèles ?

D'autres modèles ont utilisé par le passé des données historiques pour estimer la volatilité et d'autres facteurs pour ajuster les frais. Cependant :

* Les données historiques sont un indicateur retardé et peuvent ne pas prédire avec précision la volatilité future.
* Les événements de marché externes (comme les changements réglementaires ou les fluctuations économiques) peuvent rendre les tendances passées peu fiables.
* Les modèles complexes à paramètres multiples risquent le surapprentissage — performant bien sur les données passées mais mal sur de nouvelles conditions inédites.

Notre approche est plus simple, adaptative et ancrée dans le comportement de trading en temps réel.

#### ⚙️ Comment ça fonctionne

* **Nous ne prédisons pas la volatilité ni d'autres facteurs macroéconomiques**\
  Au lieu de cela, notre modèle bénéficie intrinsèquement du comportement des arbitragistes dans différents régimes de marché :
  * **Forte volatilité :** Plus d'opérations d'arbitrage de plus grande taille → Frais plus élevés pour les LPs, couvrant une plus grande part de l'IL.
  * **Faible volatilité :** Moins d'opérations, plus petites → L'IL est naturellement plus faible, mais les LPs gagnent tout de même des frais plus élevés que dans un modèle à frais fixes.
* **Notre modèle utilise**
  * Un prix de pool à pondération exponentielle pour détecter les opérations d'arbitrage.
  * Une courbe de frais exponentielle basée sur l'impact sur le prix de chaque Swap.
  * Un plafond de frais maximum de 5% pour maintenir l'équité envers les traders.

{% hint style="success" %}
Cela garantit que les frais s'adaptent dynamiquement à l'impact des échanges tout en s'ajustant automatiquement aux conditions changeantes du marché.
{% endhint %}

* **Incitations équilibrées**\
  Les arbitragistes conservent toujours \~50% de leurs profits après les frais dynamiques, ce qui les incite à maintenir les prix du pool en ligne avec le marché.

#### 📌 Points Clés

* Aucune dépendance aux prédictions de volatilité ou d'autres facteurs macroéconomiques.
* S'adapte automatiquement à la volatilité du marché en fonction du comportement réel des échanges.
* Protège les LPs contre l'IL sur une base par-Swap.
* Maintient de fortes incitations pour les arbitragistes à combler les écarts de prix.
* Bénéficie aux traders grâce à une Liquidité plus profonde et des frais de base plus faibles.
