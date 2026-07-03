---
hidden: true
---

# FAQ veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Quelle est la différence entre le CAKE verrouillé et le veCAKE ? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE est une nouvelle version du Staking de CAKE à durée fixe offrant davantage d'avantages et de puissance aux détenteurs de CAKE verrouillé. Notamment le vote sur les jauges, des incitations supplémentaires, l'amplification du rendement, et bien plus encore.

#### Que se passe-t-il pour les récompenses du pool CAKE lors du déploiement du nouveau veCAKE <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

Les émissions de récompenses du pool CAKE seront redirigées pour récompenser tous les détenteurs de veCAKE en fonction de leur solde de veCAKE par rapport à l'offre totale.

Les récompenses en CAKE et les récompenses hebdomadaires de partage des revenus peuvent désormais être réclamées chaque semaine le jeudi.

Veuillez noter que pour continuer à recevoir des récompenses, les utilisateurs devront migrer vers le nouveau Staking veCAKE.

#### Quelle est la durée maximale pendant laquelle je peux verrouiller mon CAKE <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

La durée maximale pendant laquelle vous pouvez verrouiller votre CAKE a été étendue à 4 ans.

#### veCAKE est-il un nouveau jeton ? Peut-il être transféré ? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE est un nombre généré en temps réel basé sur la quantité de CAKE verrouillé et le temps de verrouillage restant. Il ne s'agit pas d'un jeton standard et ne peut pas être transféré.

#### Pourquoi mon solde de veCAKE a-t-il changé ? Comment calculer son solde ? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

Le solde de veCAKE diminue de manière linéaire jusqu'à 0 en fonction de la durée de verrouillage restante. Ainsi, lorsque nous approchons de l'heure de déverrouillage, votre solde diminue.

Le solde de veCAKE peut être calculé par :

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### Comment augmenter mon veCAKE ? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Une fois que vous avez une position veCAKE active, vous pouvez soit ajouter davantage de CAKE, soit renouveler/prolonger votre durée de verrouillage pour augmenter votre solde de veCAKE.

#### Que se passe-t-il lorsque la position se déverrouille ? Puis-je la renouveler immédiatement ? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Lorsque la position de Staking veCAKE est déverrouillée, vous pouvez retirer tous les CAKE stakés.

Pour renouveler votre position, vous devez retirer tous les CAKE et créer une nouvelle position de Staking en choisissant le montant à verrouiller et la durée de verrouillage.

#### J'ai verrouillé pour 1 semaine, pourquoi le temps de verrouillage restant est-il inférieur à 1 semaine ? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Lorsque vous verrouillez avec le nouveau veCAKE, l'heure de déverrouillage est arrondie au jeudi le plus proche en heure UTC. Par exemple, si vous verrouillez pour 1 semaine un mardi, votre heure de déverrouillage réelle sera le jeudi suivant, soit 2 jours plus tard.

Vous pouvez prévisualiser votre heure de déverrouillage réelle en bas de la page.

#### Puis-je verrouiller davantage de CAKE dans le pool CAKE ? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

Non.

Une fois veCAKE déployé, le pool de Staking CAKE sera déprécié et n'acceptera plus aucune prolongation ou dépôt de CAKE.

Pour verrouiller du CAKE et bénéficier de ses avantages, rendez-vous sur la page veCAKE.

#### Pourquoi ne puis-je pas migrer ? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

La migration du pool CAKE vers veCAKE nécessite que vous ayez une position active. Si votre position de Staking dans le pool CAKE est déjà déverrouillée, retirez simplement ces CAKE et créez une position de Staking veCAKE native.

Dans certains cas, la migration ne peut pas être effectuée lorsque le temps de verrouillage restant dans votre pool CAKE est inférieur à 7 jours. Dans ce cas, attendez simplement le déverrouillage, retirez ces CAKE et créez une position de Staking veCAKE native.

#### Puis-je retirer mon CAKE verrouillé de manière anticipée ? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

Non.

Une fois verrouillé, le CAKE sera staké dans le contrat veCAKE jusqu'à l'heure de déverrouillage.

#### Puis-je migrer partiellement mon CAKE ? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

Non.

Vous ne pouvez migrer l'intégralité de votre position dans le pool CAKE qu'en une seule fois.

#### Que se passera-t-il avec iCAKE, bCAKE, vCAKE et rCAKE ? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Pour iCAKE :**

L'IFO iCAKE a maintenant été mis à niveau pour prendre en charge veCAKE. Consultez :

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Pour bCAKE :**

L'amplificateur de Farm bCAKE a maintenant été mis à niveau pour prendre en charge veCAKE. Consultez :

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Pour vCAKE :**

Le Vote vCAKE a maintenant été mis à niveau pour prendre en charge veCAKE. Consultez :

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Pour rCAKE :**

Tous les détenteurs de veCAKE (natifs ou migrés) seront automatiquement inscrits dans le nouveau pool de partage des revenus. Les parts de revenus sont distribuées selon le calendrier existant. L'ancien pool de partage des revenus sera abandonné ; les utilisateurs peuvent réclamer leurs récompenses en attente en accédant à la carte des avantages. Consultez :

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Lien rompu](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### Les portefeuilles multisig peuvent-ils être utilisés pour interagir avec veCAKE ?

Oui

Cependant, un modificateur `noContract` a été mis en place dans le contrat de Staking veCAKE pour les adresses non inscrites sur la liste blanche. Pour activer le Staking ou la migration depuis le pool de Staking CAKE à durée fixe, tous les portefeuilles multisig basés sur des contrats doivent effectuer une action unique d'auto-inscription sur la liste blanche.

Pour s'inscrire sur la liste blanche, visitez l'une des pages suivantes :

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Une invite devrait apparaître. Cliquez sur « Liste blanche » et procédez à la transaction dans votre portefeuille multisig.

Une transaction sera envoyée au propriétaire du veCAKE, qui est un contrat avec une fonction d'écriture sans permission permettant à tout contrat de s'auto-inscrire sur la liste blanche.

Si l'invite n'apparaît pas, suivez ces instructions pour exécuter la transaction depuis [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11) :

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Pourquoi y a-t-il plusieurs APR ?

Verrouiller du CAKE pour obtenir du veCAKE offre un certain nombre d'avantages considérables autour de la suite de produits développés par PancakeSwap. Les avantages et incitations se présentent sous différentes formes et proviennent de sources différentes. C'est pourquoi il y a plusieurs APR.

Vous pouvez les gagner tous simultanément ; l'APR combiné sera donc la somme de tous les APR.

Veuillez noter que de nombreux autres avantages de veCAKE ne peuvent pas être quantifiés sous la forme d'APR, comme [l'amplificateur de rendement bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) ou [l'IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). N'oubliez pas de les consulter également.

#### Qu'est-ce que l'APR du pool veCAKE ?

Il s'agit de l'incitation provenant des émissions de CAKE, dont le taux est contrôlé par la jauge de vote du pool veCAKE.

Pour augmenter les émissions vers cette jauge, consultez [le Vote des Jauges](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### Qu'est-ce que l'APR de Partage des Revenus ?

Il s'agit de l'incitation provenant du partage des revenus du protocole, issus des frais de Swap collectés dans les produits DEX.

Consultez [le Partage des Revenus](/broken/pages/wQegezs7c6A2HzQjPEjh) pour plus d'informations.
