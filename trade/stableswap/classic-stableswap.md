# Classic StableSwap

Le Classic StableSwap est une implémentation de l'AMM de Curve Finance sur PancakeSwap. Il ajoute une courbe d'invariant linéaire à somme constante (x+y=k) par-dessus la formule de produit constant (x\*y=k) pour maintenir les prix plus stables tant que le Pool de Liquidité n'est pas extrêmement déséquilibré. En conséquence, puisque les StableSwaps sont limités à des actifs de prix similaires, la perte impermanente est moins préoccupante (sauf dans les cas extrêmes de désancrages) et le Glissement est inférieur à celui d'un AMM normal qui utilise uniquement la formule de produit constant.

Lorsque vous effectuez un Swap (trade) sur le StableSwap, vous payez des frais de trading moins élevés que les 0,25% habituels sur l'AMM normal de PancakeSwap. La répartition des frais est la suivante :

* 50% pour les LP en récompenses&#x20;
* 40% pour le rachat et burn de CAKE&#x20;
* 10% pour la trésorerie PancakeSwap

## Frais StableSwap

Les frais par paire sont détaillés dans le tableau ci-dessous :

<table><thead><tr><th width="150">Paire stable</th><th width="132">Frais de trading</th><th width="118.33333333333331">Récompenses LP</th><th width="124">Rachat CAKE</th><th>Trésorerie PancakeSwap</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-USDT</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>HAY-BUSD</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>HAY-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>axlUSDC-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>BNBx-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>stkBNB-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr></tbody></table>

La Kitchen déploiera progressivement les paires StableSwap et révisera les frais pour continuer à tester et améliorer le produit.

## Pourquoi utiliser StableSwap plutôt que l'AMM normal ?

* Échangez vos stablecoins ou d'autres paires d'actifs à prix similaires plus efficacement avec les mêmes étapes de trade.&#x20;
* Avec la fonctionnalité StableSwap, le Glissement de trading est inférieur à celui d'un AMM normal.&#x20;
* Les frais de trading sur StableSwap sont moins élevés que ceux de l'AMM normal.
