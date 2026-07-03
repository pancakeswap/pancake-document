# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Les Yield Farms permettent aux utilisateurs de gagner des CAKE tout en soutenant PancakeSwap en stakant des jetons LP.

Consultez notre [guide d'utilisation des Farms](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) pour commencer à farmer.

Apprenez [comment trouver les contrats intelligents des Farms](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Le Yield Farming peut offrir de meilleures récompenses que les Syrup Pools, mais il comporte un risque de **Perte Impermanente**. C'est moins effrayant que cela n'y paraît, mais il vaut la peine de comprendre ce concept avant de commencer.

Consultez cet excellent [article sur la Perte Impermanente](https://academy.binance.com/en/articles/impermanent-loss-explained) de la Binance Academy pour en savoir plus.
{% endhint %}

## Calcul des récompenses

Le calcul de l'APR des Yield Farms inclut à la fois :

* **L'APR des récompenses LP** obtenu en fournissant de la Liquidité ; et
* **L'APR de base des récompenses de la Farm** obtenu en stakant des jetons LP dans la Farm.

Pourquoi ? Parce que lorsque vous stakez vos jetons LP dans une Farm pour gagner des CAKE, vous continuez à fournir de la Liquidité au Pool de Liquidité, ce qui vous permet également de percevoir des récompenses LP !

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Comment calculons-nous ces chiffres ?

### Calcul de l'APR de base des récompenses de la Farm

L'**APR de base de la Farm** est calculé en fonction du multiplicateur de la Farm et du montant total de Liquidité dans la Farm — il s'agit de la quantité de CAKE distribuée à la Farm.

### Calcul de l'APR des récompenses LP

En plus de cela, les farmers reçoivent des **récompenses LP** pour avoir fourni de la Liquidité. Voici un exemple de calcul des **récompenses LP** :

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

Dans la paire WBNB/BUSD ci-dessus, nous observons les valeurs suivantes :

**Liquidité :** 387,42 M$\
**Volume 24H :** 96,97 M$\
**Volume 7J :** 709,73 M$

* Calcul des frais annuels
  * Utilisez le volume sur 24H pour calculer la **part des frais** revenant aux fournisseurs de Liquidité dans le Pool (basé sur une structure de frais de trading de 0,17 %) :\
    96 970 000 $ × 0,17/100 = **164 849 $**
  * Ensuite, utilisez cette **part des frais** pour estimer les **frais annuels projetés** gagnés par le Pool (sur la base du volume actuel sur 24H) :\
    164 849 $ × 365 = **60 169 885 $**
* Nous pouvons maintenant utiliser les frais annuels pour calculer l'**APR des récompenses LP :** Il s'agit des **frais annuels** divisés par la **Liquidité :**\
  (60 169 885 $ / 387 420 000 $) × 100 = **15,53 % d'APR de récompense LP**
