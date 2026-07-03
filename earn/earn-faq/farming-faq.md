---
hidden: true
---

# FAQ sur le Farming

### Pourquoi y a-t-il plusieurs APR ?

En V3, vous pouvez concentrer vos actifs en fournissant de la Liquidité afin d'augmenter votre part par rapport à la Liquidité totale disponible, ce qui vous permet de gagner un pourcentage plus élevé de récompenses.&#x20;

Par conséquent, en fonction des paramètres de plage de prix de la position, chaque position de Liquidité aura son propre APR de frais LP et son propre APR de farming.

L'APR global est calculé avec le montant total des récompenses en CAKE en USD, divisé par le montant total des actifs dans les positions actives actuellement stakées dans la Farm. Ainsi, l'APR de farming global n'est qu'une référence générique et ne représente pas les APR individuels de chaque position.

Pour voir votre APR de farming, consultez vos positions listées sous chaque Farm.

###

### Que se passe-t-il si ma position de Liquidité sort de la plage pendant que je stake dans la Farm ?

En V3, seules les positions de Liquidité actives (dans la plage) gagnent des CAKE provenant des Farms.

La position cesse de recevoir des récompenses en CAKE lorsque le prix sort de la plage.

Si le prix revient dans la plage, la position recommencera à recevoir des récompenses en CAKE. Aucune action supplémentaire n'est requise de la part des stakers.



### Existe-t-il des moyens d'ajuster automatiquement ma position afin qu'elle soit toujours dans la plage et génère des récompenses de frais ?

PancakeSwap v3 prend en charge le dépôt de Liquidité en un clic via Zap, disponible sur BNB Chain et Ethereum.



### Vaut-il toujours mieux farmer avec une position de Liquidité dont la plage est plus petite ?

Fournir de la Liquidité dans une plage de prix plus petite permet de concentrer votre Liquidité, ce qui augmente vos parts relatives par rapport à la Liquidité totale dans la plage de prix, vous permettant potentiellement de gagner davantage de récompenses en CAKE.

Cependant, gardez à l'esprit que seules les positions de Liquidité actives gagnent des récompenses en CAKE. Cela signifie que vous ne gagnerez des récompenses que lorsque le prix de trading actuel se trouve dans la plage de prix définie dans la position de Liquidité.

Si vous devez ajuster la plage de prix de votre position, vous devrez unstaker, retirer la Liquidité et créer une nouvelle position avec la plage de prix mise à jour. Gardez à l'esprit que des ajustements fréquents ne constituent pas toujours la stratégie la plus optimale, car ils réalisent la perte impermanente et impliquent des frais de gas pour effectuer plusieurs transactions.



### Combien de positions puis-je staker dans une seule Farm ?

Il n'y a pas de limite maximale de positions que vous pouvez staker dans une Farm.

Mais gardez à l'esprit que vous devrez dépenser des frais de gas pour récolter manuellement depuis chacune des positions. Prenez toujours en compte les frais de gas dans les opérations de rendement.



### À quelle fréquence dois-je récolter mes récompenses ?

La fréquence à laquelle vous récoltez vos récompenses vous appartient, mais il convient de garder à l'esprit qu'il y a des frais minimes liés à chaque récolte. Vous pouvez voir ces frais dans votre portefeuille lors de la confirmation après avoir cliqué sur « Récolter ».

Cela montre les frais de récolte tels qu'ils apparaissent dans le portefeuille MetaMask. Les différents portefeuilles afficheront l'information légèrement différemment. Envisagez de laisser vos récompenses s'accumuler pendant un certain temps afin de payer des frais moins fréquemment.



### Que faire si je veux ajuster ma position pendant que je stake dans la Farm ?

Pendant le Staking dans la Farm, vous pouvez ajouter ou retirer de la Liquidité sans l'unstaker. Localisez simplement la position de Liquidité que vous souhaitez ajuster, cliquez sur son titre/identifiant, et vous accéderez à la page de détail de la position où vous pourrez utiliser les boutons « Ajouter » et « Retirer ».

