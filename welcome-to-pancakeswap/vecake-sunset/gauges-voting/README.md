---
description: Utilisez votre veCAKE pour voter et décider de la distribution des émissions de CAKE
hidden: true
---

# Vote par Gauges

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Qu'est-ce qu'une gauge ?

Pour comprendre le Vote par Gauges, vous pouvez considérer tout produit nécessitant des émissions de CAKE comme une série de gauges. Cela inclut les farms, le pool de récompenses hebdomadaires CAKE, les vaults de gestionnaires de positions, etc.

Les détenteurs de veCAKE peuvent désormais utiliser leur veCAKE comme votes pour décider quel pourcentage de CAKE va vers quel produit. Plus une gauge accumule de veCAKE via le Vote par Gauges, plus les émissions de CAKE allouées au pool de Liquidité ou au vault du gestionnaire de positions sous-jacent seront importantes.

{% hint style="info" %}
Les votes de chaque epoch (E-0) déterminent les émissions de CAKE pour l'epoch suivante (E+1), et ces changements ne prennent effet qu'après la clôture de l'epoch en cours.
{% endhint %}

#### Types de gauges

Il existe deux types de gauges : « core » et « non-core ». Les émissions de CAKE vers les premières sont contrôlées par la Cuisine, tandis que la communauté influence les émissions vers les pools « non-core » en votant avec du veCAKE.

1. Les gauges « core » incluent les paires avec des tokens majeurs et des stablecoins (WBTC, ETH, BNB, USDC, USDT, etc.) — la Cuisine veillera à ce que ces paires reçoivent suffisamment de récompenses CAKE car elles contribuent significativement aux revenus du protocole.
2. Les gauges « non-core » représentent toutes les autres gauges non classifiées comme gauges « core ».

## Comment voter ?

### 1 - Comprendre le calendrier de vote

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Le vote de pondération des gauges se déroule toutes les deux semaines. Le début d'un epoch, comme pour le partage de revenus, est à 00:00 UTC chaque jeudi en semaine paire.

Dans l'exemple ci-dessus :

* L'Epoch 1 commence à 00:00 UTC, le 1er, jeudi de la semaine 1.
* L'Epoch 1 se termine 2 semaines plus tard, à 00:00 UTC, le 15, jeudi de la semaine 3.
* Les utilisateurs peuvent voter du 1er au 14 à partir de 00:00 UTC.
* **Aucun** vote ne peut être exprimé entre le 14 et le 15 à 00:00 UTC, car les votes sont en cours d'ajustement et de décompte.
* Les résultats du vote seront enregistrés par snapshot à 00:00 UTC le 15. Fin de l'Epoch 1.
* Les résultats du vote seront appliqués dans les 72 heures suivant la clôture d'un epoch.

### 2 - Devenir éligible

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Étant donné que le veCAKE diminue progressivement en fonction du temps de verrouillage restant, les résultats du vote seront enregistrés par snapshot à la fin de chaque epoch. Cela inclut le nombre total de veCAKE et le veCAKE de chaque utilisateur.

Dans l'exemple ci-dessus :

* Les résultats de l'Epoch 1 seront basés sur les soldes veCAKE à 00:00 UTC, le 15.
* Les utilisateurs dont la position veCAKE se déverrouille avant ou au 15 auront un solde veCAKE de 0 au moment du snapshot. Ils n'ont donc aucun pouvoir de vote pour l'Epoch 1.

Par conséquent, pour être éligible, vous devez disposer d'une position veCAKE active qui se déverrouille **APRÈS** la date de fin/snapshot de l'epoch en cours.

Dans l'exemple ci-dessus :

* Si vous souhaitez voter lors de l'epoch 1, vous devez avoir une position veCAKE qui se déverrouille le 21 ou après le 21, c'est-à-dire le jeudi de la semaine 3.

### 3 - Consulter les résultats de vote actuels

Rendez-vous dans « CAKE staking », faites défiler vers le bas et cherchez la section « Gauges Voting », puis cliquez sur « Check Gauges ».

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Dans la section supérieure gauche, vous trouverez :

* Votre veCAKE.
* La date du snapshot et la date de fin du vote pour l'epoch en cours.
* Le nombre total de récompenses CAKE à distribuer lors du prochain epoch, basé sur les résultats du vote de l'epoch en cours.
* Le montant total de votes veCAKE exprimés.

En haut à droite, vous trouverez un graphique en secteurs représentant le pourcentage reçu par chaque gauge.

En bas, vous trouverez la liste complète de toutes les gauges de vote, avec le nombre de votes reçus et le pourcentage de pondération attendu pour l'epoch en cours. Il existe également des champs « boost » et « caps » détaillant deux caractéristiques importantes des gauges. Continuez la lecture pour plus de détails.

#### Boost de gauge et plafonds d'émissions

Pour s'assurer que les récompenses CAKE vont aux gauges les plus productives, chaque gauge peut se voir appliquer un boost et/ou un plafond d'émissions. Ces deux caractéristiques peuvent coexister.

