# Farms

PancakeSwap Infinity Farming ist eine einfache, gaseffiziente Möglichkeit für Nutzer, Liquiditätsbelohnungen zu verdienen, ohne ihre LP-Token staken zu müssen. Sobald Liquidität zu einem berechtigten Pool hinzugefügt wird, beginnen die Belohnungen automatisch zu akkumulieren.

#### ⚙️ Funktionsweise

Hier ist eine kurze Übersicht, wie das System Belohnungen verfolgt und verteilt:<br>

**✅ Kein Staking erforderlich**

* Halten Sie einfach Ihre LP-Position in Ihrer Wallet.
* Sie müssen Ihre Assets nicht sperren oder mit zusätzlichen Smart Contracts interagieren.
* Sie beginnen automatisch Belohnungen zu verdienen, wenn Sie Liquidität hinzufügen.

#### 📈 Belohnungsverteilung

* Nur In-Range-Positionen (solche, die aktive Liquidität bereitstellen) erhalten Belohnungen.
* Belohnungen sind proportional zu den Gebühren, die Ihre Position in jeder Periode (Epoche genannt) verdient hat.

#### ⏳ Was ist eine Epoche?

* Eine Epoche ist ein festes Zeitfenster – derzeit auf 8 Stunden festgelegt.
* Belohnungen werden nach jeder Epoche berechnet und verteilt.
* Epochen sind derzeit um 00:00, 08:00 und 16:00 Uhr UTC angesetzt.

***

#### 🔄 Farming & Einfordern-Prozess

1. **Positionen verfolgen:** Das Backend-System überwacht Ihre LP-Positionen über alle Farms hinweg.
2. **Belohnungsberechnung:** Am Ende jeder Epoche:
   1. Berechnet das System Ihre Belohnungen basierend auf Ihrer Liquidität und den generierten Gebühren.
   2. Es verarbeitet die Belohnungen in einen Merkle-Baum und übermittelt eine Merkle-Wurzel an einen Smart Contract.
3. **Einspruchsfrist:**
   1. Nach der Veröffentlichung der Merkle-Wurzel beginnt die 1-stündige Einspruchsfrist.
   2. Während der Einspruchsfrist:
      1. Können die neu berechneten Belohnungen nicht eingefordert werden.
      2. Bleiben Belohnungen aus früheren Epochen weiterhin zum Einfordern verfügbar.
      3. Automatisierte und von der Community betriebene Verifizierungstools prüfen die Genauigkeit der veröffentlichten Daten. Wenn Abweichungen festgestellt werden, kann ein Einspruch erhoben werden, um fehlerhafte Verteilungen zu verhindern.
4. **Belohnungen einfordern:**
   1. Sobald die Einspruchsfrist endet, können Sie Ihre Belohnungen für die neueste Epoche einfordern.
   2. Alle ausstehenden Belohnungen über alle Farms können in einer einzigen, gaseffizienten Transaktion eingefordert werden.
5. **Nicht eingeforderte Belohnungen werden übertragen:**
   1. Alle nicht eingeforderten Belohnungen werden auf nachfolgende Epochen übertragen. Jede Aktualisierung enthält frühere Belohnungen und stellt sicher, dass keine Einnahmen verloren gehen oder verfallen.

{% hint style="info" %}
Engere Liquiditätsspannen führen generell zu höheren Einnahmen, erhöhen jedoch die Wahrscheinlichkeit, dass eine Position aus dem Range herausfällt und nicht mehr für Belohnungen berechtigt ist.
{% endhint %}

#### 🌱 Zusammenfassung

✅ Kein Staking\
✅ Gaseffizientes Einfordern\
✅ Regelmäßige Belohnungsaktualisierungen\
✅ Fairer und transparenter Einspruchsprozess\
✅ Belohnungen akkumulieren, bis Sie zum Einfordern bereit sind
