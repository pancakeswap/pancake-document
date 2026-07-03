# ALP Syrup Pool (Arbitrum)

ALP est un token qui alimente la Liquidité sur PancakeSwap Perpetuals V2. Les utilisateurs mintent/achètent des ALP à l'aide de tokens de garantie tels que USDC, USDT, DAI, ETH et BTC. Ces tokens fournissent de la Liquidité au moteur de trading PancakeSwap Perpetuals alimenté par ApolloX. Les tokens ALP **ne peuvent pas être transférés entre Portefeuilles** et ne peuvent être **mintés/vendus que via le contrat ALP et stakés dans le pool ALP**.

### Guide étape par étape

#### Acheter/Minter des ALP

1. Cliquez pour accéder à la page [PancakeSwap ALP Pool (V2)](https://perp.pancakeswap.finance/en/ALP) et connectez votre Portefeuille.
2. Après avoir connecté votre Portefeuille, cliquez sur **Buy ALP**. Vous pouvez utiliser n'importe quel actif du pool ALP pour acheter des ALP.
3. Après avoir vérifié les informations, cliquez sur **Buy ALP** pour finaliser la transaction.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Buy%20ALP%20Module.png" alt=""><figcaption></figcaption></figure>

**Staker des ALP (Arbitrum)**

1. Cliquez sur **Stake Now** sur la page du tableau de bord Pancake ALP, ou cliquez [ici](https://pancakeswap.finance/pools?chain=arb).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/png%20%284%29.png" alt=""><figcaption></figcaption></figure>

2. Sélectionnez le Syrup Pool CAKE-ALP.
3. **Activez** l'ALP et cliquez sur **Stake**.
4. Sélectionnez le montant d'ALP à staker et cliquez sur **Confirmer**.

**Vendre des ALP**

1. &#x20;Cliquez pour accéder à la page ALP Pool (V2) et connectez votre Portefeuille.
2. Après avoir connecté votre Portefeuille, cliquez sur **Sell ALP**.

Conditions de vente des ALP :

* &#x20;L'utilisateur peut vendre ses ALP 48 heures après leur achat.
* &#x20;Montant d'ALP pouvant être vendus : min\[(Valeur du pool de Liquidité - Valeur des positions de l'utilisateur)\*50%]/Prix du marché de l'ALP. Par exemple, si la valeur du pool de Liquidité est de 10 000 000 USDT, la valeur de la position de l'utilisateur est de 5 000 000 USDT et le prix du marché de l'ALP est de 2 USDT, le montant maximum d'ALP que l'utilisateur peut vendre est de 1 250 000.&#x20;
* Par ailleurs, le montant d'actifs que les utilisateurs reçoivent après la vente de leurs tokens ALP ne peut pas dépasser le pool de Liquidité ALP. Par exemple, si le pool de Liquidité ne contient que 1 000 USDT, le montant maximum d'USDT que les utilisateurs recevront sera de 1 000 USDT, et les ALP restants pourront être vendus contre d'autres cryptomonnaies.
