# FAQ et dépannage des Syrup Pools

## Dépannage

### **Je ne trouve plus le Syrup Pool dans lequel je stakais !**

Vous devriez pouvoir trouver le Syrup Pool sous l'onglet « Terminé » sur la page des Syrup Pools.&#x20;

En sélectionnant « Stakés uniquement », il vous sera plus facile de retrouver vos actifs.

### **Pourquoi ne puis-je pas unstaker mes jetons d'un Syrup Pool ?**

Si vous n'êtes pas en mesure d'unstaker depuis le pool « Staker du CAKE, Gagner du CAKE », veuillez vérifier que vous n'avez pas vendu les jetons SYRUP dans votre portefeuille. Ce jeton sert de `preuve de propriété` de votre CAKE dans le pool CAKE Manuel.&#x20;

### **Pourquoi mes jetons gagnés sont-ils passés à zéro après le staking/unstaking ?**

Ne vous inquiétez pas ! Ils sont déjà dans votre portefeuille.

Chaque fois que vous stakez ou unstakez depuis un Syrup Pool ou une Farm, vos jetons gagnés sont récoltés et envoyés à votre portefeuille en même temps.

## **Questions générales**

### Comment l'APR des Syrup Pools est-il calculé ?

> APR du Syrup Pool = Récompenses annualisées (USD) / Fonds stakés par l'utilisateur dans le Syrup Pool (USD) \* 100

À titre d'exemple simple, prenons un pool de 60 jours avec 300 000 USD de récompenses et 3 000 000 USD de CAKE stakés dedans.

L'APR fluctue à mesure que davantage de CAKE est staké par les utilisateurs, et en fonction des variations de prix du CAKE et du jeton de récompense.

|                                                              | **Calcul**                        | Montant                                    |
| ------------------------------------------------------------ | --------------------------------- | ------------------------------------------ |
| Total des récompenses à distribuer (valeur USD)              |                                   | 300 000 USD                                |
| Période de distribution                                      |                                   | 60 jours                                   |
| Distribution quotidienne                                     | 300 000 / 60 =                    | 5 000 USD par jour                         |
| **Récompenses annualisées (valeur USD)**                     | 5 000 \* 365 =                    | **1 825 000 USD**                          |
| **Valeur du CAKE staké par les utilisateurs dans le pool (valeur USD)** |                        | **3 000 000 USD**                          |
| **APR**                                                      | (1 825 000 / 3 000 000) \* 100 =  | <p></p><p><strong>60,833 % APR</strong></p> |

### **À quoi fait référence le numéro « Fin » sur mon Syrup Pool ?**

Il indique le nombre de blocs restants avant l'arrêt de la distribution des récompenses pour ce pool. Une fois que le pool a atteint ce bloc, vous devriez unstaker vos jetons, car vous ne recevrez plus aucune récompense après cela.

### **D'où viennent les récompenses des Syrup Pools ?**

Il existe trois types principaux de Syrup Pools.

1. Staker du CAKE, gagner du CAKE
2. Staker du CAKE, gagner d'autres jetons.&#x20;
3. Staker d'autres jetons, gagner du CAKE

Les récompenses pour les Syrup Pools « Staker du CAKE, gagner du CAKE » proviennent des [émissions de CAKE](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). À chaque bloc, un certain nombre de jetons CAKE sont alloués comme récompenses pour ces pools.

Les récompenses pour le type « Staker du CAKE, gagner d'autres jetons » sont fournies par les équipes de projets qui sponsorisent un Syrup Pool.

Pour le type « Staker d'autres jetons, gagner du CAKE », la trésorerie de PancakeSwap rachète des CAKE sur le marché pour les distribuer comme récompenses. Ces pools sont financés par PancakeSwap, et non par les projets eux-mêmes.

### Qu'est-ce que le jeton SYRUP ?

Le jeton SYRUP de PancakeSwap est déposé dans votre portefeuille lorsque vous interagissez avec le Syrup Pool **Manuel** « Staker du CAKE, Gagner du CAKE ». Il n'est pas staké pour&#x20;

Il s'agit essentiellement d'une reconnaissance de dette indiquant la quantité de CAKE que vous avez stakée dans le pool.

Il vous sera restitué automatiquement lorsque vous unstakerez votre CAKE de ce pool.

{% hint style="warning" %}
Ne vendez pas vos jetons SYRUP ! Vous devez restituer vos SYRUP pour unstaker vos CAKE du pool CAKE Manuel. La quantité de SYRUP que vous restituez doit être la même que la quantité de CAKE que vous unstakez.
{% endhint %}
