# Frais et Routes

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

Dans Exchange V3, par défaut, le Smart Router de PancakeSwap utilise la Liquidité de V3, V2, StableSwap (BNB Chain), ainsi que l'AMM et les teneurs de marché (BNB Chain et Ethereum), pour exécuter les échanges et trouver le meilleur prix pour les traders.

Cependant, les utilisateurs peuvent toujours personnaliser leur échange en choisissant les sources de Liquidité que le routeur doit utiliser, et activer ou désactiver les multihops et le routage divisé.

### **Vérifier le taux et le montant des frais actuellement appliqués**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Pour savoir combien votre Swap actuel sera facturé, consultez la section « Frais » dans les détails du Swap.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

Pour savoir quel type de Pool et quel palier de frais s'appliquent à votre échange, consultez la section « Route ».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Pour plus de détails, cliquez sur l'icône en forme de loupe afin d'afficher la route de trading complète.



### **Personnaliser les sources de Liquidité**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

En haut de l'interface « Personnaliser le routage », vous pouvez choisir quelle source de Liquidité le routeur doit utiliser pour votre échange. Pour accéder à cette interface, vous pouvez :

* Cliquer sur « Personnaliser le routage » en bas de l'affichage de la route de trading.
* Cliquer sur l'icône d'engrenage dans l'interface de Swap, puis sur « Personnaliser le routage » en bas.

Par défaut, toutes les sources de Liquidité sont activées et le Smart Router tire pleinement parti de l'ensemble des Liquidités disponibles sur PancakeSwap.

Veuillez noter que le routeur n'acheminera PAS les échanges entre les pools de Liquidité AMM et les teneurs de marché. Lorsque votre échange est exécuté par des teneurs de marché, il ne passe par aucun pool de Liquidité AMM.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Vous pouvez cliquer sur le bouton « Réinitialiser » en haut à droite pour rétablir les paramètres par défaut.



### **Personnaliser les préférences de routage**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

En bas de l'interface « Personnaliser le routage », vous pouvez personnaliser vos préférences de routage en activant ou désactivant les multihops et le routage divisé.

Les multihops permettent aux tokens de passer par plusieurs étapes entre différents pools de Liquidité afin d'obtenir le meilleur résultat. Les désactiver limitera les échanges aux Swaps directs, ce qui pourrait entraîner un Glissement plus élevé, voire une perte de fonds.

Le routage divisé permet de fractionner les échanges de tokens en plusieurs routes pour obtenir le meilleur résultat. Le désactiver limitera les échanges à une seule route, ce qui pourrait entraîner une efficacité réduite ou un Glissement plus élevé.

{% hint style="warning" %}
Si votre échange ne peut pas être exécuté en raison d'une configuration de trading personnalisée, un avertissement apparaîtra. Vous pouvez cliquer sur « Vérifier vos paramètres » pour accéder rapidement à l'interface « Personnaliser le routage », ou choisir « Réinitialiser par défaut » pour rétablir rapidement vos paramètres.
{% endhint %}
