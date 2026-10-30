# 🧙 Page 1

## Comment retirer votre NFT du PancakeSwap NFT Marketplace

Les pages du PancakeSwap NFT Marketplace ne sont plus disponibles, mais le smart contract du marketplace est toujours actif. Si vous avez mis un NFT en vente et qu'il ne s'est jamais vendu, il est toujours détenu par le contrat du marketplace. Vous pouvez le récupérer vous-même en annulant la mise en vente directement sur BscScan.

Cela prend quelques minutes par NFT et ne coûte qu'une petite quantité de BNB pour les frais de gas.

### Avant de commencer

Vous aurez besoin de :

* **Le même portefeuille que celui utilisé pour mettre le NFT en vente.** Seul le portefeuille qui a créé une mise en vente peut l'annuler.
* **Un portefeuille de navigateur** (par exemple MetaMask, l'extension Trust Wallet ou l'extension Binance Wallet) configuré sur **BNB Smart Chain**.
* **Une petite quantité de BNB** pour payer le gas. Chaque NFT est retiré dans une transaction distincte.

Gardez ces adresses à portée de main :

| Élément                    | Adresse                                      |
| -------------------------- | -------------------------------------------- |
| Contrat du marketplace     | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Collection Pancake Squad   | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Collection Pancake Bunnies | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Restez en sécurité**
>
> * Interagissez uniquement avec le contrat du marketplace `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Vérifiez toujours l'adresse dans l'URL de BscScan.
> * Le retrait de votre NFT ne nécessite **jamais** d'envoyer des BNB ou des tokens, ni de signer une approbation (`approve` ou `setApprovalForAll`). Si un site web ou une personne vous le demande, il s'agit d'une arnaque.
> * PancakeSwap ne vous enverra jamais de message privé et ne vous demandera jamais votre phrase secrète.

### Étape 1 : Trouver les NFT que vous avez encore mis en vente

Pour chaque NFT que vous souhaitez retirer, vous avez besoin de deux informations : l'**adresse de la collection** et le **token ID**.

1. Ouvrez la [page Read Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) du contrat du marketplace sur BscScan.
2. Trouvez et développez **`viewAsksByCollectionAndSeller`**.
3. Remplissez les champs :
   * `collection` : l'adresse de la collection indiquée dans le tableau ci-dessus (par exemple, Pancake Squad est `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller` : l'adresse de votre portefeuille
   * `cursor` : `0`
   * `size` : `100`
4. Cliquez sur **Query**.
5. Consultez le résultat `tokenIds`. Il s'agit des token IDs que vous avez encore mis en vente dans cette collection, et ce sont les NFT que vous pouvez retirer.
6. Si vous avez mis en vente des NFT dans plusieurs collections, répétez les étapes 3 à 5 pour chaque collection.

**Si `tokenIds` est vide (`[]`)**, vous n'avez aucune mise en vente active dans cette collection. Votre NFT a soit été vendu (auquel cas vous avez déjà reçu les BNB), soit vous avez annulé la mise en vente auparavant (auquel cas il est déjà revenu dans votre portefeuille).

**Si vous avez plus de 100 mises en vente** dans une même collection, le dernier nombre du résultat est le prochain curseur. Relancez la requête en utilisant ce nombre comme `cursor` pour voir le reste.

**Si votre NFT provient d'une collection autre que Pancake Squad ou Pancake Bunnies**, développez **`viewCollections`** sur la même page, saisissez `cursor = 0` et `size = 100`, puis cliquez sur **Query** pour voir toutes les collections prises en charge par le marketplace.

### Étape 2 : Retirer votre NFT

1. Ouvrez la [page Write Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) du contrat du marketplace sur BscScan.
2. Cliquez sur **Connect to Web3** et connectez le même portefeuille que celui qui a mis le NFT en vente. Assurez-vous que votre portefeuille est sur BNB Smart Chain.
3. Trouvez et développez **`cancelAskOrder`**.
4. Remplissez les champs :
   * `_collection` : l'adresse de la collection de l'étape 1
   * `_tokenId` : le token ID de l'étape 1, sous forme de nombre simple (par exemple `1234`)
5. Cliquez sur **Write** et confirmez la transaction dans votre portefeuille. Vous n'envoyez aucun BNB ; vous ne payez que le gas.
6. Une fois la transaction réussie, le NFT est de retour dans votre portefeuille.
7. Répétez l'opération pour chaque NFT que vous souhaitez retirer.

Pour vérifier que cela a fonctionné, relancez l'étape 1. Le token ID ne devrait plus apparaître dans la liste.

### Dépannage

| Problème                                                  | Signification et marche à suivre                                                                                                                                                                                                  |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Erreur : `Order: Token not listed`                        | Le portefeuille connecté n'a pas mis en vente ce token ID dans cette collection, ou le NFT a déjà été vendu ou retiré. Vérifiez que vous utilisez le portefeuille d'origine ainsi que l'adresse de collection et le token ID corrects. |
| Le bouton Write ne fait rien                              | Votre portefeuille est probablement sur le mauvais réseau. Passez sur BNB Smart Chain et reconnectez-vous.                                                                                                                        |
| Gas insuffisant ou fonds insuffisants                     | Ajoutez une petite quantité de BNB à votre portefeuille pour couvrir le gas.                                                                                                                                                      |
| Je n'ai plus accès au portefeuille qui a mis le NFT en vente | Seul le portefeuille d'origine peut annuler la mise en vente. Personne, y compris PancakeSwap, ne peut le retirer à votre place.                                                                                                  |
