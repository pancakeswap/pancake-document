# So verwenden Sie TWAP

## Was ist TWAP?

TWAP (Time-weighted Average Price) ist ein gängiger Ordertyp aus dem CeFi-Bereich, der eine Order in kleinere Trade-Größen aufteilt und diese in regelmäßigen Abständen ausführt. Das Hauptziel einer TWAP-Order ist es, den Preiseinfluss der Order zu reduzieren. Es kann auch nützlich sein, wenn ein Nutzer eine Dollar-Cost-Averaging-Strategie (DCA) umsetzen und einen bestimmten Token nach einem regelmäßigen Zeitplan kaufen möchte (z. B. einmal im Monat).

Daher eignet sich TWAP am besten, wenn die Ordergröße im Vergleich zur verfügbaren Liquidität groß ist oder wenn ein Nutzer eine Phase hoher Preisvolatilität ohne klaren Auf- oder Abwärtstrend erwartet.

## So richten Sie eine TWAP-Order ein

1. Gehen Sie zur Swap-Seite und wählen Sie die TWAP-Order-Option, indem Sie auf „TWAP" klicken.
2. Wählen Sie die „Von"- und „Zu"-Token und geben Sie den Betrag ein, den Sie handeln möchten.
3. Die Oberfläche ermöglicht sowohl dTWAP-Market-Orders, die alle Trades zum verfügbaren Marktpreis ausführen, als auch dTWAP-Limit-Orders, die einzelne Trades nur ausführen, wenn sie innerhalb des vom Nutzer festgelegten Preislimits liegen. \
   In diesem Beispiel haben wir gewählt, die TWAP-Orders zum Marktpreis auszuführen.
4. Als nächstes legen wir die TWAP-Parameter fest. Es gibt 3 Hauptparameter, die die Effektivität der dTWAP-Order steuern:
   1. Gesamtanzahl der Trades: Ermöglicht dem Nutzer, die Anzahl der einzelnen Trades anzugeben, in die seine Order aufgeteilt wird. Der Schieberegler der Oberfläche beginnt mit 1 Trade und ermöglicht dem Nutzer, die Anzahl der einzelnen Trades zu erhöhen, oder der Nutzer kann die Gesamtanzahl der Trades direkt in das Eingabefeld eingeben.\
      Nutzer sollten beachten, dass bei der Festlegung dieses Parameters ein gewisser Kompromiss besteht: Mehr Trades bedeuten kleinere individuelle Trade-Größen, was einen geringeren Preiseinfluss bedeutet. Mehr Trades bedeuten jedoch auch mehr Transaktionen und höhere Gesamtgasgebühren.&#x20;
   2. Trade-Intervall: Legt den Zeitabstand zwischen jedem einzelnen Trade fest. Die Oberfläche beginnt mit dem minimal erlaubten Wert (2 Minuten), der die minimale Zeit für das Taker-Bieterverfahren und die Block-Abwicklung zwischen den einzelnen Teilen lässt. Der Nutzer kann es auf eine beliebige gewünschte Dauer einstellen. Ein Trade wird niemals ausgeführt, bevor diese Zeit nach dem vorherigen Trade verstrichen ist.\
      Nutzer sollten auch bei der Festlegung dieses Parameters Bedacht walten lassen: Längere Intervalle würden Arbitrageuren ein längeres Zeitfenster geben, um etwaige Preisdiskrepanzen in den betroffenen Pools zu schließen und die Reserven wieder ins Gleichgewicht zu bringen (auf Augenhöhe mit dem Spotpreis). Dies würde jedoch die Ausführungszeit der Order verlängern und dem endgültigen Ausführungspreis Unsicherheit hinzufügen, insbesondere in Zeiten erhöhter Volatilität.
   3. Maximale Dauer: Die maximale Zeit, in der alle einzelnen Trades der vollständigen dTWAP-Order ausgeführt werden können. Nach dieser Frist verfällt der Trade, unabhängig von den tatsächlich ausgetauschten Beträgen.\
      Beachten Sie, dass bei Limit Orders möglicherweise nicht alle Teilorders ausgeführt werden, je nachdem, ob der Preis innerhalb der festgelegten Parameter bleibt. \
      Die empfohlene Standarddauer wird berechnet, indem die Anzahl der Intervalle mit dem Trade-Intervall multipliziert und dieser Betrag dann verdoppelt wird, um als Puffer ausreichend Zeit für Onchain-Aktivitäten zu ermöglichen. (Beachten Sie, dass eine Dauer, die kürzer als der obige Standard ist, zu einer teilweise ausgeführten Order führen kann.)

Wie zu sehen ist, bieten diese Parameter erhebliche Flexibilität bei der Anpassung jeder Order unter Berücksichtigung von Faktoren wie Marktbedingungen, aktuellen Gasgebühren usw.

8. Klicken Sie auf „Order platzieren". Überprüfen Sie Ihre Orderdetails, akzeptieren Sie den Haftungsausschluss und klicken Sie auf „Order bestätigen".
9. Sobald die Transaktion verarbeitet wurde, können Sie den Status Ihrer Order im Bestellverlauf unter „Offene Orders" einsehen.
10. Offene Orders können jederzeit storniert werden, indem Sie die Order erweitern und auf die Schaltfläche „Order stornieren" klicken.

Zu berücksichtigende Punkte

* Orders werden in kleineren Trades über einen bestimmten Zeitraum ausgeführt und unterliegen Marktbedingungen und anderen Risiken.
* Ihr Trade kann zu einem Preis ausgeführt werden, der erheblich vom aktuellen Marktpreis abweicht (jedoch nicht schlechter als Ihr Limitpreis, falls Sie einen festgelegt haben), was zu erheblichen Verlusten führen könnte. Wenn der verfügbare Marktpreis schlechter als der von Ihnen festgelegte Limitpreis ist, werden einige der Trades Ihrer Order möglicherweise nicht ausgeführt, was zu einer teilweise ausgeführten Order führt.
* Die Trades basieren auf einem dezentralen Protokoll, das Off-Chain-Taker verwendet, die miteinander konkurrieren, um Orders auszuführen. Diese Taker sind berechtigt, eine Gebühr zu verlangen, die das Protokoll für den gewinnenden Taker von den Ausgabe-Token abzieht.&#x20;
* Taker können Gasgebühren für Ihre Transaktionen berücksichtigen, wenn sie ihre Gebühren festlegen, was zu Schwankungen bei den Gebührenbeträgen führen kann.

<br>
