# ❓ FAQ Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Avant d'effectuer un Bridge

1.  **Puis-je utiliser des Portefeuilles mobiles ou d'autres Portefeuilles que MetaMask pour Bridger des CAKE ?**

    Actuellement, le Bridging CAKE de PancakeSwap prend en charge Coinbase Wallet, MetaMask et les Portefeuilles compatibles MetaMask. La prise en charge d'autres Portefeuilles est prévue prochainement.

    _Conseil :_ Pour éviter les risques liés au copier-coller de clés privées ou de phrases secrètes, nous vous recommandons de créer de nouveaux Portefeuilles via des extensions de Portefeuille de bureau pour le Bridging.
2.  **Pourquoi un itinéraire ou un token est-il indisponible ?**

    Certains itinéraires dépendent de la capacité du Bridge, de la prise en charge des tokens ou de la Liquidité. Veuillez réessayer ultérieurement ou utiliser un autre fournisseur. Les tokens disponibles par chaîne sont affichés directement dans l'interface Bridge.
3.  **J'obtiens une erreur lors de la soumission de la transaction de Bridging.**

    Essayez de saisir le montant manuellement plutôt que d'utiliser le bouton « MAX », et supprimez les décimales du montant si nécessaire.
4.  **Pourquoi mon devis de Bridge affiche-t-il « Insufficient X to cover native fee » ?**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Le Bridging nécessite des frais de gas payés en token natif de la chaîne source, par exemple :

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Assurez-vous de disposer de suffisamment de tokens natifs dans votre Portefeuille source pour couvrir les frais et compléter la transaction.
5.  **Pourquoi le bouton affiche-t-il « X CAKE Exceeded » ?**

    Il existe une limite de capacité quotidienne pour le Bridging de CAKE entre BSC et Aptos afin de garantir la sécurité. Essayez avec un montant plus faible ou attendez et réessayez plus tard. Les limites sont ajustées dynamiquement par les Chefs en fonction de la demande.
6.  **Pourquoi ne puis-je pas trouver un token spécifique ?**

    Le token peut ne pas être pris en charge sur l'itinéraire que vous avez choisi ou peut manquer de Liquidité. Essayez une autre chaîne ou un montant différent.
7.  **Puis-je effectuer un Bridge de BNB Chain vers Ethereum mais vers une adresse différente ?**

    Non, pour des raisons de sécurité, le Bridging ne fonctionne qu'entre la même adresse sur les chaînes EVM.
8.  **Pourquoi ne puis-je pas Bridger moins de 0,00000001 CAKE ?**

    Les tokens Aptos, y compris CAKE sur Aptos, ont un maximum de 8 décimales. Les transactions inférieures à 0,00000001 seront rejetées ou arrondies à la baisse. Cela s'applique également au Bridging vers Ethereum. Tout montant résiduel reste dans votre Portefeuille source.

***

## Après le Bridge

1.  **Puis-je annuler un transfert Bridge après confirmation ?**

    Non, une fois lancée, la transaction Bridge est gérée par le fournisseur et ne peut pas être annulée. Pour inverser l'opération, Bridgez les actifs en sens inverse via une nouvelle transaction.
2.  **Que faire si ma transaction est bloquée en attente ?**

    Le Bridging peut prendre jusqu'à 30 minutes. Vérifiez le statut de votre transaction en recherchant son hash sur l'explorateur du fournisseur Bridge concerné :

    * Debridge : [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan : [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer : [https://stargate.finance/](https://stargate.finance/)
    * cBridge : [https://celerscan.com/](https://celerscan.com/)

    Si la transaction est toujours en attente après 60 minutes, veuillez contacter nos administrateurs via nos [canaux sociaux](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **Je n'ai pas reçu mes CAKE. Que dois-je faire ?**
   * Lors du Bridging de CAKE vers Aptos pour la première fois, vous devrez peut-être **réclamer manuellement** vos CAKE. Assurez-vous que votre Portefeuille Aptos dispose de suffisamment d'APT pour le gas. Consultez le [guide de Bridging Aptos](https://docs.pancakeswap.finance/bridge/bridging/aptos) et l'[explication d'Aptos](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Lors du Bridging vers BNB Chain ou Ethereum, certains Portefeuilles nécessitent que vous ajoutiez manuellement l'adresse du token CAKE pour voir votre solde. À titre d'exemple, suivez ce [guide MetaMask](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) — les autres Portefeuilles disposent généralement d'un processus similaire.
   * Si vous ne voyez toujours pas vos CAKE après 60 minutes, contactez nos administrateurs via nos [canaux sociaux](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
