# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dual Investment vous permet d'engager des fonds à un prix cible et de percevoir une récompense fixe, quelle que soit l'évolution du marché. Choisissez un actif, indiquez si vous souhaitez **Buy Low** ou **Sell High**, puis sélectionnez un prix cible et une date de règlement. Au règlement, vous recevez votre capital plus la récompense, soit dans l'actif que vous avez déposé, soit converti à votre prix cible.

Dual Investment est disponible sur BNB Chain avec **BTCB** et **BNB**, en paire avec **USDT**.

{% hint style="info" %}
Dual Investment n'est pas un produit d'épargne. Selon le prix de règlement, vos fonds peuvent être convertis en un autre actif à votre prix cible, et cet actif peut valoir moins que ce que vous avez déposé.
{% endhint %}

***

## Qu'est-ce que Dual Investment ?

#### **Deux issues, une récompense fixe**

Chaque produit Dual Investment possède un prix cible et une date de règlement. Lorsque vous souscrivez, votre récompense est verrouillée à l'APR affiché. Au règlement, le prix du marché détermine laquelle des deux issues s'applique :

* **Le prix n'atteint pas votre cible.** Vous récupérez votre actif d'origine plus la récompense.
* **Le prix atteint votre cible.** Votre capital et votre récompense sont convertis dans l'autre actif à votre prix cible.

Vous percevez la récompense dans les deux cas. Seul l'actif que vous recevez change.

#### **Buy Low**

Utilisez Buy Low si vous seriez heureux d'acheter du BTCB ou du BNB en dessous du prix actuel. Vous déposez des **USDT** et choisissez un prix cible inférieur au prix actuel.

| Prix de règlement                | Vous recevez                                                          |
| -------------------------------- | --------------------------------------------------------------------- |
| Égal ou supérieur à votre cible  | USDT (capital + récompense)                                           |
| Inférieur à votre cible          | BTCB ou BNB, achetés à votre prix cible, ainsi que votre récompense   |

#### **Sell High**

Utilisez Sell High si vous seriez heureux de vendre du BTCB ou du BNB au-dessus du prix actuel. Vous déposez du **BTCB ou du BNB** et choisissez un prix cible supérieur au prix actuel.

| Prix de règlement                | Vous recevez                                                    |
| -------------------------------- | --------------------------------------------------------------- |
| Égal ou inférieur à votre cible  | BTCB ou BNB (capital + récompense)                              |
| Supérieur à votre cible          | USDT, vendus à votre prix cible, ainsi que votre récompense     |

#### **Comment fonctionne l'APR**

L'APR dépend de la proximité du prix cible avec le prix actuel et de la durée du produit. Les cibles plus proches du prix actuel offrent un APR plus élevé, car elles ont plus de chances d'être converties. Les cibles plus éloignées rapportent moins, mais ont plus de chances de vous restituer votre actif d'origine.

Votre récompense se calcule ainsi :

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Exemple : Buy Low**

Le BTCB s'échange à 83 467 $. Vous souscrivez 1 000 USDT à un produit Buy Low d'1 jour avec une cible à 82 000 $ et un APR de 14,68 %. Votre récompense est d'environ 0,40 USDT.

| Prix de règlement  | Vous recevez                          |
| ------------------ | ------------------------------------- |
| 82 000 $ ou plus   | 1 000,40 USDT                         |
| Moins de 82 000 $  | 0,0122 BTCB (1 000,40 USDT ÷ 82 000 $) |

Si le BTCB se règle à 78 000 $, vous achetez quand même à 82 000 $. Vous détiendriez 0,0122 BTCB valant environ 951,60 USDT, soit moins que ce que vous avez déposé.

#### **Exemple : Sell High**

Le BTCB s'échange à 83 467 $. Vous souscrivez 0,01 BTCB à un produit Sell High d'1 jour avec une cible à 84 500 $ et un APR de 89,28 %. Votre récompense est d'environ 0,0000245 BTCB.

| Prix de règlement   | Vous recevez                            |
| ------------------- | --------------------------------------- |
| 84 500 $ ou moins   | 0,0100245 BTCB                          |
| Plus de 84 500 $    | 847,07 USDT (0,0100245 BTCB × 84 500 $) |

Si le BTCB se règle à 88 000 $, vous vendez quand même à 84 500 $. Vous recevriez 847,07 USDT pour du BTCB qui aurait valu environ 882 USDT.

#### **Qui se trouve de l'autre côté ?**

Chaque produit est coté par un teneur de marché, qui prend la contrepartie de votre position. Les teneurs de marché déposent une garantie qui sécurise votre paiement. En cas de défaillance d'un teneur de marché, votre créance est couverte par sa garantie.

