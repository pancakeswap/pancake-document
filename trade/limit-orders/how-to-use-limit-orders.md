---
hidden: true
---

# Comment utiliser les Ordres Limit

## Qu'est-ce qu'un Ordre Limit ?

Un ordre Limit est un outil permettant aux utilisateurs d'acheter ou de vendre des actifs à un prix spécifié ou meilleur, au lieu de dépendre du prix du marché au moment de l'exécution. Dans un ordre Limit, si le prix est garanti, l'exécution de l'ordre ne l'est pas — les ordres Limit ne seront exécutés que si le prix satisfait les conditions de l'ordre.

## Comment configurer un ordre Limit ?

1. Rendez-vous sur la page Swap et sélectionnez l'option d'ordre Limit en cliquant sur "LIMIT", ou utilisez ce lien : [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Sélectionnez les tokens "De" et "Vers" que vous souhaitez échanger. Dans cet exemple, nous avons choisi USDC et ETH respectivement, ce qui signifie que nous souhaitons acheter de l'ETH avec des USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Saisissez le montant que vous souhaitez échanger. Notez que le prix Limit affichera le prix actuel du marché, ce qui permettra d'estimer le montant de sortie des tokens de destination (ETH).
2. Définissez le prix Limit souhaité. Les trades ne seront exécutés QUE lorsque le prix du marché disponible est meilleur ou égal au prix Limit. Le montant de sortie du token de destination sera mis à jour en conséquence.

Dans l'exemple ci-dessous, nous souhaitons acheter de l'ETH lorsque le prix est de 1 900 $ ou mieux. Le montant d'ETH reçu sera égal ou supérieur à 0,037 ETH. Seules les offres égales ou supérieures à ce montant seront éligibles pour exécuter l'ordre. Ce montant tient compte des frais de gas et des frais de trading.

{% hint style="info" %}
Remarque importante : Les frais étant prélevés sur le montant du token de sortie, le prix Limit inclut les frais de gas et de trading. Les utilisateurs doivent donc en tenir compte lors de la définition du prix. Par exemple, les frais de gas d'un ordre très petit peuvent représenter un pourcentage très élevé de la sortie de l'ordre, ce qui se traduit par un prix Limit réel non compétitif avec le prix spot du marché.
{% endhint %}

3.  Cliquez sur "Place order". Vérifiez les détails de votre ordre, acceptez l'avertissement et cliquez sur "Confirm order".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Une fois la transaction effectuée, vous pourrez voir votre ordre dans la section d'historique des ordres, sous "Open orders". \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Les ordres ouverts peuvent être annulés à tout moment en développant l'ordre et en cliquant sur le bouton "Cancel Order".

Points à prendre en compte :

* Votre ordre peut ne pas être exécuté si le prix du marché disponible est inférieur au prix Limit que vous avez défini.
* Les trades sont basés sur un protocole décentralisé qui utilise des takers off-chain qui se font concurrence pour exécuter les ordres. Ces takers sont autorisés à demander des frais, que le protocole déduit des tokens de sortie pour le taker gagnant.&#x20;
* Les takers peuvent prendre en compte les frais de gas pour vos transactions lors de la définition de leurs frais, ce qui peut entraîner des fluctuations dans les montants de frais.
* Lors de la spécification d'un prix Limit, les utilisateurs verront dans l'interface le montant minimum de tokens de destination qu'ils recevront si l'ordre est exécuté. Seuls les takers proposant des offres égales ou supérieures à ce montant seront éligibles pour exécuter l'ordre. Ce montant tient compte des frais de gas et des frais de trading.
