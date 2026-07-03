# 🌊 Pools de Liquidité

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

Dans le nouvel Exchange V3, la Liquidité sera gérée sous la forme de positions non-fongibles. Vous continuerez à percevoir une part des frais en fournissant de la Liquidité.

Lorsque vous ajoutez votre token à un Pool de Liquidité, vous recevrez des tokens NFT de Fournisseur de Liquidité et partagerez les frais.

### **Positions de Liquidité non-fongibles**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

Dans V3, les fournisseurs de Liquidité ont désormais plus de contrôle sur la plage de prix dans laquelle ils souhaitent déployer leur Liquidité. Ainsi, lorsque vous ajoutez votre token à un Pool de Liquidité en V3, vous créez une nouvelle position de Liquidité non-fongible avec ses paramètres uniques.

Par conséquent, en V3, les positions de Liquidité sont des NFTs. Veuillez noter que ces NFTs sont transférables et représentent la propriété des actifs sous-jacents ainsi que des frais de Trading qu'ils ont générés.

En V3, les frais de Trading ne seront plus automatiquement composés dans la position. Vous pouvez les réclamer manuellement sur chacune des pages de détails de position.

Vous pouvez récupérer vos fonds à tout moment en retirant votre Liquidité.

### **Liquidité active et plages de prix**

En V3, les fournisseurs de Liquidité peuvent configurer leurs positions pour ne fournir de la Liquidité que lorsque le prix se situe dans une certaine plage. Si le prix de Trading sort de cette plage, la position ne contiendra plus qu'un seul type de token de la paire et deviendra inactive.

Les positions de Liquidité inactives ne participeront pas aux échanges et ne généreront aucun frais de Trading.

### **Liquidité concentrée**

En V3, grâce à la fonctionnalité de Liquidité concentrée, les fournisseurs de Liquidité peuvent concentrer leurs dépôts de tokens pour ne fournir de la Liquidité que dans une plage de prix spécifique. Avec la même quantité d'actifs sous-jacents, V3 peut supporter des échanges bien plus importants.

Cela se traduit par un niveau de Liquidité relative bien supérieur à celui de V2. Les fournisseurs de Liquidité peuvent ainsi générer davantage de frais de Trading avec le même montant de capital.

Voici un exemple :

> Baller et Claire ont tous deux fourni de la Liquidité dans le Pool CAKE/USDT avec l'équivalent de 1 000 USD en tokens. Le prix actuel du CAKE est de 5 USDT.
>
> À l'instar de PancakeSwap v2, Baller a fourni sa Liquidité sur toute la plage de prix. Il a donc déposé l'intégralité de son capital, soit 500 USDT et 100 CAKE.
>
> Claire utilise la nouvelle fonctionnalité de Liquidité concentrée de PancakeSwap v3 et crée une position avec une plage de prix allant de 2 à 12,5 USDT par CAKE. Elle dépose 185 USDT et 37 CAKE, pour un total de 370 $. Elle peut désormais utiliser les 630 $ restants ailleurs, par exemple en bloquant des CAKE dans le Syrup Pool pour profiter d'un rendement élevé en CAKE tout en bénéficiant d'une série d'avantages dans l'écosystème PancakeSwap.
>
> Tant que le CAKE reste dans la plage de prix de 2 à 12,5, Baller et Claire recevront le même montant de récompenses en frais de Trading, même si Claire a déposé bien moins de capital dans le Pool de Liquidité.

### **Frais de Trading**&#x20;

La fourniture de Liquidité vous offre une récompense sous forme de frais de Trading lorsque des utilisateurs utilisent votre Pool de Liquidité pour effectuer des Swaps.

Chaque fois qu'un utilisateur effectue un échange sur PancakeSwap, pour chaque saut (Swap) dans chaque Pool de Liquidité Exchange V3, selon le niveau de frais du Pool de Liquidité, le trader paie des frais allant de 0,01 % à 1 %. Les taux de frais et leur répartition sont présentés ci-après :

<details>

<summary>Frais de Trading (EVM)</summary>

| Composante des frais / Niveau de frais | 0,01 % | 0,05 % | 0,25 % | 1 %  |
| ------------------------ | ----- | ----- | ----- | --- |
| Fournisseur de Liquidité       | 67 %   | 66 %   | 68 %   | 68 % |
| Burn CAKE                | 15 %   | 15 %   | 23 %   | 23 % |
| Trésorerie                 | 18 %   | 19 %   | 9 %    | 9 %  |

