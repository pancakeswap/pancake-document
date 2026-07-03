# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### Que dois-je faire sur PancakeSwap sur d'autres blockchains ?

Fournissez de la Liquidité, tradez et farmez comme vous en avez l'habitude. Si vous êtes déjà un utilisateur multichain, pensez à fournir de la Liquidité sur PancakeSwap sur les autres blockchains sur lesquelles nous avons déployé (comme Ethereum), car nous offrons des récompenses en CAKE sur BNB Smart Chain, ce qui vous permet de gagner encore plus de CAKE sans avoir à Bridger ces actifs !

### **Y aura-t-il davantage de paires ?**

Oui, mais nous procéderons par étapes afin de prioriser la sécurité des fonds des utilisateurs et l'inflation de CAKE. N'hésitez pas à nous faire part, dans les espaces communautaires, de ce que vous pensez devoir être ajouté à PancakeSwap sur d'autres blockchains, ainsi que des blockchains supplémentaires sur lesquelles PancakeSwap devrait être déployé.

### **Pourquoi les frais de gas pour staker des jetons LP sont-ils élevés ?**

Une petite quantité de jeton natif (par exemple, de l'ETH sur Ethereum) est requise lors de la première configuration. La première transaction sera donc légèrement plus coûteuse.

De plus, d'autres frais (principalement des frais de gas) sont impliqués dans le farming cross-chain. Consultez [cette](faq.md#are-there-any-fees-when-i-do-crosschain-farming) section dédiée pour en savoir plus.

### **Pourquoi le staking et le unstaking prennent-ils 30 minutes ?**

Toutes les transactions cross-chain prennent environ 30 minutes. Cela s'explique par :

* Les transactions doivent être exécutées à la fois sur la blockchain de farming (comme Ethereum) et sur BNB Chain.
* La transmission des messages cross-chain prend du temps.
* La nécessité de garantir la sécurité et la synchronisation de toutes les données entre les différentes blockchains.

### **Où sont mes récompenses CAKE récoltées ?**

Vos CAKE récoltés seront distribués sur BNB Smart Chain. Veuillez changer le réseau blockchain dans votre portefeuille pour vérifier le solde de CAKE.

### **Je ne peux pas récolter car mon portefeuille ne prend pas en charge le changement entre différentes blockchains !**

Veuillez essayer d'utiliser une autre application de portefeuille qui prend en charge le multichain et le changement de chaîne.

Notez que le staking et le unstaking de jetons LP déclenchent également la récolte de tous les CAKE gagnés vers votre portefeuille sur BNB Smart Chain. Ainsi, si vous ne souhaitez pas utiliser une autre application de portefeuille, stakez davantage, ou unstakez une petite quantité de jetons LP pour récolter vos CAKE gagnés.

### Y a-t-il des frais lors du Crosschain Farming ?

Contrairement au farming natif sur BNB Chain, le farming sur d'autres blockchains implique des activités cross-chain. Voici les frais concernés :

**1 - Frais de gas pour la création d'un contrat proxy**

Un contrat proxy doit être créé sur BNB Chain pour le farming cross-chain. Les frais de gas liés à la création du contrat proxy sont inclus dans la transaction.

Ces frais ne sont prélevés qu'une seule fois, lors de la première transaction de « stake ».

**2 - Frais de gas pour les appels sur BNB Chain**

Lorsque les utilisateurs déposent ou retirent des jetons LP, un exécuteur effectue des transactions au nom des utilisateurs sur BNB Chain. Les frais de gas liés à ces appels sont inclus dans la transaction.

Ces frais sont prélevés à chaque transaction de dépôt ou de retrait.

**3 - Frais de gas pour les appels sur d'autres blockchains**

Lorsque les utilisateurs retirent des jetons LP, un exécuteur effectue les transactions finales pour libérer les jetons LP sur d'autres blockchains (comme Ethereum). Les frais de gas liés à ces appels sont inclus dans la transaction.

Ces frais ne sont prélevés que lors des transactions de retrait.

**4 - Frais de messagerie cross-chain**

Nous utilisons un bus de messages alimenté par Celer pour acheminer nos messages cross-chain. Des frais de messages sont donc inclus en fonction de la longueur en octets du message.

Ces frais sont prélevés à chaque transaction de stake. Lors des transactions de unstake, ces frais sont prélevés deux fois, car une communication bidirectionnelle entre BNB Chain et les autres blockchains est nécessaire pour garantir la sécurité.

```
messagingFee = feeBase + message.length * feePerByte;
```

Vous pouvez trouver les variables de la formule dans le contrat du bus de messages :

* Ethereum : `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain : `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - Le fonds de démarrage**

Il ne s'agit pas strictement d'un « frais ».&#x20;

Pour chaque nouvel utilisateur qui commence à faire du Crosschain Farming sur PancakeSwap, lors de la première transaction de « stake », nous déposerons 0,005 BNB dans son portefeuille BNB Chain. Le montant correspondant en jetons natifs sur la chaîne de farming (comme de l'ETH sur Ethereum) sera prélevé de la transaction de dépôt, au taux du marché fourni par l'oracle de prix.

Ceci vise à aider les utilisateurs à démarrer leur aventure sur BNB Chain en toute simplicité. Nous comprenons la difficulté d'avoir des CAKE récoltés sans pouvoir explorer l'écosystème dynamique de PancakeSwap faute de BNB pour les frais de gas.

Ces frais ne sont prélevés qu'une seule fois, lors de la première transaction de « stake ».

### D'où proviennent les émissions ?&#x20;

_mis à jour le 10 octobre 2022_

Pour l'instant, les Chefs ont redirigé 0,0189 CAKE par bloc du CAKE pool vers toutes les Farms cross-chain.&#x20;

Voici la répartition des émissions :

<table><thead><tr><th width="249"></th><th>Multiplicateur</th><th>CAKE par bloc</th></tr></thead><tbody><tr><td><strong>CAKE Pool</strong></td><td>-</td><td><strong>8,9811</strong></td></tr><tr><td><strong>Toutes les Farms Cross-chain</strong></td><td>-</td><td><strong>0,0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0,5x</td><td>0,0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0,2x</td><td>0,0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0,2x</td><td>0,0042</td></tr></tbody></table>

### Que se passe-t-il lors du dépôt, de la récolte et du retrait ?

Le Crosschain Farming PancakeSwap revient à utiliser un jeton LP « suppléant » pour farmer sur BNB Chain, avec le même MasterChef PancakeSwap. Les récompenses en CAKE sont calculées et distribuées sur BNB Chain, contrôlées et sécurisées par le même contrat MasterChef.

#### Lors d'un dépôt :

1. Les utilisateurs demandent le dépôt de jetons LP sur les blockchains de farming (comme Ethereum).
2. Les jetons LP sont transférés vers les contrats de coffre de farming.
3. Le bus de messages Celer est utilisé pour transmettre le message de « dépôt » à BNB Chain.
4. Un exécuteur sur BNB Chain crée le même montant de jetons de farming en guise de « suppléants », puis les dépose dans les Farms.

#### Lors d'une récolte :

Les récompenses en CAKE étant calculées et distribuées sur BNB Chain, les utilisateurs peuvent réclamer leurs récompenses en CAKE via une seule transaction BNB Chain, sans avoir besoin d'opérations cross-chain.

#### Lors d'un retrait :

1. Les utilisateurs demandent le retrait de jetons LP sur les blockchains de farming (comme Ethereum).
2. Le bus de messages Celer est utilisé pour transmettre le message de « retrait » à BNB Chain.
3. Un exécuteur sur BNB Chain retire les jetons de farming des Farms, les brûle, transfère les CAKE gagnés aux utilisateurs, et utilise le bus de messages Celer pour transmettre le message de confirmation à la blockchain de farming d'origine.
4. Un exécuteur sur la blockchain de farming confirme tout cela, puis libère les jetons LP des contrats de coffre.
