# Dynamic Fee Hook

Der offizielle Dynamic Fee Hook von PancakeSwap ist darauf ausgelegt, einen faireren Werteaustausch zwischen Liquiditätsanbietern und Tradern zu schaffen. Er schützt LPs vor übermäßigem Impermanent Loss (IL) und hält den Markt gleichzeitig für Trader effizient.

Dieser Hook wurde vom PancakeSwap-Kernteam entwickelt und ist speziell darauf ausgerichtet, eine intelligente, adaptive Alternative zu herkömmlichen Festgebührenmodellen anzubieten.

#### 🔍 Warum dynamische Gebühren?

Große Arbitrage-Trades führen zu größerer Preisdivergenz in Pools und erhöhen den IL für LPs. Unser dynamisches Gebührenmodell erhebt proportional höhere Gebühren auf größere Arbitrage-Trades, um dieses Risiko auszugleichen – lässt dabei jedoch genug Spielraum für Arbitrageure, um Gewinne zu erzielen und die Preise im Gleichgewicht zu halten.

#### 📊 Wie unterscheidet sich dies von anderen Modellen?

Andere Modelle haben in der Vergangenheit historische Daten verwendet, um Volatilität und andere Faktoren zur Gebührenanpassung zu schätzen. Allerdings:

* Historische Daten sind ein nachlaufender Indikator und können zukünftige Volatilität möglicherweise nicht genau vorhersagen.
* Externe Marktereignisse (wie regulatorische Änderungen oder wirtschaftliche Verschiebungen) können vergangene Trends unzuverlässig machen.
* Komplexe, parameterreiche Modelle riskieren Überanpassung – sie funktionieren gut mit vergangenen Daten, aber schlecht unter neuen, unbekannten Bedingungen.

Unser Ansatz ist einfacher, adaptiv und basiert auf dem Echtzeit-Handelsverhalten.

#### ⚙️ Funktionsweise

* **Wir sagen keine Volatilität oder andere Makrofaktoren voraus**\
  Stattdessen profitiert unser Modell inhärent vom Verhalten von Arbitrageuren unter verschiedenen Marktbedingungen:
  * **Hohe Volatilität:** Mehr Arbitrage-Trades mit größerem Volumen → Höhere Gebühren für LPs, die einen größeren Anteil des IL abdecken.
  * **Niedrige Volatilität:** Weniger, kleinere Trades → IL ist von Natur aus geringer, aber LPs verdienen immer noch höhere Gebühren als bei einem Festgebührenmodell.
* **Unser Modell verwendet**
  * Einen exponentiell gewichteten Pool-Preis zur Erkennung von Arbitrage-Trades.
  * Eine exponentielle Gebührenkurve basierend auf der Preisauswirkung jedes Swaps.
  * Eine maximale Gebührenobergrenze von 5%, um die Fairness für Trader aufrechtzuerhalten.

{% hint style="success" %}
Dies stellt sicher, dass die Gebühren dynamisch mit der Trade-Auswirkung skalieren und sich automatisch an veränderte Marktbedingungen anpassen.
{% endhint %}

* **Ausgewogene Anreize**\
  Arbitrageure behalten nach Abzug der dynamischen Gebühren immer noch ca. 50% ihrer Gewinne und sind dadurch motiviert, die Pool-Preise im Einklang mit dem Markt zu halten.

#### 📌 Wichtigste Erkenntnisse

* Keine Abhängigkeit von Volatilitäts- oder anderen Makrofaktorvorhersagen.
* Passt sich automatisch an die Marktvolatilität basierend auf dem tatsächlichen Handelsverhalten an.
* Schützt LPs vor IL auf einer Swap-für-Swap-Basis.
* Erhält starke Anreize für Arbitrageure, Preislücken zu schließen.
* Kommt Tradern durch tiefere Liquidität und niedrigere Basisgebühren zugute.
