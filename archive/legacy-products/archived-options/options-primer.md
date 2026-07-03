# Introduction aux options



{% hint style="danger" %}
\[ARCHIVÉ] Options – À partir du 11 mars 2025\
Si vous avez encore de la Liquidité à retirer, veuillez le faire immédiatement en visitant https://www.stryke.xyz/en/trade.
{% endhint %}



## Que sont les options ?

Les options sont des contrats dérivés qui confèrent à l'acheteur le droit, mais non l'obligation, d'acheter (option d'achat/call) ou de vendre (option de vente/put) un actif sous-jacent à un prix prédéterminé (prix d'exercice) dans un délai donné (date d'expiration).

## Types d'options

### Options d'achat (Call Options)

Une option d'achat donne au détenteur le droit d'acheter l'actif sous-jacent au prix d'exercice convenu à ou avant la date d'expiration. Les traders achètent des options d'achat lorsqu'ils anticipent une hausse du prix de l'actif sous-jacent. Cela leur permet de bénéficier d'une appréciation potentielle du prix sans avoir à posséder directement l'actif sous-jacent.

> Un trader achète une option d'achat sur Bitcoin avec un prix d'exercice de 50 000 $ expirant dans un mois. Si le prix du Bitcoin monte au-dessus de 50 000 $ dans ce délai, l'investisseur peut exercer l'option pour acheter du Bitcoin à 50 000 $, réalisant potentiellement un bénéfice sur la différence de prix.

### Options de vente (Put Options)

Une option de vente donne au détenteur le droit de vendre l'actif sous-jacent au prix d'exercice convenu à ou avant la date d'expiration. Les traders achètent des options de vente lorsqu'ils s'attendent à une baisse du prix de l'actif sous-jacent. Cela leur permet de profiter des baisses de prix potentielles sans avoir à vendre l'actif sous-jacent à découvert. Les options de vente sont également généralement utilisées pour se couvrir contre les risques à la baisse dans des portefeuilles d'investissement.

> Un trader achète une option de vente sur Ethereum avec un prix d'exercice de 3 000 $ expirant dans deux semaines. Si le prix d'Ethereum tombe en dessous de 3 000 $ dans ce délai, le trader peut exercer l'option pour vendre Ethereum à 3 000 $, réduisant ainsi les pertes potentielles.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Positions sur options

Pour chaque type d'option, il existe deux positions potentielles :

### **Option longue (Acheteur d'option)**&#x20;

Cette position implique de payer une prime initiale pour acquérir l'option. Si l'option se termine en bénéfice, le détenteur reçoit un règlement.

### **Option courte (Émetteur/Vendeur d'option)**

