# 🍯 \[Archivé] Pottery

{% hint style="danger" %}
\[Archivé] Pottery – À partir du 3 novembre 2023
{% endhint %}

Pottery combine le staking verrouillé de CAKE avec des éléments de loterie pour vous donner une chance de gagner un rendement plus élevé sur votre dépôt de CAKE ! C'est facile et sûr car vous récupérerez toujours au moins tout le CAKE que vous avez déposé.

## Détails :

* Déposez du CAKE sur la page Pottery avec un minimum de 1 CAKE&#x20;
* Le dépôt ferme le premier lundi de chaque mois pour une cohorte Pottery différente (23:59 UTC ce lundi-là) et est ouvert à partir du vendredi précédent vers 10:00 UTC, sauf arrangements spéciaux annoncés à l'avance (le premier Pottery ferme le 8 août 2022 à 23:59 UTC)
* Durant la phase bêta du produit, il existe un plafond au dépôt total de CAKE pour chaque cohorte Pottery (le plafond de dépôt maximum est de 600 000 CAKE)
* Le CAKE déposé sera dirigé vers le pool de staking verrouillé et bloqué pendant dix (10) semaines. 80 % des récompenses de staking totales seront envoyées au pool Pottery pour le tirage, 20 % seront réservées pour votre retrait&#x20;
* Pour chaque cohorte Pottery (une par mois), il y aura dix (10) tirages hebdomadaires chaque vendredi (à midi UTC) après le dépôt, produisant huit (8) gagnants par semaine ; une même adresse peut gagner plus d'un des huit créneaux gagnants chaque semaine \*
* Plus votre dépôt est important par rapport au pool global, plus vos chances de gagner sont élevées ; les gagnants peuvent réclamer leur prix juste après chaque tirage&#x20;
* Chaque cohorte Pottery effectue le tirage séparément&#x20;
* Ce n'est qu'après 10 semaines à compter de la date de verrouillage de la cohorte Pottery que vous pouvez retirer votre CAKE&#x20;
* Pottery utilise l'implémentation VRF de Chainlink pour un vrai aléatoire sécurisé

## Cohorte Pottery&#x20;

Le vendredi avant le premier lundi de chaque mois, une cohorte Pottery sera ouverte pour vous permettre de déposer du CAKE et d'y participer pendant les 10 semaines suivantes. Cette disposition combine le dépôt pour le diriger vers le pool de staking verrouillé, de sorte que le contrat Pottery de la cohorte puisse coordonner les récompenses de staking du dépôt depuis le pool de staking verrouillé.

Chaque date de dépôt et de verrouillage constituera une cohorte distincte — une pour chaque mois — par exemple, tous les dépôts du 5 septembre 2022 seront dans une cohorte, tous les dépôts du 3 octobre 2022 seront dans une autre cohorte.

Bien que les tirages puissent avoir lieu simultanément pour différentes cohortes, les pools de prix de chaque cohorte sont séparés pour garantir l'équité.

