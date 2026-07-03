# 🎟️ Lotterie

Das Spielen der PancakeSwap Lotterie gibt Ihnen die Chance, riesige CAKE-Preise zu gewinnen! Es ist einfach, fair, und Sie können so oft teilnehmen, wie Sie möchten, solange Sie das CAKE zum Kauf eines Tickets haben.

[Smart Contract anzeigen](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Details:**

* Kosten eines Lotterie-Tickets: \~5 USD in CAKE.
* Individuelle Begrenzung pro Nutzer: Keine Gesamtbegrenzung, aber es können jeweils nur 100 Tickets auf einmal gekauft werden.
* Beim Kauf eines Tickets erhalten die Nutzer eine zufällige 6-stellige Kombination, wobei jede Ziffer zwischen 0 und 9 liegt, z. B. „1-9-3-2-0-4". Stimmen Sie die Zahlen von links ab, um Preise zu gewinnen – je mehr Zahlen übereinstimmen, desto größer der Preispool, an dem Sie teilhaben.
* Die Lotterie verwendet die VRF-Implementierung von Chainlink für echte, sichere Zufälligkeit.

## Ticketpreise und Mengenrabatt

Die Lotterie-Ticketpreise werden zu Beginn jeder neuen Lotterierunde festgelegt und orientieren sich an 5 USD (können bei plötzlichen Preisschwankungen leicht abweichen).

Der Kauf mehrerer Lotterie-Tickets auf einmal gewährt einen Mengenrabatt. Sie können bis zu 100 Tickets in einem Kauf erwerben, wobei der Rabatt bei 2 Tickets beginnt und bei 100 Tickets auf 10 % ansteigt.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%20PM.png)

## **So gewinnen Sie**

Stimmen Sie die Zahlen **von der linken Seite Ihres Tickets** mit den am Ende einer Lotterierunde gezogenen Gewinnzahlen ab.

* Schon die Übereinstimmung der ersten Zahl bringt Ihnen einen kleinen Preis.&#x20;
* Je mehr Zahlen übereinstimmen, desto größer der Preispool, an dem Sie teilhaben.

## **‌**Preisberechtigung

‌Jedes Ticket enthält insgesamt sechs Lotteriekugeln, von 0 bis 9. Um zu gewinnen, müssen Ihre Zahlen mit den gezogenen Zahlen in derselben Reihenfolge wie die Lotteriekugeln übereinstimmen, beginnend von links auf dem Ticket. Zum Beispiel:

Gezogene Zahlen

![Gezogene Zahlen](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png)

Ihre Ticket-Zahlen

![Ihr Ticket A](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png)

Im obigen Beispiel stimmen bei Ticket A fünf der Ticket-Zahlen mit denselben gezogenen Zahlen in genau der gleichen Reihenfolge überein – alle außer der vierten.

Da die vierte Stelle jedoch **nicht** mit der gezogenen Zahl übereinstimmt, zählen nur die ersten drei Stellen als übereinstimmend. Dies würde einen Preis für „Erste 3 übereinstimmend" gewinnen.

![Ihr Ticket B](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png)

Beispiel Ticket B. Hier ein Pechvogel. Obwohl die letzten fünf Stellen übereinstimmen, stimmt die erste Stelle nicht überein, sodass dieses Ticket überhaupt nichts gewinnt.

Sie nehmen nur an Preisen aus der höchsten Preiskategorie teil, für die Sie berechtigt sind. Ein Ticket, das die ersten drei Zahlen trifft, ist nur für Preise der Dreier-Kategorie berechtigt, nicht für die Einer- oder Zweier-Kategorien.

**Bitte beachten: Die Stellen müssen in der richtigen Reihenfolge übereinstimmen, von links nach rechts.**

## Preisaufteilung zwischen den Preiskategorien

‌Nachdem eine Runde gezogen wurde und Tickets mit übereinstimmenden Zahlen ermittelt sind, werden die Preise vergeben. Der von jedem Ticket gewonnene Betrag hängt davon ab, wie viele andere Tickets in der gleichen Preiskategorie gewonnen haben.

‌Wenn Sie beispielsweise das einzige Ticket haben, das drei Zahlen in der richtigen Reihenfolge getroffen hat, und der vorbestimmte Anteil des Preispools für Ihre Kategorie 2000 CAKE beträgt, erhalten Sie die vollen 2000 CAKE.

‌Wenn jedoch Sie und drei weitere Personen drei Zahlen in der richtigen Reihenfolge treffen, würden die 2000 CAKE auf die vier Gewinner-Tickets aufgeteilt, sodass Sie 500 CAKE erhalten würden.

Siehe [Lotterie FAQ für eine Aufschlüsselung der Preise](lottery-faq.md#how-are-prizes-broken-down-between-brackets) für jede Kategorie.
