# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

CLAMM ermöglicht es Liquiditätsanbietern, ihr Kapital innerhalb **bestimmter Preisspannen** zu allokieren. Dies führt zu:

* **Höherer Kapitaleffizienz**: Mehr Liquidität bei aktiven Handelspreisen.
* **Tieferer Liquidität**: Bessere Ausführung für Trader.
* **Aktivem LP-Management**: LPs müssen Positionen anpassen, wenn sich die Preise bewegen.
* **Höherem Impermanent-Loss**-Potenzial für Out-of-Range-Positionen.

{% hint style="info" %}
CLAMM operiert auf der Konstantprodukt-Formel (X \* Y = K). Jede Liquiditätsposition ist nicht fungibel und wird als NFT dargestellt.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM oder „Bin Pool")

LBAMM implementiert **diskrete Preisbins**, die jeweils Liquidität auf einem bestimmten Preisniveau halten. LBAMM folgt der **Konstantsummen-Formel (X + Y = K).**



**Wesentliche Merkmale:**

* **0 Preisauswirkung** bei Trades innerhalb eines Bins.
* **Fungible Liquidität** (Liquidität innerhalb jedes Bins ist ein ERC-20-Token).
* **Niedrigere Gaskosten** für die Anpassung von LP-Positionen.
* **Unterstützung für verschiedene Liquiditätsformen** (z. B. asymmetrisch, gleichmäßig).
* Besser geeignet für **Paare mit geringer Volatilität** aufgrund der flachen Preiskurve pro Bin.

> 🥞 **PancakeSwap ist das erste Protokoll, das LBAMM-Pools mit Hooks anbietet.**

{% hint style="success" %}
Sowohl CLAMM- als auch LBAMM-Pools unterstützen **Hooks**, die es Entwicklern ermöglichen, das Pool-Verhalten anzupassen. Pool-Typen sind über neue Pool-Manager erweiterbar, die ohne Protokoll-Neuimplementierung hinzugefügt werden können.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Funktion</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Preiskurve</strong></td><td>Konstantprodukt (X * Y = K)</td><td>Konstantsumme (X + Y = K)</td></tr><tr><td><strong>Liquiditäts-Token</strong></td><td>Nicht fungibel (NFT)</td><td>Fungibel (ERC-20 pro Bin)</td></tr><tr><td><strong>Am besten geeignet für</strong></td><td>Paare mit hoher/niedriger Volatilität</td><td>Paare mit niedriger Volatilität</td></tr><tr><td><strong>Vorteile</strong></td><td><ol><li>Kapitaleffizienz</li><li>Gaseffizient bei breiten/vollständigen Spannen</li><li>Weit verbreitet</li></ol></td><td><ol><li>0 Preisauswirkung innerhalb des Bins</li><li>Günstigeres LP-Management</li><li>Flexible Liquiditätsformen</li></ol></td></tr><tr><td><strong>Hook-Unterstützung</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Gebühren

PancakeSwap Infinity unterstützt ein flexibles und erweiterbares Gebührensystem durch statische und dynamische Gebühreneinstellungen. Dieses Setup gibt sowohl Pool-Erstellern als auch LPs leistungsstarke Werkzeuge zur Optimierung verschiedener Handelsstrategien und Risikoprofile.

#### 🔁 Dynamische Gebühren

* Dynamische Gebühren werden in Echtzeit über Hook-Contracts bestimmt.
* Diese Gebühren können basierend auf externen Faktoren wie Volatilität, Handelsvolumen, Nutzerstatus (z. B. CAKE-Bestände) oder einer beliebigen benutzerdefinierten Logik im Hook schwanken.
* Pools mit dynamischen Gebühren müssen die Einstellung bei der Pool-Erstellung aktivieren und einen Hook anhängen, der in der Lage ist, Gebühren über `beforeSwap` zu modifizieren.
* Sobald ein Pool initialisiert ist, ist der Gebührentyp (dynamisch oder statisch) unveränderlich.

Dynamische Gebühren bieten maximale Flexibilität und optimieren Gebührenstrukturen für LPs und Swapper basierend auf den Marktbedingungen.

#### 📌 Statische Gebühren

* Statische Gebührenpools haben eine feste Gebühr, die bei der Pool-Erstellung festgelegt wird.
* Diese Gebühren können nach der Initialisierung des Pools nicht mehr geändert werden.
* Geeignet für einfachere Anwendungsfälle oder wenn die Vorhersehbarkeit der Gebührenstruktur wichtig ist.<br>

**🔒 Maximale Gebührenobergrenzen:**

* CLAMM-Pools: Bis zu 100% (hauptsächlich für spezialisierte oder experimentelle Anwendungsfälle)
* LBAMM-Pools: Begrenzt auf 10%<br>

**🏛 Protokollgebühr (für statische Gebührenpools):**

* PancakeSwap erhebt eine Protokollgebühr auf Infinity-Pools
* 33% der LP-Gebühr, maximal 0,4%

| **LP-Gebühr**       | **Protokollgebühr** |
| ------------------- | ------------------- |
| 1%                  | 0,33%               |
| 2%                  | 0,4% (begrenzt)     |
| Dynamischer Gebühren-Pool | 0%            |

#### 🛠️ Einrichtungshinweise für Pool-Ersteller

* Bei der Initialisierung eines Pools über den PoolManager muss der Ersteller wählen:
  * Ob der Pool eine statische oder dynamische Gebühr verwendet
  * Ob ein Hook-Contract angehängt ist (für dynamische Gebühren erforderlich)

Diese Einstellungen sind dauerhaft und bestimmen, wie sich der Pool während seiner gesamten Lebensdauer verhält.
