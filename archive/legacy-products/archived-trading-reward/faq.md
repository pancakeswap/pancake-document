---
description: FAQ Trading Reward
---

# FAQ

{% hint style="danger" %}
\[Archivé] Trading Reward – À partir du 23 août 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Général

#### Pourquoi mon volume tradé n'a-t-il pas été suivi ?

* Les chiffres de volume prennent du temps à se mettre à jour et sont sujets aux délais du SubGraph. Veuillez revérifier ultérieurement.
* Votre transaction doit être routée via la **paire de trading exacte** mise en avant sur la [page Trading Reward](https://pancakeswap.finance/trading-reward#rewards-breakdown), y compris le niveau de frais. Consultez [ce tutoriel](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) pour savoir comment consulter vos routes de trading
* Seules les paires de trading V3 sont éligibles à ce programme
* Veuillez utiliser la même adresse de portefeuille éligible au programme de Trading Reward sur Ethereum et BNB Chain
* Si votre volume de trading dans une paire est trop faible, vous pourriez ne pas être éligible pour réclamer des récompenses
* Utiliser des agrégateurs de trading tiers peut entraîner le routage de vos transactions via d'autres fournisseurs de Liquidité et ne pas être suivi

#### Pourquoi ai-je beaucoup tradé mais ne reçu qu'un très petit montant de récompenses ?

Le montant de la récompense de trading est basé sur les frais de trading payés lors de ces transactions.

Si vos transactions sont routées via des paires avec un faible niveau de frais, par exemple 0,01 %, vous payez des frais très faibles pour votre transaction. Par conséquent, le nombre de récompenses diminuera en conséquence.

## Campagne Top Traders

#### Dois-je rester dans le classement requis pendant toute la durée pour gagner la campagne ?

Non, vous devez uniquement être classé plus haut que le classement requis **à la fin de la campagne**. Mais il est recommandé de se classer plus haut et de maintenir le rang. Veillez à vérifier régulièrement pour vous assurer que vous ne sortez pas du classement requis.

#### Sur quelle base le classement est-il établi ?

Le classement est basé sur le nombre de récompenses accumulées par chaque utilisateur via le trading. Le montant de la récompense équivaut à un pourcentage fixe des frais de trading payés lors des transactions.

## Campagne CAKE Stakers

#### Mon adresse était éligible pour la campagne précédente. Pourquoi n'est-elle pas éligible pour la dernière ?

Chaque campagne a ses propres exigences d'éligibilité, comme le seuil minimum de veCAKE au moment du snapshot.

De plus, le moment du snapshot est fixé à l'heure de fin de chaque campagne. Comme le veCAKE diminue avec le temps, votre solde de veCAKE peut tomber en dessous du seuil pour les futures campagnes.

Vous devrez peut-être augmenter votre veCAKE. Suivez simplement les instructions sur la page.

#### Pourquoi me dit-on que j'ai des récompenses supplémentaires qui ne peuvent pas être réclamées ?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

Le montant de veCAKE au moment du snapshot déterminera le montant maximum de récompenses que vous pouvez gagner dans la campagne. Consultez la note de bas de page dans la section « Max Reward Cap ».

Pendant qu'une campagne est active, vous pouvez augmenter votre veCAKE et élever ce plafond à tout moment.

#### Qu'est-ce que le « veCAKE au moment du snapshot » ?

Le veCAKE diminue progressivement avec le temps à mesure que le temps de verrouillage restant diminue. Par conséquent, similaire à l'iCAKE pour les IFO, un solde de veCAKE snapshot — le solde de veCAKE à un moment spécifique, qui est statique — est mieux adapté comme métrique de qualification.

Dans Trading Reward, le moment du snapshot correspond à la fin de chaque campagne. Ainsi, votre « solde de veCAKE au moment du snapshot » signifie « votre solde de veCAKE à l'heure de fin de la campagne ».

#### Comment le « veCAKE au moment du snapshot » est-il lié à la campagne ?

* Votre solde de veCAKE au moment du snapshot est supérieur au seuil requis
* Le montant maximum de récompenses que vous pouvez gagner est lié à y % de votre solde de veCAKE au moment du snapshot

Par exemple :

1. Alice a verrouillé 300 CAKE pour 2 ans (104 semaines) le jour 1. Le jour 1, Alice aura un solde de veCAKE de `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149`.
2. Une campagne de Trading Reward est lancée le jour 1, avec un seuil de veCAKE de 100 et un plafond de récompense de 1 %. La campagne se termine dans 30 jours.
3. Après 30 jours, la position d'Alice aura un temps de verrouillage restant d'environ 99,71 semaines, donc un solde de veCAKE de `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Par conséquent, pour cette campagne, Alice aura `143` veCAKE au moment du snapshot.
5. 143 est supérieur à 100, Alice est donc éligible à la campagne ; elle peut commencer à trader des paires éligibles pour gagner des récompenses de trading.
6. Avec un plafond de récompense de 1 %, le montant maximum de CAKE qu'Alice peut gagner dans cette campagne est de `143 * 1% = 1,43` CAKE.
7. Alice peut augmenter son veCAKE à tout moment avant la fin de la campagne, soit en verrouillant plus de CAKE, soit en prolongeant sa position.

#### Comment puis-je vérifier mon veCAKE au moment du snapshot pendant la campagne ?

Vous pouvez vérifier sur la page Trading Reward.

La page vous alertera lorsque votre veCAKE au moment du snapshot est inférieur au seuil ou que vos récompenses sont actuellement plafonnées par celui-ci.

Dans ces cas, vous pouvez cliquer sur le bouton « Increase veCAKE » pour augmenter votre veCAKE sans quitter la page.

#### Puis-je augmenter mon veCAKE pendant la campagne ?

Oui, vous pouvez augmenter votre veCAKE à tout moment avant la fin de la campagne. Votre « veCAKE au moment du snapshot » sera mis à jour en conséquence.
