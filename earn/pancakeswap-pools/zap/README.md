---
description: Ajouter de la Liquidité en un seul clic
---

# Zap

### Qu'est-ce que le Zap <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap est une fonctionnalité qui vous permet d'ajouter de la Liquidité facilement. Avec Zap, vous pouvez fournir de la Liquidité avec n'importe quel token dont vous disposez, indépendamment des tokens requis dans le Pool. Définissez simplement la plage de prix, choisissez le montant à fournir et exécutez. Vos tokens seront automatiquement équilibrés pour former la position de Liquidité, tout en étant échangés de la manière la plus efficace possible, avec le plus faible impact sur les prix et le moins de Glissement possible.

### Chaînes prises en charge

* v3 — Tous les Pools sur BNB Chain, Pools sélectionnés sur les réseaux Ethereum et Arbitrum
* Infinity — Tous les Pools CLAMM (sans Hook) sur BNB Chain

### Comment utiliser <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Pour l'instant, Zap prend en charge :

* 🆕 N'importe quel token !
* Utilisation d'un token unique
* 🆕 Utilisation de deux tokens
* 🆕 Ou... utilisation de plusieurs tokens (oui, il peut être utilisé comme collecteur de dust)

#### Démarrer <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Pour utiliser Zap, accédez simplement à la page Add Liquidity, sélectionnez la paire de Trading pour laquelle vous souhaitez fournir de la Liquidité, le niveau de frais et la plage de prix.

Sélectionnez ensuite le montant de tokens que vous souhaitez fournir en Liquidité.

L'option Zap apparaîtra automatiquement lorsqu'un ou plusieurs tokens manquent de solde.

Cliquez sur le lien pour ouvrir la fenêtre modale Zap.

#### Initier le Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dans la nouvelle fenêtre modale « Zap in », vous trouverez les champs suivants :

1. La paire de Trading pour laquelle vous effectuez un Zap (fourniture de Liquidité).
2. Le ou les tokens de dépôt et le ou les montants à déposer. Vous pouvez librement ajouter ou supprimer des tokens pour le Zap.
3. La plage de prix de la nouvelle position. Vous pouvez également cliquer sur les flèches pour basculer entre différents affichages de prix.
4. Une répartition détaillée de la façon dont la fonctionnalité Zap traitera vos tokens de dépôt.
5. Un récapitulatif des statistiques incluant :
   1. La valeur estimée en USD pour la nouvelle position de Liquidité.
   2. Le montant estimé de tokens dans la nouvelle position de Liquidité.
   3. Les fonds restants estimés en USD après le Zap. Dans la plupart des cas, cette valeur devrait être nulle. Si le Pool de Liquidité ou les tokens disposent de très peu de Liquidité, cette valeur peut augmenter.
   4. L'impact sur les prix pour les Swaps de tokens et les rééquilibrages lors du Zap.
   5. L'impact sur les prix pour l'ajout de Liquidité et la construction de la position.
   6. Les frais de Zap. Selon la paire de Liquidité, le taux de frais peut varier.

{% hint style="warning" %}
Notez que vous pourriez avoir besoin de reconfigurer le montant à Zapper en fonction de votre solde disponible. Si vous n'avez pas de solde pour l'un des tokens, veuillez le supprimer.
{% endhint %}

{% hint style="info" %}
Vous remarquerez peut-être que les paramètres d'« Add V3 Liquidity » sont automatiquement reportés dans la fenêtre modale Zap, notamment le montant du dépôt et les paramètres de plage de prix.
{% endhint %}

#### Lancer le Zap <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Cliquez enfin sur « Approve » et confirmez dans la fenêtre contextuelle du Portefeuille pour l'autorisation de token.

Cliquez ensuite sur « Preview » pour ouvrir la fenêtre modale de confirmation finale. Avant de continuer, veuillez prendre le temps de vérifier toutes les statistiques et estimations affichées dans la fenêtre de confirmation finale, en particulier les chiffres d'impact et le Glissement maximum.

Cliquez enfin sur « Add Liquidity » et confirmez dans la fenêtre contextuelle de votre Portefeuille.

Une fois la transaction confirmée, votre nouvelle position sera visible dans la page « My Position ».

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Paramètres supplémentaires <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Si vous souhaitez personnaliser davantage votre expérience Zap, cliquez simplement sur l'icône d'engrenage dans le coin supérieur droit. Dans les paramètres, vous pouvez configurer :

* Le Glissement maximum lors du Zap.
* Le délai d'expiration de la transaction.
* L'utilisation ou non de la Liquidité agrégée de KyberSwap pour effectuer le rééquilibrage des tokens. Désactivez cette option si vous souhaitez n'échanger que dans les Pools PancakeSwap.
* Le mode Degen peut être utilisé pour effectuer des Zaps avec un Glissement très élevé. Non recommandé pour un usage courant — à utiliser à vos propres risques.

{% hint style="warning" %}
Veuillez noter que les paramètres de Glissement et de délai d'expiration sont indépendants de ceux des pages Swap et Liquidité.
{% endhint %}

#### Zap avec deux tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Vous pouvez désormais effectuer un Zap de votre Liquidité avec deux tokens. Cela est utile lorsque votre solde disponible ne correspond pas aux paramètres de prix et au ratio de tokens requis. Utilisez simplement Zap et le ratio sera automatiquement rééquilibré.

#### Zap avec plusieurs tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Oui, cela fonctionne comme un collecteur de tokens dust. C'est idéal pour regrouper de petits soldes dans votre Portefeuille et les placer dans une position pour commencer à générer des frais de Trading.&#x20;