Si vous souhaitez ajuster les configurations de la plage de prix d'une position de Liquidité, vous devrez l'unstaker de la Farm, retirer toute la Liquidité et créer une nouvelle position en ajoutant de la Liquidité.



### Qu'est-ce qui influence l'APR de farming ?

En Farm v3, l'APR de récompense CAKE peut varier entre les positions de Liquidité. Il est basé sur les facteurs suivants :

* Taux d'émission de CAKE vers les Farms\
  \- plus de CAKE génèrera un rendement plus élevé pour toutes les Farms. En savoir plus sur [notre page de tokenomics](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)
* Multiplicateur de la Farm\
  \- les Farms avec un multiplicateur plus élevé recevront davantage de CAKE proportionnellement à toutes les Farms. Veuillez noter que les Farms v3 et v2 + StableSwap utilisent deux ensembles séparés de multiplicateurs. Et les Farms sur Ethereum et BNB Chain utilisent également deux ensembles séparés de multiplicateurs.
* Le nombre de jetons déposés dans la position\
  \- plus de jetons dans la position se traduit par une part relative plus grande par rapport à la Liquidité active totale dans le pool de la Farm et permet d'obtenir davantage de récompenses en CAKE
* La plage de prix sélectionnée\
  \- une plage de prix plus petite permet une concentration plus élevée pour le même montant de jetons déposés, ce qui se traduit par une part relative plus grande par rapport à la Liquidité active totale dans le pool de la Farm, et permet d'obtenir davantage de récompenses en CAKE
* Le montant de Liquidité actuellement active\
  \- si davantage d'utilisateurs déposent et concentrent leur Liquidité dans la même plage que vous, vous gagnerez moins de récompenses en CAKE en raison d'une part relative plus petite par rapport au total
* Si la position de Liquidité est active\
  \- seules les positions de Liquidité actives gagneront des récompenses en CAKE de la Farm



### Pourquoi est-ce que je vois une fenêtre contextuelle « Mettre à jour les positions » ?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Peu après le lancement de V3, les Chefs ont mis en œuvre une mise à jour sur les Farms pour rendre les calculs de récompenses plus précis et fiables. Si vous voyez cette fenêtre contextuelle, cela signifie que certaines de vos positions nécessitent une mise à jour.

Cliquez simplement sur « Tout mettre à jour » et confirmez dans la fenêtre contextuelle de votre portefeuille.

Veuillez noter que les Chefs appliquent également cette mise à jour aux données de Staking historiques entre le lancement de Farm V3 et la mise en œuvre de cette mise à jour. S'il y a des récompenses en CAKE supplémentaires, elles seront airdropées sur votre portefeuille avant le 1er mai 2023.



### Pourquoi une Farm 2x en V3 a-t-elle un APR inférieur à une Farm 1x en V2 ?

Premièrement, lors de la comparaison des APR, vous devez vous assurer que la Liquidité totale stakée entre les deux Farms est égale.

De plus, nous avons maintenant plusieurs groupes de Farms qui ont leur propre flux d'émissions de CAKE. Et chaque groupe de Farms partage des ensembles séparés de multiplicateurs.

Une Farm individuelle recevra des émissions de CAKE basées sur :

* A = Total de CAKE par seconde/bloc pour le groupe de Farms auquel elle appartient
* B = Nombre total de multiplicateurs dans le groupe auquel elle appartient
* C = Le multiplicateur qu'elle possède

`CAKE par bloc/seconde = C / B * A`

Les valeurs ci-dessus peuvent être trouvées dans chacun des contrats [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I).



### Puis-je utiliser bCAKE dans les Farms v3 ?

Oui

bCAKE pour les Farms V3 arrivera très prochainement après le déploiement de PancakeSwap Farm V3. Restez à l'écoute.