Dans cette position, le vendeur reçoit une prime initiale pour émettre l'option. Cependant, si l'option se termine en bénéfice (pour l'acheteur ; sur la base du prix sous-jacent, du prix d'exercice et du type d'option), le vendeur est obligé de payer un règlement.

## Options américaines vs européennes

* **Options américaines :** Peuvent être exercées à tout moment avant la date d'expiration. Cette flexibilité les rend plus précieuses que les options européennes.
* **Options européennes :** Ne peuvent être exercées qu'à la date d'expiration. Elles sont généralement moins chères que les options américaines en raison de leur manque de flexibilité.

## Quand utiliser les options ?

Voici quelques exemples de cas d'usage :

1. **Spéculation :** Un investisseur pense que le prix du Bitcoin augmentera au cours du mois prochain. Il achète des options d'achat sur Bitcoin pour profiter de la hausse anticipée.
2. **Couverture :** Un validateur de cryptomonnaie souhaite se couvrir contre des baisses potentielles du prix d'Ethereum. Il achète des options de vente sur Ethereum pour se protéger contre les pertes si le prix tombe en dessous d'un certain niveau.
3. **Génération de revenus :** Un investisseur crypto qui détient une grande quantité d'Ether décide d'émettre des options d'achat sur ses avoirs, gagnant des primes tout en participant aux potentielles hausses de prix.

## Tarification des options

La tarification des options est complexe et implique divers facteurs, le modèle Black-Scholes étant le plus couramment utilisé.&#x20;

Les principaux facteurs influençant la tarification des options incluent :

* **Prix de l'actif sous-jacent :** Le cours actuel du marché de l'actif sous-jacent.
* **Prix d'exercice :** Le prix auquel le détenteur de l'option peut acheter ou vendre l'actif sous-jacent.
* **Volatilité :** Le degré de fluctuations de prix de l'actif sous-jacent.&#x20;
* **Temps jusqu'à l'expiration :** Le temps restant avant l'expiration de l'option.
* **Taux d'intérêt :** Le taux de rendement sans risque.

La tarification des options détermine la prime/les frais qu'un émetteur reçoit lorsqu'un trader d'options achète son option. Les émetteurs d'options sont exposés au risque de payer un règlement si leurs options expirent dans la monnaie (ITM, profitable pour l'acheteur). En conséquence, les primes qu'ils perçoivent des acheteurs doivent refléter équitablement la probabilité d'un événement ITM.

Les primes des CLAMM options PancakeSwap sont dérivées du modèle Black-Scholes avec les hypothèses suivantes :

* Le taux sans risque est supposé être zéro.
* La volatilité est basée sur la volatilité historique sur 30 jours de l'actif sous-jacent [utilisée comme proxy pour la volatilité implicite (IV)].

Quelques exceptions incluent :

* Les IV de $ETH et $BTC sont prises directement de Deribit si les prix d'exercice correspondent. Si les prix d'exercice ne correspondent pas, les prix d'exercice supérieurs et inférieurs les plus proches de Deribit sont pondérés en fonction du degré d'écart pour définir l'IV.
* $ARB utilise une volatilité historique basée sur le bêta sur 30 jours en calculant le prix d'exercice effectif de l'actif de base par rapport à $ETH pour extrapoler l'IV, qui est multiplié par le bêta de l'actif de base par rapport à $ETH.

Les actifs à forte volatilité auront une prime plus élevée que les actifs à moindre volatilité, car le risque pour les émetteurs que l'option expire ITM est plus grand.

## Règlement des options

### Conditions de règlement

* Le règlement est déterminé sur la base du caractère « dans la monnaie » de l'option à l'expiration.
* Le règlement est calculé uniquement si l'option est dans la monnaie (ITM) lors de l'exercice.

### Conditions ITM

* **Option d'achat (Call) :** Si le prix au comptant lors du règlement > prix d'exercice
* **Option de vente (Put) :** Si le prix au comptant lors du règlement < prix d'exercice

### Calcul du règlement

* **Option d'achat (Call) :** #Options \* (Prix au comptant lors du règlement - Prix d'exercice)
* **Option de vente (Put) :** #Options \* (Prix d'exercice - Prix au comptant lors du règlement)

### Caractère « dans la monnaie »

Le caractère dans la monnaie désigne la valeur intrinsèque d'une option, déterminée en comparant son prix d'exercice à son prix au comptant au moment de l'exécution.

### Classification

1. Hors de la monnaie (OTM) :
   1. Une option est OTM si le prix au comptant lors du règlement diffère du prix d'exercice et qu'aucune valeur ne serait échangée en cas de règlement immédiat.
   2. Conditions :
      1. Option d'achat (Call) : Prix au comptant < Prix d'exercice
      2. Option de vente (Put) : Prix au comptant > Prix d'exercice

{% hint style="info" %}
Une option d'achat $ETH avec un prix d'exercice de 2 000 $ serait OTM si le prix au comptant est de 1 800 $ (1 800 $ < 2 000 $, soit OTM).
{% endhint %}

2. À la monnaie (ATM) :
   1. Une option est ATM si le prix au comptant lors du règlement est égal au prix d'exercice et qu'aucune valeur ne serait échangée en cas de règlement immédiat.
   2. Conditions : pour les options d'achat et de vente : Prix au comptant = Prix d'exercice

{% hint style="info" %}
Une option d'achat $ETH et une option de vente $ETH avec un prix d'exercice de 1 800 $ seraient toutes deux ATM si le prix au comptant est également de 1 800 $ (1 800 $ = 1 800 $, soit ATM).
{% endhint %}

3. Dans la monnaie (ITM) :
   1. Une option est ITM si le prix au comptant lors du règlement diffère du prix d'exercice et qu'il existe une valeur à échanger en cas de règlement immédiat.
   2. Conditions :
      1. Option d'achat (Call) : Prix au comptant > Prix d'exercice
      2. Option de vente (Put) : Prix au comptant < Prix d'exercice

{% hint style="info" %}
Une option d'achat $ETH avec un prix d'exercice de 1 600 $ serait ITM si le prix au comptant est de 1 800 $ (1 800 $ > 1 600 $, soit ITM).
{% endhint %}

Le règlement perçu par l'acheteur de l'option équivaut à la garantie perdue par l'émetteur de l'option. Le règlement exclut la prime d'option payée, qui est prise en compte lors du calcul des bénéfices ou pertes pour les acheteurs et émetteurs d'options.
