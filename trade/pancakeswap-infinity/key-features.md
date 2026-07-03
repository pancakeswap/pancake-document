# Hauptfunktionen

### 1️⃣ Singleton

In PancakeSwap v3 hatte jeder Liquiditätspool seinen eigenen Contract, was das Erstellen von Pools und das Swappen über mehrere Pools hinweg teurer machte.

Infinity behebt dies durch die Implementierung des Singleton-Modells. Nun befinden sich alle Pools innerhalb eines einzigen Contracts, des sogenannten PoolManager. Diese Änderung senkt die Gaskosten für die Pool-Erstellung um bis zu 99% und macht Multi-Hop-Swaps (Swaps, die durch mehrere Pools führen) deutlich günstiger, indem unnötige Token-Transfers vermieden werden.

#### ⚙️ **Funktionsweise:**

* Die Daten jedes Pools werden in einem gemeinsamen Contract mithilfe einer eindeutigen Pool-ID gespeichert.
* Das Erstellen eines neuen Pools ist nun nur noch eine Zustandsaktualisierung, keine vollständige Contract-Implementierung.
* Das Swappen zwischen Pools ist schneller und verbraucht weniger Gas.<br>

Dieser Singleton-Ansatz macht PancakeSwap Infinity zusammen mit anderen Optimierungen wie Flash Accounting und ERC-6909 zu einer der gaseffizientesten DEX-Plattformen, die heute verfügbar sind.

***

### ⚡️ Flash Accounting

Flash Accounting ist eine leistungsstarke Optimierung in PancakeSwap Infinity, die dabei hilft, Gasgebühren bei komplexen Transaktionen wie Multi-Hop-Swaps und Liquiditätsänderungen zu reduzieren.

In älteren Versionen (wie v3) wurden Token bei jedem Schritt einer Transaktion in jeden Pool hinein und heraus bewegt. Dies führte zu hohen Gaskosten, insbesondere bei Multi-Hop-Swaps.

Mit Flash Accounting ist dies nicht mehr nötig. Anstatt Token nach jedem Schritt zu transferieren, verfolgt PancakeSwap Infinity alle Token-Bewegungen intern und führt erst am Ende der gesamten Transaktion einen einzigen abschließenden Transfer durch. Das spart erheblich Gas.

#### ⚙️ **Funktionsweise:**

* Wenn Sie mit Infinity interagieren (z. B. swappen oder Liquidität hinzufügen), berechnet das System das Nettoguthaben der Token, die Sie schulden oder erhalten.
* Diese Netto-Token-Guthaben werden vorübergehend mithilfe von Transient Storage gespeichert, einer neuen Funktion, die mit dem Cancun-Upgrade von Ethereum (EIP-1153) eingeführt wurde.
* Transient Storage ist günstiger als herkömmlicher Speicher, da er nur für die Dauer der Transaktion besteht – kein dauerhaftes Schreiben oder Lesen ist erforderlich.

***

### 🪙 Native Token-Unterstützung

Mit der Einführung der Singleton-Architektur und Flash Accounting unterstützt PancakeSwap Infinity nun native Gas-Token (z. B. BNB, ETH) direkt in Liquiditätspools – kein Wrapping und Unwrapping mehr erforderlich.

#### ✅ Wichtige Highlights

* **Direkte Native-Token-Pools:** Sie können nun Pools wie ETH/USDC, BNB/CAKE erstellen, ohne WETH oder WBNB zu benötigen.
* **Gaseffizient:** Native Token-Transfers sind ca. 50% günstiger als ERC-20-Token-Transfers, was zu niedrigeren Gaskosten für Swaps und Liquiditätsaktionen führt.<br>

**Zuvor entfernt, jetzt wieder aktiviert:** Die native Token-Unterstützung fehlte in früheren Versionen aufgrund von Implementierungskomplexität und Liquiditätsfragmentierung.

***

### 📈 Benutzerdefinierte Preiskurven

PancakeSwap Infinity gibt Entwicklern die Möglichkeit, benutzerdefinierte Preismodelle für Pools zu erstellen – über das traditionelle Modell, das in den meisten AMMs verwendet wird, hinaus.

{% hint style="success" %}
**Entwickler können völlig neue Swap-Verhaltensweisen und Liquiditätsmodelle entwickeln, die auf bestimmte Asset-Typen oder Handelsstrategien zugeschnitten sind.**
{% endhint %}

#### 🔧 Was sind benutzerdefinierte Preiskurven?

Benutzerdefinierte Preiskurven ermöglichen es Entwicklern:

* Die native Pool-Manager-Logik zu umgehen und Pools mit benutzerdefinierten Swap-Verhaltensweisen zu erstellen.
* Zu ändern, wie Token-Beträge für Swaps oder Liquiditätsmodifikationen berechnet werden.
* Benutzerdefinierte Gebührenmechanismen einzubinden, wie zum Beispiel:
  * Liquiditätsabzugsgebühren
  * Rabatte oder Strafen basierend auf der Strategie

All dies wird durch before/after-Swap-Hook-Callbacks ermöglicht, die Swap-Parameter dynamisch abfangen und modifizieren können.

#### 🛠 Beispielanwendungsfälle

* **StableSwap-Kurven:** Flachere Kurven um ein 1:1-Preisverhältnis entwerfen, um die Preisauswirkung zwischen Assets wie USDC und USDT zu reduzieren.
* **RWAs:** Benutzerdefinierte Verhaltensweisen für verschiedene Asset-Typen mit dynamischem Angebot erstellen.
* **Hook-Level-Gebühren:** Einzigartige Gebühren erheben, die sich von Pool-Level-Gebühren unterscheiden, wie z. B. Entwicklergebühren.
* **Benutzerdefinierte Risikomodelle:** Preisgestaltung anpassen, um Volatilität, Orakeldaten oder externe Metriken widerzuspiegeln.