Par exemple, dans un Pool avec un niveau de frais de 0,25 % :

* Parmi toutes les positions de Liquidité actives (dans la plage), il y a au total 10 CAKE et 10 BNB.
* Un utilisateur échange 1 CAKE contre 1 BNB.
* Un autre utilisateur échange 1 BNB contre 1 CAKE.
* Les fournisseurs de Liquidité dont la plage couvre le prix actuel ont gagné un total de 0,0017 CAKE et 0,0017 BNB grâce aux échanges.
* Les positions dont la plage de prix ne couvre pas le prix actuel, et donc inactives, ne contribuent pas aux échanges et ne génèrent aucun frais.

</details>

<details>

<summary><strong>Frais de Trading (Solana)</strong></summary>

**Niveaux de frais disponibles pour les Pools V3 CLMM :**\
0,01 %, 0,02 %, 0,03 %, 0,04 %, 0,05 %, 0,1 %, 0,15 %, 0,16 %, 0,18 %, 0,2 %, 0,25 %, 0,4 %, 0,6 %, 0,8 %, 1 %, 2 %, 3 %, 4 %

**Remarque :** La **répartition des frais reste identique** pour tous les niveaux de frais.

| Composante des frais                 | % des frais de Swap totaux | Description                                                   |
| ----------------------------- | ------------------- | ------------------------------------------------------------- |
| **LPs (Fournisseurs de Liquidité)** | 84 %                 | Perçus par les LPs qui fournissent de la Liquidité dans la plage de prix active |
| **Burn**                      | 8 %                  | Définitivement supprimés pour réduire l'offre de CAKE                     |
| **Trésorerie**                  | 8 %                  | Alloués à la trésorerie du protocole PancakeSwap                |

**Exemple : Répartition des frais dans un Pool CAKE/SOL à 0,25 %**

1. **Configuration du Pool :** Liquidité active totale : 10 CAKE et 10 SOL (positions dans la plage).
2. **Swaps effectués :**
   * L'utilisateur A échange 1 CAKE → 1 SOL.
   * L'utilisateur B échange 1 SOL → 1 CAKE.
3. **Total des frais collectés :**
   * 0,25 % par échange × 2 échanges = **0,005 CAKE + 0,005 SOL**.
4. **Répartition des frais :**
   * **84 % aux LPs :** 0,0042 CAKE + 0,0042 SOL
   * **8 % au Burn :** 0,0004 CAKE + 0,0004 SOL
   * **8 % à la Trésorerie :** 0,0004 CAKE + 0,0004 SOL
5. **Gains des LPs :**
   * Seuls les **LPs dans la plage** perçoivent des frais. Les frais sont distribués proportionnellement en fonction de la part de chaque LP.
   * Les **LPs hors plage** ne perçoivent **aucun frais**.

</details>

### **Générer des CAKE**

Pour rendre encore plus intéressante votre activité de fournisseur de Liquidité, vous pouvez également mettre vos positions de Liquidité au travail pour générer de nouveaux rendements sur les [Farms CAKE](https://pancakeswap.finance/liquidity/pools), tout en continuant à percevoir des récompenses sous forme de frais de Trading.

***

## Exchange V2

### LP Tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Par exemple, si vous déposez des **CAKE** et des **BNB** dans un Pool de Liquidité, vous recevrez des tokens **CAKE-BNB LP**.

Le nombre de LP Tokens que vous recevez représente votre part dans le Pool de Liquidité CAKE-BNB.

Vous pouvez également récupérer vos fonds à tout moment en retirant votre Liquidité.

### **Générer des frais de Trading**

Chaque fois qu'un utilisateur effectue un échange sur PancakeSwap, pour chaque saut (Swap) dans chaque Pool de Liquidité Exchange V2, le trader paie des frais fixes de 0,25 %, **dont 0,17 %** sont reversés dans le Pool de Liquidité sous forme de frais de Trading.

### **Générer des CAKE**

L'ancien Exchange V2 continuera à fonctionner en parallèle avec le nouvel Exchange V3. Ainsi, certaines paires de Trading resteront sur PancakeSwap Exchange V2 et disposeront de leurs Farms V2 correspondantes. Veuillez vérifier les étiquettes pour identifier les versions des exchanges.



## Impermanent Loss

La fourniture de Liquidité n'est pas sans risque, car vous pouvez être exposé à une Impermanent Loss (perte non permanente).

[« En termes simples, l'Impermanent Loss est la différence entre la détention de tokens dans un AMM et leur détention dans votre Portefeuille. » - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
