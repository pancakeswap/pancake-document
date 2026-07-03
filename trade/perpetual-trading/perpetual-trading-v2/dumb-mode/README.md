---
hidden: true
---

# Dumb Mode

### Übersicht

[**Dumb Mode**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) auf PancakeSwap Perpetuals bietet ein vereinfachtes Handelserlebnis, das ideal für Händler ist, die auf die minütlichen Schwankungen des Wertes eines Basiswerts handeln möchten. Dumb Mode vereinfacht den Handel, indem er unnötige Informationen reduziert und es Nutzern ermöglicht, kurzfristige Positionen problemlos zu eröffnen und zu schließen.

### Wie es funktioniert

Nutzern stehen Ablaufzeiträume von 5 Minuten, 15 Minuten, 30 Minuten und 1 Stunde mit unterschiedlichen ROI-Verhältnissen zur Verfügung. Nutzer können wählen, ob sie einen Basiswert Long oder Short gehen möchten.

Am Ende des Ablaufzeitraums, wenn der Basiswert in einer Gewinnposition ist (Preis größer als der Eröffnungspreis bei Long, Preis kleiner als der Eröffnungspreis bei Short), erzielen Nutzer einen Gewinn.

Jeder Ablaufzeitraum hat ein anderes ROI-Verhältnis. Je länger der Ablaufzeitraum, desto höher der ROI. Prozentsätze und Gebühren sind wie folgt:<br>

| Ablaufzeitraum | Gewinn-ROI (nach Gebühren)\* | Verlust-ROI | Gebühren (bei Gewinn) |
| -------------- | ---------------------------- | ----------- | --------------------- |
| 5 Minuten      | 50 %                         | -100 %      | 6 % der Sicherheitsleistung |
| 15 Minuten     | 55 %                         | -100 %      | 6 % der Sicherheitsleistung |
| 30 Minuten     | 70 %                         | -100 %      | 6 % der Sicherheitsleistung |
| 1 Stunde       | 83 %                         | -100 %      | 6 % der Sicherheitsleistung |

\*Der Gewinn-ROI kann gelegentlich je nach Marktbedingungen angepasst werden. Bitte prüfen Sie diese Seite auf Aktualisierungen.

Beispielszenario:

* Gewählte Position: Long
* Eingesetzte Sicherheitsleistung: 100 USDT
* Ablaufzeitraum: 60 Sekunden
* BTCUSD-Preis bei Eröffnung: 50.000 $
* BTCUSD-Preis nach 60 Sekunden: 50.001 $

Der Nutzer erzielt einen Gewinn von **100 USDT \* 75 % = 75 USDT**

Weitere Informationen zum Öffnen einer Dumb-Mode-Position finden Sie [hier](dumb-mode-guide.md).

### Märkte und Margin-Assets

Dumb Mode unterstützt den Handel in folgenden Märkten und Margin-Assets auf **BNB Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Markt</td><td>Margin-Assets</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

Dumb Mode unterstützt den Handel in folgenden Märkten und Margin-Assets auf **Arbitrum, opBNB und Base Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Markt</td><td>Margin-Assets</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

Die Unterstützung für weitere Assets/Chains befindet sich in der Entwicklung.

### Gebühren

Eine Gebühr von **6 %** des Einsatzes oder der Sicherheitsleistung wird bei einem erfolgreichen Trade erhoben. Diese ist bereits vor dem ROI einberechnet.

<br>
