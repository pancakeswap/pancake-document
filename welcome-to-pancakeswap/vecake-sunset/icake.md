---
description: Staking veCAKE et Allocations IFO
hidden: true
---

# iCAKE

### **Qu'est-ce que le nouveau iCAKE ?**

Après la transition vers veCAKE, le nouveau iCAKE sera basé sur le solde veCAKE.

* Tout comme l'ancien iCAKE, il détermine la limite maximale d'engagement de CAKE dans les ventes publiques IFO de PancakeSwap. Par exemple, si vous avez 200 iCAKE, vous pouvez engager 200 CAKE dans les ventes publiques IFO.
* Le nouveau nombre d'iCAKE est calculé à partir du solde veCAKE à la fin de chaque IFO. Par conséquent, vous aurez des nombres d'iCAKE différents pour chaque IFO.
* Étant donné que le solde veCAKE diminue progressivement avec votre temps de verrouillage restant, votre iCAKE pour les futurs IFOs diminuera également avec votre solde veCAKE. Pour maintenir votre nombre d'iCAKE, ajoutez davantage de CAKE au Staking ou renouvelez/prolongez votre verrouillage.

**iCAKE N'est PAS un nouveau token, c'est une métrique numérique utilisée par le système IFO de PancakeSwap.**

### Comment l'iCAKE est-il calculé ?

Le nombre d'iCAKE que vous détenez est basé sur le solde veCAKE à la fin de chaque IFO, multiplié par un ratio prédéfini.

Le veCAKE est une valeur calculée dynamiquement en fonction du montant de CAKE que vous verrouillez et du temps restant dans le verrouillage. Pour en savoir plus sur le calcul du veCAKE, consultez [ici](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Un ratio supplémentaire est appliqué par-dessus le solde veCAKE, ajusté par la Cuisine pour chaque IFO. Par exemple, si le ratio est de 2x et que vous avez 1 veCAKE à la fin du prochain IFO, vous pouvez engager jusqu'à 2 CAKE.

Exemple :

* Vous avez verrouillé 100 CAKE pour 2 ans.
  * Votre temps de verrouillage restant est : `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (secondes)
  * Le temps de verrouillage maximum est : `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (secondes)
  * En ce moment, vous avez : `100 * (62899200 / 126403199) ~= 49,76` veCAKE
* Le prochain IFO est planifié ; sa date de fin est exactement 1 semaine plus tard, soit `604800` secondes après le moment actuel.
  * À ce moment-là, votre temps de verrouillage restant sera : `62899200 - 604800 = 62294400` (secondes)
  * À ce moment-là, vous aurez : `100 * (62294400 / 126403199) ~= 49,28` veCAKE
* Pour cet IFO, le ratio est fixé à `3x`
* Par conséquent, pour cet IFO, vous avez : `49,28 * 3 = 147,84` iCAKE, ce qui signifie que vous pouvez engager jusqu'à 147,84 CAKE dans la vente publique.

### Comment vérifier le nombre d'iCAKE que je possède ?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Vous pouvez vérifier le nombre d'iCAKE que vous détenez sur la page IFO [ici](https://pancakeswap.finance/ifo).

Veuillez garder à l'esprit que lorsqu'aucun IFO n'est à venir, votre iCAKE sera calculé en utilisant le solde veCAKE en temps réel, qui diminue progressivement seconde par seconde.

Lorsqu'un IFO est à venir, votre iCAKE sera calculé en utilisant le solde veCAKE au moment du snapshot, c'est-à-dire à la fin de l'IFO. Votre iCAKE ne diminuera pas ou ne changera pas jusqu'à la fin de l'IFO.

### **Comment augmenter mon nombre d'iCAKE ?**

Vous pouvez augmenter votre nombre d'iCAKE à tout moment en :

* Ajoutant davantage de CAKE à votre position de Staking veCAKE.
* Prolongeant votre position de Staking veCAKE.

sur la [Page de Staking CAKE](https://pancakeswap.finance/cake-staking)

### Qu'est-ce que le « Ratio » dans le calcul de l'iCAKE ?

Le Ratio est un facteur de contrôle supplémentaire appliqué par-dessus le solde veCAKE lors du calcul de l'iCAKE.

Par exemple, si le ratio est de 2x et que vous avez 1 veCAKE à la fin du prochain IFO, vous pouvez engager jusqu'à 2 CAKE.

Entre chaque IFO, la cuisine optimisera le « Ratio » en fonction de diverses métriques. L'ajustement sera publié sur tous les canaux sociaux.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Vous pouvez vérifier le nombre actuel du « Ratio » pour les calculs d'iCAKE en vous rendant sur [la page IFO](https://pancakeswap.finance/ifo).
