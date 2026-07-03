# Swap FAQ

## Swap

### Was ist neu in Exchange V3?

* Konzentrierte Liquidität – Liquidität wird auf den am stärksten gehandelten Preisbereich konzentriert, was bedeutet:
  * Geringere Kursabweichung beim Handel für Händler
  * Potenziell höhere LP-Gebührenbelohnungen für Liquiditätsanbieter
* Eine flexible Handelsgebührenstruktur – Liquiditätsanbieter können bei der Erstellung von Liquiditätspaaren oder der Bereitstellung von Liquidität zwischen mehreren Handelsgebührenstufen wählen.
* Anpassbarer Preisbereich – Liquiditätsanbieter können auch wählen, für welche Preisspannen sie Liquidität bereitstellen möchten.
* Nicht-fungible Liquiditätspositionen – Jede Liquiditätsposition hat eine eindeutige ID entsprechend ihrer Konfiguration (z. B. Preisbereich). Daher können Sie mehrere Positionen mit demselben Handelspaar, aber unterschiedlichen Konfigurationen und Liquiditätsbeträgen erstellen und verwalten.
* Abwärtskompatibel – Exchange v3 nutzt auch die Legacy-v2- und StableSwap-Liquiditätspaare, um stets die beste Handelsroute bereitzustellen.
* Integrierte Limit Order – Erfahrene Nutzer können den neuen anpassbaren Preisbereich bei der Liquiditätsbereitstellung nutzen, um effektiv eine Limit Order zu erstellen, die alle Token in den gewünschten umwandelt, wenn der Preis das Ziel erreicht.



### Kann ich meine eigenen Token zu Exchange V3 hinzufügen?

Jeder kann Liquiditätspools erstellen, indem er Liquidität auf V3 hinterlegt.

Folgende Token werden jedoch derzeit **NICHT** unterstützt:

* Token mit Übertragungsgebühr
* Rebase-Token

Für diese Token fügen Sie bitte **KEINE** Liquidität bei Exchange V3 hinzu. Ihre Assets könnten in der Liquiditätsposition feststecken.



### **Warum wird meine Transaktion nicht ausgeführt?**

PancakeSwap ist eine DeFi-Anwendung, die mit der Wallet interagiert, um Onchain-Transaktionen für Swaps, die Erstellung von LPs, Staking in Farms und Pools usw. abzuwickeln.

**Gasgebühren**

