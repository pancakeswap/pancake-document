# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### Comment les multiplicateurs bCAKE sont-ils calculés ?

Vous pouvez remarquer que vous obtenez des multiplicateurs de boost bCAKE différents selon les farms dans lesquelles vous stakez.

C'est parce que les multiplicateurs de bCAKE - Farm Boosters sont calculés à l'aide des métriques suivantes lors de l'activation ou de l'actualisation :

* `userLpBalanceInFarm` : Le montant de Liquidité que vous stakez dans la farm.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : Le montant total de Liquidité stakée dans la farm ou le montant actif actuel de Liquidité dans le pool LP V3. bCAKE choisit le chiffre le plus petit entre les deux.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : Le nombre de veCAKE en temps réel que vous détenez
* `veCAKE.totalSupply` : L'offre totale de veCAKE en temps réel

Le multiplicateur est calculé selon la méthode suivante :

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` et `constantB` sont définis par la cuisine et peuvent être ajustés à l'avenir en fonction des retours de la communauté et des conditions de marché. `constantB` varie entre les différentes farms pour compenser les différences de prix de LP.

`constantA` et `constantB` peuvent être récupérés via :

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Mais :

{% hint style="info" %}
**En résumé**

Plus vous souhaitez booster de LP (Liquidité)

Plus vous devez verrouiller de CAKE sur des durées longues
{% endhint %}

### Pourquoi mes multiplicateurs changent-ils même après l'activation ?

Veuillez noter que **toute action d'un utilisateur sur la position de farming ou le pool de Staking CAKE mettra automatiquement à jour votre multiplicateur de boost** en fonction des données et statistiques les plus récentes des farms et du pool de Staking CAKE, notamment :

* Staker/Dé-staker une position dans/depuis la farm
* Récolter des récompenses CAKE depuis la farm
* Prolonger la durée de votre Staking CAKE
* Ajouter davantage de CAKE à votre position de Staking à terme fixe
* Convertir votre position de Staking CAKE en mode flexible

{% hint style="warning" %}
Veuillez noter :&#x20;

Pour garantir l'équité et prévenir les abus potentiels utilisant des données obsolètes, le Farm booster est conçu pour être sans permission et gouverné par la communauté. Par conséquent, **n'importe qui** peut appeler la fonction `updateLiquidity(address _tokenId)` sur le contrat MasterChef V3 pour actualiser les multiplicateurs de boost de n'importe quel utilisateur avec les données les plus récentes.

De plus, la cuisine surveillera également toutes les positions de farming bCAKE activées et actualisera toute position dont le multiplicateur est obsolète.
{% endhint %}

### Pourquoi ne puis-je pas booster une position ?

1. Le Farm booster n'est disponible que pour des farms sélectionnées. Davantage de farms seront rendues disponibles à l'avenir. Pour l'instant, **recherchez le chiffre APR vert avec une icône de fusée verte.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. En raison de l'implication de plusieurs contrats, certaines interactions de contrats nécessitent un peu plus de tokens de gas (BNB). Veillez donc à disposer de suffisamment de BNB dans votre Portefeuille. Si l'erreur persiste, essayez d'augmenter manuellement la limite de gas de la transaction.

### Quel est le multiplicateur de boost bCAKE maximum que je peux obtenir ?

Actuellement, le boost maximum qu'un utilisateur peut obtenir pour un Farm booster est de 2,5x, ce qui lui offre 2,5x les APR d'origine.

Veuillez noter que le boost maximum que vous pouvez obtenir varie selon les types de Liquidité que vous souhaitez staker :

* V3 : 2x maximum
* V2, StableSwap : 2,5x maximum
* Gestionnaires de positions : 2,5x maximum

### Comment puis-je augmenter mes multiplicateurs de boost bCAKE ?

* Ajouter davantage de CAKE dans la position de Staking veCAKE
* Prolonger ou renouveler la durée de votre position de Staking veCAKE

En résumé :

**Stakez plus de CAKE, stakez plus longtemps**

[En savoir plus sur le calcul des multiplicateurs de boost bCAKE](faq.md#how-are-the-bcake-multipliers-calculated).

### D'où proviennent les récompenses CAKE supplémentaires boostées ?

**Rassurez-vous, aucune émission supplémentaire n'est allouée pour rendre bCAKE possible.**

Comme pour le Staking veCAKE CAKE, bCAKE booste la part individuelle des utilisateurs par rapport aux autres.

Même si l'APR de base peut diminuer après le déploiement de bCAKE, les Chefs estiment qu'il s'agit d'un bon compromis car cela bénéficie aux fidèles amateurs de CAKE en boostant leur rendement de farming, crée davantage de demande pour CAKE et constitue une excellente incitation au Staking CAKE.

### Pourquoi le multiplicateur que je reçois est-il faible ?&#x20;

bCAKE - Farm booster fonctionne en évaluant à la fois votre position de Staking veCAKE et votre position de farming de Liquidité par rapport aux autres utilisateurs. En résumé :

> Si les utilisateurs souhaitent booster davantage de Liquidité dans la farm, ils doivent verrouiller plus de CAKE pour des durées plus longues dans le pool.

Cette conception garantit que les avantages ne sont pas réservés aux grands détenteurs, mais à tout utilisateur disposant d'une position de Staking CAKE significative par rapport à sa position de farming.

Pour en savoir plus sur le calcul du multiplicateur, cliquez [ici](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Pourquoi seul un nombre limité de farms bénéficie-t-il du booster ?

Étant donné que bCAKE implique la mise à jour de l'un des produits principaux de PancakeSwap, à savoir le Yield Farming de Liquidité, les Chefs souhaitent adopter une approche plus prudente et progressive pour le lancement.

Par conséquent, lors de la phase initiale de lancement du produit, de nombreux paramètres sont très conservateurs, notamment le nombre de farms que les utilisateurs peuvent booster, quelles farms ils peuvent booster, ainsi que le paramètre de difficulté pour recevoir le multiplicateur de boost.

**Les Chefs ajusteront les paramètres en fonction des retours de la communauté.**

### **bCAKE V3 est-il audité ?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE a été audité par des auditeurs internes et externes.

Consultez les rapports d'audit ici : [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
