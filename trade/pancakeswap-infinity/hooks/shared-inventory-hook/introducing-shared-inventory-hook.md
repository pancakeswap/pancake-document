---
description: '2026-08-21'
---

# Vorstellung des Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Fünf Paare zu quoten sollte nicht das Fünffache an Kapital kosten. Onchain ist das aber genau der Deal, den jeder Asset-Emittent bekommt: Liquidität ist an das jeweilige Paar gebunden, sodass jedes neue Paar weiteres Kapital erfordert – das meiste davon liegt einfach nur herum und verdient nichts, bis genau dieses Paar in genau dieser Preisspanne gehandelt wird. Jedes Mal, wenn Sie ein neues Paar quoten möchten, stellen Sie frisches Kapital als Liquidität bereit – Kapital, das dann an dieses eine Paar gebunden ist und nirgendwo anders genutzt werden kann.

Der Shared Inventory Hook (SIH) durchbricht diese Bindung. Er ist der neueste Hook auf PancakeSwap Infinity – und der erste, der auf Kapitaleffizienz ausgelegt ist.

_💡 Kurz erklärt: Ein Hook ist ein Smart Contract (wie ein Add-on), der sich in einen Infinity-Pool einklinkt und mitten im Swap eigene Logik ausführt – ohne dass ein neuer Handelsplatz aufgesetzt werden muss._

Wie funktioniert das nun?

Statt in jedem Pool einen separaten Bestand zu binden, finanziert ein RWA-Asset-Emittent **ein gemeinsames Inventar**, und der Shared Inventory Hook quotet daraus Tiefe in das jeweils gehandelte Paar – Just-in-Time, genau im Moment des Swaps. Stellen Sie es sich als ein Lager vor, das alle Gerichte der Küche versorgt, statt eines eigenen Lagers für jedes. Ein Bestand leistet die Arbeit von vielen.

Genau dieser Wandel macht SIH kapitaleffizient, und er zeigt sich auf drei Arten:

* **Kapital bleibt aktiv und arbeitet.** Liquidität aus dem Hook-Inventar wird bei einem Swap Just-in-Time eingespeist, sodass sie aktiv arbeitet und Ihnen Gebühren einbringt, statt brachzuliegen.
* **Gebührenchance aus einem Bestand über mehrere Paare.** Ein Inventar verdient über alle Paare, die es bedient, sodass Sie Gebührenfluss mit deutlich weniger eingesetztem Kapital erfassen.
* **Geringere Preisauswirkung.** Da die zum Swap-Zeitpunkt gequotete Liquidität tiefer ist, erfahren große Trades eine geringere Preisauswirkung, sobald SIH den besten Preis quotet.
* **Höhere Kapitaleffizienz.** Einmal finanzieren; dasselbe Kapital sichert die Tiefe über jedes SIH-aktivierte Paar. Außerdem können Sie SIH für ein neues Paar aktivieren, ohne Kapital hinzuzufügen.

> \*\*Bereits überzeugt? Bringen Sie Ihre Assets kapitaleffizient onchain – füllen Sie dieses Formular aus → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**Der Beweis liegt onchain**

SIH ging im August mit bStocks live, und die wichtigste Zahl ist, wie hart dieses Kapital arbeitet. Beim jüngsten Hook-Snapshot (21. Aug. 2026) sind 75 % des gemeinsamen Inventars aktiv über die drei Paare eingesetzt (Hook-Inventar ~297.000 $, aktiv ~224.000 $). Bei den zwei etablierten Paaren, CRCLB und MUB, liegt die Auslastung bei ~99 % (98,96 % / 98,95 %). Kapital, das in klassischen V3-CLAMM-Pools brachliegen würde, ist hier in der Range und quotet.

In den ersten Wochen (bis 21. Aug.) haben die drei Paare ~710.000 $ in 5.713 Swaps gehandelt – bedient aus einem gemeinsamen Inventar von ~297.000 $ und mit LP-Gebühren in der 0,25-%-Stufe.

_**Quellen:** Internes Dune-Dashboard_ **Live-Pools:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Wohin die Reise geht**

Das Modell ist auf Skalierung ausgelegt – mehr Paare, ein gemeinsamer Bestand, der sich über Tausende von rund um die Uhr gehandelten Märkten erstreckt. Es ist der schnellste Weg, den wir bisher gesehen haben, um die gesamte Paar-Palette eines Tokens onchain zu bringen, ohne das dahinterstehende Kapital zu vervielfachen.

Live-SIH-Pools finden Sie auf der [PancakeSwap Earn-Seite](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001) – öffnen Sie **Infinity** und suchen Sie unter den Pool-Merkmalen nach **Shared Inventory**. SIH ist derzeit für CRCLB / USDT, MUB / USDT und GMEB / USDT aktiviert.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Hinweis: Retail-LPs können bereits über Earn Liquidität zu diesen Pools hinzufügen – diese Einlage wird zu residenter Pool-Liquidität und wird getrennt vom gemeinsamen Inventar gehalten._

_**Wichtig:**_

_SIH ist weniger anfällig für Preisdrift als eine klassische LP-Position, da das Inventar nur im Moment eines Swaps eingesetzt wird. Es ist aber nicht risikofrei. Der Operator hält weiterhin Inventar, das sich mit dem Markt bewegt. Wie bei jeder Onchain-Strategie hängen die Ergebnisse von Volumen, Inventar, Hedging und Marktbedingungen ab._

Bereit, die Kapitaleffizienz zu maximieren? Lassen Sie Ihre Token-Paare jetzt für SIH aktivieren → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, Die Chefs 🥞

***

_Haftungsausschluss: Dieser Inhalt dient ausschließlich allgemeinen Informations- und Bildungszwecken. Er ist nicht als Finanz-, Rechts- oder sonstige professionelle Beratung zu verstehen. Die Preise digitaler Assets können volatil sein. Der Wert Ihrer Anlage kann sinken oder steigen._
