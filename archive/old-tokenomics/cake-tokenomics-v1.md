# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Emissionsrate** <a href="#emission-rate" id="emission-rate"></a>

### **Pro Block**

| **Kennzahl**                                                                           | **Emission/Block (CAKE)** | **Emission/Tag (CAKE)** |
| -------------------------------------------------------------------------------------- | ------------------------: | ----------------------: |
| Emission                                                                               |                        40 |               1.152.000 |
| Wöchentlich verbrannt [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                    -25,75 |                -787.600 |
| **Effektive Emission**                                                                 |              **<14,25\*** |           **364.400\*** |

\*Die effektive Emission liegt tatsächlich leicht unter diesem Betrag: Täglich werden zusätzlich 45.000 CAKE von dem für die Lotterie vorgesehenen Betrag umgeleitet und verbrannt (PID 137 – Details unten).

Zusätzlich zu den oben genannten Werten wird auch eine dynamische Menge CAKE [an die Dev-Adresse geprägt](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) mit einer Rate von 9,09 %. Das bedeutet: Wenn 100 CAKE geerntet werden, werden zusätzlich 9,09 CAKE geprägt und an die Dev-Adresse gesendet.

{% hint style="info" %}
Alle an die Dev-Adresse geprägten CAKE werden im wöchentlichen Burn verbrannt und gelangen nie in den Umlauf.

Daher haben wir sie in der obigen Emissionsrate nicht berücksichtigt.
{% endhint %}

## Verteilung <a href="#distribution" id="distribution"></a>

| Verteilt an                          | Belohnung/Block (% der Emission) | Belohnung/Block (CAKE gesamt) |           Belohnung/Tag |
| ------------------------------------ | --------------------------------: | ----------------------------: | ----------------------: |
| Farms und Lotterie                   |                            10,62% |                          4,25 |     122.400 (ca.) |
| davon umgeleitet und verbrannt       |                                   |                               |              -46.000 |
| Syrup Pools                          |                               25% |                            10 |     288.000 (ca.) |
| **Tägliche CAKE-Gesamtemission**     |                                   |                               | **364.400 (ca.)** |

## **Weitere deflationäre Mechanismen** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Der Burn-Prozess erfolgt derzeit manuell. [Burn-Transaktionen hier anzeigen](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Zusätzlich zu den oben genannten Mechanismen wird CAKE auch auf folgende Weisen verbrannt:

* **0,05 %** jedes auf PancakeSwap V2 getätigten Handels
* **100 %** der an die Dev-Adresse gesendeten CAKE
* **100 %** der CAKE-Performance-Gebühren aus IFOs
* **100 %** der für die Profilerstellung und NFT-Prägung ausgegebenen CAKE
* **100 %** der bei Farm-Auktionen gebotenen CAKE
* **20 %** der für Lotterie-Tickets ausgegebenen CAKE
* **45.000** CAKE pro Tag (historisch der Lotterie zugewiesen) _(Der CAKE dafür wird von einer Farm generiert – PID 137)_
* **3 %** jeder Prognoserunde werden verwendet, um CAKE zum Verbrennen zu kaufen
* **2 %** jeder Renditeauszahlung im Auto CAKE Pool
* **2 %** jedes NFT-Verkaufs auf dem NFT Market werden verwendet, um CAKE zum Verbrennen zu kaufen

## Warum ist der CAKE-Burn manuell?

Um schnell zu starten, wurde PancakeSwap als MVP (Minimum Viable Product) mit dem MasterChef-Vertrag gestartet, der 40 CAKE pro Block ausgibt. Aus diesem Grund hat das frühe Team keine zusätzlichen Funktionen wie die Möglichkeit zur Anpassung der CAKE-Prägungslogik hinzugefügt. Da die Migration zu einem neuen MasterChef viel Zeit und Aufwand erfordern würde, entschied sich das Team, die CAKE-Emissionen stattdessen durch einen manuellen Burn-Prozess zu reduzieren, indem zwei Pools erstellt wurden:

* Legacy Lottery Pool (PID – 137) – verbrannte CAKE aus der Lotterie
* Burn Pool (PID – 138) – verbrannte CAKE pro Block

Diese Pools funktionieren ähnlich wie Farms, wobei die Entwickler den Prozentsatz der 40 CAKE pro Block, der ihnen zugewiesen wird, nach jeder Abstimmung zur Reduzierung der CAKE-Emissionen anpassen können.

{% hint style="warning" %}
Am Tag des Burns kann das auf der Homepage angezeigte Angebot plötzlich um mehrere Millionen CAKE ansteigen.

Keine Sorge – **DIESER CAKE GELANGT NIE TATSÄCHLICH IN DEN UMLAUF:**
{% endhint %}

Dieser scheinbare Anstieg liegt daran, wie alle für den Burn vorgesehenen CAKE während der Woche gespeichert werden.

Die an beide Pools PID-137 und PID-138 gesendeten CAKE werden vor Abschluss der wöchentlichen Token-Burns geerntet, was dazu führt, dass das auf der Seite angezeigte Gesamtangebot um ca. 6 Millionen ansteigt. Dies liegt daran, dass ausstehende CAKE nicht im Gesamtangebot erfasst werden, bis sie am Burn-Tag geerntet werden. Sobald die Token-Burn-Transaktion abgeschlossen ist, werden die ca. 6 Millionen als "Bisher verbrannt" angezeigt.

## So bestätigen Sie das CAKE-Angebot selbst

Um zu bestätigen, dass das auf der PancakeSwap-Homepage angezeigte umlaufende CAKE-Angebot korrekt ist:

1. Rufen Sie den CAKE-Token-Vertrag auf BscScan auf und [sehen Sie, wie viel CAKE von der Burn-Adresse gehalten wird.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Das ist die Gesamtmenge an CAKE, die verbrannt wurde (für immer aus dem Umlauf entfernt und nicht mehr abrufbar).
2. Subtrahieren Sie dann diesen verbrannten Betrag vom "Gesamtangebot", das BscScan anzeigt.
3. Dies ergibt das tatsächliche CAKE-Angebot.



#### **Mehr über die deflationären Mechanismen von CAKE erfahren Sie auf der nächsten Seite.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