Stellen Sie daher zunächst sicher, dass Sie **genügend BNB haben, um die Gasgebühr** der Onchain-Transaktionen zu bezahlen. Typischerweise schwanken Gasgebühren je nach Anzahl der Transaktionen in der Warteschlange; bei mehr Transaktionen kann eine höhere Gasgebühr erforderlich sein, um die Transaktion durchzusetzen. Auf BNB Smart Chain liegen die Gasgebühren typischerweise zwischen Cent und einem US-Dollar in BNB. Erfahren Sie mehr über [Gasgebühren hier](https://academy.binance.com/en/glossary/gas).

**Transaktionsgebühren**

Wenn Ihre Swap-Aktion immer noch nicht durchgeführt wird und ein Fehler angezeigt wird, der Sie zur Anpassung der Kursabweichung auffordert, sollten Sie prüfen, ob die Token, die Sie tauschen möchten, **Gebühren und Einschränkungen für Transaktionen** haben.

Es ist nicht ungewöhnlich, dass Token auf BNB Smart Chain eine **Transaktionsgebühr** in ihren Verträgen enthalten. Diese Gebühren können beispielsweise für den Burn oder die Finanzierung einer Treasury eines Fair-Launch-Projekts verwendet werden – so hat zum Beispiel dieser [APX-Token eine Steuer von 1 % auf jede Transaktion](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) zum Senden an eine Burn-Adresse, sodass mehr Transaktionen mehr Burning bedeuten und den APX-Token-Inhabern Wert zufügt.

Mit der Transaktionsgebühr – egal ob inklusiv (ein Teil des Swap-Betrags wird an eine andere Adresse als Ihre Adresse gesendet, sodass der Output geringer als erwartet für den geschätzten Input ist) oder exklusiv (ein zusätzlicher Transfer von Ihrer Adresse für zusätzliche Token, sodass der Input größer als erwartet für den geschätzten Output ist) – beeinflusst sie den Eingabe- und Ausgabebetrag, dem Sie beim Unterzeichnen der Transaktion zustimmen. In vielen Fällen kann die Transaktion die Eingabe- und Ausgabeanforderungen aufgrund der Steuer nicht erfüllen.

**Swappen mit Transaktionsgebühren**

Bevor Sie Token tauschen, besuchen Sie bitte deren Website, um zu verstehen, ob ein Transaktionsgebührenmechanismus vorhanden ist (oder _Steuer_, wie es viele Projekte nennen). Falls vorhanden, stellen Sie sicher, dass Sie eine Kursabweichung festlegen, die ausreicht, um die Transaktionsgebühr zu berücksichtigen – z. B. wenn eine Transaktionsgebühr von 5 % vorliegt, müssen Sie die Kursabweichung auf mindestens 5 % plus die normale Handelskursabweichung je nach Handelsbetrag und Token-Liquidität einstellen, etwa 5,5 %–6 %.

In einigen extremen Fällen, einschließlich einiger Betrugsversuche, haben manche Token sogar eine Sperre bei den meisten oder allen Onchain-Transfers oder erlauben nur bestimmten Adressen den Verkauf. In solchen Fällen ist es unmöglich, den Token erfolgreich zu tauschen. Informieren Sie sich über den Token, den Sie tauschen möchten, und achten Sie auf etwaige Gebühren und Einschränkungen!



### Verwendet die neue Swap-Oberfläche v2- oder StableSwap-Liquidität?

Ja. Das neue Swap v3 verwendet Liquidität von PancakeSwap v3, v2 und StableSwap, um die beste Handelsroute zu erhalten.



### Was ist Split Routing?

Bei Swap v3 kann Ihr Trade in mehrere Routen aufgeteilt werden, um den besten Kurs zu erzielen.

Um weitere Details darüber zu erhalten, wie Ihr Trade geroutet wird, tippen Sie auf die Schaltfläche „v" im Abschnitt „Route", um diesen zu erweitern und die Details anzuzeigen.

Mehr dazu erfahren Sie [hier](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Wie passe ich bestimmte Liquiditätsquellen an oder deaktiviere sie?

Das neue Swap v3 verwendet Liquidität von PancakeSwap v3, v2 und StableSwap, um die beste Handelsroute zu erhalten. Sie können jedoch bestimmte Liquiditätsquellen anpassen oder deaktivieren, wenn Ihr Trade nicht durch sie geroutet werden soll.

Klicken Sie beim Anzeigen einer Handelsroute auf die Schaltfläche „Routing anpassen". Oder klicken Sie auf das Zahnrad-⚙️-Symbol in der oberen rechten Ecke der Swap-Oberfläche und wählen Sie „Routing anpassen".

Im Pop-up „Routing anpassen" können Sie auswählen, welche Liquiditätsquelle Sie nutzen möchten, oder Multi-Hops vollständig deaktivieren.

Hinweis: Das Deaktivieren von Multi-Hops kann bei bestimmten Handelspaaren zu erhöhter Kursabweichung oder schlechteren Handelskursen führen. Gehen Sie vorsichtig vor.

Mehr dazu erfahren Sie [hier](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Liquidität

### Was sind Gebührenstufen und wie wähle ich die richtige aus?

Bei Exchange v3 können Sie bei der Bereitstellung von Liquidität zwischen verschiedenen Handelsgebühren (0,01 %, 0,05 %, 0,25 % und 1 %) für dasselbe Token-Paar wählen.

Beispielsweise könnte es für CAKE-BNB ein 0,25%-Paar geben, was bedeutet, dass für jeden Trade eine Handelsgebühr von 0,25 % anfällt. Einige Liquiditätsanbieter könnten jedoch wählen, Liquidität für ein CAKE-BNB-Handelspaar mit einer Gebühr von 0,05 % bereitzustellen, ein besseres Angebot zu machen und mehr Handelsvolumen anzuziehen.

Es gibt keine „richtige" Antwort auf die Wahl der Handelsgebührenkonfiguration. Es hängt von den Token im Handelspaar ab. Im Allgemeinen sollten volatile Token eine höhere Handelsgebühr haben, um den durch die Volatilität verursachten unbeständigen Verlust besser zu kompensieren. Andererseits haben Token wie Stablecoins kleinere Preisbewegungen und geringere unbeständige Verluste, daher sollte deren Handelsgebühr niedriger sein.

Bei der Auswahl eines Token-Paares wählt die Oberfläche „Liquidität hinzufügen" automatisch die beliebteste Gebührenstufe für Sie aus.



### Warum sind meine zwei hinterlegten Token nicht in USD gleichwertig?

Bei Exchange V3 werden die zugrunde liegenden Assets in einer Liquiditätsposition nicht immer einen gleichwertigen USD-Betrag haben. Dies hängt von den Preisbereichseinstellungen einer Position und dem aktuellen Preis des Paares ab.

Wenn Ihre Position außerhalb des Bereichs gerät, werden alle Token in ein einziges Asset umgewandelt. Außerdem können Sie Liquidität für einen Preisbereich bereitstellen, der den aktuellen Preis nicht abdeckt, und nur ein einziges Asset hinterlegen. Lesen Sie weiter, um mehr zu erfahren ⬇️



### Was passiert, wenn meine Liquiditätsposition außerhalb des Bereichs gerät?

Sie verdienen keine Handelsgebührenbelohnungen, wenn der aktuelle Preis außerhalb des in Ihrer Position definierten Preisbereichs liegt.

Darüber hinaus werden alle Token in ein einziges Asset umgewandelt, je nach Richtung der Preisbedingung.

Wenn beispielsweise eine Position von CAKE/BUSD mit einem Preisbereich von 3 BUSD pro CAKE bis 5 BUSD pro CAKE konfiguriert ist, werden alle Assets in der Position in BUSD umgewandelt, wenn der CAKE-Preis 5 BUSD pro CAKE oder mehr erreicht, und umgekehrt.

Bitte beachten Sie, dass Sie wieder Handelsgebührenbelohnungen erhalten, wenn der Preis wieder in den Bereich zurückkehrt. Es sind keine weiteren Maßnahmen erforderlich.



### Ist es immer besser, Liquidität mit einem kleineren Bereich bereitzustellen?

Die Bereitstellung von Liquidität in einem kleineren Preisbereich hilft dabei, Ihre Liquidität auf einen spezifischen Preisbereich zu konzentrieren und Ihren relativen Anteil an der gesamten Liquidität innerhalb dieses Preisbereichs zu steigern, wodurch Sie potenziell mehr Handelsgebührenbelohnungen verdienen.

Bitte beachten Sie jedoch, dass nur aktive Liquiditätspositionen Handelsgebührenbelohnungen verdienen. Das bedeutet, dass Sie Belohnungen nur erhalten, wenn der aktuelle Handelspreis innerhalb des in der Liquiditätsposition definierten Preisbereichs liegt.



### Gibt es Möglichkeiten, meine Position automatisch anzupassen, sodass sie immer im Bereich ist und Gebührenbelohnungen verdient?

PancakeSwap v3 unterstützt die Einzel-Klick-Liquiditätseinzahlung über Zap, verfügbar auf BNB Chain und Ethereum.



### Wie sieht die Handelsgebührenaufteilung für Exchange v3 aus?

|                         | 0,01 % | 0,05 % | 0,25 % | 1 %  |
| ----------------------- | ------ | ------ | ------ | ---- |
| Liquiditätsanbieter     | 67 %   | 66 %   | 68 %   | 68 % |
| CAKE-Burn               | 15 %   | 15 %   | 23 %   | 23 % |
| Treasury                | 18 %   | 19 %   | 9 %    | 9 %  |

### Werden LP-Gebührenbelohnungen wie in Exchange v2 automatisch zusammengesetzt?

Nein.

Bei Exchange v3 müssen Sie Handelsgebührenbelohnungen manuell einfordern. Dies können Sie auf der Positionsdetailseite tun. Alle Ihre v3-Liquiditätspositionen finden Sie auf der Liquiditätsseite.



### Was beeinflusst die LP-APR?

Bei Exchange v3 kann die LP-Gebührenbelohnungs-APR zwischen Liquiditätspositionen variieren. Sie basiert auf folgenden Faktoren:

* Handelsvolumen\
  \- mehr Volumen generiert mehr Gebührenbelohnungen
* Gebührenstufe des Liquiditätspaares\
  \- höhere Gebührenstufe generiert mehr Gebührenbelohnungen aus einzelnen Trades
* Anzahl der hinterlegten Token\
  \- mehr Token in der Position bedeuten einen größeren relativen Anteil an der gesamten aktiven Liquidität, was mehr Handelsgebührenbelohnungen aus Trades ergibt
* Der gewählte Preisbereich\
  \- kleinerer Preisbereich ermöglicht eine höhere Konzentration für denselben hinterlegten Token-Betrag, was zu einem größeren relativen Anteil an der gesamten aktiven Liquidität führt und mehr Handelsgebührenbelohnungen aus Trades ergibt
* Die Menge der derzeit aktiven Liquidität\
  \- wenn mehr Nutzer Liquidität mit demselben Bereich wie Sie hinterlegen und konzentrieren, verdienen Sie weniger Handelsgebühren aufgrund eines kleineren relativen Anteils
* Ob die Liquiditätsposition aktiv ist\
  \- nur aktive Liquiditätspositionen verdienen Handelsgebührenbelohnungen



### Kann ich v2-Liquidität bereitstellen?

Die Bereitstellung von v2-Liquidität ist nicht mehr ratsam. Wir empfehlen die Verwendung von v3-Liquidität, um die neuen Funktionen zur Effizienzverbesserung zu nutzen.

Wenn Sie dennoch v2-Liquidität hinzufügen möchten:

* Wenn das Token-Paar keinen v3-Pool hat oder in v2 mehr Liquidität hat als der größte Pool in v3, erscheint eine Schaltfläche „V2-Liquidität hinzufügen". Klicken Sie einfach darauf, um zur Bereitstellung von v2-Liquidität zu wechseln.
* Alternativ können Sie `/v2` in der URL verwenden, um immer die v2-Liquiditätsbereitstellung zu nutzen.



### Warum kann ich einem soeben erstellten Paar keine Liquidität hinzufügen?

Aufgrund eines Fehlers im Legacy Exchange V2 (der in jeder UniSwap V2-Fork vorhanden ist) können Sie einem Paar keine Liquidität über die normale PancakeSwap-Liquiditäts-Oberfläche und ihre Vertragsaufrufe hinzufügen, wenn ein Paar:

* Durch Aufruf von `createPair` auf FactoryV2 ohne Hinterlegung anfänglicher Liquidität und Prägung der anfänglichen LP-Token erstellt wurde
* Dann wurde einer der Token in dem Paar manuell in den Pool-Vertrag übertragen, während `sync` aufgerufen wurde.

{% hint style="info" %}
In letzter Zeit wurden vermehrt solche Angriffe auf PancakeSwap Exchange V2 auf BNB Chain beobachtet.&#x20;

Wir empfehlen dringend, unsere Oberfläche zu verwenden, um das Handelspaar für Ihren Token durch Hinzufügen der anfänglichen Liquidität bei der Paarerzeugung zu erstellen.
{% endhint %}

Während The Kitchen intensiv an einer Lösung arbeitet, finden Sie hier eine Schritt-für-Schritt-Anleitung zur Behebung dieses Problems mit BscScan:

#### Pool-Adresse und BscScan-Seite lokalisieren

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Wenn Ihr Paar betroffen ist, sehen Sie in der Fehlermeldung den Link zur BscScan-Seite für das Handelspaar/den Pool.

Alternativ können Sie zu Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)) gehen, auf „Read Contract" → „6. getPair" klicken, die Adressen der beiden Token in Ihrem Handelspaar eingeben und auf „Query" klicken. Sie sollten die Paaradresse im Ergebnisfeld sehen.

#### Prüfen, welcher Token hinterlegt wurde, und den anderen Token manuell in das Paar übertragen

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

Aus dem Token-Guthaben-Feld auf BscScan können Sie prüfen, welcher Token in den Pool hinterlegt wurde. Normalerweise sollte es der gepaarte Token sein (wie WBNB, USDT usw.)

Nach der Bestätigung müssen Sie das andere Asset manuell in den Pool-Vertrag übertragen. Dies können Sie in der Wallet-App Ihrer Wahl tun, indem Sie die Pool-Adresse als Empfänger eingeben.

Sie können einen beliebigen Betrag übertragen, aber da dies effektiv „Spenden" von Assets an einen Pool ist, übertragen Sie Ihre Assets in eine Liquiditätsposition ohne Prägung von Liquiditäts-Token. Daher empfehlen wir, diesen Betrag minimal zu halten.

{% hint style="warning" %}
WICHTIG: Nachdem Sie den Token übertragen haben, müssen Sie sofort `sync()` im Pool aufrufen.
{% endhint %}

Dies können Sie tun, indem Sie die BscScan-Seite für das Handelspaar aufrufen, zu „Write Contract" → „8. Sync" gehen und auf die Schaltfläche „Write" klicken. Sie müssen Ihre Wallet verbinden, bevor Sie die Transaktion durchführen.

Sobald die Transaktion bestätigt ist, können Sie die nachfolgende Liquidität über die PancakeSwap-Oberfläche hinzufügen.

#### Was ist, wenn ich den Launch-Preis festlegen möchte?

Sie müssen den Pool auf den Launch-Preis anpassen, während Sie den Token übertragen und den Pool reparieren.

Der zu übertragende Betrag kann mit folgender Formel berechnet werden:

* `tokenInside`: Der Token, der bereits in den Pool übertragen wurde. Normalerweise sollte es der gepaarte Token sein (wie WBNB, USDT usw.)
* `tokenToSend`: Der Token, der als nächstes in den Pool gesendet werden soll. Normalerweise Ihr Projekttoken.
* `tokenInside.price`: Der USD-Preis von tokenInside
* `tokenToSend.price`: Der USD-Preis von tokenToSend (der Launch-Preis)
* `pool`: Der V2-Pool

Mit der folgenden Formel:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Wenn das Ergebnis kleiner als 0 ist (tritt normalerweise auf, wenn der Launch-Preis sehr hoch ist, müssen Sie möglicherweise zuerst mehr `tokenInside` in den Pool hinterlegen).



### Wie verwalte ich stabile LP und Legacy-v2-LP?

Sie können diese wie gewohnt verwalten, indem Sie die [Liquiditäts](https://pancakeswap.finance/liquidity)-Seite aufrufen.



### Warum muss ich die Genehmigung für USDT zurücksetzen, bevor ich sie aktiviere/genehmige?

Bei Betrieb im Ethereum-Mainnet folgt der USDT-Token einer anderen Logik für die Verwaltung von Genehmigungen und Token-Zuteilungen.&#x20;

Wenn die Ausgabenzuweisungen zu niedrig sind, ist es daher erforderlich, die Genehmigung zurückzusetzen, bevor eine neue festgelegt wird.