Le Boost de gauge est un multiplicateur appliqué au nombre de votes reçus par une gauge, allant de 1x à 2,5x (les gauges pour les pools V3 sont plafonnées à 2x). Cela vise à encourager les votes et la Liquidité pour les paires de trading importantes.

Le plafond d'émissions est un plafond maximum sur le pourcentage de pondération qu'une gauge peut recevoir, allant de 2 % à 20 %. Cela vise à promouvoir l'équité dans l'allocation et à prévenir les abus du système de gauges.

Par exemple :

* Une gauge a 10 votes, un boost de 2x et un plafond de 15 %. Le total des votes est de 100.
* Après application du boost, cette gauge aura 20 votes, soit 20 % de pondération par rapport au total (100).
* Cependant, avec un plafond de 15 %, le pourcentage final de récompenses CAKE que cette gauge reçoit lors du prochain epoch sera ajusté à 15 %.

#### Comment le Boost de gauge et les plafonds d'émissions sont-ils déterminés ?

Lors du processus de candidature pour une gauge, nous demandons aux candidats de proposer la valeur du multiplicateur de boost et le pourcentage de plafond d'émissions qu'ils souhaitent attribuer à la gauge. Ces valeurs doivent être votées par les détenteurs de veCAKE, conjointement avec l'ensemble de la candidature pour la gauge.

L'option par défaut pour toutes les gauges est un multiplicateur de 1,00x et un plafond d'émissions de 5 %. Ces valeurs peuvent être modifiées par de futures propositions.

{% hint style="info" %}
Veuillez noter que les résultats du vote sont mis à jour chaque semaine. Les chiffres sont calculés en fonction des soldes veCAKE à 00:00 UTC le prochain jeudi.
{% endhint %}

### 4 - Ajouter des gauges à voter

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Pour voter sur une gauge, faites défiler vers le bas et cherchez la section « My Votes ». Cliquez sur « Add Gauge ».

Dans la fenêtre contextuelle, vous pouvez ajouter des gauges à votre liste de votes en cliquant sur l'icône bleue « + ». Vous pouvez consulter les résultats de vote actuels dans la liste, ainsi que les boosts et plafonds.

Pour localiser rapidement une gauge, vous pouvez utiliser des filtres pour trier les gauges par blockchains, niveaux de frais et types de Liquidité. Vous pouvez également saisir le ticker du token dans le champ de recherche.

### 5 - Sélectionner le pourcentage de veCAKE à allouer à chaque gauge

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Une fois les gauges ajoutées, vous pouvez sélectionner quel pourcentage de votre veCAKE va vers chacune des gauges.

C'est parce que :

* Le veCAKE diminue progressivement avec le temps de verrouillage restant. Il est peu pratique d'estimer et de calculer le nombre exact de veCAKE à voter.
* Il est fastidieux de revoter à chaque epoch à venir. Par conséquent, le Vote par Gauges est conçu pour reporter vos décisions de vote sur tous les epochs à venir jusqu'à ce que vous en exprimiez un nouveau.

Dans l'exemple ci-dessus :

* En ce moment, j'ai 2,62 veCAKE.
* J'ai décidé d'allouer 80 % à CAKE-BNB, soit 2,10 veCAKE en ce moment.
* 20 % à USDC-ETH, soit 0,52 veCAKE, également en ce moment.
* Mon total de veCAKE diminuera progressivement avec le temps de verrouillage restant. Au moment du snapshot, je pourrais avoir moins de veCAKE, mais ma décision de répartition 80 % - 20 % sera toujours appliquée aux résultats finaux.
* De plus, cette décision de 80 % - 20 % sera appliquée à chaque epoch à venir jusqu'à ce que je la mette à jour en soumettant une nouvelle demande de vote, ou jusqu'à ce que mon veCAKE atteigne 0 en raison du déverrouillage.

Une fois votre décision confirmée, cliquez sur « Submit vote » et confirmez dans votre Portefeuille.

### 6 - Mettre à jour vos votes

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Une fois votre vote soumis, vous pouvez voir vos votes mis à jour dans « Current Votes ». Et le veCAKE restant est mis à jour.

Veuillez noter que la décision de vote pour chaque gauge ne peut être mise à jour que tous les 10 jours. Une fois une demande de vote soumise, toutes les gauges votées seront soumises à une période de refroidissement de 10 jours avant de pouvoir soumettre une nouvelle demande de mise à jour.

Pour mettre à jour votre décision de vote, modifiez le pourcentage et soumettez à nouveau.

{% hint style="info" %}
Veuillez noter qu'après avoir obtenu davantage de veCAKE en ajoutant des CAKE ou en prolongeant la durée de verrouillage, vous devez mettre à jour manuellement toutes les gauges en soumettant à nouveau la demande de vote.

La période de refroidissement de 10 jours s'applique quelle que soit la modification de vos décisions en pourcentage.
{% endhint %}