![(À titre d'illustration uniquement, la date de verrouillage réelle de la cohorte pour le premier Pottery a été fixée au 8 août 2022)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

Par exemple, il y a 2 tirages distincts le 9 septembre 2022, l'un pour la cohorte du 1er août comme sixième tirage hebdomadaire et un autre pour la cohorte du 5 septembre comme premier tirage hebdomadaire. Si la cohorte du 1er août a un total de 100 000 CAKE déposés et la cohorte du 5 septembre a un total de 300 000 CAKE déposés, le prix hebdomadaire de la cohorte du 1er août ne proviendra que des récompenses de staking de ces 100 000 CAKE, tandis que le prix hebdomadaire de la cohorte du 5 septembre ne proviendra que des récompenses de staking de ces 300 000 CAKE. Si vous avez uniquement déposé du CAKE dans la cohorte du 1er août, vous avez une chance de gagner le prix hebdomadaire le 9 septembre sur la base des récompenses de staking de 100 000 CAKE. Si vous avez déposé du CAKE dans les cohortes du 1er août et du 5 septembre, vous avez une chance de gagner les deux prix hebdomadaires le 9 septembre.

#### Pourquoi avons-nous besoin du système de cohortes ? Pourquoi ne pas tout regrouper ensemble ?

Comme Pottery interagit avec le staking à terme fixe de CAKE, tout dépôt ne peut être retiré qu'après la durée de verrouillage. Si nous voulions tout regrouper, bien que nous puissions ajouter plus de dépôts après le verrouillage initial et les bloquer également pour 10 semaines, les déposants initiaux ne pourraient pas retirer à temps.

## **Financement du pool de prix et allocation des récompenses de staking**

Les dépôts sont regroupés en cohortes mensuelles pour une gestion plus efficace des récompenses de staking qui sont également regroupées pour chaque cohorte. Les récompenses de staking sont utilisées pour financer le pool de prix et certaines récompenses de staking pour le dépôt dans le Pottery.

80 % des récompenses de staking seront dirigées pour financer le pool de prix pour 10 tirages hebdomadaires et les 20 % restants seront réservés comme récompenses de staking lors du retrait de votre dépôt CAKE après 10 semaines.

Cependant, comme les récompenses de staking du pool de staking CAKE verrouillé ne sont distribuées qu'après la durée de verrouillage — 10 semaines dans ce cas — pour une meilleure expérience produit et pour faciliter les tirages hebdomadaires juste après la date de dépôt, le contrat emprunte 80 % des récompenses de staking totales estimées de la cohorte depuis le trésor CAKE sur la base de l'APR au moment du verrouillage. Le CAKE emprunté est utilisé pour le paiement de chaque tirage hebdomadaire.

À la fin des 10 semaines, lorsque les récompenses sont distribuées depuis le pool de staking, le trésor CAKE sera remboursé en premier, puis le reste sera redirigé vers le coffre-fort pour que les utilisateurs puissent le retirer avec leur dépôt initial dans la cohorte.

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEH6IySHEmy1P1k5S3W_PvnFMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMZKuQ4TnNTfKRdU8s3UXO1n0Smnp8_6sAg)

Par exemple, si la cohorte Pottery du 1er août 2022 a attiré 100 000 CAKE de dépôts au total, le rendement estimé pour 10 semaines de staking verrouillé est d'environ 3 674 CAKE. Le contrat empruntera 80 % de celui-ci, soit environ 2 940 CAKE, pour le pool de prix de 10 tirages hebdomadaires, soit 294 CAKE en prix totaux pour chaque tirage hebdomadaire avant frais.

Il est important de noter que les récompenses et l'APR à la fin de la durée depuis le dépôt peuvent changer au cours des 10 semaines en fonction d'autres dépôts et leurs périodes de verrouillage dans le pool de CAKE verrouillé ; il peut y avoir un léger écart par rapport aux pourcentages spécifiés (+/- 10 %).

Toutes les récompenses de staking nettes de frais seront retournées aux déposants via le pool de prix ou les récompenses. Si l'APR réel est inférieur à l'APR estimé au moment du verrouillage, cela signifie que plus de récompenses sont distribuées aux déposants lors des tirages hebdomadaires et moins pour la portion de récompenses de staking. Si l'APR réel est supérieur à l'APR estimé au moment du verrouillage, moins de récompenses sont distribuées via les tirages hebdomadaires et davantage sont réservées pour les récompenses de staking disponibles au retrait. En définitive, la valeur attendue est la même.

## **Comment gagner — Calcul des probabilités**

Les probabilités sont calculées sur la base de la part du montant de dépôt par rapport à la taille totale du dépôt de la cohorte. Simplement, plus vous avez déposé de CAKE, plus vos chances de gagner chaque tirage hebdomadaire sont élevées. Par exemple, si vous avez déposé 10 000 CAKE et que le dépôt total de la cohorte est de 100 000 CAKE, vous avez 10 % de chances de gagner à chaque tirage hebdomadaire.

Une même adresse peut gagner plus d'un des 8 créneaux gagnants chaque semaine.

Dans le cas extrême, si tous les 100 000 CAKE de la cohorte sont déposés par vous, vous gagnerez tous les prix de chaque tirage hebdomadaire. Cependant, cela signifie que le rendement final que vous obtiendrez est le même que si vous mettiez 100 000 CAKE dans le pool de staking verrouillé pendant 10 semaines, mais vous devrez également payer les frais de Pottery.

## **Risques — Important !**

Vous avez la garantie de récupérer 100 % de ce que vous avez déposé en 10 semaines. Cependant, vous ne pouvez _que_ retirer votre dépôt de CAKE après 10 semaines de verrouillage, sans autre moyen de retrait anticipé.

En participant à Pottery, vous risquez les récompenses de staking, ainsi que d'autres utilités de CAKE verrouillé comme iCAKE et vCAKE. Si vous n'avez rien gagné lors des 10 tirages hebdomadaires, vous auriez perdu 80 % des récompenses de staking que vous étiez censé obtenir si vous aviez verrouillé votre CAKE dans le pool de staking pendant 10 semaines.

Veuillez participer en fonction de votre préférence de risque ; une fois les CAKE déposés, personne ne peut vous aider à les retirer prématurément.

## **Frais**

Huit pour cent (8 %) du pot de prix distribué chaque semaine seront prélevés comme frais de destruction. Nous prévoyons de revoir et d'ajuster la structure des frais en conséquence après la phase bêta du produit.

## **Prêt à participer ?**

Si vous avez bien compris la structure du produit, les risques et les frais — consultez cette page sur [comment participer](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) depuis l'interface web PancakeSwap et la [FAQ Pottery](https://docs.pancakeswap.finance/products/pottery/pottery-faq) !
