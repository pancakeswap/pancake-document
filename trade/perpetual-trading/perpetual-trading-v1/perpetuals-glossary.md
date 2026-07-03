# Glossaire des Perpétuels V1

**Vous trouverez ici la définition de tous les termes propres au trading à terme.**

### **Trading Perpétuel**

&#x20;Les perpétuels, swaps perpétuels ou perps sont un type particulier de contrat à terme sans date d'expiration.



### **Levier**

Le Levier est un mécanisme de trading. Les traders peuvent l'utiliser pour accroître leur exposition au marché en n'ayant à payer qu'une fraction du montant total de l'investissement. En termes simples, vous empruntez des fonds pour démultiplier votre investissement.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Marge**

La marge est la garantie que vous déposez pour vos positions à Levier. Elle peut être utilisée selon deux modes :

* Mode Marge Cross : Toutes les positions cross utilisant le même actif de marge partagent le même solde de marge cross. En cas de Liquidation, l'intégralité de votre marge ainsi que les positions ouvertes restantes sur cet actif peuvent être saisies.
* Mode Marge Isolated : Gérez le risque de chaque position individuellement en limitant la marge allouée à chacune. Si le ratio de marge d'une position atteint 100%, la position sera liquidée. La marge peut être ajoutée ou retirée des positions dans ce mode.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Ratio de Marge** : Ratio de Marge = Marge de Maintenance / Solde de Marge. Vos positions seront liquidées lorsque le Ratio de Marge atteint 100%.

**Ratio de Maintenance** : Le montant minimum de solde de marge requis pour maintenir vos positions ouvertes.

**Solde de Marge** = Solde du Portefeuille + PNL Non Réalisé. Vos positions seront liquidées dès que le Solde de Marge <= Marge de Maintenance.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Actifs :

**Dépôt** : Déposez vos fonds sur votre compte Futures.

**Retrait** : Retirez vos fonds de votre compte Futures vers votre Portefeuille.

**Solde** : Solde du Portefeuille = Total des Transferts Nets + Total des Profits Réalisés + Total des Frais de Financement Nets - Total des Commissions.

**PNL Non Réalisé** : Profit et perte non réalisés sur cette position, calculés sur la base du Prix Marqué, ainsi que le pourcentage de rentabilité.

**Modes :**&#x20;

* Mode Actif Unique : Supporte le trading de Futures USDⓈ-M en utilisant uniquement l'actif de marge unique du symbole. Le PNL des positions avec le même actif de marge peut être compensé. Supporte le Mode Marge Cross et le Mode Marge Isolated.
* Mode Multi-Actifs : Trading de Futures USDⓈ-M sur plusieurs actifs de marge. Le PNL peut être compensé entre les différentes positions d'actifs de marge. Supporte uniquement le Mode Marge Cross.

{% hint style="info" %}
Remarque : Si des positions ou des ordres ouverts existent dans les Futures USDⓈ-M, le Mode Multi-Actifs ne peut pas être activé. Ce mode s'applique uniquement aux Futures USDⓈ-M. Avant de l'activer, veuillez lire attentivement le guide afin de mieux gérer le risque de votre compte Futures USDⓈ-M lorsque vous utilisez ce mode.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Ordres

**Achat/Long :** Ouvrir un ordre Long. Dans cet ordre, vous achetez un actif et attendez de le vendre lorsque le prix monte. "Acheter" et "long" sont utilisés de manière interchangeable.

**Vente/Short :** Ouvrir un ordre Short. Dans cet ordre, vous empruntez un actif, le vendez, et espérez le racheter lorsque le prix baisse. "Vendre" et "short" sont utilisés de manière interchangeable.

**Ordre Limit :** Un ordre Limit est un ordre d'achat ou de vente à un prix précis ou plus avantageux. Les ordres Limit ne sont pas garantis d'être exécutés.

**Ordre Market :** Un ordre Market est un ordre d'achat ou de vente au meilleur prix disponible actuellement. Il est exécuté contre les ordres Limit préalablement placés dans le carnet d'ordres. Lors d'un ordre Market, vous payez des frais en tant que taker.

**Ordre Stop Limit :** La manière la plus simple de comprendre un ordre Stop Limit est de le décomposer en prix stop et prix Limit. Le prix stop est simplement le prix qui déclenche l'ordre Limit, et le prix Limit est le prix de l'ordre Limit déclenché. Ainsi, dès que votre prix stop est atteint, votre ordre Limit est immédiatement placé dans le carnet d'ordres.

**Ordre Stop Market :** Similaire à l'ordre Stop Limit, l'ordre Stop Market utilise un prix stop comme déclencheur. Cependant, lorsque le prix stop est atteint, il déclenche un ordre Market plutôt qu'un ordre Limit.

**Trailing Stop :** Un Trailing Stop est un type d'ordre conçu pour verrouiller des profits ou limiter les pertes lorsqu'un trade évolue favorablement. Les Trailing Stops ne bougent que si le prix évolue favorablement. Une fois qu'il se déplace pour verrouiller un profit ou réduire une perte, il ne revient pas en arrière.

**Post Only :** Le mode Post Only signifie que les traders ne peuvent placer un ordre que s'il sera inscrit dans le carnet d'ordres en tant qu'ordre Maker. Un ordre qui serait exécuté comme ordre Taker sera rejeté. Aucun ordre Market ne peut être passé et aucun ordre ne sera exécuté. Les ordres en attente peuvent être annulés en mode post-only.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Reduce Only :** Un ordre Reduce Only ne fera que réduire votre position, jamais l'augmenter.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**Les instructions TIF** vous permettent de spécifier la durée pendant laquelle vos ordres resteront actifs avant d'être exécutés ou expirés. Vous pouvez choisir parmi les options suivantes :

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel) : L'ordre reste actif jusqu'à ce qu'il soit exécuté ou annulé.&#x20;
* **IOC** (Immediate Or Cancel) : L'ordre s'exécute immédiatement (en totalité ou partiellement). Si seulement partiellement exécuté, la portion non exécutée est annulée.&#x20;
* **FOK** (Fill Or Kill) : L'ordre doit être entièrement exécuté immédiatement. Sinon, il ne sera pas exécuté du tout.
