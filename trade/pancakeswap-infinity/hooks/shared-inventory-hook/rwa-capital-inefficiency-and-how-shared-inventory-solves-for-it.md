---
description: '2026-09-04'
---

# RWA-Kapitalineffizienz – und wie Shared Inventory sie löst

Ein PancakeSwap-Fallstudien-Experiment (Teil 1: Die Ausgangslage)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Dies ist der erste Teil einer zweiteiligen Fallstudie. In diesem Teil beschreiben wir das reale Problem der Kapitaleffizienz, mit dem Emittenten von RWA-Assets konfrontiert sind, stellen vor, wie der Shared Inventory Hook (SIH) von PancakeSwap dieses Problem lösen soll, und führen ein laufendes Fallstudien-Experiment ein, mit dem wir ihn anhand von Onchain-Daten testen.

In den nächsten Wochen veröffentlichen wir Teil 2: Die Ergebnisse.

***

### 🧩 Was ist das Kapitaleffizienz-Problem?

Die RWA-Branche liebt eine Kennzahl: **wie viel tokenisiert wurde.** Sie ist die Schlagzeile fast jedes Reports – eine neue Anlageklasse kommt hinzu, Milliarden wurden ausgegeben, Wachstum in dreistelligen Prozentbereichen.

Es gibt eine zweite Kennzahl, die oft untergeht, aber ein aussagekräftigeres Signal sein könnte: **Wie viel davon kann tatsächlich gehandelt werden?**

