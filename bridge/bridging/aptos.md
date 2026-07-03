---
description: Bridge CAKE entre les chaînes EVM et Aptos
---

# Comment effectuer un Bridge – EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Le guide suivant utilise BNB Chain comme exemple de chaîne EVM. Le même processus peut être appliqué à Ethereum.
{% endhint %}

## Bridge CAKE de BNB Smart Chain vers Aptos

1 - Assurez-vous que votre Portefeuille prend en charge à la fois BNB Smart Chain et le réseau principal Aptos. Ou que vous avez les deux Portefeuilles installés dans votre navigateur.

Ouvrez ensuite le [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Nous devons d'abord connecter notre Portefeuille BNB Smart Chain.

Cliquez sur « Connect » et choisissez le Portefeuille de votre choix dans la section « EVM ». Confirmez et approuvez ensuite dans la fenêtre contextuelle de votre Portefeuille.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Nous devons ensuite connecter notre Portefeuille Aptos.

Dans la fenêtre de connexion du Portefeuille, choisissez le Portefeuille de votre choix dans la section « Aptos ». Confirmez et approuvez ensuite dans la fenêtre contextuelle de votre Portefeuille.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Cliquez sur le « v » dans le champ de sélection de token supérieur et choisissez « CAKE ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Saisissez le nombre de CAKE que vous souhaitez Bridger vers Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Si votre Portefeuille Aptos vient d'être créé et ne dispose pas de solde en APT (Aptos Coin), nous vous recommandons de conserver l'option « gas on destination » à sa valeur par défaut. Le Bridge déposera une petite quantité d'APT dans votre Portefeuille, non seulement pour vous aider à démarrer votre parcours sur Aptos, mais aussi parce que vous aurez besoin d'APT pour le gas afin d'enregistrer et de réclamer vos CAKE Bridgés.

Modifier cette option pourrait entraîner l'échec du Bridging.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Cliquez sur « Transfer » pour initier la transaction de Bridging et confirmez via la fenêtre contextuelle de confirmation du Portefeuille.

Veuillez noter que selon l'état de votre Portefeuille BNB Smart Chain et de votre Portefeuille Aptos, vous pourriez avoir besoin d'approuver **plusieurs** confirmations de Portefeuille. Par exemple, si vous Bridgez des CAKE vers Aptos pour la première fois, vous devrez :

* Approuver la dépense de CAKE sur le contrat de Bridging (depuis votre Portefeuille BNB Smart Chain)
* Enregistrer CAKE (depuis votre Portefeuille Aptos)

Pour plus de détails, consultez [cette explication détaillée](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 - Installez-vous confortablement. Cela ne devrait prendre que quelques minutes. Une fois le Bridging terminé, les CAKE seront déposés dans votre Portefeuille Aptos. Vous pouvez suivre la progression grâce à la barre de progression.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Bridging de CAKE vers Aptos pour la première fois

Le Bridging de CAKE vers des Portefeuilles Aptos nécessite des transactions d'enregistrement et de réclamation. Cela est fait pour renforcer la sécurité des utilisateurs et est propre à Aptos.

### **Si vous avez déjà des APT (Aptos Coin) dans votre Portefeuille :**

Il vous sera demandé d'enregistrer CAKE sur votre Portefeuille Aptos s'il n'est pas encore enregistré. Aucune transaction de réclamation supplémentaire n'est nécessaire dans ce cas.

### **Si vous n'avez pas d'APT (Aptos Coin) dans votre Portefeuille :**

Une fois la transaction Bridge terminée, vous devrez réclamer manuellement vos CAKE. Pour couvrir les frais de gas liés à la réclamation, des tokens APT seront envoyés à votre Portefeuille Aptos depuis votre Portefeuille source.

Ces étapes d'enregistrement et de réclamation ne s'appliquent que lors de votre première interaction avec un token sur Aptos. Les transferts ultérieurs du même token ne nécessiteront pas ces actions.

Avant de Bridger des CAKE vers Aptos pour la première fois, assurez-vous que votre adresse Aptos dispose de suffisamment d'APT pour les frais de gas. Pour plus de détails, consultez l'explication d'Aptos ici : [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Bridge CAKE d'Aptos vers BNB Smart Chain

1 - Assurez-vous que votre Portefeuille prend en charge à la fois BNB Smart Chain et le réseau principal Aptos. Ou que vous avez les deux Portefeuilles installés dans votre navigateur.

Ouvrez ensuite le [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Nous devons d'abord connecter notre Portefeuille BNB Smart Chain.

Cliquez sur « Connect » et choisissez le Portefeuille de votre choix dans la section « EVM ». Confirmez et approuvez ensuite dans la fenêtre contextuelle de votre Portefeuille.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Nous devons ensuite connecter notre Portefeuille Aptos.

Dans la fenêtre de connexion du Portefeuille, choisissez le Portefeuille de votre choix dans la section « Aptos ». Confirmez et approuvez ensuite dans la fenêtre contextuelle de votre Portefeuille.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Cliquez sur le « v » dans le champ de sélection de token supérieur et choisissez « CAKE ». Cliquez ensuite sur le bouton à double flèche au milieu de la page pour inverser la direction du Bridging.

Assurez-vous que le réseau « Aptos » se trouve dans le champ supérieur.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - Saisissez le nombre de CAKE que vous souhaitez Bridger vers BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - Si votre Portefeuille BNB Smart Chain vient d'être créé et ne dispose pas de solde en BNB (token de gas), nous vous recommandons de conserver l'option « gas on destination » à sa valeur par défaut. Le Bridge déposera une petite quantité de BNB dans votre Portefeuille. Cela vous aidera à démarrer votre parcours sur BNB Smart Chain et à explorer le dynamique écosystème PancakeSwap.

7 - Cliquez sur « Transfer » et approuvez les transactions depuis la fenêtre contextuelle de votre Portefeuille.

8 - Installez-vous confortablement. Cela ne devrait prendre que quelques minutes. Une fois le Bridging terminé, les CAKE seront déposés dans votre Portefeuille BNB Smart Chain. Vous pouvez suivre la progression grâce à la barre de progression.
