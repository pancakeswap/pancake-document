# Gebühren und Routen

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

In Exchange V3 nutzt der PancakeSwap Smart Router standardmäßig Liquidität aus V3, V2, StableSwap (BNB Chain) sowie den AMM- und Market-Maker-Quellen (BNB Chain & Ethereum), um Trades auszuführen und den besten Preis für Trader zu finden.

Nutzer können ihren Trade jedoch jederzeit anpassen, indem sie auswählen, welche Liquiditätsquellen der Router verwenden soll, sowie Multihops und Split-Routing aktivieren oder deaktivieren.

### **Gebührensatz und Gebührenbetrag prüfen**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Um zu prüfen, wie viel Trading-Gebühr für Ihren aktuellen Swap anfällt, schauen Sie sich den Abschnitt „Gebühr" in der Swap-Detailansicht an.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

Um zu prüfen, durch welchen Pool-Typ und welche Gebührenstufe Ihr Trade aktuell geleitet wird, schauen Sie sich den Abschnitt „Route" an.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Für mehr Details klicken Sie auf das Lupen-Symbol, um die vollständige Anzeige der Trading-Route aufzurufen.



### **Liquiditätsquellen anpassen**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

Im oberen Bereich der Oberfläche „Routing anpassen" können Sie auswählen, welche Liquiditätsquelle die Route beim Weiterleiten Ihres Trades verwenden soll. Um diese Oberfläche aufzurufen, können Sie:

* Auf „Routing anpassen" am unteren Ende der Trading-Routenanzeige klicken.
* Auf das Zahnrad-Symbol in der Swap-Oberfläche klicken und anschließend unten auf „Routing anpassen" klicken.

Standardmäßig sind alle Liquiditätsquellen aktiviert, und Smart Router nutzt die gesamte verfügbare Liquidität innerhalb von PancakeSwap optimal aus.

Bitte beachten Sie, dass der Router Trades NICHT zwischen AMM-Liquiditätspools und MM-Market-Makern leitet. Wenn Ihr Trade von MM-Market-Makern ausgeführt wird, wird er keine AMM-Liquiditätspools durchlaufen.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Sie können auf die Schaltfläche „Zurücksetzen" oben rechts klicken, um die Konfigurationen auf die Standardwerte zurückzusetzen.



### **Routing-Einstellungen anpassen**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

Im unteren Bereich der Oberfläche „Routing anpassen" können Sie Ihre Routing-Einstellungen anpassen, indem Sie Multihops und Split-Routing aktivieren oder deaktivieren.

Multihops ermöglichen es Token, über mehrere Hops zwischen verschiedenen Liquiditätspools zu wechseln, um den besten Preis zu erzielen. Das Deaktivieren dieser Option schränkt Trades auf direkte Swaps ein, was zu höherer Kursabweichung oder sogar Kapitalverlust führen kann.

Split-Routing ermöglicht es, Token-Swaps in mehrere Routen aufzuteilen, um den besten Preis zu erzielen. Das Deaktivieren dieser Option schränkt die Ausführung von Trades auf eine einzige Route ein, was zu geringerer Effizienz oder höherer Kursabweichung führen kann.

{% hint style="warning" %}
Wenn Ihr Trade aufgrund einer angepassten Trading-Konfiguration nicht ausgeführt werden kann, wird eine Warnung angezeigt. Sie können auf „Einstellungen prüfen" klicken, um die Oberfläche „Routing anpassen" schnell aufzurufen, oder „Auf Standard zurücksetzen" wählen, um Ihre Konfigurationen schnell auf die Standardwerte zurückzusetzen.
{% endhint %}