{% hint style="info" %}
In früheren AMM-Versionen (z. B. PancakeSwap v2/v3) war die Preislogik fest kodiert und starr. Die Architektur von PancakeSwap Infinity eröffnet die Möglichkeit, kapitaleffizientere und maßgeschneiderte Pools zu erstellen.
{% endhint %}

#### 🔍 Entwicklerflexibilität

* Entwickler können benutzerdefinierte Hook-Contracts implementieren, um die Preislogik zu überschreiben.
* Hook-Callbacks wie beforeSwap und afterSwap ermöglichen die vollständige Kontrolle darüber, wie Token-Deltas berechnet und angewendet werden.

***

### 🧮 ERC-6909: Effiziente Multi-Token-Buchhaltung

PancakeSwap Infinity übernimmt[ ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), einen leichtgewichtigen und gaseffizienten Token-Standard, der für die interne Buchhaltung mehrerer Token innerhalb eines einzigen Contracts entwickelt wurde. Es ersetzt viele traditionelle ERC-20-Operationen durch Mint- und Burn-Primitive – was zu erheblichen Gaseinsparungen und vereinfachten Transaktionsabläufen führt.

#### ⚙️ Funktionsweise

Anstatt Token bei jeder Interaktion in das Protokoll hinein und heraus zu bewegen, repräsentieren ERC-6909-Token interne Guthaben:

* Mint: Wenn Nutzer Token einzahlen oder einen Trade durchführen, können sie wählen, ERC-6909-Token als Ansprüche zu erhalten.
* Burn: Anstatt ERC-20-Token erneut zu übertragen, können Nutzer später einfach diese ERC-6909-Token verbrennen, um Guthaben zu begleichen oder neue Operationen zu finanzieren.

Dieses Modell reduziert den Bedarf an externen Token-Transfers drastisch, die typischerweise höhere Gaskosten verursachen und mit Logik von Drittanbietern interagieren (z. B. USDCs Blacklisting-Prüfungen).

#### 🪙 Vorteile von ERC-6909

<table><thead><tr><th width="262.9921875">Funktion</th><th width="497.7421875">Vorteil</th></tr></thead><tbody><tr><td>✅ Interne Guthabenansprüche</td><td>Kein wiederholter Token-Transfer zwischen Nutzer und Contract nötig</td></tr><tr><td>✅ Gaseffizientes Mint/Burn</td><td>Konstanter Overhead unabhängig vom Token, keine externen Contract-Aufrufe</td></tr><tr><td>✅ Einfacher als ERC-1155</td><td>Kleinere Codegröße, keine Callbacks, keine gebündelten Transfer-Anforderungen</td></tr><tr><td>✅ Multi-Token-Unterstützung</td><td>Ein einziger Contract kann mehrere Token-Typen mit isolierten Guthaben verwalten</td></tr><tr><td>✅ Nahtlose Integration mit PoolManager</td><td>Beseitigt redundante ERC-20-Genehmigungen und Transfers</td></tr></tbody></table>

#### 🚀 Anwendungsfälle

* **Hochfrequenzhändler:** Gasintensive Transfers vermeiden und direkt mit internen Guthaben interagieren.
* **Liquiditätsmanager:** Positionen effizienter öffnen und schließen ohne übermäßige Token-Bewegungen.

#### 💡 Wichtige Hinweise

* Nutzer entscheiden sich für den ERC-6909-Ablauf, wenn sie Token-Transfers nicht sofort abwickeln müssen.
* Interne Guthaben können konsolidiert und später netto abgerechnet werden, was Power-Nutzern mehr Kontrolle und Flexibilität gibt.

***

### 💸 Donate-Methode

Die `donate()`-Methode ermöglicht es Nutzern, In-Range-Liquiditätsanbieter innerhalb eines Pools direkt zu incentivieren, indem sie Token spenden. Diese Methode stützt sich auf das Gebührenbuchhaltungssystem des Pools, um die Zahlungen zu erleichtern, und stellt sicher, dass nur Pool-Token unterstützt werden.

#### 🔹 Hauptfunktionen:

* **Direkte Zahlungen an LPs:** Spenden werden direkt an Liquiditätsanbieter geleistet und belohnen diejenigen, die Liquidität im aktiven Bereich des Pools aufrechterhalten.
* **Unterstützt nur Pool-Token:** Die `donate()`-Methode unterstützt nur Spenden in den Token des Pools, da sie das Gebührenbuchhaltungssystem nutzt, um eine ordnungsgemäße Verteilung sicherzustellen.
* **Offen für alle Nutzer:** Jeder Nutzer kann die `donate()`-Methode aufrufen und so jeden zur Incentivierung aktiver Liquiditätsbereitstellung ermächtigen.

Obwohl die `donate()`-Methode ein leistungsstarkes Werkzeug zur Incentivierung von LPs ist, sollten Spender beachten, dass ihre Spenden von anderen Nutzern per Frontrunning ausgenutzt werden können. Dies kann auftreten, wenn ein Nutzer kurz vor einer Spende schnell Liquidität zum Pool hinzufügt und so einen Teil der gespendeten Mittel erhält.

Um Frontrunning zu verhindern, müssen Spender möglicherweise zusätzliche Strategien bei der Gestaltung ihrer Spendemechanismen berücksichtigen, wie zum Beispiel:

* Sicherstellen, dass Spenden so erfolgen, dass opportunistisches Frontrunning minimiert wird.
* Zeitverzögerungen oder spezifische Bedingungen hinzufügen (mithilfe von before/after-Donate-Hook-Callbacks), die sicherstellen, dass die Spenden nicht auf diese Weise ausgenutzt werden.
