---
hidden: true
---

# FAQ sur le CAKE Syrup Pool

## FAQ

### Quelle durée de verrouillage peut-on choisir ?

Vous pouvez choisir entre 1 et 52 semaines. Qu'est-ce qui vous convient le mieux ?

### Quelles variables influencent les rendements (%) du nouveau CAKE Syrup Pool (options de Staking flexible et à durée fixe) ?

Comme les options de Staking flexible et à durée fixe font partie du même pool, les variables suivantes influencent le rendement (APR/APY) des deux :

* Le total de CAKE staké en Staking flexible et à durée fixe (la somme des deux). Plus il y a de CAKE staké, plus l'APR/APY est faible.
* Le total de CAKE verrouillé en Staking à durée fixe. Plus il y a de CAKE verrouillé, cela implique davantage d'amplifications de rendement, ce qui réduit les récompenses en CAKE pour les autres (notamment le Staking flexible).
* La durée de verrouillage moyenne de tous les CAKE verrouillés en Staking à durée fixe. Si la durée de verrouillage moyenne augmente, l'APR/APY diminue.

### Puis-je récolter les récompenses pendant la période de verrouillage ?

Non. Vous pouvez récolter les récompenses uniquement à la fin de la durée de verrouillage. Cela est lié au rendement que nous proposons ainsi qu'aux implémentations techniques.

### Puis-je prolonger la durée de verrouillage ?

Oui. La prolongation de la durée de verrouillage ajoute du temps à votre **durée de verrouillage initiale**. Lorsque vous choisissez de prolonger votre durée de verrouillage, notez que :

Nouvelle durée de verrouillage prolongée = durée de verrouillage initiale + durée ajoutée

### Puis-je retirer mon CAKE du Staking à durée fixe via le contrat si je change d'avis ?

Non. Votre CAKE ne peut pas être retiré du Staking à durée fixe à aucun moment jusqu'à la fin de votre durée de verrouillage et le déverrouillage de votre CAKE.

### Qu'est-ce que le montant « CAKE Verrouillé » ?

Le montant « CAKE Verrouillé » correspond au solde initial de CAKE verrouillé d'un utilisateur plus les récompenses en CAKE à ce jour.&#x20;

CAKE Verrouillé = Solde initial de CAKE verrouillé + Récompenses en CAKE

Lors de l'ajout de davantage de CAKE au Staking à durée fixe, le montant « CAKE à verrouiller » correspond au solde initial de CAKE verrouillé de l'utilisateur, aux récompenses en CAKE à ce jour, et au CAKE ajouté.

### L'APR du pool CAKE à durée fixe peut-il changer après avoir verrouillé mon CAKE ?

Oui, l'APR du pool CAKE à durée fixe est variable, tout comme les anciens pools CAKE. L'APR du pool CAKE à durée fixe n'est pas fixe et dépend de :

* Le total de CAKE staké dans le pool CAKE (la somme du Staking flexible + Staking à durée fixe).
* La durée de verrouillage moyenne de tous les CAKE verrouillés en Staking à durée fixe.
* Une amplification de rendement (similaire à un multiplicateur) calculée à partir de la durée de verrouillage initiale d'un utilisateur. Plus vous verrouillez votre CAKE longtemps, plus l'amplification de rendement est élevée.

Par exemple, si vous verrouillez votre CAKE pendant 52 semaines, votre amplification de rendement sera plus importante que si vous le verrouillez pendant 26 semaines. L'amplification de rendement augmente de manière linéaire en fonction de la durée de verrouillage de votre CAKE.

### Puis-je toujours participer aux IFO si mon CAKE est verrouillé dans le pool de Staking à durée fixe, ou dois-je acheter davantage de CAKE ?

Non, un montant séparé de CAKE est nécessaire. Cependant, le Staking avec verrouillage donne accès aux ventes publiques IFO. Consultez [iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md).

### Puis-je voter si mon CAKE est verrouillé dans le pool de Staking à durée fixe ?

Oui ! Consultez [vCAKE](../../../welcome-to-pancakeswap/vecake-sunset/archive-vecake/vecake.md).

### Puis-je utiliser à la fois le pool de Staking flexible CAKE et le pool de Staking à durée fixe CAKE en même temps ?

Oui, lorsque vous effectuez un Staking de CAKE à durée fixe, un pool secondaire de Staking flexible de CAKE apparaîtra automatiquement pour vous permettre de choisir.

### Y a-t-il des frais pour convertir le CAKE en Staking flexible vers le Staking à durée fixe ?

Non. Il n'y a pas de frais supplémentaires pour déplacer le CAKE du Staking flexible vers le Staking à durée fixe, uniquement des frais de gas.

### Que se passe-t-il à la fin de la durée de verrouillage ? Qu'est-ce que le « Brûlage différé » ?

{% hint style="warning" %}
**Le Brûlage différé brûlera les récompenses en CAKE futures et les récompenses en CAKE déjà gagnées.** Pour éviter de perdre des récompenses en CAKE que vous avez déjà gagnées, nous vous recommandons de démarrer une nouvelle période de Staking à durée fixe ou de convertir votre CAKE en Staking flexible à la fin de votre période de Staking avec verrouillage.
{% endhint %}

Lorsque votre période de Staking à durée fixe se termine et que votre CAKE est déverrouillé, vous disposez de 7 jours pour effectuer l'une des deux options suivantes :

* Verrouiller votre CAKE pour commencer une nouvelle période de Staking à durée fixe\
  ou
* Convertir votre CAKE staké en Staking flexible (sans frais de retrait de 72 heures).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20before%20after%20burning.png)

Pendant ces 7 jours, vous continuerez à gagner des CAKE.

Après 7 jours, si vous n'avez effectué aucune des deux options, votre CAKE staké entrera dans ce qu'on appelle le « Brûlage différé ». **Avec le « Brûlage différé », vos récompenses en CAKE (y compris les récompenses déjà gagnées) commenceront à être envoyées au brûlage.** Le pourcentage de récompenses en CAKE envoyées au brûlage augmentera de manière linéaire pendant la période de 90 jours du « Brûlage différé » jusqu'à atteindre 100 %, ce qui signifie que toutes les récompenses en CAKE sont brûlées.

Ainsi, pour ne pas manquer de récompenses en CAKE, nous vous recommandons de démarrer une nouvelle période de Staking à durée fixe ou de convertir votre CAKE en Staking flexible à la fin de votre période de Staking avec verrouillage.

Voici un exemple :

> Jean a staké 100 CAKE pendant 52 semaines, il a gagné 50 CAKE pendant sa période de Staking, et maintenant la période de Staking a expiré.&#x20;
>
> Il n'a alors effectué aucune action, et sa position est passée en mode « Brûlage différé ».
>
> Pendant la période de Brûlage différé de 90 jours, les 50 CAKE qu'il a gagnés seront progressivement brûlés, ainsi que tout nouveau CAKE gagné.&#x20;
>
> Après 90 jours, les récompenses qu'il gagne réellement deviendront 0. Cependant, les 100 CAKE qu'il a initialement déposés ne seront pas affectés.
>
> Démarrez une nouvelle période de Staking à durée fixe ou convertissez en Staking flexible, et ne faites pas comme Jean.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20after%20burning%20started.png)
