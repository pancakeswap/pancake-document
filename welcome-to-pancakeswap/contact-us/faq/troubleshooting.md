---
description: Messages d'erreur courants. Utilisez la barre latérale ➡️ pour accéder directement à l'erreur que vous rencontrez.
---

# Résolution des Erreurs

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

Il peut arriver que vous rencontriez un problème sans solution évidente. Ces conseils de dépannage peuvent vous aider à résoudre les problèmes que vous rencontrez.

## **Problèmes sur l'Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

Vous essayez de swapper des tokens, mais votre tolérance au Glissement est trop faible ou la Liquidité est insuffisante.

{% tabs %}
{% tab title="Solution" %}
1. Actualisez votre page et réessayez plus tard.
2. Essayez d'échanger un montant plus faible à la fois.
3. Augmentez votre tolérance au Glissement :
   1. Appuyez sur l'icône des paramètres sur la page de Liquidité.
   2. Augmentez légèrement votre tolérance au Glissement et réessayez. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Enfin, essayez de saisir un montant avec moins de décimales.
{% endtab %}

{% tab title="Raison" %}
**Cela se produit généralement lors du Trading de tokens avec une faible Liquidité.**

Cela signifie qu'il n'y a pas suffisamment de l'un des tokens que vous essayez de swapper dans le Pool de Liquidité : il s'agit probablement d'un token à faible capitalisation peu échangé.

Cependant, il est également possible que vous tentiez d'échanger un token frauduleux qui ne peut pas être vendu. Dans ce cas, PancakeSwap n'est pas en mesure de bloquer un token ni de rembourser les fonds.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT ou INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> ou\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Vous essayez d'ajouter ou de retirer de la Liquidité d'un Pool de Liquidité (LP), mais l'un des deux tokens de la paire est en quantité insuffisante.

{% tabs %}
{% tab title="Solution" %}
**Actualisez votre page et réessayez, ou réessayez plus tard.**

Toujours sans résultat ?

