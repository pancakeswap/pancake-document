---
description: Comment « débloquer » les transactions en attente bloquées dans votre MetaMask
---

# Résoudre les transactions bloquées en attente sur MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Si votre transaction est bloquée en attente dans Metamask et que le bouton « Cancel » n'y change rien, vous devrez peut-être utiliser cette méthode pour débloquer votre file d'attente.

Cette méthode consiste essentiellement à écraser la transaction bloquée par une autre transaction, de priorité plus élevée.

### **1. Activer le nonce de transaction personnalisé**

1\. Ouvrez votre extension MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Cliquez sur l'icône de cercle coloré en haut à droite, puis sur **Settings** dans le menu déroulant.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Dans le menu Settings, sélectionnez **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Faites défiler jusqu'à **Advanced gas controls**. Activez cette option (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Toujours dans les paramètres Advanced, continuez à faire défiler jusqu'à **Customize transaction nonce**. Activez cette option (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Trouver votre transaction bloquée**

Nous allons maintenant trouver la transaction bloquée et noter son « nonce ». Il s'agit d'une sorte d'identifiant, que nous réutiliserons plus tard.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Revenez en haut de la page de MetaMask. Dans l'onglet « Assets », trouvez le type de token de votre transaction bloquée (ici, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. Dans le menu du token, repérez votre transaction **Pending** dans la zone Queue. Cliquez sur votre transaction pour afficher plus de détails.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Cherchez l'entrée **Nonce** et notez ce nombre.

### **3. Écraser la transaction bloquée**

Nous allons maintenant créer une nouvelle transaction pour remplacer celle qui est bloquée. Nous allons personnaliser le nonce afin qu'il soit identique à celui que vous venez de noter.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Créez une nouvelle transaction pour remplacer votre transaction bloquée. Cette fois, augmentez les **Transaction Fee**. Ici, nous les avons fait passer de 9 à 20. Cela rendra plus probable l'inclusion de votre transaction dans un bloc.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Sur la page de confirmation, vérifiez que votre Gas Price est bien au nouveau montant, plus élevé.

11\. Trouvez l'entrée **CUSTOM NONCE** et remplacez le nonce par le nombre que vous avez noté à l'étape 8. Cliquez ensuite sur Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Votre nouvelle transaction devrait maintenant être acceptée dans un bloc. Pour le vérifier, ouvrez MetaMask et cliquez sur l'onglet **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Votre transaction terminée devrait apparaître en haut de votre liste Activity. Si elle affiche encore « Pending » en orange, vous devrez attendre un peu plus longtemps, ou recommencer la procédure avec des frais de transaction (gas price) encore plus élevés.

Comme aucun portefeuille ne peut créer deux transactions avec le même nonce, si la transaction de remplacement réussit, votre transaction bloquée sera annulée.<br>
