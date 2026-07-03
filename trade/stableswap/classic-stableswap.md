# Classic StableSwap

Der Classic StableSwap ist eine Implementierung des AMM von Curve Finance auf PancakeSwap. Er fügt der Formel des konstanten Produkts (x\*y=k) eine lineare Invariante der konstanten Summe (x+y=k) hinzu, um die Preise möglichst stabil zu halten, solange der Liquiditätspool nicht extrem unausgewogen ist. Da StableSwaps auf ähnlich bepreiste Assets beschränkt sind, ist der unbeständige Verlust kein so großes Problem (außer in extremen Depeg-Fällen), und die Kursabweichung ist geringer als bei normalen AMMs, die nur die Formel des konstanten Produkts verwenden.

Wenn Sie einen Swap (Trade) auf dem StableSwap durchführen, zahlen Sie niedrigere Handelsgebühren als die üblichen 0,25 % auf dem normalen PancakeSwap AMM. Die Gebührenaufteilung ist wie folgt:

* 50 % an den LP als Belohnungen&#x20;
* 40 % für CAKE-Rückkauf und -Burn&#x20;
* 10 % an die PancakeSwap-Treasury

## StableSwap-Gebühren

Die Gebühren für die Paare sind in der folgenden Tabelle aufgeführt:

<table><thead><tr><th width="150">Stabiles Paar</th><th width="132">Handelsgebühren</th><th width="118.33333333333331">LP-Belohnungen</th><th width="124">CAKE-Rückkauf</th><th>PancakeSwap-Treasury</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0,01 %</td><td>0,005 %</td><td>0,004 %</td><td>0,001 %</td></tr><tr><td>USDC-BUSD</td><td>0,01 %</td><td>0,005 %</td><td>0,004 %</td><td>0,001 %</td></tr><tr><td>USDC-USDT</td><td>0,01 %</td><td>0,005 %</td><td>0,004 %</td><td>0,001 %</td></tr><tr><td>HAY-BUSD</td><td>0,04 %</td><td>0,02 %</td><td>0,016 %</td><td>0,004 %</td></tr><tr><td>HAY-USDT</td><td>0,04 %</td><td>0,02 %</td><td>0,016 %</td><td>0,004 %</td></tr><tr><td>axlUSDC-USDT</td><td>0,04 %</td><td>0,02 %</td><td>0,016 %</td><td>0,004 %</td></tr><tr><td>BNBx-WBNB</td><td>0,04 %</td><td>0,02 %</td><td>0,016 %</td><td>0,004 %</td></tr><tr><td>stkBNB-WBNB</td><td>0,04 %</td><td>0,02 %</td><td>0,016 %</td><td>0,004 %</td></tr></tbody></table>

The Kitchen wird schrittweise StableSwap-Paare einführen und die Gebühren anpassen, um das Produkt weiter zu testen und zu verbessern.

## Warum sollte ich den StableSwap statt des normalen AMM-Swap verwenden?

* Tauschen Sie Ihre Stablecoins oder andere Paare mit ähnlichen Asset-Preisen effizienter mit denselben Trade-Schritten&#x20;
* Mit der StableSwap-Funktion ist die Kursabweichung beim Handel geringer als beim normalen AMM&#x20;
* Die StableSwap-Handelsgebühren sind niedriger als beim normalen AMM
