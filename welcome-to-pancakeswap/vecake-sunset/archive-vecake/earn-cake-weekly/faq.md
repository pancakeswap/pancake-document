# FAQ

### J'ai verrouillé mes CAKE ou migré ma position du pool CAKE. Pourquoi ai-je encore 0 parts ? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Les parts sont mises à jour à chaque distribution hebdomadaire à 00:00 UTC chaque jeudi.

Les récompenses s'accumulent uniquement lorsque vous avez complété un epoch entier de Staking.&#x20;

Les epochs sont des périodes de 7 jours, démarrant chaque jeudi à 00:00 UTC. Par exemple, si vous stakez un mardi, votre premier epoch commencera le jeudi. Une fois votre Staking terminé jusqu'au jeudi suivant, vous pourrez réclamer vos récompenses pour cette période du jeudi au jeudi suivant, c'est-à-dire l'epoch 1.

Revenez vérifier chaque jeudi pour consulter vos récompenses mises à jour.

### Pourquoi mes parts/récompenses sont-elles à 0 malgré une position de Staking active ? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Lors du calcul des récompenses, la durée de verrouillage restante est arrondie à la semaine inférieure. Par conséquent, pour recevoir des parts, vous devez vous assurer que votre position de Staking se déverrouille au plus tôt le jeudi suivant à 00:00 UTC.

Par exemple, la semaine 1 commence à 00:00 UTC, jeudi 1er janvier. Pour recevoir des récompenses pour la distribution de la semaine 1, vous devez :

* Rejoindre avant 00:00 UTC, le 1er janvier.
* Disposer d'une position de Staking veCAKE active, qui se déverrouille au plus tôt le 00:00 UTC, 15 janvier (jeudi de la semaine 3).

Veuillez noter que si votre position de Staking se déverrouille à 00:00 UTC, 8 janvier (jeudi de la semaine 2), vous recevrez tout de même 0 récompenses pour la semaine 1 car votre solde veCAKE atteindra 0 à 00:00 UTC, le 8 janvier.

### Puis-je rejoindre une période de distribution en milieu de semaine ? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Non. Comme indiqué, les récompenses ne peuvent commencer à s'accumuler que si vous stakez déjà au début de l'epoch, c'est-à-dire chaque semaine à 00:00 UTC le jeudi.&#x20;

### Comment recevoir davantage de récompenses ? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Étant donné que vos parts dans les pools sont calculées en fonction de votre solde veCAKE au moment de la distribution (à 00:00 UTC le prochain jeudi), pour recevoir davantage de récompenses, augmentez simplement votre solde veCAKE en :

* Verrouillant davantage de CAKE dans la position de Staking veCAKE
* Renouvelant votre position de Staking

Veuillez noter qu'après avoir ajouté des CAKE ou prolongé votre position, vos parts ne seront mises à jour qu'au début du prochain epoch, soit à 00:00 UTC le prochain jeudi.

### Pourquoi les récompenses injectées chaque semaine ne correspondent-elles pas à 100 % au volume affiché sur les différents outils de suivi (comme la page Info) ? Pourquoi les récompenses hebdomadaires du pool CAKE ne correspondent-elles pas à 100 % aux résultats du Vote par Gauges ?

Le nombre de récompenses CAKE injectées chaque semaine peut ne pas correspondre exactement aux chiffres calculés à partir du volume affiché sur les différents outils de suivi. Plusieurs facteurs externes peuvent influencer le nombre de récompenses CAKE pouvant être converties :

* Le prix du token CAKE au moment où les frais de trading sont convertis et traités
* Les prix des actifs sous-jacents au moment où les frais de trading sont convertis et traités
* Pour économiser des frais de gas et des coûts opérationnels, les revenus des blockchains autres que BNB Chain sont traités mensuellement. Ils seront injectés avec un délai d'un mois et lissés sur une base hebdomadaire.
* Certaines paires de trading peuvent manquer de Liquidité lors du traitement des frais de trading.
* Certaines paires de trading peuvent contenir des tokens avec une logique personnalisée empêchant le traitement de leurs frais.
* Des retards de transactions dus aux performances des infrastructures et des systèmes de support.

Les Chefs travaillent activement à l'application d'outils et de pratiques pour s'assurer qu'un plus grand nombre de frais de trading générés puissent être traités et convertis en CAKE.
