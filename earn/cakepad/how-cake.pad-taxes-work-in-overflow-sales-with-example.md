# Come funzionano le Tasse CAKE.PAD nelle Vendite Overflow – Con Esempio

1. Le tasse vengono addebitate **solo se** l'evento CAKE.PAD **è sovrasottoscritto**
   1. Sovrasottoscrizione = Depositi totali di tutti gli utenti > Importo obiettivo di raccolta.
   * La tassa viene detratta solo dai fondi in eccesso impegnati dai partecipanti. Nessuna commissione viene pagata dal progetto partner CAKE.PAD.
   * Il progetto partner CAKE.PAD riceve il 100% dell'importo obiettivo di raccolta.
   * Le tasse CAKE.PAD vengono raccolte in CAKE, e il 100% di esse verrà bruciato.
   * Le commissioni si basano sul **tasso totale di sottoscrizione del Pool** (% dell'obiettivo di raccolta):

**Tasso di sovrasottoscrizione <> Livello di commissione**&#x20;

<table data-full-width="false"><thead><tr><th>Tasso di sovrasottoscrizione</th><th>Livello di commissione</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1,00%</td></tr><tr><td>≥ 50x</td><td>0,80%</td></tr><tr><td>≥ 100x</td><td>0,60%</td></tr><tr><td>≥ 150x</td><td>0,50%</td></tr><tr><td>≥ 200x</td><td>0,40%</td></tr><tr><td>≥ 250x</td><td>0,30%</td></tr><tr><td>≥ 300x</td><td>0,25%</td></tr><tr><td>≥ 400x</td><td>0,20%</td></tr><tr><td>≥ 500x</td><td>0,15%</td></tr><tr><td>≥ 650x</td><td>0,12%</td></tr><tr><td>≥ 800x</td><td>0,10%</td></tr><tr><td>≥ 1500x</td><td>0,05%</td></tr></tbody></table>



2. **Periodo di tempo – Quando viene addebitata la tassa**

* La tassa viene addebitata alla **fine dell'evento** CAKE.PAD, quando l'utente riscatta la propria allocazione.
* Anche se un utente si iscrive in anticipo (ad es. quando la sottoscrizione è al 30% dell'obiettivo di raccolta), la tassa finale si basa sul **livello finale di sovrasottoscrizione del Pool**.
  * Esempio: Se il Pool finisce con una sovrasottoscrizione di 50x, la tassa applicabile è quella del livello 50x (0,8%).

#### Passaggi di calcolo

1.  **Allocazione dell'utente** = % del Pool totale di token partner CAKE.PAD che l'utente riceve

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Importo pagato dall'utente** = Porzione del deposito dell'utente utilizzata per riscattare i token partner CAKE.PAD

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Importo del rimborso** = Eccesso del deposito dell'utente non utilizzato per l'acquisto di token partner CAKE.PAD

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Importo della tassa** = Detrazione applicata sull'importo rimborsato all'utente

    * Il livello di commissione si basa sulla % dell'obiettivo di raccolta (vedi tabella sopra).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Output finale per l'utente**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (if applicable, else = refund_amount)
    ```

#### Esempio numerico

* **Obiettivo di raccolta (raisingAmountPool):** 100 CAKE
* **Il tuo deposito (user\_deposit\_amount):** 10 CAKE
* **Depositi totali incluso il tuo deposito (totalAmountPool):** 5.100 CAKE (51x sottoscritto = 5.100% dell'obiettivo di raccolta, implica un tasso di sovrasottoscrizione di 50x)
  * Livello di commissione corrispondente = 0,80% (basato sulla tabella delle aliquote fiscali sopra)

**Passaggi:**

1. `user_allocation = 10 / 5,100 = 0.00196 (0.196% pool allocation)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**Importi finali ricevuti dall'utente**

1. **Allocazione token:** 0,196 CAKE in valore di token partner CAKE.PAD
2. **Rimborso finale:** ~9,72 CAKE (da 10 CAKE depositati − 0,196 CAKE per l'allocazione token − 0,0784 CAKE di tassa)
