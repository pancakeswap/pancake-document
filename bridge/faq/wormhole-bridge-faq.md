---
hidden: true
---

# FAQ du Wormhole Bridge

### Q : Comment puis-je vérifier ma transaction ? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Explorateur Wormhole

Sur la page de statut du Bridge, vous trouverez un lien vous permettant d'accéder à votre transaction sur l'Explorateur Wormhole. Lorsque votre transaction sur la chaîne source est terminée mais n'a pas encore été vérifiée par Wormhole, le statut de votre transaction ressemblera à ceci :

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

L'option « find redeem » est une méthode alternative que vous pouvez suivre pour compléter votre transaction sur la chaîne de destination. Vous pouvez utiliser cette méthode dans le cas où le Wormhole Bridge se bloque ou ne parvient pas à mettre à jour le statut de votre transaction Bridge. Pour récupérer votre transaction, cliquez d'abord sur le bouton de réclamation.

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

Cette option s'affichera alors pour vous permettre de reprendre votre transaction. Cliquez dessus pour être redirigé vers le forum (lien dans la prochaine question) où vous pourrez compléter votre transaction de réclamation. <br>

### Q : J'ai envoyé des tokens vers \<chaîne> — mes tokens ne sont pas arrivés dans mon Portefeuille cible, mais ils ont quitté mon Portefeuille d'origine. Que dois-je faire ?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

Vous devez soit a) les récupérer, soit, si la réclamation a déjà réussi, b) les ajouter à votre Portefeuille :

**a) Réclamation :**

* Accédez à [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)
* Vous devez saisir votre chaîne source et l'identifiant de transaction correspondant (que vous pouvez trouver dans votre Portefeuille ou avec votre adresse dans l'Explorateur de Blocs de la blockchain)

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Cliquez sur Recover
* Cliquez sur Redeem et acceptez l'approbation du Portefeuille

**b) Ajouter les tokens à votre Portefeuille :**

**Metamask :**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* Dans l'onglet des actifs MetaMask, cliquez sur « import tokens »
* L'adresse du contrat peut être trouvée dans la transaction de l'explorateur de blocs concerné en cliquant sur le nom du token. Lorsque vous cliquez sur le nom du token, une nouvelle fenêtre s'ouvre et l'adresse du contrat se trouve sur la droite dans le résumé du profil.
* Vous aurez également besoin d'un symbole — il peut s'agir de n'importe quel nom vous permettant de reconnaître le token.
* Cliquez sur « add custom token »

Consultez le tutoriel vidéo — Comment ajouter un token dans votre Portefeuille MetaMask [ici.](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### J'ai Bridgé le token X mais je ne peux pas l'échanger maintenant. Aucun DEX ne dispose de marchés liquides,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

Vous avez Bridgé un token qui ne dispose d'aucune Liquidité sur la chaîne cible. Vous devrez utiliser Portal bridge pour le Bridger en sens inverse. Vous pouvez le faire en collant l'adresse du contrat du token (que vous pouvez trouver dans votre Portefeuille ou avec votre adresse dans l'explorateur de la blockchain) dans le champ de recherche « select a token » de Portal.

Vous trouverez un aperçu complet des marchés liquides [ici](https://portalbridge.com/docs/faqs/liquid-markets).

#### Comment puis-je récupérer mes tokens sur la chaîne cible ?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

Si vous avez accidentellement actualisé la page pendant le processus de transfert ou si vous n'avez pas réclamé vos tokens, vous pouvez suivre le tutoriel [ici](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow).
