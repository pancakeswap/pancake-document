# FAQ Social Login

{% hint style="info" %}
Pour plus d'informations, consultez : [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Vue d'ensemble générale

**1. Qu'est-ce que le social login de PancakeSwap et pourquoi l'utiliser ?**

Le social login vous permet d'accéder à PancakeSwap en utilisant votre compte **Google**, **X (Twitter)**, **Discord** ou **Telegram** — aucune extension de portefeuille ni phrase secrète requise. Un portefeuille auto-custodial est créé en arrière-plan, vous permettant d'essayer DeFi instantanément, même avec de petits montants. Cela abaisse la barrière à l'entrée, surtout dans les moments où l'action est urgente.

**2. Quelles chaînes le social login prend-il en charge ?**

Votre portefeuille social login fonctionne sur toutes les chaînes actuellement prises en charge par PancakeSwap :

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Tous les portefeuilles sont **compatibles EVM** et peuvent être utilisés sur ces réseaux nativement via PancakeSwap. Si vous souhaitez voir la prise en charge d'autres chaînes (y compris non-EVM), faites-le nous savoir !

**3. Où puis-je utiliser le portefeuille social login ?**

Vous pouvez l'utiliser directement dans n'importe quel **navigateur** de bureau ou mobile via l'application web PancakeSwap. Il n'est **pas compatible** avec les applications de portefeuille externes ni les navigateurs dApp.



### 🛠️ Configuration et utilisation du portefeuille

**4. Comment le portefeuille est-il créé et sécurisé ?**

Votre portefeuille est créé automatiquement lors de la connexion et sécurisé à l'aide d'un **système de partage de clés 2 sur 2**. Les deux partages sont nécessaires pour reconstituer la clé et générer une signature.

Pour plus d'informations sur le chiffrement des partages, consultez :

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Combien de portefeuilles puis-je créer ?**

Vous obtenez **un portefeuille par compte social par dApp**. Par exemple, si vous utilisez votre compte Google sur une autre application utilisant également Privy, un portefeuille séparé sera créé.



### 🔐 Sécurité et confidentialité

**6. Quelqu'un peut-il accéder à mon portefeuille s'il vole mon appareil ?**

Non. Même si quelqu'un accède à votre appareil, il aurait encore besoin de votre **social login** et (si défini) de votre **mot de passe de récupération**.

**7. Quelles données sont stockées par PancakeSwap ou Privy ?**

* PancakeSwap **ne stocke pas** les partages de clés liés au portefeuille.
* Privy stocke le **partage d'authentification chiffré et le partage de récupération (si le processus de récupération n'est pas configuré)**.

> Si vous n'avez pas terminé la configuration de récupération, votre partage de récupération reste stocké par Privy par défaut. Pour plus d'informations, consultez : [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Récupération et gestion des sessions

**8. Puis-je utiliser le même portefeuille sur un autre appareil ou navigateur ?**

Oui ! Connectez-vous simplement avec le même compte social. S'il s'agit d'un nouvel appareil, vous devrez passer par le processus de récupération à l'aide de votre mot de passe de récupération (si configuré).

**9. Que se passe-t-il si je change d'appareil ?**

Vous serez invité à vous reconnecter avec votre compte social et à passer par le processus de récupération (configuration du mot de passe). Si vous n'avez pas défini de mot de passe de récupération, la connexion au compte social est suffisante.

**10. Que faire si je perds l'accès à mon social login et à ma méthode de récupération ?**

Si vous perdez l'accès à votre compte social et à votre méthode de récupération, **votre portefeuille ne pourra pas être récupéré**. Il n'y a pas de phrase secrète de secours et l'exportation de la clé privée n'est pas actuellement prise en charge.

> ⚠️ Rappel : L'exportation de votre clé privée, si elle est activée à l'avenir, accorderait un contrôle total de votre portefeuille à quiconque la possède — traitez-la avec une extrême prudence.

**11. Quelle est la durée des sessions actives ?**

Les sessions durent **30 jours**. Après cela, vous serez invité à **vous reconnecter** et (si nécessaire) à saisir à nouveau vos identifiants de récupération. Pendant une session active, vous pouvez effectuer des transactions sans avoir à approuver manuellement chaque action.



### ⚙️ Compatibilité et limitations

**12. Puis-je exporter ou importer des portefeuilles ?**

* **Exportation** : Non prise en charge par défaut, pour des raisons de sécurité. Cela pourrait changer dans de futures mises à jour.
* **Importation** : Non prise en charge. Vous ne pouvez pas importer des portefeuilles externes tels que MetaMask ou Phantom.

**13. Puis-je connecter ce portefeuille à d'autres dApps via WalletConnect ?**

Pas pour l'instant. Le portefeuille intégré est **limité à PancakeSwap uniquement**. Si vous souhaitez l'utiliser plus largement, faites-le nous savoir — des extensions futures sont possibles.



### 🚀 Fonctionnalités avancées

**14. Le portefeuille social login prend-il en charge l'abstraction de compte ?**

Oui. Il prend en charge les **fonctionnalités d'abstraction de compte** telles que le regroupement de transactions et le **parrainage de gaz** via des intégrations comme Biconomy, etc.

**15. Comment les transactions sans signature sont-elles activées ?**

* Après la connexion, votre session est active jusqu'à **30 jours**. Pendant cette période, PancakeSwap peut demander à Privy de signer des transactions en votre nom à l'aide de vos identifiants de session.&#x20;
* Aucune fenêtre contextuelle de portefeuille n'apparaîtra pour chaque action — tout est géré en arrière-plan. Après 30 jours, vous devrez vous reconnecter pour continuer à profiter de cette expérience sans signature.
