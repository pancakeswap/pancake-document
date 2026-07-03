# FAQ Pottery

{% hint style="danger" %}
\[Archivé] Pottery – À partir du 3 novembre 2023
{% endhint %}

## Pourquoi avons-nous besoin de Pottery alors que nous avons déjà la Loterie v2 ?

Pottery est un produit complètement différent de la Loterie v2. C'est une combinaison du pool de CAKE verrouillé et de la fonction de loterie utilisant l'implémentation VRF de Chainlink pour un vrai aléatoire sécurisé. En participant à Pottery, vous ne perdrez aucun des CAKE que vous avez déposés ; vous risquez uniquement les récompenses de staking des CAKE que vous avez déposés. Ce produit est conçu pour les détenteurs de CAKE qui sont plus réticents au risque mais souhaitent tout de même participer à un produit de cette nature. C'est une façon facile, amusante et sûre d'avoir une chance de gagner du CAKE. Apprenez-en plus sur [la structure du produit ici](https://docs.pancakeswap.finance/products/pottery).

## Pottery remplace-t-il la Loterie v2 originale ?

Pottery ne remplace pas la Loterie v2 originale. Ces deux produits sont exploités et gérés séparément. Vous pouvez participer aux deux !

## Comment Pottery aide-t-il PancakeSwap et CAKE ?

Huit pour cent (8 %) du pot de prix distribué chaque semaine seront prélevés comme frais de destruction, ce qui accroît la valeur de CAKE. Nous prévoyons de revoir et d'ajuster la structure des frais en conséquence après la phase bêta du produit.

## À quoi sert la phase bêta de Pottery ?

En raison du fonctionnement de ce nouveau produit comme l'emprunt au trésor, la gestion des cohortes et le tirage. Le produit commencera en phase bêta avec un dépôt total plafonné pour chaque Pottery afin de s'assurer que tout se passe bien. Une fois la phase bêta terminée, nous pourrons revoir et ajuster différents paramètres en fonction des opérations et des retours de la communauté, comme les frais, la fréquence de chaque cohorte, la période de verrouillage, etc.

## Pourquoi doit-il verrouiller mon CAKE pendant 10 semaines ?

Si Pottery pouvait simplement utiliser le pool de staking flexible, sa structure de produit serait beaucoup plus simple — similaire à des produits comme PoolTogether et Moonpot. Cependant, le rendement actuel du pool de staking flexible n'est pas suffisant pour produire un pool de prix significatif pour le tirage. La décision a donc été prise de verrouiller le CAKE pour une durée modérée afin d'équilibrer les récompenses pouvant financer le pool de prix. Avec davantage d'opérations et de retours de la communauté, nous pourrons revoir et ajuster la durée de verrouillage.

## Pourquoi ne puis-je pas retirer ?

Veuillez noter que le bouton de retrait s'allumera et sera disponible uniquement après 10 semaines à compter de la date de verrouillage. La date de retrait est basée sur 10 semaines après la date et l'heure de verrouillage — 23:59 UTC le premier lundi de chaque mois.

## Pourquoi ne puis-je pas voir mon dépôt ?

Il peut y avoir parfois un certain délai en raison de la lecture du Subgraph ; un signal s'affichera en cas de délais — le montant correct devrait généralement s'afficher si vous vérifiez à nouveau dans 15 minutes.

## Comment savoir si j'ai gagné lors du tirage hebdomadaire ?

Après chaque tirage le vendredi vers midi UTC, vous pouvez consulter les résultats et les gagnants dans le panneau des rounds terminés. Une autre façon de vérifier si vous avez gagné lors d'un tirage hebdomadaire est de vérifier dans le panneau de réclamation s'il y a des prix à réclamer. Consultez [cette page sur comment participer](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) !

## Quelle est la source de financement du prix ?

Les pools de prix sont financés par les récompenses de staking des dépôts. Cependant, comme les récompenses de staking du pool de staking CAKE verrouillé ne sont distribuées qu'après la durée de verrouillage — 10 semaines dans ce cas — pour une meilleure expérience produit et pour faciliter les tirages hebdomadaires juste après la date de dépôt, le contrat emprunte 80 % des récompenses de staking totales estimées de la cohorte depuis le trésor CAKE sur la base de l'APR au moment du verrouillage. Le CAKE emprunté est utilisé pour le paiement de chaque tirage hebdomadaire. Apprenez-en plus sur [la structure du produit ici](https://docs.pancakeswap.finance/products/pottery) !

## Si je gagne, dois-je réclamer manuellement le prix ?

Oui, vous devrez cliquer sur le bouton Réclamer sous le panneau de réclamation sur la page Pottery.

## Quelle est la fréquence du Pottery ?

Chaque cohorte Pottery est ouverte au dépôt le vendredi précédant vers 10:00 UTC et ferme le premier lundi de chaque mois à 23:59 UTC, sauf arrangement et préavis spéciaux. Chaque cohorte aura 10 tirages hebdomadaires les 10 vendredis suivants à midi UTC.

Le premier Pottery ouvrira les dépôts le 5 août 2022 et se verrouillera le 8 août 2022 à 23:59 UTC.

## Pourquoi le dépôt Pottery n'est-il ouvert qu'une fois par mois ?

Cette disposition combine le dépôt pour le diriger vers le pool de staking verrouillé, de sorte que le contrat Pottery de la cohorte puisse coordonner les récompenses de staking du dépôt depuis le pool de staking verrouillé. Avec davantage d'opérations et de retours de la communauté, nous pourrons revoir et ajuster la fréquence.

## Quelle est la limite de dépôt ?

Il existe un dépôt minimum de 1 CAKE. En phase bêta du produit, il y aura également un plafond de dépôt maximum pour chaque cohorte que vous pouvez consulter dans le panneau de dépôt lorsque vous effectuez le dépôt. C'est pour s'assurer que tout du côté opérationnel, y compris l'emprunt au trésor, le staking verrouillé et le tirage, se déroule bien. Bien que le maximum que vous puissiez déposer soit le plafond de dépôt maximum de cette cohorte (si personne d'autre n'a déposé de CAKE), vous gagneriez tous les prix, mais cela signifie également que le rendement final que vous obtiendrez sera le même que si vous mettiez votre CAKE dans le pool de staking verrouillé pendant 10 semaines, et vous devrez également payer les frais de Pottery.

## Pourquoi avons-nous besoin du système de cohortes ? Pourquoi ne pas tout regrouper ensemble ?

Comme Pottery interagit avec le staking à terme fixe de CAKE, tout dépôt ne peut être retiré qu'après la durée de verrouillage. Si nous voulions tout regrouper, bien que nous puissions ajouter plus de dépôts après le verrouillage initial et les bloquer également pour 10 semaines (à partir du moment du nouveau dépôt), les déposants initiaux ne pourraient pas retirer à temps.

## Qu'est-ce que le token SHARE ?

Les tokens SHARE sont générés et distribués lorsque vous déposez dans le Pottery. Ils représentent et servent de justificatif de votre part dans le pool de dépôt.

Lors du retrait, le token SHARE sera transféré au contrat Pottery et détruit.

## Où puis-je donner mon avis sur ce produit ?

N'hésitez pas à nous contacter sur [Telegram](https://t.me/pancakeswap) ou [Discord](https://discord.gg/pancakeswap) si vous avez encore des doutes sur le format ou si vous avez des retours pour nous aider à l'améliorer davantage !
