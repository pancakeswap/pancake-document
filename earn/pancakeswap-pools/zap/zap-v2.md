---
description: Fourniture de Liquidité simplifiée en un seul clic
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Qu'est-ce que le Zap ? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap simplifie la fourniture de Liquidité. Ajoutez de la Liquidité avec un seul token et en un seul clic, sans Swap manuel ni équilibrage des tokens.

* Ajouter de la Liquidité avec un seul token : Vous pouvez ajouter de la Liquidité en utilisant uniquement un token de la paire de Trading. Zap effectuera automatiquement des Swaps avec le token que vous fournissez et équilibrera automatiquement la paire de Trading selon un ratio 50/50 avant d'ajouter la Liquidité.
* Ajouter de la Liquidité avec un nombre déséquilibré de tokens dans la paire de Trading : Vous pouvez ajouter de la Liquidité même si le nombre de tokens que vous fournissez dans la paire de Trading n'est pas parfaitement équilibré par rapport au Pool actuel. Par exemple 30:70, ce qui diffère du poids par défaut du Pool de 50:50. Zap rééquilibrera automatiquement les tokens selon un ratio 50/50 avant d'ajouter la Liquidité.
* Retirer de la Liquidité et choisir le ou les tokens que vous souhaitez recevoir : Lors du retrait de Liquidité, Zap vous permet de ne recevoir qu'un seul token de la paire de Trading. Zap effectuera automatiquement des Swaps avant de vous restituer vos tokens.

### Activer Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Par défaut, la fonctionnalité Zap est activée pour tous les utilisateurs. Si vous ne voyez pas la nouvelle interface Zap lors de l'ajout ou du retrait de Liquidité, veuillez l'activer dans le panneau des paramètres. Vous pouvez ouvrir le panneau des paramètres en cliquant sur l'icône d'engrenage.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Remarque : Actuellement, la fonctionnalité Zap est en version bêta. Veuillez noter qu'elle ne prend pas en charge certains tokens, tels que les tokens avec des frais sur les transferts. Si vous rencontrez des problèmes lors de l'ajout ou du retrait de Liquidité, veuillez la désactiver dans le panneau des paramètres.
{% endhint %}

### Zap In (Ajouter de la Liquidité) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Accédez à la [page Liquidité](https://pancakeswap.finance/liquidity), et choisissez « Add Liquidity ».

Sélectionnez la paire de Trading pour laquelle vous souhaitez fournir de la Liquidité en choisissant deux tokens d'entrée. Consultez le [guide de Liquidité](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) pour en savoir plus.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Cliquez sur le bouton « Add Liquidity » pour continuer.

Si le token de la paire de Trading pour laquelle vous ajoutez de la Liquidité dispose d'un solde dans votre Portefeuille, la case à cocher correspondante sera automatiquement cochée. Si vous disposez d'un solde pour les deux tokens, les deux cases seront cochées.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap avec un seul token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Vous pouvez ajouter de la Liquidité en utilisant un seul token de la paire de Trading. Cochez simplement la case correspondant au token que vous souhaitez utiliser. Zap échangera automatiquement la moitié des tokens cochés contre l'autre token de la paire de Trading avant d'ajouter la Liquidité. Un message d'avertissement indiquera quel token sera converti.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Si l'impact sur les prix est trop élevé, Zap vous protégera par le biais du Glissement. Cliquez sur « Reduce TOKEN » pour le ramener à la limite souhaitée.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap avec deux tokens en montants déséquilibrés <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Si les deux tokens sont cochés mais que leurs montants ne correspondent pas à un ratio 50/50, l'équilibrage Zap sera déclenché. Un message vous indiquera que « Une partie de votre Token A sera convertie en Token B ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Si vous ne souhaitez pas que Zap équilibre le nombre de tokens avant d'ajouter la Liquidité, cliquez simplement sur « Don't Convert ». Dans ce cas, Zap ajustera le nombre de tokens d'entrée pour correspondre à un ratio 50/50 au lieu d'essayer d'échanger et de rééquilibrer.
{% endhint %}

### Procéder au Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Lorsque vous cliquez sur « Supply », les détails du Zap s'affichent et attendent votre confirmation.

Vous verrez :

1. Le nombre de LP Tokens que vous recevrez.
2. Les tokens d'entrée et le nombre de tokens que vous engagez.
3. La façon dont les tokens d'entrée sont échangés pour correspondre à un ratio 50/50.
4. La tolérance de Glissement que vous utilisez.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out (Retirer de la Liquidité) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap vous permet également de recevoir un seul token de la paire de Trading lors du retrait de Liquidité.

1. Accédez à la[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj_97-YuUMQjQbYbfN4)[page Liquidité](https://pancakeswap.finance/swap#/pool).
2. Cliquez sur la paire dont vous souhaitez retirer la Liquidité dans « Your Liquidity ».
3. Cliquez sur « Remove ». Une nouvelle fenêtre contextuelle s'ouvrira.

Dans la section « You Will Receive », vous pouvez décocher le token que vous ne souhaitez pas recevoir. Zap échangera et convertira automatiquement 100 % des retours dans le token coché lors du retrait de Liquidité.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
