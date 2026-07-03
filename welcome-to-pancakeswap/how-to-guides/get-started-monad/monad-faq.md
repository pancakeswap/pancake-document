# Monad FAQ

#### 1. Welche Gebührenstufen sind für PancakeSwap-Liquiditätspools verfügbar?

**Unterstützte Gebührenstufen:**

* Die folgenden Gebührenstufen sind für V3-Pools (konzentrierte Liquidität) verfügbar: `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Für V2-Pools wird nur die Gebührenstufe von 0,25% unterstützt

#### 2. Kann jeder einen Pool erstellen?

Ja. Die Pool-Erstellung ist genehmigungsfrei, mit einigen Ausnahmen:

* Es kann nur ein Pool für eine bestimmte **Tokenpaar + Gebührenstufen**-Kombination existieren (z.B. kann es nur einen WMON<>USDC-0,05%-Pool gleichzeitig geben)

#### 3. Wie lange dauert es, bis ein neu erstellter Pool angezeigt wird?

* Pools erscheinen in der Regel etwa **5 Minuten** nach der Erstellung in der Pool-Liste.
* Falls er nicht erscheint:
  * Verwenden Sie die **Suchleiste**, um ihn manuell zu finden.
  * Pools können aufgrund eines **niedrigen TVL** aus der Liste gefiltert werden.

#### 4. Warum zeigt mein Pool immer noch null als APR oder TVL?

Dies ist direkt nach der Erstellung eines neuen Pools zu erwarten:

* APR- und TVL-Daten werden erst angezeigt, sobald **mindestens ein Swap** im Pool stattgefunden hat.
* Nach einem Swap werden diese Kennzahlen innerhalb von etwa **15 Minuten** angezeigt.

#### **5. Warum schlagen meine Transaktionen manchmal fehl, wenn mein Wallet weniger als 10 MON hat?**

Monad hat eine Regel, dass jedes Konto einen **minimalen Sicherheitspuffer von 10 MON** halten muss. Wenn Ihr Guthaben niedrig ist und Sie zu viele Transaktionen zu schnell senden, kann das Netzwerk **keine neuen mehr akzeptieren**.

#### **6. Warum funktionieren die ersten 1–2 Transaktionen, aber die nächsten schlagen fehl?**

Monad verarbeitet Blöcke auf Basis einer leicht „veralteten" Ansicht Ihres Guthabens. Das bedeutet:

* Ihre **erste** Transaktion wird in der Regel problemlos verarbeitet.
* Ihre **zweite** wird möglicherweise ebenfalls durchgeführt.
* Wenn Sie jedoch **mehrere Transaktionen in kurzer Zeit** senden, geht das Netzwerk davon aus, dass Sie möglicherweise nicht genug MON haben, um alle Gasgebühren zu bezahlen.

Daher **blockiert** es die nächste Transaktion. Dies ist normal und Teil des Sicherheitssystems.

#### **7. Warum sind die Regeln bei Smart Accounts (Contract Wallets) strenger?**

Smart Accounts folgen **strengeren Regeln**:

* Sie müssen **immer** mindestens **10 MON** halten, während Contract-Code ausgeführt wird.
* Wenn Ihr Smart Account unter 10 MON liegt, kann die Transaktion **sofort zurückgesetzt werden**, auch wenn EOAs noch ein paar Transaktionen durchführen könnten.

Deshalb erfahren Smart-Account-Nutzer Fehler früher.

#### **8. Bedeutet das, dass ich Monad mit weniger als 10 MON nicht nutzen kann?**

Sie _können_ es dennoch nutzen, besonders mit einem normalen EOA – aber:

* Senden Sie nicht mehrere Transaktionen hintereinander.
* Warten Sie einige Blöcke zwischen den Transaktionen.
* Halten Sie etwas MON in Ihrem Wallet, um Probleme zu vermeiden.

#### **9. Wie vermeide ich diese Fehler?**

Einfache Tipps:

* Halten Sie wenn möglich **10 MON oder mehr** in Ihrem Wallet.
* Wenn Ihr MON-Guthaben niedrig ist, **verteilen Sie Ihre Transaktionen** (senden Sie sie nicht in schneller Folge).
* Smart-Account-Nutzer sollten **etwas mehr als 10 MON** halten, da Contract-Aufrufe zusätzliches Gas verbrauchen.
