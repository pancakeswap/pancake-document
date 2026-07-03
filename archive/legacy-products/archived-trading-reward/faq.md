---
description: Trading-Reward-FAQ
---

# FAQ

{% hint style="danger" %}
[Archiviert] Trading Reward – Stand 23. August 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Allgemein

#### Warum wurde mein Handelsvolumen nicht erfasst?

* Volumenzahlen brauchen Zeit zur Aktualisierung und können SubGraph-Verzögerungen unterliegen. Bitte prüfen Sie zu einem späteren Zeitpunkt erneut.
* Ihr Handel muss über das **genaue** auf der [Trading-Reward-Seite](https://pancakeswap.finance/trading-reward#rewards-breakdown) hervorgehobene Handelspaar geleitet werden, einschließlich der Gebührenklasse. Sehen Sie sich [dieses Tutorial](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) an, um Ihre Handelsrouten einzusehen.
* Nur V3-Handelspaare sind für dieses Programm berechtigt.
* Bitte verwenden Sie dieselbe Wallet-Adresse, die für das Trading-Reward-Programm sowohl auf Ethereum als auch auf der BNB Chain berechtigt ist.
* Wenn Ihr Handelsvolumen innerhalb eines Paares zu gering ist, sind Sie möglicherweise nicht berechtigt, Belohnungen zu beanspruchen.
* Die Nutzung von Drittanbieter-Handelsaggregatoren kann dazu führen, dass Trades über andere Liquiditätsanbieter geleitet und nicht erfasst werden.

#### Warum habe ich viel gehandelt, aber nur sehr geringe Belohnungen erhalten?

Der Betrag der Handelsbelohnung basiert auf der in diesen Trades gezahlten Handelsgebühr.

Wenn Ihre Trades über Paare mit einer niedrigen Gebührenklasse, zum Beispiel 0,01 %, geleitet werden, zahlen Sie eine sehr geringe Gebühr für Ihren Trade. Daher wird die Anzahl der Belohnungen entsprechend geringer.

## Top-Traders-Kampagne

#### Muss ich für die gesamte Zeit innerhalb des erforderlichen Rankings bleiben, um die Kampagne zu gewinnen?

Nein, Sie müssen nur **am Ende der Kampagne** ein höheres Ranking als das erforderliche haben. Es wird jedoch empfohlen, ein höheres Ranking zu erzielen und beizubehalten. Und stellen Sie sicher, dass Sie regelmäßig nachsehen, um sicherzustellen, dass Sie nicht aus dem erforderlichen Ranking herausfallen.

#### Auf welcher Grundlage wird das Ranking erstellt?

Das Ranking basiert auf der Anzahl der Belohnungen, die jeder Nutzer durch den Handel ansammelt. Der Belohnungsbetrag entspricht einem festen % der von ihnen in den Trades gezahlten Handelsgebühren.

## CAKE-Stakers-Kampagne

#### Meine Adresse war für die vorherige Kampagne berechtigt. Warum ist sie es für die neueste nicht?

Jede Kampagne hat ihre eigenen Berechtigungsanforderungen, wie den Mindestschwellenwert für den veCAKE-Betrag zum Snapshot-Zeitpunkt.

Außerdem ist der Snapshot-Zeitpunkt auf den Endzeitpunkt jeder Kampagne festgelegt. Da veCAKE mit der Zeit abnimmt, kann Ihr veCAKE-Guthaben für zukünftige Kampagnen unter den Schwellenwert fallen.

Möglicherweise müssen Sie Ihren veCAKE erhöhen. Folgen Sie einfach den Anweisungen auf der Seite.

#### Warum wird mir mitgeteilt, dass ich zusätzliche Belohnungen habe, die nicht beansprucht werden können?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

Der veCAKE-Betrag zum Snapshot-Zeitpunkt bestimmt den maximalen Betrag an Belohnungen, den Sie aus der Kampagne verdienen können. Sehen Sie sich die Fußnote aus dem Abschnitt "Maximale Belohnungsgrenze" an.

Solange eine Kampagne aktiv ist, können Sie Ihren veCAKE erhöhen und diese Grenze jederzeit erhöhen.

#### Was ist "veCAKE zum Snapshot-Zeitpunkt"?

veCAKE nimmt mit der Zeit allmählich ab, da die verbleibende Sperrdauer abnimmt. Daher ist ähnlich wie IFO iCAKE ein Snapshot-veCAKE-Guthaben — das veCAKE-Guthaben zu einem bestimmten Zeitpunkt, das statisch ist — besser als Qualifikationsmetrik geeignet.

Im Trading Reward bezieht sich der Snapshot-Zeitpunkt auf das Ende jeder Kampagne. Daher bedeutet Ihr "veCAKE-Guthaben zum Snapshot-Zeitpunkt" "Ihr veCAKE-Guthaben zum Kampagnenendzeitpunkt".

#### Wie steht "veCAKE zum Snapshot-Zeitpunkt" mit der Kampagne in Zusammenhang?

* Ihre Anzahl von veCAKE-Guthaben zum Snapshot-Zeitpunkt ist höher als der erforderliche Schwellenwert.
* Der maximale Betrag an Belohnungen, den Sie verdienen können, ist mit y % Ihres veCAKE-Guthabens zum Snapshot-Zeitpunkt verknüpft.

Zum Beispiel:

1. Alice hat am Tag 1 300 CAKE für 2 Jahre (104 Wochen) gesperrt. Am Tag 1 hat Alice ein veCAKE-Guthaben von `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149`.
2. Eine Trading-Reward-Kampagne wird am Tag 1 mit einem Schwellenwert von 100 veCAKE und einer 1-Prozent-Belohnungsgrenze gestartet. Die Kampagne endet in 30 Tagen.
3. Nach 30 Tagen hat Alices Position eine verbleibende Sperrdauer von ca. 99,71 Wochen und daher ein veCAKE-Guthaben von `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Daher hat Alice für diese Kampagne `143` veCAKE zum Snapshot-Zeitpunkt.
5. 143 ist größer als 100, also ist Alice für die Kampagne berechtigt. Sie kann mit dem Handel berechtigter Paare beginnen, um Handelsbelohnungen zu verdienen.
6. Mit einer 1-Prozent-Belohnungsgrenze beträgt der maximale CAKE-Betrag, den Alice aus dieser Kampagne verdienen kann, `143 * 1% = 1,43` CAKE.
7. Alice kann ihr veCAKE jederzeit vor Ende der Kampagne erhöhen, entweder durch das Sperren von mehr CAKE oder durch die Verlängerung ihrer Position.

#### Wie kann ich mein veCAKE zum Snapshot-Zeitpunkt während der Kampagne überprüfen?

Sie können dies auf der Trading-Reward-Seite überprüfen.

Die Seite warnt Sie, wenn Ihr veCAKE zum Snapshot-Zeitpunkt unter den Schwellenwert fällt oder Ihre Belohnungen derzeit davon begrenzt werden.

In diesen Fällen können Sie auf die Schaltfläche "veCAKE erhöhen" klicken, um Ihr veCAKE zu erhöhen, ohne die Seite zu verlassen.

#### Kann ich mein veCAKE während der Kampagne erhöhen?

Ja, Sie können Ihr veCAKE jederzeit vor Ende der Kampagne erhöhen. Ihr "veCAKE zum Snapshot-Zeitpunkt" wird entsprechend aktualisiert.
