# Wie CAKE.PAD-Steuern bei Overflow-Verkäufen funktionieren – mit Beispiel

1. Steuern werden nur erhoben, **wenn das** CAKE.PAD-Event **überzeichnet ist**
   1. Überzeichnung = Gesamteinzahlungen aller Nutzer > Fundraising-Zielbetrag.
   * Die Steuer wird ausschließlich von den überschüssigen eingesetzten Mitteln der Teilnehmer abgezogen. Das CAKE.PAD-Partnerprojekt zahlt keine Gebühren.
   * Das CAKE.PAD-Partnerprojekt erhält 100 % seines angestrebten Fundraising-Betrags.
   * CAKE.PAD-Steuern werden in CAKE erhoben, und 100 % davon werden verbrannt.
   * Gebühren basieren auf der **gesamten Zeichnungsrate des Pools** (% des Fundraising-Ziels):

**Überzeichnungsrate <> Gebührenstufe**&#x20;

<table data-full-width="false"><thead><tr><th>Überzeichnungsrate</th><th>Gebührenstufe</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1,00 %</td></tr><tr><td>≥ 50x</td><td>0,80 %</td></tr><tr><td>≥ 100x</td><td>0,60 %</td></tr><tr><td>≥ 150x</td><td>0,50 %</td></tr><tr><td>≥ 200x</td><td>0,40 %</td></tr><tr><td>≥ 250x</td><td>0,30 %</td></tr><tr><td>≥ 300x</td><td>0,25 %</td></tr><tr><td>≥ 400x</td><td>0,20 %</td></tr><tr><td>≥ 500x</td><td>0,15 %</td></tr><tr><td>≥ 650x</td><td>0,12 %</td></tr><tr><td>≥ 800x</td><td>0,10 %</td></tr><tr><td>≥ 1500x</td><td>0,05 %</td></tr></tbody></table>



2. **Zeitpunkt – Wann wird die Steuer erhoben?**

* Die Steuer wird **am Ende des** CAKE.PAD-Events erhoben, wenn der Nutzer seine Zuteilung einfordert.
* Selbst wenn ein Nutzer früh einzeichnet (z. B. wenn die Zeichnung bei 30 % des Fundraising-Ziels liegt), basiert die endgültige Steuer auf der **endgültigen Pool-Überzeichnungsrate**.
  * Beispiel: Wenn der Pool am Ende 50-fach überzeichnet ist, gilt die 50x-Gebührenstufe (0,8 %).

#### Berechnungsschritte

1.  **Nutzerzuteilung** = Anteil des gesamten CAKE.PAD-Partner-Token-Pools, den der Nutzer erhält

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Vom Nutzer bezahlter Betrag** = Anteil der Einzahlung des Nutzers, der zum Einlösen von CAKE.PAD-Partner-Token verwendet wird

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Rückerstattungsbetrag** = Überschuss aus der Einzahlung des Nutzers, der nicht für den CAKE.PAD-Partner-Token-Kauf verwendet wird

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Steuerbetrag** = Abzug vom Rückerstattungsbetrag des Nutzers

    * Die Gebührenstufe basiert auf dem % des Fundraising-Ziels (siehe Tabelle oben).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Endgültiges Ergebnis für den Nutzer**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (falls zutreffend, sonst = refund_amount)
    ```

#### Numerisches Beispiel

* **Fundraising-Ziel (raisingAmountPool):** 100 CAKE
* **Ihre Einzahlung (user\_deposit\_amount):** 10 CAKE
* **Gesamteinzahlungen inkl. Ihrer Einzahlung (totalAmountPool):** 5.100 CAKE (51-fach gezeichnet = 5.100 % des Fundraising-Ziels, entspricht einer 50-fachen Überzeichnungsrate)
  * Entsprechende Gebührenstufe = 0,80 % (basierend auf der Steuersatztabelle oben)

**Schritte:**

1. `user_allocation = 10 / 5.100 = 0,00196 (0,196 % Pool-Zuteilung)`
2. `user_pay_amount = 100 × 0,00196 = 0,196 CAKE`
3. `refund_amount = 10 − 0,196 = 9,804 CAKE`
4. `tax_amount = 9,804 × 0,008 = 0,0784 CAKE`
5. `final_refund = 9,804 − 0,0784 = ~9,72 CAKE`

**Endgültige Beträge für den Nutzer**

1. **Token-Zuteilung:** CAKE.PAD-Partner-Token im Wert von 0,196 CAKE
2. **Endgültige Rückerstattung:** ~9,72 CAKE (aus 10 CAKE Einzahlung − 0,196 CAKE für Token-Zuteilung − 0,0784 CAKE Steuer)
