# 📈 Analysen (Info-Seite)

## Info-Seite&#x20;

Rufen Sie PancakeSwaps native Analyse-Seite hier auf: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Alle Kerndaten werden vom internen PCS-Indexer bezogen, der seinerseits Daten aus Ereignissen erfasst, die beim Aufruf des Contracts ausgelöst werden.&#x20;

Für die Datumsdimension im internen Indexer von PancakeSwap verwenden wir internationale Standardzeit (UTC) für tägliche Statistiken. Wenn die horizontale Achse im Dashboard ein Datum anzeigt, entspricht dieses daher dem Datum in internationaler Standardzeit (UTC).<br>

## Kernkennzahlen

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volumen (Handelsvolumen):** Wir überwachen die Tagesdaten für jedes Handelspaar und die täglichen Handelsdaten für jeden Token. Das tägliche Handelsvolumen wird berechnet, indem das Handelsvolumen jedes Tokens für den Tag mit seinem Preis multipliziert wird.

**Total Value Locked:** Alle Pools werden vom internen Indexer abgerufen und der Wert reserve\_usd oder total\_value\_locked\_usd aus jedem Pool ausgelesen.&#x20;

**Preis:** Im internen PCS-Indexer verwenden wir mehrere Basis-Pools zur Berechnung von USD-bezogenen Preisen. Der primäre Pool ist der Stablecoin-Handelspool, bei dem wir den Handelspool mit dem höchsten Volumen als Basis-Pool verwenden und den USD-Preis des Stablecoins basierend auf dem Handelsvolumengewicht berechnen. Zusätzlich wird auch der Handelspool des Basis-Tokens zum Chain-Stablecoin als Basis-Pool berücksichtigt, um den USD-Preis zu liefern.

_Token, die nicht auf der Whitelist stehen oder nicht mit Token auf der Whitelist gepaart sind, werden von diesen Berechnungen ausgeschlossen._

<br>
