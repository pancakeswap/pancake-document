# Lotterie FAQ

## Was passiert, wenn es keine Gewinner gibt?

Wenn CAKE aus den Preispools nicht gewonnen wird, geht er nicht verloren! Nicht beanspruchte CAKE werden auf die nächste Lotterierunde übertragen.

## Mein Ticket stimmt mit mehreren Zahlen überein, aber ich kann keinen Preis einfordern

Tickets sind nur dann für Preise berechtigt, wenn die Zahlen von links nach rechts übereinstimmen. Lesen Sie die [Lotterie v2-Dokumentation](./) für eine ausführliche Erklärung.

## Wie unterscheidet sich Lotterie v2 von Lotterie v1?

Lotterie v2 verteilt Preise breiter als Lotterie v1. Es gibt jedem Ticket eine 1-zu-10-Chance, die erste Zahl zu treffen, was bedeutet, dass mehr Tickets zumindest einen kleinen Preis gewinnen. Außerdem gibt es 6 (statt 4) Zahlen, die sequenziell übereinstimmen müssen, um den größten Preis zu gewinnen.

Insgesamt bedeutet dies, dass mehr Tickets einen Preis gewinnen können, aber der größte Jackpot seltener gewonnen wird, was zu enormen Top-Preispools führt!

**Lotterie v2 führt ein:**

* günstigere Ticketpreise (\~5 USD in CAKE pro Ticket), die nicht stark mit dem CAKE-Preis schwanken
* Mengenrabatte beim Ticketkauf
* 6 abgestufte Preispool-Kategorien mit steigenden Preispools, je mehr Zahlen übereinstimmen
* manuelle Zahlenwahl (optional), sodass Nutzer ihre Glückszahlen verwenden können
* [Chainlinks Implementierung von VRF](https://docs.chain.link/docs/chainlink-vrf/) für echte, sichere Zufälligkeit
* insgesamt niedrigere Gebühren (weitere Informationen [weiter unten auf dieser Seite](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets))

[Mehr über die Funktionen, das Gameplay und die Preise von Lotterie v2 erfahren](./)

## Wie werden die Preise zwischen den Kategorien aufgeteilt?

Der Preispool jeder Kategorie ist ein Anteil der gesamten CAKE jeder Lotterierunde.

* | Kategorie (Zahlen in richtiger Reihenfolge getroffen) | CAKE-Anteil |
  | ----------------------------------------------------- | ----------- |
  | Erste 1 Zahl                                          | 2%          |
  | Erste 2 Zahlen                                        | 3%          |
  | Erste 3 Zahlen                                        | 5%          |
  | Erste 4 Zahlen                                        | 10%         |
  | Erste 5 Zahlen                                        | 20%         |
  | Erste 6 Zahlen                                        | 40%         |
  | Verbrennung                                           | 20%         |

## Kann ich meine Tickets zurück in CAKE tauschen?

Nein, nach dem Kauf können Sie Ihr Ticket nicht mehr in CAKE zurückkonvertieren.

## Muss ich meinen Preis manuell einfordern, wenn ich gewinne?

Ja, Sie müssen auf der Lotterie-Seite unter „Sind Sie ein Gewinner?" auf die Schaltfläche **Jetzt prüfen** klicken.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## Wie oft findet die Lotterie statt?

Eine Lotterieziehung findet alle 12 oder 36 Stunden statt. Eine Lotterieziehung findet täglich statt, abwechselnd um 0 Uhr UTC und 12 Uhr UTC; die nächsten Runden nach den 0-Uhr-UTC-Runden finden nach 36 Stunden statt, die nächsten Runden nach den 12-Uhr-UTC-Runden nach 12 Stunden.

![Lotterie-Einspritzzeitplan](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## Welche Transaktionsgebühr zahle ich beim Kauf von Tickets?

Jeder Ticketkauf ist eine Transaktion. Der Kauf eines einzelnen Tickets in einem Lotterie-Kaufvorgang kostet den normalen Gebührenbetrag für eine Transaktion.

Der Kauf von mehr Tickets in diesem Vorgang erhöht jedoch die Gebühr. Der Kauf von 100 Tickets statt 1 multipliziert die Gebühr nicht mit 100, kann den Gebührenbetrag aber 5–6-mal erhöhen (was jedoch variiert).

## Wie funktioniert der Mengenrabatt?

Der Mengenrabatt belohnt den Kauf größerer Mengen an Tickets mit einem gestaffelten Rabatt. Wenn Sie nur 2 Tickets kaufen, ist der Rabatt vernachlässigbar, summiert sich aber schnell, wenn Sie die Anzahl der Tickets in einer Transaktion erhöhen.

Der Rabatt gilt nur für jede Transaktion bis zu 100 Tickets. Der Rabatt wird nicht auf die nächste Transaktion oder nächste Runde übertragen.

## Warum kann ich nur 100 Tickets kaufen?

Sie können in einem Kauf maximal 100 Tickets erwerben, aber Sie können mehrere Käufe tätigen. Nichts hindert Sie daran, nach Ihren ersten 100 weitere Tickets zu kaufen.

## Wenn ich manuell zwei oder mehr Tickets mit denselben Zahlen erstelle und diese gewinnen, bin ich für jeden Preis pro Ticket berechtigt?

Ja, jedes Ticket wird als separater Lotterieeintrag behandelt. Beachten Sie jedoch, dass die Preise nicht 1:1 sind, da jedes Gewinner-Ticket, das Sie besitzen, den jeweiligen Anteil an den Gesamtpreisen der Kategorie verringert.

## Einspritzzeitplan: Wann wird CAKE zur Lotterie hinzugefügt?

Wenn Personen Tickets kaufen, wird das von ihnen ausgegebene CAKE dem Lotterietopf hinzugefügt. Zusätzlich werden 8.000 CAKE in regelmäßigen Abständen auch alle zwei Runden in den Lotterietopf eingespritzt (injiziert), über sieben Runden pro Woche, wie im oben abgebildeten Lotterie-Zeitplan dargestellt.
