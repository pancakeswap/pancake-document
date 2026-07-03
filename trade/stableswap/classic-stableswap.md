# Classic StableSwap

Classic StableSwap è un'implementazione dell'AMM di Curve Finance su PancakeSwap. Aggiunge la curva invariante a somma costante lineare (x+y=k) sopra la formula del prodotto costante (x\*y=k) per mantenere i prezzi più equilibrati finché il Pool di Liquidità non è estremamente sbilanciato. Di conseguenza, poiché gli StableSwap sono limitati ad asset con prezzi simili, la perdita impermanente non è una preoccupazione rilevante (tranne nei casi estremi di depeg) e lo Slippage è inferiore rispetto all'AMM normale che utilizza solo la formula del prodotto costante.

Quando esegui uno Swap (scambio) sullo StableSwap, pagherai commissioni di trading inferiori rispetto allo 0,25% abituale sull'AMM normale di PancakeSwap. La ripartizione delle commissioni è la seguente:

* 50% agli LP come ricompense
* 40% per il riacquisto e il burn di CAKE
* 10% al Treasury di PancakeSwap

## Commissioni StableSwap

Le commissioni per coppia sono riportate nella tabella seguente:

<table><thead><tr><th width="150">Coppia Stabile</th><th width="132">Commissioni di Trading</th><th width="118.33333333333331">Ricompense LP</th><th width="124">Riacquisto CAKE</th><th>Treasury PancakeSwap</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-USDT</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>HAY-BUSD</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>HAY-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>axlUSDC-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>BNBx-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>stkBNB-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr></tbody></table>

Il team rilascerà gradualmente le coppie StableSwap e revisionerà le commissioni per testare e migliorare ulteriormente il prodotto.

## Perché dovrei usare StableSwap invece del normale AMM Swap?

* Scambia le tue stablecoin o altre coppie con prezzi di asset simili in modo più efficiente con gli stessi passaggi di trading
* Con la funzione StableSwap, lo Slippage di trading è inferiore rispetto all'AMM normale
* Le commissioni di trading StableSwap sono inferiori rispetto all'AMM normale
