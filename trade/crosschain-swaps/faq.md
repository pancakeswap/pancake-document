# ❓ FAQ

### 1. Wie funktioniert die Kursabweichungstoleranz bei Cross-Chain Swaps?

Bei Cross-Chain Swaps wird Ihr ausgewählter Kursabweichungstolerierprozentsatz unabhängig auf Swaps sowohl auf der Quell- als auch auf der Ziel-Chain angewendet.

**Beispiel:**

* BNB auf BNB Chain zu ARB auf Arbitrum swappen
* Kursabweichungstoleranz auf 1% gesetzt
* Die Route könnte sein:
  1. BNB gegen USDC auf BNB Chain swappen
  2. USDC von BNB Chain zu Arbitrum über Across bridgen
  3. USDC gegen ARB auf Arbitrum swappen
* In diesem Fall gilt die 1%-Kursabweichungstoleranz separat für:
  * Den Swap auf BNB Chain
  * Den Swap auf Arbitrum

Dies stellt sicher, dass Sie vor übermäßigen Preisbewegungen auf beiden Abschnitten der Transaktion geschützt sind, während der Bridging-Prozess selbst von den Kursabweichungseinstellungen unberührt bleibt.

### 2. Was passiert, wenn meine Transaktion fehlschlägt?

Wenn Ihr Cross-Chain Swap in irgendeiner Phase auf einen Fehler stößt, wird dieser wie folgt behandelt:

1.  **Swap-/Transaktionsfehler auf der Quell-Chain**

    ➝ Sie erhalten Ihren ursprünglichen Token sofort auf der Quell-Chain zurück.
2.  **Bridge-Transaktionsfehler**

    ➝ Across verarbeitet eine Rückerstattung innerhalb von 90 Minuten bis 2 Stunden, und Sie erhalten das überbrückte Asset auf der Quell-Chain zurück. Relay verarbeitet die Rückerstattung in solchen Szenarien zwischen SOL <> EVM innerhalb einer Minute.
3.  **Swap-Fehler auf der Ziel-Chain**

    ➝ Sie erhalten das überbrückte Asset auf der Ziel-Chain, ohne den abschließenden Swap zu Ihrem Ziel-Token.

{% hint style="info" %}
**Hinweis:** Sie können den Status Ihrer Transaktionen jederzeit über die Transaktionsverlauf-Registerkarte in der Wallet-Verbindungsoberfläche überprüfen.
{% endhint %}

### 3. Sind meine Cross-Chain Swaps MEV-geschützt?

MEV Guard wird nur auf der BNB Chain unterstützt, wenn Swaps direkt von einer verbundenen Wallet mit aktiviertem MEV Guard initiiert werden.

* Wenn Ihr Cross-Chain Swap einen Swap auf BNB Chain als Quell-Chain beinhaltet und Sie MEV Guard aktiviert haben, ist dieser Swap MEV-geschützt.
* Wenn BNB Chain die Ziel-Chain ist, wird der Swap vom Bridging-Relayer/-System ausgeführt und ist nicht MEV-geschützt, da er nicht von Ihrer verbundenen Wallet initiiert wird.

{% hint style="info" %}
**Hinweis:** Andere Chains wie Arbitrum und Base unterstützen derzeit keinen MEV Guard-Schutz auf PancakeSwap.
{% endhint %}

### 4. Kann ich Stablecoins zwischen Chains swappen?

Ja – Sie können Stablecoins wie USDC, USDT und DAI direkt zwischen allen unterstützten Chains swappen und bridgen.

Sie haben zwei Optionen:

1.  **Direktes Bridging:**

    Unterstützte Stablecoins (wie USDC, USDT usw.) direkt von einer Chain zu einer anderen bridgen.
2.  **Gegen andere Token swappen:**

    Sie können einen Stablecoin auch gegen beliebige andere auf der Ziel-Chain unterstützte Token mithilfe der Liquiditätspools von PancakeSwap swappen – entweder vor oder nach dem Bridging.

{% hint style="info" %}
**Hinweis:** Unterstützte Stablecoins für direktes Bridging können je nach Chain variieren.
{% endhint %}

### 5. Werden meine Swaps PCSX verwenden?

Nein – PCSX wird für die Abwicklung von Cross-Chain Swaps nicht unterstützt.

Cross-Chain Swaps auf PancakeSwap werden ausschließlich über folgende Kanäle geleitet:

* **PancakeSwap-Liquiditätspools** (v2, v3, Infinity, StableSwap) für On-Chain-Swaps, und
* **Across- & Relay-Protokolle** für das Bridging von Assets zwischen Chains.

PCSX kann nicht zur Abwicklung oder Weiterleitung eines Teils einer Cross-Chain-Swap-Transaktion verwendet werden.

### 6. Gibt es ein Mindest- oder Höchstlimit für den Swap-Betrag?

Ja – sowohl Mindest- als auch Höchstlimits gelten für Cross-Chain-Transaktionen.

* **Höchstlimit:**\
  Hängt von der verfügbaren Bridge-Liquidität für den ausgewählten Token und die ausgewählte Chain ab. Dieser Wert kann sich in Echtzeit je nach Netzwerk- und Liquiditätsbedingungen ändern.
* **Mindestlimit:**\
  Festgelegt, um sicherzustellen, dass es für Relayer wirtschaftlich sinnvoll ist, die Bridge-Transaktion zu verarbeiten.

{% hint style="info" %}
**Hinweis:** Die genauen Mindest- und Höchstlimits variieren je nach Bridge-Token. Wenn Ihr Transaktionsbetrag außerhalb des zulässigen Bereichs liegt, zeigt die Oberfläche eine klare Fehlermeldung an und fordert Sie auf, den Betrag anzupassen.
{% endhint %}
