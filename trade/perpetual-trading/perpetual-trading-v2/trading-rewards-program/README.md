---
description: ApolloX wird das Handelsprämien-Programm auf V2 starten
hidden: true
---

# Handelsprämien-Programm

### Programmübersicht

Die Details sind wie folgt:

Aktivitätszeitraum: Die Daten variieren von Zyklus zu Zyklus und für verschiedene Chains.

Zeitpunkt der Prämienausschüttung: Jeder Zyklus läuft täglich von 00:00 Uhr (UTC) bis 23:59 Uhr (UTC). Prämien werden am nächsten Tag gegen 03:00 Uhr (UTC) ausgegeben. Nutzer müssen ihre Prämien innerhalb von 30 Tagen nach der Ausstellung einlösen. Falls sie dies nicht tun, widerruft die Plattform die Prämien.&#x20;

Prämienbetrag: Gedeckelt bei 15.000 USD in APX täglich.

Aktivitätsregeln: Nutzer, die auf V2 handeln, erhalten Anteile aus einem Prämienpool. Nutzer, die APX in der DAO staken, um ein veNFT zu erhalten, genießen Boost-Multiplikatoren entsprechend dem aus dem veNFT berechneten Power-Wert.&#x20;

| Power-Wert                | Boost-Multiplikator |
| ------------------------- | ------------------- |
| 50.000 < Power =<100.000  | 1,5                 |
| 100.000 < Power =<300.000 | 2                   |
| Power > 300.000           | 2,5                 |

Berechnungsformel für Handelsprämien:&#x20;

Am Ende jedes Handelsprämien-Zyklus werden die effektiven Handelsgebühren und der Staking-Betrag des Nutzers in diesem Zyklus berechnet, um die Gewichtung und den Betrag der APX-Prämien zu bestimmen. Die Formel lautet wie folgt:

r = R\*W / sum(Wi)



Parameter:

| r       | APX-Prämie des Nutzers für diesen Zyklus                                                                                                                                                                                                                                                                                                        |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Bestimmt durch den V2-Handelsgebührenbeitrag des Nutzers vom Vortag und den aktuellen APX-Token-Preis                                                                                                                                                                                                                                           |
| W       | <p>Individueller Gesamtgewichtungswert W=f*w, wobei;</p><p>f die effektiven Handelsgebühren des Nutzers in diesem Zyklus bezeichnet, die in USD umgerechnet werden.</p><p>w ist der Boost-Multiplikator, den der Nutzer in diesem Zyklus durch das Staking von APX in der DAO erhält. (Weitere Informationen finden Sie in der obigen Tabelle.)</p> |
| sum(Wi) | Der Gesamtwert aller Nutzer. Wi steht für den Wert eines einzelnen Nutzers, und sum(Wi) für die Summe aller Nutzerwerte.                                                                                                                                                                                                                        |

&#x20;

Die Berechnungsformel für R lautet wie folgt:

R=Min(Dollar-Wert-Multiplikator \* Handelsgebühr, Dollar-Wert-Obergrenze) / Max(APX letzter Preis, APX Preisuntergrenze)

* Dollar-Wert-Multiplikator: 0,70 in dieser Epoche
* Handelsgebühr: Wert der V2-Gebühreneinnahmen vom Vortag in USD umgerechnet
* Dollar-Wert-Obergrenze: 15.000 gemäß Systemkonfiguration
* APX letzter Preis: Basierend auf dem aktuellen APX-Token-Preis
* APX Preisuntergrenze: 0,04 in dieser Epoche

Geschäftsbedingungen

* Nach dem Ende jedes Zyklus kann ApolloX die Programmregeln entsprechend dem Nutzerfeedback und den Marktbedingungen anpassen. Prämien werden nicht linear ausgegeben.
* Während der Aktivität wird die Plattform den Prozentsatz der V2-Handelsgebühreneinnahmen, der in den ALP-Pool fließt, von 50 % auf 20 % reduzieren. Die verbleibenden 30 % werden für den Rückkauf von APX verwendet.
* Aufgrund der unterschiedlichen Handelsgebühren für jedes Handelspaar auf V2 können die erhaltenen Prämien der Nutzer variieren, auch wenn deren effektive Handelsvolumina identisch sind.
* Die für jeden Zyklus auszuschüttenden Prämien werden in der folgenden Vertragsadresse gespeichert: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX behält sich das Recht der abschließenden Auslegung dieser Aktivität vor.

Risikohinweis: Der Handel mit Krypto-Futures birgt erhebliche Risiken. Alle Handelsaktivitäten erfolgen nach eigenem Ermessen und auf eigenes Risiko. Die hier enthaltenen Informationen sind nicht als Finanz- oder Anlageberatung von ApolloX zu verstehen. ApolloX haftet nicht für Verluste, die aus der Nutzung von ApolloX entstehen könnten.

### Prämien einlösen

Da das Handelsprämien-Programm von unseren Partnern bei ApolloX veranstaltet wird, gehen Sie bitte wie folgt vor, um Ihre Prämie einzulösen:\
\
Schritt 1: Gehen Sie zu unserer [PancakeSwap Perpetuals-Seite](https://perp.pancakeswap.finance/en/futures/v2/).

Schritt 2: Klicken Sie oben auf der Seite auf die Registerkarte „Trading Reward (V2)".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Schritt 3: Sie werden auf die ApolloX-Prämieneinlöseseite weitergeleitet, um Ihren aktuellen Prämien-Status zu überprüfen. Klicken Sie während des Aktivitätszeitraums auf „Einlösen", um Ihre Prämien zu beanspruchen.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
