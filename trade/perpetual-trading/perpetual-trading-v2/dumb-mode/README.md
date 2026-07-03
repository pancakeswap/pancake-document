---
hidden: true
---

# Mode Dumb

### Présentation

Le [**Mode Dumb**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) sur PancakeSwap Perpetuals offre une expérience de trading simplifiée, idéale pour les traders qui préfèrent trader sur les fluctuations minute par minute de la valeur d'un actif sous-jacent. Le Mode Dumb simplifie le trading en réduisant le bruit, permettant aux utilisateurs d'entrer et de sortir facilement de positions à court terme.

### Fonctionnement

Les utilisateurs disposent d'une sélection de fenêtres d'expiration de 5 minutes, 15 minutes, 30 minutes et 1 heure avec différents ratios de retour sur investissement. Les utilisateurs peuvent choisir de prendre une position long ou short sur un actif sous-jacent.

À la fin de la période d'expiration, si l'actif sous-jacent est en position gagnante (prix supérieur au prix d'ouverture pour un long, prix inférieur au prix d'ouverture pour un short), les utilisateurs pourront réaliser un profit.

Chaque période d'expiration a un ROI (retour sur investissement) différent. Plus la période d'expiration est longue, plus le ROI est élevé. Les pourcentages et frais sont les suivants :<br>

| Période d'expiration | ROI en cas de gain (net de frais)\* | ROI en cas de perte | Frais (sur les gains) |
| ----------------- | --------------------------- | ---------- | ----------------- |
| 5 minutes         | 50%                         | -100%      | 6% de la garantie  |
| 15 minutes        | 55%                         | -100%      | 6% de la garantie  |
| 30 minutes        | 70%                         | -100%      | 6% de la garantie  |
| 1 heure            | 83%                         | -100%      | 6% de la garantie  |

\*Le ROI en cas de gain peut être ajusté occasionnellement en fonction des conditions du marché. Veuillez consulter cette page pour toute mise à jour.

Par exemple, dans le scénario suivant :

* Position sélectionnée : Long
* Garantie déposée : 100 USDT
* Période d'expiration : 60 secondes
* Prix BTCUSD à l'ouverture : 50 000 $
* Prix BTCUSD après 60 secondes : 50 001 $

L'utilisateur réalisera un profit de **100 USDT \* 75% = 75 USDT**

Pour plus d'informations sur l'ouverture d'une position en Mode Dumb, cliquez [ici](dumb-mode-guide.md).

### Marchés et Actifs de Marge

Le Mode Dumb supporte le trading sur les marchés et actifs de marge suivants sur **BNB Chain** :

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Marché</td><td>Actifs de Marge</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

Le Mode Dumb supporte le trading sur les marchés et actifs de marge suivants sur **Arbitrum, opBNB et Base** :

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Marché</td><td>Actifs de Marge</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

La prise en charge d'autres actifs/chaînes est en cours de développement.

### Frais

Des frais de **6%** du principal ou de la garantie sont facturés en cas de trade gagnant. Ce montant est déjà calculé avant le ROI.

<br>
