# Referenz-Agent — Order/Intents Settlement Agent

> Ein ERC-8183 Provider-Agent, der jeweils einen einzelnen Swap-Intent-Job erfüllt, indem er diesen über die PancakeSwap-Aggregation weiterleitet und das Ziel-Token direkt an den Client liefert.

### 0. Zuordnung zu ERC-8183

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) definiert einen **Job** mit drei Rollen und Zuständen: Open → Funded → Submitted → Terminal. BNBs **BNBAgent SDK** ist die Live-Implementierung.

| Rolle                                                         | In diesem Agent                                                                                                                                      |
| ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Client** (Agent-A)                                          | veröffentlicht einen Swap-Intent: "Tausche X von Token A → Token B, liefere mir ≥ `minOut`", hinterlegt den Input + ein Trinkgeld als Sicherheit      |
| **Provider** (Agent-B) — **dies ist unser Referenz-Agent**    | stellt ein Angebot über **PancakeSwap-Aggregation** und führt, sofern er `minOut` erreichen oder übertreffen kann, den Swap aus und liefert Token B an den Client |
| **Evaluator**                                                 | überprüft, ob der Client eine Token-B-Menge ≥ `minOut` erhalten hat; gibt das Trinkgeld frei (oder erstattet dem Client)                             |

Das Ergebnis ist objektiv messbar ("Hat der Client ≥ `minOut` erhalten?"), was genau erklärt, warum dies für ERC-8183 geeignet ist, während der Rebalancer dies nicht war.

***

### 1. Zweck & Kurzfassung

> Ein **Provider**-Agent, der jeweils einen einzelnen Swap-Intent-Job erfüllt, indem er diesen über die PancakeSwap-Aggregation weiterleitet und das Ziel-Token direkt an den Client liefert — und nichts weiter.

***

### 2. Was der Agent tun DARF (Fähigkeiten-Allowlist)

| # | Fähigkeit                   | Schnittstelle                                                    | Hinweise                                                                              |
| - | --------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| A | Offene Jobs entdecken        | BNBAgent SDK (ERC-8183-Registry)                                 | Nur-Lesen; Filterung auf Swap-Intent-Jobs, die er bedienen kann                       |
| B | Route anfragen               | **PancakeSwap-Aggregation** (Aggregator API / Smart Router)      | Nur-Lesen; bester Preis über V3                                                       |
| C | Job annehmen                 | BNBAgent SDK (Funded → committed)                                | Nur wenn sein aktuelles Angebot ≥ `minOut` und Trinkgeld ≥ Mindestbetrag              |
| D | Swap ausführen               | PancakeSwap-Router                                               | Input aus Job-Sicherheit gezogen; **Output-Empfänger = der Client**, in einer Transaktion |
| E | Ergebnis einreichen          | BNBAgent SDK (→ Submitted)                                       | Der Settlement-Transaktions-Hash als Nachweis                                         |
| F | Trinkgeld beanspruchen       | ERC-8183-Sicherheit / x402                                       | Nur nachdem der Evaluator den Job als Terminal markiert hat                            |

**Das Ergebnis jeder Abwicklung geht direkt an den Client. Das einzige Einkommen des Agents ist das Trinkgeld des Jobs.**

***

### 3. Feste Sicherheitsvorgaben (Voraussetzung für das Listing)

| Sicherheitsvorgabe                           | Regel                                                                                                                                                                    |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Niemals annehmen, was nicht erfüllt werden kann** | Einen Job nur annehmen, wenn ein _aktuelles_ Angebot `minOut` übertrifft. Andernfalls den Job im Funded-Zustand für einen anderen Provider belassen.                   |
| **Neu anbieten bei Ausführung**              | Unmittelbar vor der Abwicklung neu anbieten; abbrechen, wenn die Route `minOut` nicht mehr erreicht (keine veralteten Angebote).                                         |
| **Atomare Abwicklung**                       | Pull-from-Sicherheit → Swap → Lieferung an Client in **einer Transaktion**, Output-Empfänger = Client. Der Agent darf Client-Gelder nie über einen fehlgeschlagenen Schritt hinaus halten. |
| **Kursabweichung**                           | Ausführungs-Kursabweichung begrenzt; gelieferter Betrag muss nach Kursabweichung noch ≥ `minOut` sein, sonst wird die Transaktion zurückgesetzt. Niemals `amountOutMin = 0`. |
| **Deadline**                                 | Kurze Deadline für die Settlement-Transaktion (≤ 5 Min.); eigene Deadline des Jobs einhalten.                                                                            |
| **Min. Trinkgeld / Max. Wert**               | Jobs unterhalb einer Trinkgeld-Untergrenze oder oberhalb eines Job-Wert-Limits nicht annehmen.                                                                           |
| **Token-Safelist**                           | Nur Jobs bedienen, deren Token auf der PancakeSwap-Token-Liste stehen (Schutz gegen Honeypot / gefälschte Token).                                                        |
| **Single-Job-Parallelität (v1)**             | Jeweils nur einen Job erfüllen; keine Überkapazität.                                                                                                                     |
| **Gas-Vorbedingung**                         | Vor der Annahme sicherstellen, dass genug BNB für die vollständige Abwicklung vorhanden ist.                                                                             |
| **Idempotent**                               | Einen bereits Submitted/Terminal-Job nicht doppelt einreichen oder erneut erfüllen.                                                                                      |

Wenn eine Regel nicht erfüllt werden kann, **Job überspringen** — niemals eine Abwicklung erzwingen.

