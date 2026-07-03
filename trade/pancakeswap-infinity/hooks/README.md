# Hooks

{% hint style="info" %}
Wenn Sie Entwickler sind oder detaillierte technische Dokumentation zur Entwicklung eines Hooks suchen, besuchen Sie bitte [diese Seite](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Hooks sind leistungsstarke Erweiterungen, mit denen Entwickler das Verhalten von Liquiditätspools in PancakeSwap Infinity erweitern und anpassen können. Stellen Sie sich diese als „Plugins" oder „Widgets" vor, die neue Funktionen zu Liquiditätspools hinzufügen.

#### 🔍 Was sind Hooks?

* Hooks sind externe Smart Contracts, die von jedem erstellt werden können – Entwickler, Protokolle oder Community-Mitglieder – und an Liquiditätspools angehängt werden, um deren Verhalten zu erweitern oder zu modifizieren.
* Jeder Pool kann nur einen Hook angehängt haben, aber ein einzelner Hook kann viele Pools bedienen.
* Hooks können benutzerdefinierten Code vor oder nach wichtigen Aktionen ausführen, wie zum Beispiel:
  * Initialisierung eines Pools
  * Swapping
  * Hinzufügen/Entfernen von Liquidität
  * Spenden<br>

**⛓️ Funktionsweise von Hooks:**

* Ein Hook wird bei der Pool-Erstellung ausgewählt und kann später nicht mehr geändert werden.
* Ein Hook-Contract wird bei bestimmten Aktionen (Swap, Liquidität hinzufügen usw.) ausgelöst und führt Logik vor oder nach diesen Aktionen aus, wie im Contract definiert.
* Zum Beispiel könnte ein Hook:
  * Swap-Gebührenrabatte für CAKE-Inhaber anbieten
  * Benutzerdefinierte Gebühren erheben und Belohnungen verteilen
  * Neue Swap-Logik wie StableSwaps oder TWAP-ähnliche Orders ermöglichen<br>

#### ⚙️ Hook-Callbacks

Hooks können in zehn spezifischen Momenten ausgelöst werden. Entwickler können auswählen, welche sie implementieren möchten:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Diese ermöglichen die Implementierung hochgradig anpassbarer und modularer Verhaltensweisen durch Hooks.

#### 🔧 Zwei Arten von Hooks

**Typ 1: Keine Autorisierung erforderlich**

Diese Hooks laufen automatisch und erfordern keine Nutzergenehmigung. Sie werden durch Aktionen wie Swaps oder Liquiditätsänderungen ausgelöst.



Beispiele:

* Dynamische Gebühren: Swap-Gebühren basierend auf der Marktvolatilität anpassen
* Gebührenrabatte: Rabatten für Nutzer gewähren, die CAKE halten oder hohe Volumen handeln



Beispielablauf (CAKE-Gebührenrabatt):

1. Ein Nutzer initiiert einen Swap.
2. Der Hook prüft das CAKE-Guthaben über den `beforeSwap` Hook-Callback.
3. Wenn der Nutzer gemäß den definierten Schwellenwerten ausreichend CAKE hält, erhält er 50% Rabatt auf Pool-Gebühren.
4. Der Rest der Transaktion läuft wie gewohnt weiter.<br>

{% hint style="success" %}
Diese Hooks benötigen keine spezielle Benutzeroberfläche oder zusätzliche Interaktion. Die Vorteile werden automatisch angewendet.
{% endhint %}

**Typ 2: Nutzerautorisierung erforderlich**

Diese Hooks erfordern, dass Nutzer direkt mit ihnen interagieren, eine Genehmigung erteilen und möglicherweise Mittel übertragen müssen, oft um Positionen zu erstellen oder zu verwalten.



Beispiele:

* Limit-Orders: Einen Swap nur ausführen, wenn der Zielpreis erreicht wird.
* TWAMM: Große Orders in kleinere Teile aufteilen für eine bessere Ausführung.
* Aktives Liquiditätsmanagement: LP-Positionen automatisch für optimale Renditen verwalten.



Beispielablauf (Limit-Order-Hook):

1. Der Nutzer interagiert direkt mit dem Hook-Contract (nicht der üblichen Swap-Oberfläche).
2. Er gibt Details wie Limitpreis, Token-Paar und Betrag ein.
3. Der Hook gibt ein Quittungs-Token aus, das die Order repräsentiert.
4. Wenn der Pool-Preis später das Ziel erreicht, führt der Hook die Order über afterSwap aus.
5. Der Nutzer kann das Quittungs-Token zurückgeben, um die getauschten Assets einzufordern.

{% hint style="info" %}
Diese Hooks benötigen oft eine benutzerdefinierte Benutzeroberfläche, und Nutzer müssen dem Hook-Contract vertrauen und genehmigen, ihre Mittel zu halten.
{% endhint %}

#### 🚀 Anwendungsfälle & Innovation

Hooks eröffnen unbegrenzte Möglichkeiten, darunter:

* Benutzerdefinierte AMMs (z. B. Stablecoin-Kurven)
* Liquiditäts-Mining-Belohnungen
* Automatisierte Handelsstrategien, Liquiditätsmanagement
* On-Chain-Limit-Orders, andere Order-Typen
* Dynamische Preisgestaltung und Gebührenanpassungen
* Renditesteigernde LP-Strategien<br>

Mit Hooks können Entwickler eine völlig neue DeFi-Erfahrung auf der bestehenden Infrastruktur von PancakeSwap Infinity aufbauen – was die Entwicklung beschleunigt und die Kosten senkt.
