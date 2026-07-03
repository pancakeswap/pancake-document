# Infinity StableSwap

### Présentation

Infinity StableSwap est un type de pool au sein de [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity), optimisé pour échanger des actifs dont les prix sont censés rester proches — comme les stablecoins (ex. USDC/USDT) ou les actifs étroitement ancrés (ex. paires de tokens wrappés, tokens de staking liquide et tokens de restaking liquide).

Il est propulsé par un hook StableSwap fonctionnant sur l'architecture Infinity, inspiré du design StableSwap NG de Curve. Il est actuellement disponible sur BNB Chain, avec des projets d'expansion vers d'autres chaînes à l'avenir.

***

### Fonctionnement

Infinity StableSwap utilise une courbe d'invariant stable — un hybride entre somme constante et produit constant :

* Près de l'ancrage → la courbe se comporte comme une somme constante, ce qui entraîne un très faible Glissement pour les échanges proches de 1:1.
* Loin de l'ancrage → la courbe se rapproche progressivement du produit constant, ce qui aide à restaurer l'équilibre et protège le pool lors de grands déséquilibres ou d'événements de désancrage.

Cela la rend particulièrement efficace pour les paires stables où la précision du prix et la faiblesse du Glissement sont primordiales.

***

### Caractéristiques principales

Optimisé pour les Swaps proches de l'ancrage : Faible Glissement pour les échanges entre actifs dont les prix sont censés être approximativement équivalents.

Apport de Liquidité simplifié : Les fournisseurs de Liquidité (LP) déposent les deux tokens de manière proportionnelle sans avoir à sélectionner ou gérer des plages de prix — contrairement aux pools CLAMM.

Tokens LP ERC-20 : Votre position LP est représentée par un token ERC-20 standard, ce qui facilite son utilisation dans des programmes de rendement, des campagnes de points et d'autres protocoles DeFi.

Frais dynamiques : Les frais peuvent s'ajuster en fonction des conditions d'équilibre du pool, en récompensant les échanges qui aident à ramener le pool vers l'équilibre et en décourageant ceux qui aggravent le déséquilibre.

Prise en charge du routage Infinity : Les échanges sont automatiquement routés via les pools StableSwap lorsqu'ils offrent le meilleur prix — aucune étape supplémentaire n'est requise pour les traders.

Paramètre d'amplification (A) ajustable : Les opérateurs de pool peuvent augmenter ou diminuer progressivement le paramètre A pour s'adapter aux conditions changeantes du marché, avec des garde-fous pour éviter les changements brusques.

***

### Paramètres du pool

Le comportement du pool StableSwap est régi par un petit ensemble de paramètres, généralement définis lors de la création du pool.

#### Coefficient d'amplification (A)

Le paramètre A contrôle à quel point le pool reste proche de l'ancrage au prix 1:1.

| Valeur A | Effet                                                                                    |
| -------- | ---------------------------------------------------------------------------------------- |
| A élevé  | Courbe plus resserrée autour de l'ancrage ; faible Glissement près de 1:1 ; plus sensible au déséquilibre |
| A faible | Courbe plus souple ; se comporte davantage comme un pool standard à produit constant     |

Règle générale : Utilisez un A élevé pour les actifs avec un ancrage fort et fiable (ex. USDC/USDT). Utilisez un A faible pour les actifs avec des ancrages plus souples ou plus volatils (ex. certaines paires LST).

Le paramètre A peut être progressivement augmenté ou diminué par l'opérateur du pool sur une période de temps définie. Les modifications sont appliquées progressivement avec des garde-fous pour éviter les manipulations ou les changements de prix soudains.

#### Multiplicateur de frais hors-ancrage

Un paramètre supplémentaire qui ajuste les frais effectifs lorsque le pool s'éloigne de l'équilibre. Il contribue à décourager les échanges qui déséquilibreraient davantage le pool et rend celui-ci plus robuste lors de périodes de stress du marché ou d'événements de désancrage.

#### Frais dynamiques

Des frais sont prélevés sur chaque Swap et versés aux fournisseurs de Liquidité. Infinity StableSwap prend en charge les frais dynamiques — ce qui signifie que les frais effectifs sur un échange donné peuvent varier en fonction de l'état actuel du pool (par exemple, si l'échange améliore ou détériore l'équilibre).

***

### Infinity StableSwap vs. Classic StableSwap

Si vous avez déjà utilisé le StableSwap existant de PancakeSwap, voici ce qui change — et ce qui reste identique.

| <p><br></p>                        | Classic StableSwap                                        | Infinity StableSwap                                                            |
| ---------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Courbe de tarification             | Invariant stable (hybride somme constante / produit constant) | Même courbe d'invariant stable, même faible Glissement près de l'ancrage   |
| Tokens LP ERC-20                   | ✅ Oui                                                     | ✅ Oui                                                                          |
| Création de pool                   | Nécessite une configuration manuelle par l'équipe         | Sans permission — n'importe qui peut créer un pool                             |
| Frais de Swap                      | Fixes par paire (ex. 0,01% pour USDC/USDT)                | Frais dynamiques — s'ajustent selon l'impact de l'échange sur l'équilibre du pool |
| Paramètre d'amplification (A)      | Statique — défini une fois, ne peut être modifié          | Ajustable — peut être augmenté ou diminué progressivement dans le temps        |
| Multiplicateur de frais hors-ancrage | ❌ Non supporté                                           | ✅ Supporté — aide à protéger le pool lors des événements de désancrage        |
| Efficacité du gas                  | Standard                                                  | Améliorée — bénéficie du Singleton et de la comptabilité Flash d'Infinity      |

