---
description: Comment débloquer les transactions en attente bloquées dans MetaMask
---

# Débloquer les Transactions en Attente sur MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Si votre transaction est bloquée en attente dans MetaMask et que le bouton "Annuler" ne fonctionne pas, vous devrez peut-être utiliser cette méthode pour vider votre file d'attente.

Cette méthode fonctionne en remplaçant essentiellement la transaction bloquée par une autre transaction de priorité plus élevée.

### **1. Activer le Nonce de Transaction Personnalisé**

1\. Ouvrez votre extension MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Cliquez sur l'icône colorée en haut à droite et sélectionnez **Paramètres** dans le menu déroulant.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Dans le menu Paramètres, sélectionnez **Avancé**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Faites défiler vers le bas jusqu'à voir **Contrôles avancés du gaz**. Activez cette option.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Toujours dans les paramètres Avancés, continuez de faire défiler jusqu'à voir **Personnaliser le nonce de transaction**. Activez cette option.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Retrouver Votre Transaction Bloquée**

Nous allons maintenant retrouver la transaction bloquée et noter son "nonce". Il s'agit d'une sorte d'identifiant que nous réutiliserons par la suite.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Retournez à la page principale de MetaMask. Dans l'onglet "Actifs", trouvez le type de token correspondant à votre transaction bloquée (dans cet exemple, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. Dans le menu du token, trouvez votre transaction **En attente** dans la zone File d'attente. Cliquez sur votre transaction pour afficher plus de détails.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Repérez l'entrée **Nonce** et notez ce numéro.

### **3. Remplacer la Transaction Bloquée**

Nous allons maintenant créer une nouvelle transaction pour remplacer celle qui est bloquée. Nous personnaliserons le numéro Nonce de façon à ce qu'il soit identique à celui que vous venez de noter.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. Créez une nouvelle transaction pour remplacer celle qui est bloquée. Cette fois-ci, augmentez les **Frais de Transaction**. Dans cet exemple, nous les avons augmentés de 9 à 20. Cela augmentera la probabilité que votre transaction soit incluse dans un bloc.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. Sur la page de confirmation, vérifiez que votre Prix du Gaz correspond bien au nouveau montant plus élevé.

10\. Trouvez l'entrée **NONCE PERSONNALISÉ** et remplacez le nonce par le numéro que vous avez noté à l'étape 7. Cliquez ensuite sur Confirmer.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-AU0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Votre nouvelle transaction devrait maintenant être acceptée dans un bloc. Pour le vérifier, ouvrez MetaMask et cliquez sur l'onglet **Activité**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Votre transaction terminée devrait apparaître en tête de votre liste d'Activité. Si elle affiche toujours "En attente" en orange, vous devrez patienter un peu plus longtemps ou recommencer la procédure avec des frais de transaction encore plus élevés (prix du gaz).

Étant donné qu'aucun Portefeuille ne peut créer deux transactions avec le même nonce, si la transaction de remplacement que vous avez créée aboutit, votre transaction bloquée sera annulée.<br>
