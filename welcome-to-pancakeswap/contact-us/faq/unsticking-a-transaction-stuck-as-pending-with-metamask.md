---
description: Come "sbloccare" le transazioni in sospeso bloccate nel tuo MetaMask
---

# Risolvere le Transazioni Pending Bloccate su MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Se la tua transazione è bloccata su pending in Metamask e il pulsante “Cancel” non ti aiuta, potresti dover usare questo metodo per liberare la coda.

Questo metodo funziona sostanzialmente sovrascrivendo la transazione bloccata con un'altra transazione a priorità più alta.

### **1. Abilita il Nonce di Transazione Personalizzato**

1\. Apri il plugin MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Clicca sull'icona del cerchio colorato in alto a destra e seleziona **Settings** dal menu a tendina.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Nel menu Settings, seleziona **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Scorri verso il basso fino a trovare **Advanced gas controls**. Attiva l'opzione (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Sempre nelle impostazioni Advanced, continua a scorrere fino a trovare **Customize transaction nonce**. Attiva l'opzione (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Trova la Tua Transazione Bloccata**

Ora andremo a trovare la transazione bloccata e prenderemo nota del “nonce”. È una sorta di identificatore che riutilizzeremo più avanti.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Torna alla pagina principale di MetaMask. Nella scheda “Assets”, trova il tipo di token della tua transazione bloccata (in questo caso, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. Nel menu del token, trova la tua transazione **Pending** nell'area Queue. Clicca sulla transazione per maggiori dettagli.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Cerca la voce **Nonce** e annota questo numero.

### **3. Sovrascrivi la Transazione Bloccata**

Ora creeremo una nuova transazione per sostituire quella bloccata. Personalizzeremo il numero del Nonce, in modo che sia lo stesso di quello che hai appena annotato.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Crea una nuova transazione per sostituire quella bloccata. Questa volta, aumenta la **Transaction Fee**. Qui l'abbiamo aumentata da 9 a 20. Questo renderà più probabile che la tua transazione venga inclusa in un blocco.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Nella pagina di conferma, assicurati che il Gas Price sia ora al nuovo importo più alto.

11\. Trova la voce **CUSTOM NONCE** e cambia il nonce con il numero che hai annotato nel passaggio 8. Ora clicca su Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. La tua nuova transazione dovrebbe ora essere accettata in un blocco. Per verificarlo, apri MetaMask e clicca sulla scheda **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. La tua transazione completata dovrebbe comparire in cima alla lista Activity. Se è ancora indicata come “Pending” in arancione, dovrai attendere ancora un po' oppure ripetere la procedura con una transaction fee (gas price) ancora più alta.

Poiché nessun portafoglio può creare due transazioni con lo stesso nonce, se la transazione sostitutiva va a buon fine, la tua transazione bloccata verrà annullata.<br>