#### Ce qui reste identique

* La courbe de tarification principale et le faible Glissement près de l'ancrage sont inchangés.

#### Ce qui est nouveau et meilleur

* Création de pool sans permission : Les pools peuvent être créés sans nécessiter de configuration manuelle de l'équipe.
* Les frais dynamiques protègent les LP : Au lieu d'un frais fixe unique, les frais peuvent s'ajuster par échange selon que celui-ci améliore ou nuit à l'équilibre du pool — rendant le pool plus résilient lors de conditions volatiles.
* Paramètre A adaptable : Le coefficient d'amplification peut être ajusté dans le temps à mesure que les conditions du marché évoluent, plutôt que d'être figé lors du déploiement.

***

### Questions fréquentes

Quels actifs sont adaptés à Infinity StableSwap ?

Les actifs dont les prix sont censés rester proches : stablecoins (USDC, USDT, BUSD, etc.), équivalents wrappés du même actif (ex. WBTC/cbBTC), et certaines paires de tokens de staking liquide / restaking liquide (LST/LRT) où la volatilité de l'ancrage est faible.

<br>

En quoi Infinity StableSwap est-il différent de l'ancien StableSwap de PancakeSwap ?

Infinity StableSwap est implémenté en tant que hook sur PancakeSwap Infinity, ce qui signifie qu'il hérite de tous les avantages de l'infrastructure Infinity, notamment des coûts de gas réduits via le Singleton et la comptabilité Flash, ainsi qu'un système de frais plus flexible. Il prend également en charge de nouvelles fonctionnalités comme les frais dynamiques et l'amplification ajustable que l'ancien StableSwap ne proposait pas.

<br>

Dois-je gérer ma position dans le temps ?

Non. Contrairement aux pools CLAMM, vous n'avez pas besoin de définir ou d'ajuster des plages de prix. Votre Liquidité est toujours active sur l'ensemble de la courbe, donc il n'y a aucun risque que votre position sorte de la plage.

<br>

Puis-je fournir de la Liquidité avec un seul token ?

Oui, les dépôts en token unique sont supportés.

<br>

Comment fonctionnent les frais dynamiques ?

Dans Infinity StableSwap, les frais de Swap peuvent varier par échange en fonction de l'impact de cet échange sur l'équilibre du pool. Les échanges qui contribuent à ramener le pool vers l'équilibre peuvent payer des frais effectifs plus faibles, tandis que les échanges qui aggravent le déséquilibre peuvent payer des frais plus élevés. Cela est conçu pour protéger les LP et maintenir des conditions de pool plus saines.



***



## Créer un pool Infinity StableSwap



Les pools Infinity StableSwap sont sans permission — n'importe qui peut en créer un sans avoir besoin de l'approbation de l'équipe PancakeSwap.

<br>

### Étape par étape

1\. Rendez-vous sur la page Farm/Liquidité et cliquez sur Créer un pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Sélectionnez StableSwap Pool parmi les types de pools disponibles.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Sélectionnez la paire de tokens pour votre pool (ex. USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Paramètres du pool

| Paramètre                     | Fonction                                                                                                       |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Frais de Swap                 | Frais prélevés sur chaque Swap, versés aux LP. Par défaut, 0,01% pour les paires stables très proches.         |
| A (Amplification)             | Contrôle à quel point la courbe reste proche de l'ancrage. Plus élevé = Glissement plus faible près de 1:1, mais plus sensible au déséquilibre. |
| Multiplicateur de frais hors-ancrage | Augmente les frais lorsque le pool s'éloigne de l'équilibre, décourageant les échanges qui aggravent le déséquilibre. |
| Durée de la moyenne mobile    | Fenêtre temporelle utilisée pour calculer le prix moyen mobile lors des ajustements de frais dynamiques.       |

⚠️ Définissez les paramètres avec soin. Des paramètres incorrects — notamment un A très élevé sur un actif à ancrage souple — peuvent augmenter le risque pour les LP. En cas de doute, utilisez le préréglage correspondant à votre type d'actif et évitez de modifier les paramètres Avancés.

<br>

Choisissez un préréglage de paramètres de pool — cela définit automatiquement les paramètres recommandés pour votre type d'actif. Vous pouvez toujours les ajuster manuellement via le bouton Avancé.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Préréglage                                       | A    | Multiplicateur de frais hors-ancrage | Durée de la moyenne mobile (secondes) |
| ------------------------------------------------ | ---- | ------------------------------------- | -------------------------------------- |
| Stablecoins rachetables en monnaie fiduciaire    | 1000 | 10                                    | 600                                    |
| Stablecoins à garantie crypto                    | 100  | 12,5                                  | 600                                    |
| Tokens de restaking liquide                      | 500  | 10                                    | 600                                    |

<br>

&#x20; Vous ne savez pas lequel choisir ?&#x20;

* Utilisez Stablecoins rachetables en monnaie fiduciaire pour les paires comme USDC/USDT
* Utilisez Stablecoins à garantie crypto pour les stablecoins algorithmiques ou adossés à des cryptomonnaies
* Utilisez Tokens de restaking liquide pour les paires LRT comme stkBNB/WBNB.

<br>

5\. Saisissez le montant du dépôt initial pour amorcer la Liquidité. Les deux montants de tokens doivent être égaux (ex. 1 USDC et 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Cliquez sur Aperçu du pool, vérifiez vos paramètres, cochez la case de confirmation, puis cliquez sur Créer le pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
