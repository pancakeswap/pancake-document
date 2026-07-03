# Calculateur APR/ROI/IL

En V3, avec la Liquidité et les Farms, la nouvelle Liquidité non fongible et la possibilité de personnaliser la plage de prix font que chaque position LP aura son propre APR de frais LP et son propre APR de farming CAKE.

Pour faciliter la fourniture de Liquidité et la rendre moins complexe, les nouveaux affichages automatiques d'APR avec un tout nouveau calculateur de ROI sont disponibles chaque fois que vous fournissez de la Liquidité ou que vous farmez.

## Calcul et affichage automatiques de l'APR <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Lorsque vous fournissez de la Liquidité, l'affichage automatique de l'APR réagit à vos modifications de configuration et calcule l'APR en fonction de vos paramètres.

Par exemple, dans la plupart des cas, si vous resserrez les paramètres de votre plage de prix, l'APR augmente.

Veuillez noter, concernant les APR de frais LP :

* Le montant estimé des récompenses de frais LP varie en fonction du palier de frais sélectionné ; les récompenses de frais doivent être réclamées et réinvesties manuellement.
* Les chiffres d'APR sont calculés à partir du volume de trading historique, qui dépend du Subgraph et peut être sujet à des délais d'indexation.

Concernant les APR de farming :

* Le montant estimé des récompenses en CAKE est basé sur les émissions de CAKE en direct vers les Farms. Ces montants sont susceptibles d'évoluer en fonction des ajustements d'émission futurs.

{% hint style="info" %}
Les chiffres sont calculés aux taux actuels et dans les conditions actuelles du Pool et sont susceptibles d'évoluer en fonction de diverses variables externes. Il s'agit d'estimations fournies à titre indicatif uniquement, et ne constituent en aucun cas une garantie de rendement.
{% endhint %}

Vous pouvez trouver cet affichage d'APR sous :

* La page « Ajouter de la Liquidité » — affichage de l'APR des frais LP
* La page de détail de chaque position de Liquidité existante — affichage de l'APR des frais LP\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* La page Farm, dans la position sous chaque Farm — affichage de l'APR combiné avec les frais LP et les récompenses CAKE\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Calculateur de ROI amélioré <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Chaque fois que vous voyez les affichages automatiques d'APR, vous pouvez cliquer dessus pour ouvrir le nouveau calculateur de ROI. Ce dernier a été entièrement repensé avec plusieurs fonctionnalités supplémentaires pour répondre aux besoins de la fourniture de Liquidité concentrée et du farming en V3.

Passons en revue chacune des sections ensemble :

### Montant du dépôt, « Staké pendant » et « Réinvestissement tous les » <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Ces trois paramètres constituent les données d'entrée de base, déjà présents dans le calculateur de ROI précédent. Ils permettent de définir :

1. Le montant des actifs déposés dans la position de Liquidité, en USD.
2. La durée pendant laquelle ces actifs seront stakés dans la position.
3. La fréquence à laquelle vous réinvestirez vos récompenses dans la position.



⓵ **Montant du dépôt**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Vous pouvez saisir manuellement le montant en USD, ou utiliser les boutons d'action rapide pour remplir rapidement 100 $, 1 000 $ ou le montant maximum autorisé en fonction du solde de jetons dans votre portefeuille.



⓶ **Durée de Staking**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Vous pouvez sélectionner la durée pendant laquelle les actifs sont stakés dans la position de Liquidité en choisissant parmi : 1 jour, 7 jours, 30 jours, 1 an et 5 ans.

Le rendement sera calculé en fonction de la durée de Staking choisie.



⓷ **Réinvestissement**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Vous pouvez sélectionner la fréquence à laquelle vous souhaitez récolter les récompenses générées par la position et les réinvestir. Vous pouvez choisir parmi : 12 heures, 1 jour, 7 jours et 30 jours.

Le rendement et l'APY seront calculés en fonction de votre choix. Si vous ne prévoyez pas de réinvestir votre position, décochez la case à gauche.

{% hint style="info" %}
En V3, les frais LP et les CAKE gagnés doivent être récoltés et réinvestis manuellement.
{% endhint %}

### &#x20;⓸ Prix historiques <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Cette section est en lecture seule et sert à consulter l'évolution historique des prix de la paire sélectionnée.

Vous pouvez consulter les évolutions historiques des prix sur différentes périodes, par exemple pour observer les fluctuations habituelles du prix, puis définir une plage de prix adaptée permettant d'équilibrer un APR plus élevé et un risque de perte impermanente plus faible.

* MIN — prix minimum
* MAX — prix maximum
* AVG — prix moyen
* CURRENT — prix actuel

{% hint style="info" %}
Le graphique de prix utilise uniquement les données de la paire V3 réelle. Par conséquent, les données de prix antérieures au déploiement de V3 ne sont pas disponibles. Les quatre indicateurs de prix correspondent à la période actuellement sélectionnée et changeront selon la sélection.
{% endhint %}

### ⓹ Plage de prix <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Cette section vous permet de vérifier le montant de Liquidité déposé dans différentes plages de prix, et de définir la plage de prix pour laquelle vous fournissez de la Liquidité.

Vous trouverez le graphique de distribution sous le titre. Plus le montant de Liquidité est élevé, plus le graphique sera haut.

Vous pouvez modifier les paramètres de votre plage de prix en :

* Faisant glisser les deux poignées sur le graphique pour augmenter ou diminuer les limites de prix minimum et maximum.
* Utilisant l'espace entre les deux poignées pour déplacer la plage sélectionnée.
* Cliquant sur les boutons + et - dans les champs de prix min et max.
* Cliquant sur les valeurs dans les champs de prix et en les saisissant manuellement.

Pour naviguer dans le graphique de distribution :

1. Utilisez les boutons loupe + et - pour zoomer et dézoomer
2. Faites glisser l'axe X (en bas) pour vous déplacer à gauche et à droite

Pour fournir de la Liquidité sur toute la plage de prix, cliquez sur « Plage complète »

### ⓺ Inverser le sens des prix pour les afficher avec une base différente <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Pour certaines paires de jetons, il est plus simple et plus intuitif d'afficher les prix avec certains jetons de base. Par exemple, pour la paire BNB/USDT, la plupart des utilisateurs préféreront voir les prix en « combien d'USDT par BNB » plutôt que l'inverse.

Vous pouvez facilement inverser l'affichage des prix. Il suffit de cliquer sur le bouton suivant « Voir les prix en : » pour basculer la base entre les deux jetons de la paire.

### ⓻ Importer et exporter (appliquer) vos paramètres <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Lorsque vous ouvrez le calculateur de ROI depuis la fenêtre « Ajouter de la Liquidité », ou en consultant une position existante, les paramètres suivants seront automatiquement importés afin que vous n'ayez pas à les reconfigurer :

1. Le montant des actifs que vous déposez
2. La plage de prix
3. Le palier de frais sélectionné

Lorsque vous avez terminé la configuration dans le calculateur de ROI, vous pouvez cliquer sur « Appliquer les paramètres » pour les transférer rapidement du calculateur vers la fenêtre « Ajouter de la Liquidité », sans avoir à les reconfigurer manuellement.

### ⓼ Calculer les récompenses de farming et l'APR <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Les récompenses de farming seront incluses dans les calculs si vous ouvrez le calculateur de ROI depuis la page « Farm ».

Vous pouvez développer les sections de détail pour voir la répartition des récompenses.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