Die Lücke zwischen diesen beiden Zahlen ist entscheidend. Auf dem maßgeblichen Tracker [rwa.xyz](http://rwa.xyz) übersteigt der Wert, der onchain _abgebildet_ wird, den Wert, gegen den zu einem beliebigen Zeitpunkt tatsächlich _gehandelt_ werden kann, bei Weitem – die Daten zeigen, dass gesperrter, referenzierter und verteilter Wert **mehr als eine Größenordnung über dem liegt, was in handelbaren Orderbüchern steht.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Quelle: app.rwa.xyz/stocks_

Für einen RWA-Emittenten ist das die Falle. Eine Aktie, einen ETF oder eine Staatsanleihe zu tokenisieren ist der einfache Teil – sie eng und zuverlässig handelbar zu machen, ist die Herausforderung, und hier entscheidet sich die Kapitaleffizienz. Das ultimative Ziel ist, Tradern zu ermöglichen, das tokenisierte Asset _tatsächlich_ einfach und günstig zu handeln – denn daraus entstehen letztlich Volumen und Gebühren.

Und deshalb ist es speziell ein Problem der _Kapitaleffizienz_ und nicht nur ein Liquiditätsproblem.

#### Jeder gestellte Pool verlangt seinen eigenen exklusiven USDT-Bestand

Um ein RWA-Paar in einem klassischen Pool mit konzentrierter Liquidität (CLAMM) handelbar zu machen, benötigen Emittenten dediziertes Quote-Asset – USDT –, das bereitliegt, damit Käufer hinein verkaufen können. Bei zehn gelisteten Paaren erfordert das CLAMM-Modell die Finanzierung von **zehn separaten USDT-Beständen**, einen pro Paar, die sich gegenseitig nicht helfen können. Das Quote-Kapital wird so in exklusive Silos zerstückelt.

Wir haben das an unserem eigenen Book gemessen. Wir haben **7 Pools für tokenisierte Aktien, die live auf PancakeSwap laufen** (jeweils ein klassischer V3-CLAMM-Pool), betrachtet und das exklusive USDT ermittelt.

Momentaufnahme: **2. September 2026.**

<table data-search="false"><thead><tr><th>Paar</th><th>Exklusives USDT im Pool</th><th>Pool-TVL</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Gesamt</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Das sind **~745.000 $ an exklusiv zugewiesenem USDT.**

Und dabei geht es nur um die Namen, die überhaupt ein Book haben.

SNXXB, KORUB, SOXSB und DJTB haben gar kein CLAMM-USDT-Book – tokenisiert, aber schwer handelbar.

***

### 🎯 Worauf sollte ein Emittent optimieren?

Ohne die Mechanik betrachtet muss ein RWA-Emittent im Kern drei Dinge lösen:

1. **Sein Asset soll wirklich und effizient handelbar sein** – enge Quotes für jedes Asset, nicht nur für Flaggschiff-Token.
2. **Möglichst wenig gebundenes Kapital** dafür – Quote-Assets sind teuer; zehn USDT-Bestände exklusiv zu finanzieren ist nicht sehr effizient.
3. **Keinen Handelstisch betreiben müssen –** Assets emittieren, ohne täglich Liquiditätsinfrastruktur betreiben zu müssen.

Die Frage ist also, ob sich Liquidität anders strukturieren lässt – und genau dafür wurde der Shared Inventory Hook von PancakeSwap entwickelt.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH ist ein PancakeSwap Infinity Hook, mit dem ein RWA-Emittent viele Paare aus einem gemeinsamen USDT-Topf statt aus einem exklusiven Bestand pro Paar absichern kann.**

SIH erreicht dies, indem es Liquidität Just-in-Time bereitstellt. Das ermöglicht:

* Tiefere Quotes bei den Paaren
* Geringere Preisauswirkung, insbesondere bei großen Trades
* Freigesetztes Kapital für RWA-Emittenten, da weniger eingesetztes Kapital mehr Paare quotet

Schauen wir uns diese Aussagen in der Praxis an.

Stand der gleichen Momentaufnahme vom **2. September 2026** hält SIH **635.028 $** an Inventar in einem einzigen Hook, quotet **11 Paare** aus **180.467 $** gemeinsamem USDT und läuft bei einer Auslastung von **87,7 %**. Damit hat SIH **3,56 Mio. $ in 17.299 Transaktionen** verarbeitet.

Das heißt: **ein gemeinsamer USDT-Bestand von ~700.000 $, der ~11 Paare quotet, gegenüber ~745.000 $, die nur 7 Paare quoten**.

Gleiche Aufgabe, nur so konzipiert, dass Kapital nicht mehr dupliziert wird.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Übertragen auf das, was Emittenten wichtig ist:

* N exklusive USDT-Bestände traditionell → ✅ ein gemeinsamer Topf mit SIH
* Ausgegeben, aber nicht handelbar → ✅ handelbar\
  Gemeinsames Inventar, das Just-in-Time rund um den Live-Preis eingespeist wird, bedeutet: Token ohne V3-USDT-Book können trotzdem gequotet werden, nicht nur geminted.
* Einen Handelstisch betreiben → ✅ ein berechtigter Operator\
  Der Emittent stellt das Inventar bereit; der Hook und sein Operator übernehmen das Quoting.

***

### 🔬 Testen Sie den Shared-Inventory-Simulator

Entwickeln Sie ein Gefühl dafür, wie sich SIH verhält, mit unserem interaktiven Vergleichstool **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Dies ist ein **übergeordneter, normalisierter Vergleich** von SIH mit einem klassischen CLAMM-Book – eine Reihe realer Faktoren wird auf beiden Seiten konstant gehalten, damit sich der Mechanismus der Kapitaleffizienz sauber isolieren lässt. Es ist ein Modell zum Verständnis, keine Gewinn- und Verlustrechnung.

Drei Tabs:

* **Simulator-Tab** – Spielen Sie mit Inventar, Bandbreite und Flow, um zu sehen, wie SIH unter verschiedenen Bedingungen im Vergleich zu einem vergleichbaren CLAMM-Pool abschneiden _würde_.
* **Comparison-Tab** – SIH direkt im Vergleich zu einem **PancakeSwap V3 CLAMM**-Book in denselben Pools, sodass Sie den Unterschied zwischen gemeinsamem und exklusivem USDT-Topf bei gebundenem Kapital und Abdeckung nebeneinander sehen.
* **Live-Data-Tab** – Messen Sie, wie SIH _tatsächlich_ gerade performt, basierend auf den Onchain-Abfragen, die diese Studie speisen.

Der Simulator soll veranschaulichen, wie der Shared Inventory Hook funktioniert. Probieren Sie ihn aus und vergleichen Sie ihn dann mit den realen Ergebnissen, die wir in den nächsten Wochen veröffentlichen.

***

### 🧪 Das Experiment

In den **nächsten Wochen** betreiben wir SIH live und messen es anhand von Onchain-Quellen an den oben genannten Aussagen zur Kapitaleffizienz. Jede Woche veröffentlichen wir neue Info-Häppchen zur SIH-Performance und -Architektur.

**Live-RWA-Paare in der Studie:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Hinweis: SNXXB, KORUB, SOXSB und DJTB haben gar kein klassisches CLAMM-Book._

**Wir veröffentlichen die Ergebnisse in den nächsten Wochen auf dem** [**Twitter-Account von PancakeSwap.**](https://x.com/PancakeSwap)

Die veröffentlichten Ergebnisse umfassen:

* **Den vollständigen Performance-Datensatz –** Alle SIH-Daten der nächsten Wochen, zu einem Gesamtbild zusammengeführt.
* **Die Frage der Kapitalallokation –** Wie viel Kapital SIH einem RWA-Emittenten tatsächlich gespart hat.
* **Treffer / Fehlschlag –** Wo SIH die Erwartungen übertroffen hat und wo nachgebessert werden muss.
* **Das Fazit –** Eine fundierte Schlussfolgerung dazu, wie effektiv SIH für die Kapitaleffizienz von RWAs tatsächlich ist.

_Hinweis zu den Daten: Die Zahlen hier stammen aus Live-Onchain-Abfragen und öffentlichen Paardaten und sind jeweils direkt belegt. Einige Vergleiche nutzen unterschiedliche Zeiträume, die wir kenntlich gemacht haben – die Studie ist darauf ausgelegt, Gleiches mit Gleichem zu messen, wo diese Einführung die Frage nur aufwerfen konnte._

***

### Möchten Sie SIH für Ihre Assets aktivieren?

Wenn Sie RWA-Emittent sind und es leid sind, für jeden gequoteten Pool einen separaten USDT-Bestand zu finanzieren, ist dies das Richtige für Sie.

Wir nehmen derzeit RWA-Emittenten auf. Füllen Sie dieses Google-Formular aus, und wir führen Sie durch die Einrichtung des Quotings Ihres Assets auf SIH – [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Danke fürs Lesen! Folgen Sie uns auf [X](https://x.com/PancakeSwap) für die neuesten Updates und diskutieren Sie mit auf [Telegram](https://t.me/PancakeSwap) und [Discord](https://discord.gg/pancakeswap).

Lasst uns bauen,\
Die Chefs 🥞

***

_Haftungsausschluss: Dieser Inhalt dient ausschließlich allgemeinen Informations- und Bildungszwecken. Er ist nicht als Finanz-, Rechts- oder sonstige professionelle Beratung zu verstehen. Die Preise digitaler Assets können volatil sein. Der Wert Ihrer Anlage kann sinken oder steigen._
