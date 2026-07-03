# ❓ FAQ

### 1. Comment fonctionne la tolérance de Glissement pour les Swaps Cross-chain ?

Pour les Swaps Cross-chain, le pourcentage de tolérance de Glissement que vous avez sélectionné s'applique indépendamment aux Swaps sur les chaînes source et destination.

**Exemple :**

* Swap de BNB sur BNB Chain vers ARB sur Arbitrum
* Tolérance de Glissement définie à 1%
* La route pourrait être :
  1. Swap de BNB vers USDC sur BNB Chain
  2. Bridge de USDC depuis BNB Chain vers Arbitrum via Across
  3. Swap de USDC vers ARB sur Arbitrum
* Dans ce cas, la tolérance de Glissement de 1% s'applique séparément à :
  * Le Swap sur BNB Chain
  * Le Swap sur Arbitrum

Cela garantit que vous êtes protégé contre des mouvements de prix excessifs sur les deux segments de la transaction, tout en maintenant le processus de Bridging lui-même non affecté par les paramètres de Glissement.

### 2. Que se passe-t-il si ma transaction échoue ?

Si votre Swap Cross-chain rencontre un échec à n'importe quelle étape, voici comment cela est géré :

1.  **Échec du Swap/de la Transaction sur la Chaîne Source**

    ➝ Vous recevrez instantanément votre token d'origine sur la chaîne source.
2.  **Échec de la Transaction de Bridge**

    ➝ Across traitera un remboursement dans un délai de 90 minutes à 2 heures, et vous recevrez l'actif bridgé sur la chaîne source. Relay, quant à lui, traite le remboursement en moins d'une minute dans ce type de scénario entre SOL <> EVM.
3.  **Échec du Swap sur la Chaîne Destination**

    ➝ Vous recevrez l'actif bridgé sur la chaîne destination, sans le Swap final vers votre token cible.

{% hint style="info" %}
**Remarque :** Vous pouvez toujours vérifier le statut de vos transactions via l'onglet d'historique des transactions dans l'interface de connexion du portefeuille.
{% endhint %}

### 3. Mes Swaps Cross-chain sont-ils protégés contre les MEV ?

MEV Guard n'est pris en charge que sur BNB Chain lorsque les Swaps sont initiés directement depuis un portefeuille connecté avec MEV Guard activé.

* Si votre Swap Cross-chain implique un Swap sur BNB Chain en tant que chaîne source et que vous avez MEV Guard activé, ce Swap sera protégé contre les MEV.
* Si BNB Chain est la chaîne destination, le Swap est exécuté par le relayeur/système de Bridging et ne sera pas protégé contre les MEV, car il n'est pas initié par votre portefeuille connecté.

{% hint style="info" %}
**Remarque :** D'autres chaînes comme Arbitrum et Base ne prennent actuellement pas en charge la protection MEV Guard sur PancakeSwap.
{% endhint %}

### 4. Puis-je échanger des stablecoins entre chaînes ?

Oui — vous pouvez échanger et bridger des stablecoins comme USDC, USDT et DAI directement entre toutes les chaînes prises en charge.

Vous avez deux options :

1.  **Bridge Direct :**

    Bridgez directement des stablecoins pris en charge (comme USDC, USDT, etc.) d'une chaîne à une autre.
2.  **Swap vers d'autres tokens :**

    Vous pouvez également échanger un stablecoin contre n'importe quel autre token pris en charge sur la chaîne destination en utilisant les pools de Liquidité de PancakeSwap — avant ou après le Bridging.

{% hint style="info" %}
**Remarque :** Les stablecoins pris en charge pour le Bridge direct peuvent varier selon la chaîne.
{% endhint %}

### 5. Mes Swaps utiliseront-ils PCSX ?

Non — PCSX n'est pas pris en charge pour les Swaps Cross-chain.

Les Swaps Cross-chain sur PancakeSwap sont exclusivement acheminés via :

* **Les pools de Liquidité de PancakeSwap** (v2, v3, Infinity, StableSwap) pour les Swaps on-chain, et
* **Les protocoles Across & Relay** pour le Bridging des actifs entre chaînes.

PCSX ne peut pas être utilisé pour faciliter ou acheminer une quelconque partie d'une transaction de Swap Cross-chain.

### 6. Y a-t-il un montant minimum ou maximum pour les échanges ?

Oui — des limites minimales et maximales s'appliquent aux transactions Cross-chain.

* **Limite Maximum :**\
  Dépend de la Liquidité disponible du bridge pour le token et la chaîne sélectionnés. Cette valeur peut fluctuer en temps réel en fonction des conditions du réseau et de la Liquidité.
* **Limite Minimum :**\
  Définie pour garantir que le traitement de la transaction de Bridge est économiquement viable pour les relayeurs.

{% hint style="info" %}
**Remarque :** Les limites exactes min et max varient selon le token bridgé. Si le montant de votre transaction est en dehors de la plage autorisée, l'interface affichera un message d'erreur clair et vous invitera à ajuster le montant.
{% endhint %}
