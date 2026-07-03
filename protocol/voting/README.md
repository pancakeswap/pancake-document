# 📔 Governance

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Im Rahmen des [Tokenomics 3.0-Updates](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) wurde diese Seite am 15. Mai 2025 aktualisiert
{% endhint %}

Die Abstimmung gibt der PancakeSwap-Community eine Stimme und ermöglicht es der Community, bei der zukünftigen Entwicklung von PancakeSwap mitzuwirken.

Besuchen Sie [PancakeSwaps nationales Abstimmungsportal](https://pancakeswap.finance/voting) und unsere [Forum](https://forum.pancakeswap.finance/)-Seite.

## Abstimmungsmechanismen

:notebook\_with\_decorative\_cover: Zusammenfassung — Was sich geändert hat (nach dem [Tokenomics 3.0-Update](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Governance-Komponente</th><th width="218.01953125">Vor Tokenomics 3.0</th><th width="205.1796875">Nach Tokenomics 3.0</th><th>Status<select><option value="q1dVFsCri7zA" label="✅ Geändert" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Unverändert" color="blue"></option></select></th></tr></thead><tbody><tr><td>Stimmrecht</td><td>1 veCAKE = 1 Stimmrecht</td><td>1 CAKE = 1 Stimmrecht</td><td><span data-option="q1dVFsCri7zA">✅ Geändert</span></td></tr><tr><td>Delegation</td><td>Erlaubt (über veCAKE-Mechanismus)</td><td>Delegation ist nicht erlaubt</td><td><span data-option="q1dVFsCri7zA">✅ Geändert</span></td></tr><tr><td>Schwellenwert für Vorschlagseinreichung</td><td>Snapshot: 100K veCAKE erforderlich</td><td>Snapshot: 100K CAKE erforderlich</td><td><span data-option="q1dVFsCri7zA">✅ Geändert</span></td></tr><tr><td>Core- vs. Community-Vorschläge</td><td>Definierte Rollen und Zwecke für jeden Vorschlagstyp</td><td>Keine Änderung</td><td><span data-option="4AGl26rwjYcI">🔁 Unverändert</span></td></tr><tr><td>Abstimmungszeitraum</td><td>Community: Fest<br>Core: Variabel</td><td>Keine Änderung</td><td><span data-option="4AGl26rwjYcI">🔁 Unverändert</span></td></tr><tr><td>Snapshot-Zeitpunkt</td><td>Beim Block der Vorschlagsveröffentlichung</td><td>Keine Änderung</td><td><span data-option="4AGl26rwjYcI">🔁 Unverändert</span></td></tr><tr><td>Quorum</td><td>Kein Mindest-Quorum</td><td>Keine Änderung</td><td><span data-option="4AGl26rwjYcI">🔁 Unverändert</span></td></tr></tbody></table>

### 1. **Stimmrecht (Geändert)**

* **Alle CAKE-Inhaber haben direkte Stimmrechte.**
* **Das Stimmrecht entspricht direkt der Anzahl der CAKE, die zum Snapshot-Zeitpunkt in der Wallet-Adresse gehalten werden**
  * **1 CAKE = 1 Stimmrecht**
  * **In Syrup Pools gestaktes CAKE zählt nicht** zu Ihrem Stimmrecht, da es zum Zeitpunkt des Snapshots nicht Teil Ihres Wallet-Guthabens ist
  * Snapshot-Guthaben = Gleicher Block, in dem der Vorschlag veröffentlicht wurde
* **Delegation wird nicht mehr unterstützt.** Jeder CAKE-Inhaber muss individuell abstimmen.

### 2. **Vorschlagseinreichung (Unverändert)**

* **So reichen Sie einen Vorschlag ein**
  * Einreichen unter [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Muss enthalten:
    * Titel
    * Inhalt
    * Beschreibung
    * On-Chain-Aktionen (falls erforderlich)
    * Abstimmungsdauer
* Arten von Vorschlägen
  1.  Core-Vorschläge

      * Können nur vom **PancakeSwap Core Team** eingereicht werden.
      * Erfordern eine Abstimmung durch CAKE-Inhaber.
      * Wenn angenommen, werden sie vom PancakeSwap-Team umgesetzt.

      Beispiele

      1. Protokollanpassungen (Produktänderungen, Gebührenänderungen)
      2. Bedeutende Verwendungen von Ökosystem-Wachstumsmitteln, die nicht durch frühere Vorschläge abgedeckt sind
  2. Community-Vorschläge
     * **Community**-Vorschläge werden von der PancakeSwap-Community eingereicht. Sie dienen dazu, Ideen vorzuschlagen und den Standpunkt der Community auszudrücken. Es handelt sich um **unverbindliche Vorschläge** der Community.
     * Jeder mit **100.000 CAKE (Snapshot-Guthaben)** kann einen Vorschlag einreichen.
     * Das PancakeSwap-Team kann starke Vorschläge in zukünftige Core-Vorschläge übernehmen
     * Community-Mitglieder können auch unser [Forum](https://forum.pancakeswap.finance/) nutzen, um Feedback zu geben und Vorschläge an das Protokoll zu machen.

### **3. Abstimmungsdauer (Unverändert)**

* Alle CAKE-Inhaber können **während des Abstimmungsfensters** für jeden Vorschlag abstimmen.
  * Community-Vorschlag: Fest auf 3 Tage festgelegt
  * Core-Vorschlag: Variabel, festgelegt von PancakeSwap
* Ihr Stimmrecht wird durch einen **Snapshot Ihres CAKE-Guthabens im Block festgelegt, in dem der Vorschlag veröffentlicht wurde**.
* **Wenn Sie nach der Veröffentlichung des Vorschlags mehr CAKE hinzufügen, erhöht sich Ihr Stimmrecht für diese spezifische Abstimmung nicht.**

Alle Details finden Sie im [Abstimmungsleitfaden](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Abstimmungsergebnis (Unverändert)**

* Das Ergebnis basiert auf **abgegebenen Gesamtstimmen** (insgesamt für die Abstimmung verwendete CAKE)
* **Es gibt derzeit kein erforderliches Mindest-Quorum** für die Annahme eines Vorschlags.

## Hinweis: Vetorecht

Zum Schutz des Protokolls **behält sich das PancakeSwap Core Team das Recht vor, in kritischen Situationen einzugreifen** — wie Sicherheitsbedrohungen oder Problemen, die den stabilen Betrieb der Plattform gefährden — **ohne dass eine Community-Abstimmung oder ein Snapshot-Poll erforderlich ist**.

In jedem Fall, in dem eine Veto-Aktion getroffen wird, wird das Core Team **eine klare öffentliche Erklärung** der Entscheidung veröffentlichen.

**Mögliche Veto-Aktionen können umfassen:**

1. **Vorübergehendes Pausieren von Smart Contracts**, um dringende Fehler oder Sicherheitslücken zu beheben.