***

## Comment utiliser Dual Investment

#### **Accédez à la page Dual Investment**

Rendez-vous sur [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) ou cliquez sur **Dual Investment** dans la barre de navigation principale de PancakeSwap.

#### **1. Choisissez un actif cible**

Sélectionnez **BTCB** ou **BNB**. Chaque carte affiche le prix actuel et la fourchette d'APR disponible sur l'ensemble des produits pour cet actif.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. Choisissez une direction**

Sélectionnez **Buy Low** pour déposer des USDT et acheter l'actif à un prix inférieur, ou **Sell High** pour déposer l'actif et le vendre à un prix supérieur.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. Choisissez une date de règlement et un prix cible**

Utilisez les filtres de durée (**1 Day**, **< 3 Days**, **< 7 Days**, et plus longues) pour affiner la liste. Les produits sont regroupés par date de règlement. Chaque ligne indique le prix cible, son écart par rapport au prix actuel, et l'APR.

Le compte à rebours à côté de chaque date de règlement indique le temps qu'il vous reste pour souscrire. Les souscriptions ferment avant le règlement.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. Saisissez le montant de votre souscription**

Cliquez sur **Subscribe** pour la cible souhaitée, puis saisissez un montant ou appuyez sur **MAX**. Chaque produit comporte un minimum et un maximum par souscription, ainsi qu'une capacité totale fixe. Une fois une cible entièrement souscrite, elle ne peut pas rouvrir ; vous devrez donc choisir un autre prix cible.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. Vérifiez et confirmez**

Vérifiez la direction, le prix cible, la date de règlement et les deux issues.&#x20;

Le taux est maintenu pendant un court laps de temps le temps de la confirmation. S'il expire ou évolue, la page récupère un nouveau taux et vous demande de l'accepter avant de continuer.

#### **6. Réclamez votre paiement**

Après le règlement, cliquez sur **Claim** sur une position, ou sur **Claim all** pour réclamer d'un coup toutes les positions réglées. Votre paiement est envoyé à votre portefeuille dans l'actif déterminé par l'issue du règlement.

***

## FAQ Dual Investment

#### **Qu'est-ce que Dual Investment ?**

Dual Investment est un produit qui vous permet d'engager des fonds à un prix cible et de percevoir une récompense fixe. Au règlement, vous recevez votre capital plus la récompense, soit dans votre actif d'origine, soit converti dans l'autre actif à votre prix cible.

#### **Quels actifs sont pris en charge ?**

BTCB et BNB, en paire avec USDT, sur BNB Chain.

#### **Quelle est la différence entre Buy Low et Sell High ?**

Buy Low vous permet de déposer des USDT et d'acheter du BTCB ou du BNB à un prix cible inférieur au prix actuel. Sell High vous permet de déposer du BTCB ou du BNB et de le vendre à un prix cible supérieur au prix actuel.

#### **Perçois-je la récompense dans les deux issues ?**

Oui. La récompense est fixée lors de votre souscription et versée dans les deux issues. Elle est versée avec votre capital, dans l'actif que vous recevez au règlement.

#### **Puis-je retirer mes fonds avant la date de règlement ?**

Non. Une fois que vous avez souscrit, vos fonds sont verrouillés jusqu'au règlement et la souscription ne peut pas être annulée.

#### **Pourquoi les APR diffèrent-ils d'un produit à l'autre ?**

Les cibles plus proches du prix actuel, et les dates de règlement plus courtes, offrent généralement des APR plus élevés, car elles présentent une probabilité de conversion plus forte. Les taux sont cotés en direct et peuvent changer entre le moment où vous ouvrez un produit et celui où vous confirmez.

#### **Pourquoi le taux a-t-il changé pendant ma souscription ?**

Les taux sont cotés en direct par les teneurs de marché et ne sont maintenus que pendant un court laps de temps. Si le taux expire, évolue, ou si un autre utilisateur remplit ce prix en premier, la page récupère un nouveau taux et vous demande de l'accepter avant de continuer.

#### **Dois-je réclamer mon paiement ?**

Oui. Après le règlement, réclamez votre paiement depuis **Your Holdings**. Vous pouvez réclamer les positions une par une ou utiliser **Claim all**.

#### **Qui prend la contrepartie de ma position ?**

Des teneurs de marché cotent chaque produit et prennent la contrepartie de votre position. Ils déposent une garantie qui sécurise votre paiement et, en cas de défaillance d'un teneur de marché, votre créance est couverte par cette garantie.

#### **Quels frais sont facturés ?**

C'est gratuit.