1. Appuyez sur l'icône des paramètres sur la page de Liquidité.
2. Augmentez légèrement votre tolérance au Glissement et réessayez.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Raison" %}
Cette erreur est causée par une tentative d'ajout ou de retrait de Liquidité d'un Pool de Liquidité (LP) avec une quantité insuffisante du token A ou du token B (l'un des tokens de la paire).

Il est possible que les prix évoluent trop rapidement et que votre tolérance au Glissement soit trop faible.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solution pour les utilisateurs avancés" %}
D'accord, vous êtes vraiment déterminé à résoudre ce problème. Nous vous déconseillons fortement de procéder ainsi, sauf si vous savez exactement ce que vous faites.

Il n'existe actuellement pas de moyen simple de résoudre ce problème depuis le site PancakeSwap : vous devrez interagir directement avec le contrat. Vous pouvez ajouter de la Liquidité directement via le contrat Router, en définissant amountAMin sur une valeur faible, puis retirer toute la Liquidité.

**Approuver le contrat LP**

Accédez au contrat du token LP que vous souhaitez approuver.\
Par exemple, voici la paire ETH/WBNB : [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Sélectionnez **Write Contract**, puis **Connect to Web3** et connectez votre Portefeuille. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. Dans la **section "1. approve"**, approuvez le token LP pour le router en saisissant :
   1. spender (address) : entrez l'adresse du contrat du token LP avec lequel vous souhaitez interagir
   2. value (uint256) : -1

**Interroger "balanceOf"**

1. Passez à **Read Contract**.
2. Dans **5. balanceOf**, saisissez l'adresse de votre Portefeuille et cliquez sur **Query**.
3. Notez le nombre affiché. Il représente votre solde dans le LP au format uint256, dont vous aurez besoin à l'étape suivante.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Ajouter ou Retirer de la Liquidité**

Accédez au contrat router : [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Sélectionnez **Write Contract** et **Connect to Web3** comme ci-dessus.
2. Trouvez **addLiquidity** ou **removeLiquidity** (selon l'action que vous souhaitez effectuer)
3. Saisissez les adresses des deux tokens du LP.
4. Dans **liquidity (uint256)**, entrez le nombre uint256 obtenu via "balanceOf" ci-dessus.
5. Définissez un **amountAMin** ou **amountBMin** faible : essayez 1 pour les deux.
6. Ajoutez l'adresse de votre Portefeuille dans **to (address)**.
7. Le délai doit être un temps epoch supérieur au moment d'exécution de la transaction.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Cela peut entraîner un Glissement très élevé et exposer l'utilisateur à une perte de fonds en cas de Frontrunning
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Réessayez, mais confirmez (signez et diffusez) la transaction dès que vous la générez.

Cela s'est produit parce que vous avez commencé à créer une transaction, mais vous ne l'avez pas signée et diffusée avant l'expiration du délai. Autrement dit, vous n'avez pas cliqué sur "Confirmer" assez rapidement.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Essayez de modifier le montant dans le champ "Vers", plaçant ainsi le symbole "(estimé)" dans le champ "De". Lancez ensuite le Swap immédiatement.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Cela se produit généralement lorsque vous tentez de swapper un token qui applique ses propres frais.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Assurez-vous d'avoir 30 % de tokens supplémentaires dans votre Portefeuille par rapport au montant que vous souhaitez échanger, ou essayez d'échanger un montant inférieur. Si vous souhaitez vendre le maximum possible, essayez 70 % ou 69 % plutôt que 100 %.\
Causé par la conception des tokens Restorative Rebase tels que tDoge ou tBTC.\
[Comprendre le fonctionnement des tokens restorative rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Une autre cause possible de ce problème est que l'émetteur malveillant du token a simplement suspendu le Trading de son token. Ou bien il a rendu l'action de vente possible uniquement pour certaines adresses de Portefeuille sélectionnées. Veuillez toujours effectuer vos propres recherches pour éviter toute fraude potentielle. Si le token que vous tentez de swapper mais qui échoue avec ce code d'erreur provient d'un airdrop, il s'agit très probablement d'une arnaque. Veuillez ne pas effectuer d'approbation de token ni suivre de liens, vos fonds pourraient être en danger si vous tentez de le faire.

### La transaction ne peut pas aboutir

Essayez d'échanger un montant plus faible, ou augmentez la tolérance au Glissement via l'icône des paramètres et réessayez. Cela est causé par une Liquidité insuffisante.

### **Impact sur le Prix trop élevé**

Essayez d'échanger un montant plus faible, ou augmentez la tolérance au Glissement via l'icône des paramètres et réessayez. Cela est causé par une Liquidité insuffisante.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Solution" %}
**Si vous avez rencontré cette erreur lors du retrait de Liquidité d'une paire BNB :**

Veuillez sélectionner "Recevoir WBNB" et réessayer.

**Si vous avez rencontré cette erreur lors d'un Swap :**

Veuillez contacter l'équipe du projet du token que vous tentez de swapper. \*\*\*\* Ce problème doit être résolu par l'équipe du projet.
{% endtab %}

{% tab title="Raison" %}
**Ce problème (lors d'un Swap) est causé par des tokens qui ont intégré en dur l'adresse du router PancakeSwap V1 dans leur contrat.**

Bien que cette pratique soit au mieux déconseillée, la raison pour laquelle ces projets l'ont fait semble être liée à leurs Tokenomics, dans lesquelles chaque achat envoie un pourcentage du token aux LP.

Les projets concernés ne fonctionneront probablement pas avec le router V2 : ils devront très probablement créer de nouvelles versions de leurs tokens pointant vers notre nouvelle adresse de router, et migrer les détenteurs de tokens existants vers leur nouveau token.

Nous recommandons que les projets ayant créé de tels tokens fassent également des efforts pour empêcher leurs utilisateurs d'ajouter ces tokens aux LP V2.

L'adresse du router à jour est [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Lors d'une tentative de Swap, la transaction échoue et ce message d'erreur s'affiche. Cette erreur a été signalée sur des appareils mobiles utilisant Trust Wallet.

{% tabs %}
{% tab title="Solution" %}
1. Tentez à nouveau la transaction avec une tolérance au Glissement augmentée.
2. Si l'étape 1 ne résout pas votre problème, envisagez d'utiliser un autre Portefeuille tel que SafePal pour votre transaction.
{% endtab %}

{% tab title="Raison" %}
**Cela se produit généralement lors du Trading de tokens avec une tolérance au Glissement insuffisante sur Trust Wallet.**

Les détails précis de ce problème sont encore en cours d'investigation.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Lors d'une tentative de Swap, la transaction échoue et ce message d'erreur s'affiche. Cette erreur a été signalée sur plusieurs plateformes.

{% tabs %}
{% tab title="Solution" %}
1. Vérifiez que vous disposez de fonds suffisants.
2. Assurez-vous d'avoir accordé au contrat l'autorisation de dépenser le montant de fonds que vous tentez d'échanger.
{% endtab %}

{% tab title="Raison" %}
Cette erreur se produit lors du Trading de tokens avec une autorisation insuffisante, ou lorsqu'un Portefeuille ne dispose pas de fonds suffisants.\
Si vous échangez des tokens avec un mécanisme Restorative Rebase comme les actifs tau tDoge ou tBTC, assurez-vous de bien comprendre leur fonctionnement en consultant ce [guide sur les tokens Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Problèmes avec les Farms**

### Fail with error 'ds-math-sub-underflow'

Vous avez épuisé l'autorisation de votre token LP accordée au contrat MasterChef.

**Utilisez un gestionnaire d'approbation de tokens tel que unrekt ou BscScan pour**

## **Problèmes avec les Syrup Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

Vous ne disposez pas de suffisamment de SYRUP dans votre Portefeuille pour retirer votre Staking du pool CAKE-CAKE.

**Procurez-vous au moins autant de SYRUP que le montant de CAKE que vous tentez de retirer.**

1. Achetez des SYRUP sur l'exchange. Si vous souhaitez retirer 100 CAKE, vous avez besoin d'au moins 100 SYRUP.
2. Réessayez de retirer votre Staking.

Si cela échoue toujours, vous pouvez effectuer un "emergencyWithdraw" directement depuis le contrat pour retirer vos tokens stakés.

1. Accédez à : [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Cliquez sur **"Connect to Web3"** et connectez votre Portefeuille. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Dans la section **"4. emergencyWithdraw"**, saisissez "0" et cliquez sur "Write".

Cela retirera vos tokens stakés et vous fera perdre les récompenses CAKE non collectées.

{% hint style="warning" %}
**Vous perdrez toutes les récompenses que vous n'avez pas encore récoltées.**
{% endhint %}

Pour éviter que cela ne se reproduise, **ne vendez pas vos SYRUP.** Vous en avez toujours besoin pour retirer votre Staking du pool "Staker CAKE Gagner CAKE".

Cette erreur s'est produite parce que vous avez vendu ou transféré des tokens SYRUP. Les SYRUP sont créés dans un ratio 1:1 avec CAKE lorsque vous stakez dans le Syrup Pool CAKE-CAKE. Les SYRUP doivent être brûlés dans un ratio 1:1 avec CAKE lors de l'appel à leaveStaking (retrait de votre CAKE du pool) ; si vous n'en avez pas suffisamment, vous ne pouvez pas retirer votre Staking.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Erreur Out of Gas

> Warning! Error encountered during contract execution \[out of gas]

Vous avez défini une limite de gaz trop basse lors d'une tentative de transaction.

{% tabs %}
{% tab title="Solution" %}
Essayez d'augmenter manuellement la **limite de gaz** (et non le prix du gaz !) dans votre Portefeuille avant de signer la transaction.

Une limite de 200 000 est généralement suffisante.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

L'exemple ci-dessus provient de MetaMask ; consultez la documentation de votre Portefeuille si vous ne savez pas comment ajuster la limite de gaz.
{% endtab %}

{% tab title="Raison" %}
En résumé, votre Portefeuille (MetaMask, Trust Wallet, etc.) ne parvient pas à terminer l'opération en cours.

Votre Portefeuille estime que la limite de gaz est trop basse, de sorte que la fonction manque de gaz avant d'avoir pu s'exécuter complètement.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Solution" %}
1. Utilisez Unrekt.net pour révoquer l'approbation du smart contract avec lequel vous tentez d'interagir
2. Approuvez à nouveau le contrat, sans définir de limite sur le montant autorisé
3. Réessayez d'interagir avec le contrat.
{% endtab %}

{% tab title="Raison" %}
Cela se produit lorsque vous avez défini une limite sur votre autorisation de dépense lors de la première approbation du contrat, puis que vous tentez de swapper un montant supérieur à cette limite.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Vous essayez probablement de retirer votre Staking d'un Syrup Pool dont les récompenses sont faibles. La solution est indiquée ci-dessous.

Sinon, vous tentez peut-être d'envoyer des tokens que vous ne possédez pas dans votre Portefeuille (par exemple, des tokens déjà assignés à une transaction en attente). Dans ce cas, assurez-vous simplement de disposer des tokens que vous souhaitez utiliser.

{% tabs %}
{% tab title="Solution" %}
Commencez par [informer l'équipe](../social-accounts.md) du pool duquel vous tentez de retirer votre Staking, afin qu'elle puisse recharger les récompenses. Si vous êtes pressé de retirer votre Staking et que vous acceptez de perdre vos récompenses en attente, essayez un emergencyWithdraw :

Vous pouvez effectuer un "emergencyWithdraw" directement depuis le contrat pour retirer vos tokens stakés.

1. Trouvez l'adresse du contrat du Syrup Pool duquel vous tentez de retirer votre Staking. Vous pouvez la trouver dans le journal des transactions de votre Portefeuille.
2. Rendez-vous sur [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) et saisissez l'adresse du contrat dans la barre de recherche.
3. Sélectionnez **Write Contract**.
4. Cliquez sur **"Connect to Web3"** et connectez votre Portefeuille.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Dans la section **"3. emergencyWithdraw"**, cliquez sur "Write".

Cela retirera vos tokens stakés et vous fera perdre les récompenses non collectées.

{% hint style="warning" %}
**Vous perdrez toutes les récompenses que vous n'avez pas encore récoltées.**
{% endhint %}
{% endtab %}

{% tab title="Raison" %}
Cette erreur tend à apparaître lorsque vous tentez de retirer votre Staking d'un ancien Syrup Pool, mais que les récompenses restantes dans le pool sont insuffisantes pour être distribuées lors du retrait. Cela provoque l'échec de la transaction.
{% endtab %}
{% endtabs %}

## **Problèmes avec Prediction**

Consultez [Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Autres problèmes**

### Erreur Provider

> Provider Error\
> No provider was found

Cela se produit lorsque vous essayez de vous connecter via une extension de navigateur comme MetaMask ou Binance Chain Wallet, mais que vous n'avez pas installé l'extension.

{% tabs %}
{% tab title="Solution" %}
Installez l'extension officielle du navigateur pour vous connecter, ou consultez notre guide sur [comment connecter un Portefeuille à PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

Passez sur BNB Smart Chain. Consultez la documentation de votre Portefeuille pour obtenir un guide si vous avez besoin d'aide.

### Already processing eth\_requestAccounts. Please wait.

Assurez-vous d'être connecté à votre application Portefeuille et qu'elle est connectée à BNB Smart Chain.

### Problèmes lors de l'achat de SAFEMOON et de tokens similaires

Pour échanger SAFEMOON, vous devez cliquer sur l'icône des paramètres et **définir votre tolérance au Glissement à 12 % ou plus.**\
Cela est dû au fait que **SafeMoon applique des frais de 10 % sur chaque transaction** :

* 5 % de frais = redistribués à tous les détenteurs existants
* 5 % de frais = utilisés pour ajouter de la Liquidité

C'est également pour cette raison que vous pourriez recevoir moins de tokens que prévu lors de votre achat.\
En savoir plus sur [Comment acheter Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Erreurs internes JSON-RPC

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Se produit lors d'une tentative de retrait de Liquidité sur certains tokens via MetaMask. La cause principale est encore inconnue. Essayez d'utiliser un autre Portefeuille.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

Vous ne disposez pas de suffisamment de BNB pour payer les frais de transaction. Vous avez besoin de plus de BNB sur le réseau BEP-20 dans votre Portefeuille.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Augmentez la limite de gaz pour la transaction dans votre Portefeuille. Consultez la documentation de votre Portefeuille pour savoir comment augmenter la limite de gaz.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Cause inconnue. Essayez ces étapes avant de réessayer :

1. Augmenter la limite de gaz
2. Augmenter le Glissement
3. Vider le cache

## **Problèmes avec le Profil**

### Oups ! Nous n'avons trouvé aucun Pancake Collectibles dans votre Portefeuille.

Nous examinons la logique à l'origine de ce problème. En attendant, veuillez essayer la solution de contournement suivante.

{% tabs %}
{% tab title="Solution de contournement 1" %}
1. Accédez à la page "Collectibles", puis revenez à la page du profil.\
   Si vous ne trouvez pas le lien, accédez directement à [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles).
2. Réessayez la création du profil.
{% endtab %}

{% tab title="Solution de contournement 2" %}
Changez l'environnement.

* Videz le cache et réessayez.
* Réessayez sur un autre navigateur.
* Réessayez avec une autre application Portefeuille.
* Réessayez sur un réseau différent (basculez entre Wi-Fi et données mobiles)
{% endtab %}
{% endtabs %}

### La vérification du nom d'utilisateur tourne indéfiniment

Il y a deux causes possibles.

1. Vous avez plusieurs Portefeuilles installés sur le navigateur.
2. Problème de réseau.

{% tabs %}
{% tab title="Solution 1" %}
Cause : Vous avez plusieurs Portefeuilles installés sur le navigateur.\
\
Ils peuvent créer des conflits entre eux. Cela échappe au contrôle de PancakeSwap et nous ne pouvons rien y faire.

1. Ne conservez qu'un seul Portefeuille installé sur le navigateur, supprimez les autres.
2. Reconnectez le Portefeuille et réessayez de définir votre nom d'utilisateur.
{% endtab %}

{% tab title="Solution 2" %}
Cause : Le réseau est instable.

Vous devez réessayer.

1. Effacez entièrement ce qui a été saisi dans le champ de texte.
2. Ressaisissez votre nom d'utilisateur, puis patientez quelques secondes.
3. Si cela ne fonctionne pas, rechargez la page et réessayez.
{% endtab %}
{% endtabs %}
