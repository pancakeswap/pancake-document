---
hidden: true
---

# FAQ sur le Partage des Revenus

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Comment les parts (rCAKE) sont-elles calculées ? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

À chaque distribution hebdomadaire, les parts de chaque utilisateur sont recalculées en fonction de :

1. La quantité de CAKE verrouillé qu'ils possèdent
2. La durée de verrouillage restante de leur CAKE verrouillé arrondie à la semaine inférieure, et la durée maximale de verrouillage autorisée (actuellement 52 semaines)

Par exemple :

Si un utilisateur a 50 CAKE verrouillés et que le temps de verrouillage restant est de 10,3 semaines, alors l'utilisateur possède `50 * (10 / 52 ) ~= 9,61` parts.

### J'ai mis à jour ma position ; pourquoi ai-je toujours 0 part ? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Les parts (rCAKE) sont mises à jour à chaque distribution hebdomadaire à 23 h 59 UTC tous les mercredis. Revenez après la prochaine distribution hebdomadaire pour voir vos parts mises à jour.

### Pourquoi mes parts sont-elles à 0 malgré une position de Staking active ? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Lors du calcul des parts (rCAKE), la durée de verrouillage restante est arrondie à la semaine inférieure. Par conséquent, pour recevoir des parts, vous devez vous assurer que votre position de Staking se déverrouille au plus tôt lors de la prochaine distribution.

Par exemple, pour recevoir des parts lors de la distribution de la semaine 1, vous devez :

* Rejoindre avant 23 h 59 UTC, le 2 août.
* Avoir une position de Staking de CAKE à durée fixe active qui se déverrouille après 23 h 59 UTC, le 9 août.

Si votre position de Staking se déverrouille avant 23 h 59 UTC, le 9 août, vous recevrez 0 part pour la semaine 1.

### Puis-je rejoindre une période de distribution en cours de semaine ? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Non, comme mentionné, les parts sont calculées au début de la période de distribution à 23 h 59 UTC chaque mercredi. Vous recevrez donc des parts à partir de la prochaine distribution et commencerez à accumuler des récompenses à partir de ce moment.

### Comment puis-je recevoir davantage de parts ? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Les parts étant calculées en fonction du montant de CAKE et de la durée de verrouillage restante, pour recevoir davantage de parts, vous pouvez :

* Verrouiller davantage de CAKE
* Prolonger votre position de Staking

Veuillez noter qu'après avoir ajouté du CAKE ou prolongé, les parts ne sont PAS mises à jour en temps réel et ne sont mises à jour qu'à chaque distribution hebdomadaire.

### Dois-je mettre à jour ma position de Staking lorsque j'ajoute davantage de CAKE ou que je prolonge le Staking ? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

Non, vous n'avez besoin de vous inscrire qu'une seule fois. Toutes les opérations ultérieures du pool de Staking CAKE informeront automatiquement le pool de partage des revenus et mettront à jour vos parts lors des prochaines distributions hebdomadaires.

### Pourquoi les récompenses hebdomadaires injectées ne correspondent-elles pas à 100 % au volume affiché sur les différents outils de suivi (comme la page Info) ?

Le nombre de récompenses en CAKE injectées chaque semaine peut ne pas correspondre à 100 % aux chiffres calculés à partir du volume affiché sur les différents outils de suivi. Plusieurs facteurs externes peuvent influencer le nombre de récompenses en CAKE pouvant être converties :

* Le prix du jeton CAKE pendant la conversion et le traitement des frais de trading
* Les prix des actifs sous-jacents pendant la conversion et le traitement des frais de trading
* Pour économiser les frais de gas et les coûts opérationnels, les revenus provenant de blockchains autres que BNB Chain sont traités mensuellement. Ils seront injectés avec un délai d'un mois avec une moyenne hebdomadaire.
* Certaines paires de trading peuvent avoir une Liquidité insuffisante lors du traitement des frais de trading.
* Certaines paires de trading peuvent contenir des jetons avec une logique personnalisée qui empêche le traitement de leurs frais.

Les Chefs travaillent activement à l'application d'outils et de pratiques pour s'assurer que davantage de frais de trading générés peuvent être traités et convertis en CAKE.
