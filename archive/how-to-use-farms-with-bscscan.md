# Comment utiliser les Farms avec BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Utiliser les Farms avec PancakeSwap peut sembler intimidant au début car cela nécessite plusieurs étapes. Ce guide vous accompagnera dans l'utilisation du contrat Farms directement via BscScan.

{% hint style="warning" %}
Veuillez comprendre que l'utilisation de BscScan pour interagir avec les contrats n'est pas recommandée pour les débutants. Si vous n'êtes pas à l'aise, nous vous suggérons d'utiliser plutôt le [Guide d'utilisation des Farms](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms).
{% endhint %}

## Trouver l'identifiant de processus de Farm

Pour interagir correctement avec le smart contract de farming, vous aurez besoin de l'identifiant de processus (PID) correspondant à votre paire LP. Pour l'instant, le moyen le plus simple de le localiser est de vérifier sur GitHub.

1\. Ouvrez le [code des Farms du site PancakeSwap sur GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Ctrl**/**Cmd** + **F** et recherchez votre paire par ticker (pas par nom de projet). Par exemple, « CAKE-BUSD ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Notez ou copiez le numéro PID — dans ce cas 389 — quelque part d'accessible. Vous en aurez besoin plus tard.

## Déposer des tokens LP via BscScan

Le dépôt de tokens LP via BscScan implique plusieurs étapes. Nous les avons décomposées pour faciliter le suivi.

### Obtenir l'adresse du contrat de staking principal

L'adresse du contrat de staking principal est : **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

En supposant que vous souhaitez le confirmer, visitez la [page BscScan du contrat de staking principal PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Vous verrez l'adresse en haut à gauche. Cliquez sur l'**icône de pages** pour la copier dans le presse-papiers. Vous en aurez besoin bientôt.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Ouvrir le contrat de votre token LP

Vous devrez approuver le smart contract pour le token LP que vous souhaitez engager dans une Farm avant de pouvoir le dépenser.

### Depuis le code source

1\. D'abord, ouvrez [farms.ts sur GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Ctrl**/**Cmd** + **F** et recherchez votre paire par ticker (pas par nom de projet). Par exemple, « CAKE-BNB »

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Lorsque vous avez le code de la paire LP recherchée, trouvez l'adresse après « 56: ». Ce sera votre adresse de contrat.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Depuis l'interface

1\. D'abord, visitez la [page Farms de PancakeSwap](https://pancakeswap.finance/farms) et recherchez la paire choisie via le champ « SEARCH » en haut à droite. Nous utilisons CAKE-BUSD pour cet exemple.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Cliquez sur **Details** pour développer la ligne et afficher plus d'informations.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Cliquez sur **View Contract** pour ouvrir le smart contract sur BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Accorder l'autorisation au contrat de token LP

Maintenant que vous avez ouvert le contrat de votre token LP sur BscScan, vous allez approuver la dépense de vos tokens LP dans la Farm.

1\. Sur la page du contrat du token LP, allez dans **Contract**, puis **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Cliquez sur **Connect to Web3** pour connecter MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirmez la connexion.

3\. Sous la fonction 1, « approve », vous verrez « spender:address ». Collez l'adresse de contrat du contrat de staking principal copiée précédemment.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Vous devrez également approuver le montant de tokens LP que le contrat peut dépenser. Dans le champ valeur, vous devrez entrer le montant en Wei. Vous pouvez utiliser le [Convertisseur d'unités BscScan](https://www.bscscan.com/unitconverter) pour convertir facilement votre montant en Wei. Ici nous utilisons 5 tokens LP CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Vous pouvez également utiliser `-1` comme valeur pour donner une approbation de dépense illimitée. Cela ne signifie pas que vous dépenserez tout par défaut, mais seulement qu'une transaction de n'importe quelle taille utilisant ce contrat sera autorisée par votre portefeuille.
{% endhint %}

6\. Cliquez sur **Write** et acceptez l'action dans votre portefeuille MetaMask. Vous pouvez maintenant engager des tokens LP dans la Farm jusqu'au montant que vous avez approuvé.

### Déposer des tokens LP avec le smart contract de staking principal

Maintenant que le contrat de staking principal est autorisé à dépenser vos tokens LP, il est temps d'effectuer un dépôt.

1\. De retour sur la [page BscScan du contrat de staking principal PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), allez dans **Contract**, puis **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Cliquez sur **Connect to Web3** pour connecter MetaMask.

3\. Faites défiler jusqu'à la fonction 2, « deposit », et entrez votre PID dans le champ « \_pid ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Si vous n'avez pas noté votre PID précédemment, vous pouvez apprendre à l'obtenir dans la section **Trouver l'identifiant de processus de Farm** plus haut sur cette page.

4\. Sous \_pid vous verrez « \_amount ». Entrez le montant que vous avez approuvé pour le contrat LP à dépenser.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Vérifiez les informations et cliquez sur **Write**. Confirmez votre action dans MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Vous pouvez confirmer que votre dépôt a fonctionné en cliquant sur **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Retirer d'un Pool

Retirer vos tokens LP d'un Pool est très similaire à effectuer un dépôt. La différence réside dans la fonction avec laquelle vous interagirez.

1\. De retour sur la [page BscScan du contrat de staking principal PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), allez dans **Contract**, puis **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Cliquez sur **Connect to Web3** pour connecter MetaMask.

3\. Faites défiler jusqu'à la fonction 15, « withdraw », et entrez votre PID dans le champ « \_pid ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Si vous n'avez pas noté votre PID précédemment, vous pouvez apprendre à l'obtenir dans la section **Trouver l'identifiant de processus de Farm** plus haut sur cette page.

4\. Sous \_pid vous verrez « \_amount ». Entrez le montant de LP que vous souhaitez retirer du Pool.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Vérifiez les informations et cliquez sur **Write**. Confirmez votre action dans MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Vous pouvez confirmer que votre retrait a fonctionné en cliquant sur **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Effectuer un retrait d'urgence**

‌Utiliser la fonction de retrait d'urgence vous permet de retirer tous vos fonds d'un pool lorsqu'aucune autre méthode ne fonctionne.

{% hint style="danger" %}
**Utiliser la fonction de retrait d'urgence vous fera perdre vos récompenses CAKE !**

L'équipe PancakeSwap vous conseille vivement d'éviter cette fonction sauf si vous y êtes officiellement invité par l'équipe PancakeSwap, ou si vous êtes très à l'aise avec les interactions avec les smart contracts et comprenez le code sous-jacent.
{% endhint %}

‌1. Sur la [page BscScan du contrat de staking principal PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), allez dans **Contract**, puis **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Cliquez sur **Connect to Web3** pour connecter MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Faites défiler jusqu'à la fonction 4, « emergencyWithdraw », et entrez votre PID dans le champ « \_pid ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Si vous n'avez pas noté votre PID précédemment, vous pouvez apprendre à l'obtenir dans la section **Trouver l'identifiant de processus de Farm** plus haut sur cette page.

5\. Vérifiez les informations et cliquez sur **Write**. Confirmez votre action dans MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Vous pouvez confirmer que votre retrait a fonctionné en cliquant sur **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