***

### 4. Außerhalb des Geltungsbereichs — der Agent DARF NICHT

1. **Client-Gelder für etwas anderes als den angegebenen Swap verwenden.** Output-Empfänger ist immer der Client.
2. **Eigenes Inventar einsetzen / Hauptrisiko übernehmen.** v1 ist **nur Sicherheits-Pull** — er leitet den hinterlegten Input des Clients weiter; er füllt nicht aus seinem eigenen Guthaben.
3. **Über Nicht-PancakeSwap- oder nicht verifizierte Contracts routen** oder außerhalb der PancakeSwap-Aggregation abwickeln.
4. **Jobs mit nicht-safegelisteten Token bedienen** oder (v1) skalierte-UI- / RWA-Token (§5).
5. **Hebel, Perps, Margin oder Lending verwenden.**
6. **Ein Ergebnis einreichen, das nicht tatsächlich erfüllt wurde** (keine falschen Beglaubigungen) oder **eigene Jobs bewerten** (Interessenkonflikt).
7. **Owner/Admin-Funktionen aufrufen** bei PancakeSwap oder den ERC-8183-Contracts.
8. **Dauerhafte Token-Genehmigungen aufrechterhalten** über eine einzelne Abwicklung hinaus; Genehmigungen auf den Job-Betrag beschränken.

***

### 5. PancakeSwap-spezifische Logik (Anwendungskorrektheit)

* **Über PancakeSwap-Aggregation routen**, nicht über einen einzelnen Pool — beste Ausführung über V2 / V3 / Stable ist das eigentliche Wertversprechen ("bester Preis gewinnt das Trinkgeld").
* **Atomar an den Client liefern**, indem die `recipient`-Adresse des Routers auf die Client-Adresse gesetzt wird; niemals ein zweistufiges "Swap zu sich selbst, dann Transfer".
* **Angebots-Aktualität** — der On-Chain-Preis ändert sich zwischen Entdeckung und Abwicklung; bei Ausführung neu anbieten (Sicherheitsvorgabe §3).
* **`minOut` ist in rohen Einheiten.** Bei **skalierten-UI- / ERC-8056-Token** (Binance Stock Tokens / RWA-Aktien) gilt: roh ≠ angezeigt; fehlerhafte Handhabung liefert still falsche Beträge. **Skalierte-UI-Token aus v1 ausschließen**, bis die Entwicklung die Verarbeitung in rohen Einheiten Ende-zu-Ende bestätigt.
* Das **Kursabweichungs-Minimum** beim Settlement-Swap muss so abgeleitet werden, dass der _gelieferte_ Betrag ≥ `minOut` ist, unter Berücksichtigung der Trinkgeld-/Gebührenaufteilung.

***

### 6. Fehler- & Wiederherstellungsverhalten

* **Angebot erfüllt `minOut` bei Ausführung nicht** → vor/atomar mit dem Sicherheits-Pull abbrechen; der Job bleibt für einen anderen Provider im Funded-Zustand. Kein Teilstatus.
* **Bereits Submitted/Terminal** → überspringen (idempotent).
* **Settlement-Transaktion wird zurückgesetzt** → Job bleibt für andere einlösbar; der Agent dokumentiert den Fehler und fährt fort.
* **Wiederholte Fehler bei einem Job** → diesen Job lokal auf die Sperrliste setzen und Alarm auslösen, anstatt in einer Wiederholungsschleife zu versuchen.

***

### 7. Integrationspunkte (der BNB / ERC-8183-Teil)

Diese werden von BNB Agent Studio / BNBAgent SDK bereitgestellt, nicht von PancakeSwap entwickelt — aber die Spezifikation hängt von ihnen ab:

* **Job-Lebenszyklus** (discover Open → accept Funded → Submitted → claim) über BNBAgent SDK.
* **Provider-Identität** über ERC-8004.
* **Sicherheit + Auszahlung** über die ERC-8183-Sicherheit / x402.
* **Evaluator** — das Prädikat muss lauten: "Client's Token-B-Guthaben ist um ≥ `minOut` gestiegen." Mit BNB bestätigen, **wer den Evaluator betreibt** (neutral/Protokoll vs. Client) und ob das Prädikat On-Chain durchsetzbar ist.

***

### 8. Empfohlene v1-Ausrichtung & offene Entscheidungen

1. **Nur Sicherheits-Pull, jeweils ein Job, nur Token-Safelist, keine skalierten-UI-Token.** Kleinstmögliche sichere Oberfläche für das Listing beim Launch.
2. **PancakeSwap Swap-Schnittstelle bestätigen** — die **Aggregator (`aggr`) HTTP API** vs. das **Smart Router SDK**. Jerrys Hinweis lautet "pcs aggr api verwenden"; muss bestätigt werden, welche der Agent aufruft, da dies die Integration ändert (und ob der Leitfaden einen Aggregationsabschnitt benötigt).
3. **Den Sicherheits-Mechanismus mit BNB bestätigen** — kann der Provider den hinterlegten Input des Clients ziehen, um den Swap zu routen, und ist die Lieferung-an-Client als Ergebnis durchsetzbar?
4. **Evaluator-Eigentümer und Prädikat bestätigen** (§7).

> Entwicklungs-Freigabe vor dem Listing: atomarer Sicherheits-Pull → Swap → Deliver-to-Client-Routing; Requote-bei-Ausführung; `minOut`-nach-Kursabweichung-Berechnung; Safelist-Durchsetzung; idempotente Job-Verarbeitung.
