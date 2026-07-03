# FAQ de la Lottery

## Que se passe-t-il s'il n'y a aucun gagnant ?

Si le CAKE dans les lots n'est pas remporté, il n'est pas perdu ! Les CAKE non réclamés sont reportés au prochain tour de la Lottery.

## Mon ticket correspond à plusieurs numéros mais je ne peux pas réclamer de prix

Les tickets ne sont éligibles aux prix que si les numéros correspondent de gauche à droite. Consultez la [documentation de la Lottery v2](./) pour une explication détaillée.

## En quoi la Lottery v2 diffère-t-elle de la Lottery v1 ?

La Lottery v2 distribue les prix de manière plus large que la Lottery v1. Elle accorde à chaque ticket une chance sur 10 de faire correspondre le premier numéro, ce qui signifie que davantage de tickets remporteront au moins un petit prix. Elle comporte également 6 numéros (au lieu de 4) à faire correspondre séquentiellement pour remporter le jackpot le plus important.

Dans l'ensemble, cela signifie que plus de tickets peuvent gagner un prix, mais que le jackpot le plus important sera remporté moins fréquemment, créant ainsi d'énormes lots de premier prix !

**La Lottery v2 introduit :**

* Des prix de tickets moins élevés (\~5 USD en CAKE par ticket) qui ne fluctuent pas fortement avec le prix du CAKE
* Des réductions pour les achats groupés
* 6 niveaux de tranches de lots avec des récompenses croissantes à mesure que plus de numéros sont mis en correspondance
* La sélection manuelle des numéros (optionnelle), permettant aux utilisateurs d'utiliser leurs numéros chanceux
* [L'implémentation VRF de Chainlink](https://docs.chain.link/docs/chainlink-vrf/) pour une véritable aléatoire sécurisée
* Des frais globaux réduits (voir [plus bas sur cette page](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) pour plus d'informations)

[En savoir plus sur les fonctionnalités, le gameplay et les prix de la Lottery v2](./)

## Comment les prix sont-ils répartis entre les tranches ?

Le lot de chaque tranche représente une portion du CAKE total de chaque tour de Lottery.

* | Tranche (numéros correspondants dans l'ordre) | Allocation CAKE |
  | --------------------------------------------- | --------------- |
  | Premier 1 numéro                              | 2%              |
  | 2 premiers numéros                            | 3%              |
  | 3 premiers numéros                            | 5%              |
  | 4 premiers numéros                            | 10%             |
  | 5 premiers numéros                            | 20%             |
  | 6 premiers numéros                            | 40%             |
  | Brûlage                                       | 20%             |

## Puis-je échanger mes tickets contre du CAKE ?

Non, une fois achetés, vous ne pourrez pas convertir vos tickets en CAKE.

## Si je gagne, dois-je réclamer le prix manuellement ?

Oui, vous devrez cliquer sur le bouton **Vérifier maintenant** sous « Êtes-vous gagnant ? » sur la page de la Lottery.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## À quelle fréquence la loterie a-t-elle lieu ?

Un tirage de loterie a lieu toutes les 12 ou 36 heures. Un tirage a lieu chaque jour en alternant entre 0h UTC et 12h UTC ; les tours suivant les tirages de 0h UTC auront lieu après 36 heures, et ceux suivant les tirages de 12h UTC auront lieu après 12 heures.

![Lottery injection schedule](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## Quels frais de transaction devrai-je payer pour acheter des tickets ?

Chaque achat de ticket constitue une transaction. L'achat d'un seul ticket lors d'une transaction entraîne des frais normaux.

Cependant, l'achat de plusieurs tickets dans la même transaction augmentera les frais. Acheter 100 tickets plutôt qu'un seul ne multipliera pas les frais par 100, mais pourra les multiplier par 5 à 6 environ (bien que cela puisse varier).

## Comment fonctionne la réduction pour achat groupé ?

La réduction pour achat groupé récompense l'achat d'un plus grand nombre de tickets avec une réduction progressive. Si vous n'achetez que 2 tickets, la réduction est négligeable, mais elle s'accumule rapidement à mesure que vous augmentez le nombre de tickets dans une même transaction.

La réduction ne s'applique qu'à chaque transaction jusqu'à 100 tickets. Elle ne se reporte pas sur la transaction suivante ni sur le tour suivant.

## Pourquoi ne puis-je acheter que 100 tickets ?

Vous ne pouvez acheter qu'un maximum de 100 tickets en une seule transaction, mais vous pouvez effectuer plusieurs achats. Rien ne vous empêche d'acheter davantage de tickets après vos 100 premiers.

## Si je crée manuellement deux tickets ou plus avec les mêmes numéros et qu'ils gagnent, suis-je éligible aux prix pour chaque ticket ?

Oui, chaque ticket est traité comme une entrée distincte à la Lottery. Notez cependant que les prix ne seront pas identiques, car chacun de vos tickets gagnants dilue la part des prix totaux de la tranche.

## Calendrier d'injection : quand le CAKE est-il ajouté à la loterie ?

Lorsque les utilisateurs achètent des tickets, le CAKE dépensé est ajouté au pot de la loterie. En outre, 8 000 CAKE sont également ajoutés (injectés) dans le pot de la loterie tous les deux tours, selon un calendrier régulier réparti sur sept tours par semaine, comme indiqué dans la figure du calendrier de la loterie ci-dessus.
