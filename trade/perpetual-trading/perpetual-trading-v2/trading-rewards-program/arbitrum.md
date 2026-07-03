# Arbitrum

Am 31. August 2023 wird PancakeSwap Perpetuals das V2-Handelsprämien-Programm auf Arbitrum starten. Nutzer, die [ALP im CAKE Syrup Pool](https://pancakeswap.finance/pools?chain=arb) auf Arbitrum staken, können Boost-Multiplikatoren genießen. Darüber hinaus gibt es keine Sperrfrist für im Rahmen dieses Programms verdiente Prämien. Nutzer können ihre USDC-Prämien jederzeit einlösen. Details sind wie folgt:

Startzeit: 31. August 2023, 08:00 Uhr (UTC)

Aktivitätszeitraum (Epoche): Jeden Donnerstag von 08:00:00 UTC bis zum nächsten Donnerstag 07:59:59, Dauer 1 Woche.

Zeitpunkt der Prämienausschüttung: Jeder Zyklus läuft täglich von 00:00 Uhr (UTC) bis 23:59 Uhr (UTC). Prämien werden jeden Donnerstag gegen 08:00 Uhr (UTC) ausgegeben. Nachdem die Stufe des Nutzers aktualisiert wurde, werden Prämien berechnet und ausgeschüttet. Nutzer müssen ihre Prämien innerhalb von 30 Tagen nach der Ausgabe einlösen. Falls sie dies nicht tun, widerruft die Plattform die Prämien.&#x20;

Prämienbetrag: Für die ersten 5 Wochen 25 % der Handelsgebühren (in USDC). Dieser Prämienpool wird dann entsprechend den Stufen ausgeschüttet.

Aktivitätsregeln: Nutzer, die auf PancakeSwap Perpetuals V2 auf Arbitrum handeln, qualifizieren sich für den Prämienpool.

### Stufenübersicht

Jeden Donnerstag um 08:00:00 UTC berechnen wir die Handelsdaten vom letzten Donnerstag 08:00:00 UTC bis zu diesem Donnerstag um 07:59:59 und aktualisieren dann die Stufe des Nutzers gemäß den Stufenregeln. Die Stufenregeln sind wie folgt (Konfiguration wird unterstützt):

<table><thead><tr><th width="161">Stufe</th><th width="249.33333333333331">Beschreibung</th><th>Gewichtung</th></tr></thead><tbody><tr><td>Diamond</td><td>Handelsvolumen der Epoche >=1 Mio. USD</td><td>5</td></tr><tr><td>Gold</td><td>Handelsvolumen der Epoche >=500.000 USD</td><td>3</td></tr><tr><td>Silver</td><td>Handelsvolumen der Epoche >=250.000 USD</td><td>1</td></tr></tbody></table>

**Hinweis: Die Stufenkriterien und Gewichtungen können sich je nach Pool-Liquidität und gesamter Handelsaktivität auf der Plattform ändern.**

Prämien werden gleichmäßig auf alle Nutzer verteilt, die sich für eine bestimmte Stufe qualifizieren.

### Berechnungsformel für Handelsprämien:&#x20;

Am Ende jedes Handelsprämien-Zyklus wird das effektive Handelsvolumen des Nutzers in diesem Zyklus berechnet, um die Gewichtung und den Betrag der USDC-Prämien zu bestimmen.

Die Formel für die Anzahl der spezifischen Prämien lautet: r = min{R \* W/Sum(Wi), R \* 20%\}, die Parameter sind wie folgt:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Menge der USDC-Prämien, die der Nutzer für die aktuelle Epoche erhalten kann</td></tr><tr><td>R</td><td>Die Prämie der aktuellen Epoche: R=(USDC-Wert der ETH-Gebühr + USDC-Wert der DAI-Gebühr + USDC-Wert der BTC-Gebühr + USDC-Gebühr)*0,25; davon müssen bei der Abrechnung 1 % Swap-Gebühr abgezogen werden – beispielsweise beträgt bei einer wöchentlichen ETH-Gebühr von 1 und einem ETH-Preis von 2.000 der USDC-Wert der ETH-Gebühr = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Der der Stufenstufe des Nutzers entsprechende Gewichtungswert</td></tr><tr><td>Sum(Wi)</td><td>Gesamtgewichtungswert aller Nutzer. Wi steht für die Gewichtung eines einzelnen Nutzers, und sum(Wi) für die Summe aller Gewichtungswerte.</td></tr></tbody></table>

* Der maximale Einnahmenanteil pro Nutzer ist auf 20 % der für das Programm reservierten Einnahmen begrenzt.

Geschäftsbedingungen

* Aufgrund der unterschiedlichen Handelsgebühren für jedes Handelspaar auf V2 können die erhaltenen Prämien der Nutzer variieren, auch wenn deren effektive Handelsvolumina identisch sind.
* Die für jeden Zyklus auszuschüttenden Prämien werden in der folgenden Vertragsadresse gespeichert:&#x20;
* PancakeSwap/ApolloX behält sich das Recht der abschließenden Auslegung dieser Aktivität vor.



Risikohinweis: Der Handel mit Krypto-Futures birgt erhebliche Risiken. Alle Handelsaktivitäten erfolgen nach eigenem Ermessen und auf eigenes Risiko. Die hier enthaltenen Informationen sind nicht als Finanz- oder Anlageberatung von PancakeSwap/ApolloX zu verstehen. PancakeSwap/ApolloX haftet nicht für Verluste, die aus der Nutzung von PancakeSwap/ApolloX entstehen könnten.

<br>
