# 🎁 Pancake Gifts

### 🎯 Was ist Pancake Gifts?

**Pancake Gifts** ermöglicht es jedem, Token – einschließlich optionalem Gas – an Freunde, Nutzer oder Communities über einen einfachen **Link** oder **QR-Code** zu senden. Es ist ein einfaches, sicheres und gasfreies Erlebnis für den Empfänger.

Es wurde entwickelt, um den Einstieg in die Kryptowelt so einfach zu machen wie das Versenden einer Nachricht – kein Wallet-Funding, kein Bridging, keine Vorabgebühren.

### 🤝 Warum wir Pancake Gifts entwickelt haben

Der Einstieg in Web3 ist immer noch mit viel Reibung verbunden. Neue Nutzer geben oft auf, bevor sie überhaupt beginnen, aufgrund von:

* **Kein Gas in der Wallet** → Keine On-Chain-Aktion möglich
* **Keine Gelder auf der richtigen Chain** → Bridging erforderlich, bevor dApps genutzt werden können
* **Krypto kaufen müssen, nur um zu beginnen** → Erfordert CEX-Registrierung oder Fiat-On-Ramp

Pancake Gifts beseitigt diese Hindernisse durch:

* ✅ **Einbeziehung von nativen Gas-Token** in das Geschenk, damit Empfänger sofort interagieren können
* ✅ **Vorabfinanzierung der Gasgebühr** (Absender zahlt eine kleine Gebühr)
* ✅ **Einlösung über einen einfachen Link oder QR** möglich – kein komplexes Onboarding



Es ist ein Werkzeug für:

* Neue Nutzer, die on-chain starten möchten
* Web3-native Communities, die **die Adoption steigern, Nutzer belohnen oder Kampagnen** auf freundlichere Weise durchführen möchten

***

### ⚙️ Funktionsübersicht

| Funktion                    | Beschreibung                                                          |
| --------------------------- | --------------------------------------------------------------------- |
| **Chain-Unterstützung**     | BNB Chain (Ersteinführung)                                            |
| **Geschenkcode-Typen**      | Link **oder** QR-Code                                                 |
| **Einmalige Nutzung**       | Jeder Code kann nur einmal eingelöst werden                           |
| **Token-Unterstützung**     | Max. 2 Token: 1 BEP-20 (erforderlich), 1 nativer Gas-Token (optional) |
| **Individuelle Beträge**    | Unterschiedliche Werte pro Token festlegbar                           |
| **Gasgebühr für Einlösung** | Absender zahlt Gas vorab (\~0,05 $ in BNB)                            |
| **Geschenkverlauf**         | Nutzer können alle gesendeten Geschenke, Einlösestatus, Ablauf sehen  |
| **Sicherheitsprüfungen**    | Token mit Übertragungsgebühren oder komplexer Logik sind nicht erlaubt |

### 🚫 Einschränkungen

1. **Ein Geschenk pro Code** – Massengeschenke werden noch nicht unterstützt.
2. **Geschenke können nicht wiederhergestellt werden** – Einmal storniert oder abgelaufen, können sie nicht erneut verwendet werden.
3. **Nicht unterstützte Token werden blockiert** – Token mit Übertragungsgebühren oder besonderer Logik zeigen bei der Erstellung einen Fehler an.
4. **Fehlgeschlagene Einlöseversuche werden wiederholt** – Das Backend versucht es einige Male erneut. Bei anhaltenden Fehlern wird das Geschenk als **nicht einlösbar** markiert und muss manuell storniert werden, um Gelder zurückzuerhalten.
5. **Geschenk muss auf derselben Chain eingelöst werden** – z. B. muss ein ETH-Geschenk auf Ethereum eingelöst werden. Cross-Chain-Einlösung wird noch nicht unterstützt.

***

### 🕒 Stornierung und Ablauflogik

Geschenke folgen einem definierten Lebenszyklus basierend auf Status und Zeit:

#### Manuelle Stornierung

* Der **Ersteller** kann jedes Geschenk stornieren, das noch **nicht eingelöst** wurde und **innerhalb des Ablaufzeitraums** liegt.
* Token (abzüglich der ursprünglichen Gasgebühr für die Einlösung) werden an den Absender zurückgegeben.
* Stornierte Geschenke können **nicht** reaktiviert oder erneut verwendet werden.

#### Automatischer Ablauf

* Geschenke **verfallen automatisch** nach einem vom Nutzer definierten Zeitraum (Standard: 7 Tage).
* Nicht eingelöste Token werden **automatisch** an die Wallet des Absenders zurückgegeben.
* Abgelaufene Geschenke sind ebenfalls nicht wiederverwendbar.

***

### 🔄 Geschenk-Status und ihre Bedeutung

| Status             | Beschreibung                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------ |
| **Ausstehend**     | Geschenk wurde erstellt und wartet auf Einlösung                                           |
| **Eingelöst**      | Geschenk wurde erfolgreich von einem Empfänger eingelöst                                   |
| **Storniert**      | Geschenk wurde manuell vom Absender storniert                                              |
| **Abgelaufen**     | Geschenk hat die Ablaufzeit überschritten, ohne eingelöst zu werden                        |
| **Nicht einlösbar** | Anzahl der Wiederholungsversuche überschritten; Geschenk muss storniert werden, um Gelder zurückzuerhalten |

***

### ⚠️ Fehlerbehandlung und Grenzfälle

1. **Nicht unterstützter Token**
   * Die Geschenkerstellung ist für Token mit Übertragungsgebühren oder besonderer Logik gesperrt.
2. **Gas-Unstimmigkeit**
   * Wenn die **tatsächlichen Einlösegaskosten ≥** der vorausbezahlten Gebühr des Absenders sind, schlägt die Einlösung automatisch fehl, um Übernutzung zu verhindern. Ein erneuter Versuch findet statt, sobald die Gasgebühren im zulässigen Bereich liegen.
3. **Fehlgeschlagene Einlöseversuche**
   * Beim ersten fehlgeschlagenen Einlöseversuch werden Wiederholungsversuche unternommen.
   * Bei anhaltenden Fehlern:
     * Empfänger sieht „Nicht einlösbar"
     * Absender muss das Geschenk manuell stornieren, um Gelder zurückzuerhalten, und der Empfänger muss einen neuen Geschenkcode anfordern.
