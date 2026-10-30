# Shared Inventory Hook

Der offizielle Shared Inventory Hook (SIH) von PancakeSwap ist darauf ausgelegt, dass ein einzelner Kapitalpool als Market Maker für jeden Pool agiert, der dieselben Token teilt, statt für jeden Pool separate Liquidität zu binden. Er bietet Tradern tiefere Kurse und geringeren Preiseinfluss, während Liquiditätsanbieter für dieselbe Abdeckung weniger Kapital einsetzen müssen.

Dieser vom PancakeSwap-Kernteam entwickelte Hook ist auf Asset-Emittenten und Market Maker zugeschnitten, die mehrere Paare on-chain stellen möchten, ohne ihren Bestand zu fragmentieren.

#### 🔍 Warum Shared Inventory?

Wer auf herkömmliche Weise Liquidität für mehrere Paare bereitstellt, bindet dediziertes Kapital in separaten Pools, von dem der Großteil zwischen den Trades ungenutzt bleibt. SIH hält stattdessen ein Guthaben pro Token und führt es nur dann als Liquidität zu, wenn ein Swap es benötigt, sodass dasselbe Kapital jeden Pool absichern kann, der diesen Token teilt.

#### 📊 Worin unterscheidet sich dies von anderen Modellen?

Konzentrierte Liquidität im herkömmlichen Sinn erfordert, das gesamte Kapital in einem einzigen Pool zu binden. Andere Cross-Pool-Ansätze wie Virtual-Balance-Settlement-Layer liegen typischerweise außerhalb des AMM selbst, wo Liquidität möglicherweise nicht als On-Chain-Pool-Tiefe sichtbar ist und nicht direkt von Aggregatoren geroutet wird.

Die Liquidität von SIH wird bei jedem Swap vom Hook in den PancakeSwap Infinity CLAMM-Pool hinein- und wieder herausgeführt, sodass sie als echte Pool-Tiefe erscheint, die Router sehen und gegen die sie füllen können.

#### ⚙️ So funktioniert es

* **Just-in-time-(JIT-)Injektion**\
  Vor jedem Swap prägt der Hook eine konfigurierte konzentrierte Liquiditätsposition im Pool; nachdem der Swap ausgeführt wurde, verbrennt er sie und verrechnet das Nettoergebnis. Die Position existiert nur für die Dauer eines Swaps, das Guthaben steht danach sofort für den nächsten Pool zur Verfügung, der es benötigt.
* **Ein Guthaben, viele Pools**\
  Der Bestand ist das eigene Token-Guthaben des Hooks, es gibt keine Einzahlung pro Pool. Jeder Token, der in mehr als einem Pool verwendet werden soll, wird von allen diesen Pools gemeinsam genutzt.

{% hint style="success" %}
Dadurch wird die Tiefe, die ein Pool stellt, vom Kapital entkoppelt, das der Pool direkt hält: Ein finanzierter Hook kann über mehrere Pools, die einen Token teilen, tiefe und enge Liquidität stellen.
{% endhint %}

* **Konfigurierbarer Hook**\
  Für jeden Pool, den er bedient, hält der Hook eine anpassbare, unabhängige Konfiguration für Preisbereich und Tiefe. Das Verschieben des Bandes erfordert lediglich eine Konfigurationsänderung, sodass sich die Kurse leicht um einen sich bewegenden Referenzpreis neu zentrieren lassen.

#### 📌 Wichtigste Erkenntnisse

* Ein gemeinsames Token-Guthaben sichert jeden Pool ab, der diesen Token verwendet. Das Hinzufügen eines neuen Pools erfordert kein zusätzliches Kapital.
* Vollständig on-chain und komponierbar: SIH-Liquidität ist echte Pool-Tiefe, die sowohl von PancakeSwap als auch von Aggregatoren Dritter geroutet werden kann.
* Trader erhalten tiefere Kurse und geringeren Preiseinfluss bei großen Volumina; Betreiber verdienen dieselben Handelsgebühren mit einem Bruchteil des herkömmlichen Kapitals.
