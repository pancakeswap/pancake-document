# Wie der v3 APR berechnet wird

{% hint style="info" %}
In V3 Liquidität und Farms, mit der neuen nicht-fungiblen Liquidität und der anpassbaren Preisbereichsfähigkeit, hat jede LP-Position ihren eigenen LP-Gebühren- und CAKE-Farming-APR.
{% endhint %}

Der Gesamt-APR setzt sich aus dem LP-Gebühren-APR und dem CAKE-Reward-APR zusammen.

### LP-Gebühr

Theoretisch gesehen können wir, ausgehend von einem Preisbereich und der Liquidität, die ein Benutzer hinzufügen möchte, die erwarteten zukünftigen Gebühren für 7 Tage wie folgt schätzen:&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Gebührenbetrag, der im vom Benutzer angegebenen Preisbereich in den letzten 7 Tagen angefallen ist
* $$L_{in}$$: Aktuelle Liquidität im vom Benutzer angegebenen Preisbereich
* $$\Delta{L}$$: Liquidität, die der Benutzer dem Preisbereich hinzufügen möchte

#### Gebühr im Bereich

Für $$fee_{in}$$ verwenden wir historische Handelsvolumendaten, die Gebührenstufe und historische Preisdaten, um den Preis im Bereich zu schätzen:

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Gebührenstufe
* $$V_{7d}$$: Gesamthandelsvolumen der letzten 7 Tage
* $$T_{in}$$: Dauer in Sekunden, in der die Preise in den letzten 7 Tagen innerhalb des Preisbereichs lagen
* $$T_{7d}$$: 7 Tage in Sekunden gemessen

### CAKE APR

#### Pool-Zuweisung

Die gesamten CAKE-Rewards pro Sekunde in MC v3 verwenden Upkeep und können durch `latestPeriodCakePerSecond` abgeleitet werden:&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

In jedem Pool können wir `poolInfo` verwenden, um das `poolWeight` durch Division von `poolInfo.allocPoint / totalAllocPoint` zu erhalten.

#### Globaler CAKE APR

Globaler APR, berechnet anhand der Gesamtmenge an aktiver und gestakter Liquidität mit den CAKE-Reward-Emissionen des Pools.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` stellt die aktuelle aktive gestakte Liquidität des Pools in USD dar und setzt sich aus allen im Bereich liegenden Positions-Ticks zusammen, die in MasterChef v3 gestakt sind.

#### Positions-CAKE APR

Die APRs für einzelne Positionen können je nach Preisbereichseinstellungen variieren.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: CAKE-Reward in USD pro Jahr im Pool
* $$USD_p$$: Gesamter USD-Wert in der Position
* $$L_{p}$$: Positions-Liquidität
* $$L_{lm}$$: Gesamte Staking-Liquidität, die vom LMPool verfolgt wird
