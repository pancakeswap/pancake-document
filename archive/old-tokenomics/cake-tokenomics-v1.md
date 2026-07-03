# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Taux d'émission** <a href="#emission-rate" id="emission-rate"></a>

### **Par bloc**

| **Métrique**                                                                              | **Émission/bloc (CAKE)** | **Émission/jour (CAKE)** |
| ----------------------------------------------------------------------------------------- | -----------------------: | -----------------------: |
| Émission                                                                                  |                       40 |                1 152 000 |
| Détruit chaque semaine [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual)    |                   -25,75 |                 -787 600 |
| **Émission effective**                                                                    |             **<14,25\*** |            **364 400\*** |

\*L'émission effective est en réalité légèrement inférieure à ce montant : 45 000 CAKE supplémentaires par jour sont prélevés sur la part allouée à la Loterie et détruits (PID 137 — Détails ci-dessous).

En plus de ce qui précède, une quantité dynamique de CAKE est également [mintée à destination de l'adresse Dev](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) à un taux de 9,09 %. Cela signifie que pour chaque 100 CAKE récoltés, 9,09 CAKE supplémentaires sont mintés et envoyés à l'adresse Dev.

{% hint style="info" %}
Tous les CAKE mintés à destination de l'adresse Dev sont détruits lors de la destruction hebdomadaire et n'entrent jamais en circulation.

C'est pourquoi nous ne les avons pas inclus dans le taux d'émission ci-dessus.
{% endhint %}

## Distribution <a href="#distribution" id="distribution"></a>

| Distribué à                             | Récompense/bloc (% de l'émission) | Récompense/bloc (CAKE total) |           Récompense/jour |
| --------------------------------------- | --------------------------------: | ---------------------------: | ------------------------: |
| Farms et Loterie                        |                            10,62% |                         4,25 |     122 400 (approx.)     |
| dont redirigé et détruit                |                                   |                              |                   -46 000 |
| Syrup Pools                             |                               25% |                           10 |     288 000 (approx.)     |
| **Émission quotidienne totale de CAKE** |                                   |                              | **364 400 (approx.)**     |

## **Autres mécanismes déflationnistes** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Le processus de destruction est actuellement manuel. [Consultez les transactions de destruction ici](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

En plus de ce qui précède, des CAKE sont également détruits de la manière suivante :

* **0,05 %** de chaque transaction effectuée sur PancakeSwap V2
* **100 %** des CAKE envoyés à l'adresse Dev
* **100 %** des frais de performance CAKE provenant des IFO
* **100 %** des CAKE dépensés pour la création de Profil et le mint de NFT
* **100 %** des CAKE mis aux enchères lors des Farm Auctions
* **20 %** des CAKE dépensés pour des tickets de Loterie
* **45 000** CAKE par jour (historiquement alloués à la Loterie) _(Ces CAKE sont générés par une Farm — PID 137)_
* **3 %** de chaque round des marchés de Prédiction est utilisé pour acheter des CAKE à détruire
* **2 %** de chaque récolte de rendement dans le pool Auto CAKE
* **2 %** de chaque vente de NFT sur le NFT Market est utilisé pour acheter des CAKE à détruire

## Pourquoi la destruction de CAKE est-elle manuelle ?

Pour lancer rapidement le projet, PancakeSwap a été déployé en tant que MVP (produit minimum viable) avec le contrat MasterChef émettant 40 CAKE par bloc. Pour cette raison, l'équipe initiale n'a pas ajouté de fonctionnalités supplémentaires, telles que la possibilité de personnaliser la logique de mint des CAKE. La migration vers un nouveau MasterChef nécessitant beaucoup de temps et d'efforts, l'équipe a choisi de réduire les émissions de CAKE via un processus de destruction manuel en créant deux pools :

* Legacy Lottery Pool (PID - 137) — destruction des CAKE issus de la Loterie
* Burn Pool (PID - 138) — destruction de CAKE par bloc

Ces pools fonctionnent de manière similaire aux Farms : les Chefs peuvent ajuster le pourcentage des 40 CAKE par bloc qui leur est alloué après chaque vote de réduction des émissions de CAKE.

{% hint style="warning" %}
Le jour de la destruction, l'offre affichée sur la page d'accueil peut soudainement augmenter de plusieurs millions de CAKE.

Ne vous inquiétez pas — **CES CAKE N'ENTRENT JAMAIS RÉELLEMENT EN CIRCULATION :**
{% endhint %}

Cette augmentation apparente est simplement due à la façon dont tous les CAKE alloués à la destruction sont stockés pendant la semaine.

Les CAKE envoyés aux pools PID-137 et PID-138 sont récoltés avant la réalisation des destructions hebdomadaires de tokens, ce qui fait bondir l'offre totale affichée sur le site d'environ 6 M. Cela s'explique par le fait que les CAKE en attente ne sont pas comptabilisés dans l'offre totale tant qu'ils ne sont pas récoltés le jour de la destruction. Une fois la transaction de destruction de tokens finalisée, ces ~6 M apparaissent dans le total des CAKE détruits à ce jour.

## Comment vérifier vous-même l'offre de CAKE

Pour confirmer que l'offre de CAKE en circulation affichée sur la page d'accueil de PancakeSwap est correcte :

1. Rendez-vous sur le contrat du token CAKE sur BscScan et [vérifiez la quantité de CAKE détenue par l'adresse de destruction.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Il s'agit du montant total de CAKE ayant été détruit (retiré définitivement de la circulation, impossible à récupérer).
2. Soustrayez ensuite ce montant détruit de l'« Offre totale » affichée par BscScan.
3. Vous obtenez ainsi l'offre réelle de CAKE.



#### **Pour en savoir plus sur les mécanismes déflationnistes de CAKE, consultez la page suivante.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
