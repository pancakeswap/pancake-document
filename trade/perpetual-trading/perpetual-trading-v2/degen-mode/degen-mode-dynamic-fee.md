# Degen Mode Dynamische Gebühr

PancakeSwap Perpetuals Degen Mode verwendet ein dynamisches Gebührenmodell. Diese Gebühr ist so konzipiert, dass sie Gebühren nach PnL erhebt und Nutzer vor Verlusten schützt.\
**Wie funktioniert das?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

wobei:

* Pnl der Gewinn oder Verlust der Position ist
* shareRate die Anteilsrate ist, d. h. der Prozentsatz des Nominalwerts, der als Gebühren gezahlt wird (standardmäßig 15 %)
* Notional der Betrag ist, der zum Öffnen der Position verwendet wird
* closeMinRate die minimale Schließungsgebühr ist, d. h. der niedrigste Betrag, den Sie zahlen können, um eine Position zu schließen (standardmäßig 0,03 %)

\
**Beispiel:**

Wenn Sie eine Position mit einem Gewinn von 100 $, einer Anteilsrate von 15 % und einem Nominalwert von 600 $ haben, würde die Schließungsgebühr wie folgt berechnet:

Schließungsgebühr = Max(100 \* 15 % / 600, 0,03 %) = 0,03 %

In diesem Fall beträgt die Schließungsgebühr 0,03 %, die minimale Schließungsgebühr.<br>

Hinweis:

Die Ausführungsgebühr wird nur beim Öffnen einer Position erhoben. Sie beträgt 0,30 USD (BNB Chain) / 0,20 USD (Arbitrum) / 0,01 USD (opBNB) / 0,30 USD (Base), ähnlich wie beim klassischen Perpetual Trading. Es gibt keine Positionseröffnungsgebühr.

Im Falle einer Liquidierung beinhaltet die 90%ige Liquidierungsverlustrate die Schließungsgebühr.
