# Come usare gli Ordini Limite

Gli ordini limite con guadagno di commissioni su PancakeSwap funzionano in modo diverso dagli ordini limite tradizionali. Quando un utente inserisce un ordine limite, sta effettivamente fornendo **Liquidità unilaterale** a un pool PancakeSwap Infinity.

Man mano che il prezzo di mercato si muove, gli Swap nel pool possono utilizzare la Liquidità dell'utente. Quando ciò accade, i token depositati vengono completamente convertiti nei token di output, e l'utente riceve:

* I token di output, e
* Le commissioni di trading guadagnate dagli Swap eseguiti contro la loro Liquidità.

***

**Esempio: Vendita di BNB per USDT**

* **Prezzo corrente nel pool BNB/USDT:** 600 USDT per BNB
* **Prezzo target / limite dell'utente:** 700 USDT per BNB

Processo:

1. L'utente imposta un ordine limite per vendere BNB a 700 USDT.
2. Il suo BNB viene depositato nel tick più vicino al prezzo di 700 USDT per BNB nel pool.
3. Quando il prezzo di mercato esterno raggiunge 700 USDT, il prezzo del pool si adegua per corrispondere (grazie alle opportunità di arbitraggio / prezzi migliori).
4. A quel punto, il BNB dell'utente viene scambiato in USDT.
5. Durante questo processo, l'utente guadagna commissioni da ogni Swap che consuma la sua Liquidità.
6. Una volta che la Liquidità è completamente consumata, l'USDT convertito (più le commissioni) viene automaticamente prelevato e inviato al Portafoglio dell'utente.

***

### Guida passo per passo

Scegli una coppia di token (es. BNB/CAKE) e l'importo che desideri vendere / acquistare

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Imposta il tuo prezzo target / limite

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Inserisci l'ordine limite e clicca su "Confirm". La Liquidità viene inserita a tuo nome nel tick più vicino al prezzo limite

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Una volta che il prezzo del pool raggiunge il tuo target, il tuo ordine viene eseguito. I token di output desiderati + le commissioni vengono automaticamente prelevati e inviati al tuo Portafoglio.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Stato dell'Ordine

Puoi visualizzare lo stato del tuo ordine cliccando qui

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Il tuo ordine può trovarsi in uno dei seguenti stati:**

| Stato           | Descrizione                                                                              |
| ---------------- | ---------------------------------------------------------------------------------------- |
| In Attesa          | In attesa che il prezzo raggiunga il tuo target                                                   |
| Eseguito           | Ordine eseguito e fondi inviati al tuo Portafoglio                                             |
| Parzialmente Eseguito | Solo una parte del tuo ordine è stata eseguita. Terrai entrambi i token (es. parte BNB, parte USDT) |
| Cancellato        | Hai cancellato l'ordine. Tutti i tuoi fondi ti vengono restituiti                              |

### FAQ

**D: Devo pagare commissioni per inserire un ordine limite?**

R: No. Invece, guadagni lo 0,1% in commissioni di trading quando il tuo ordine viene eseguito.

**D: Posso inserire ordini per qualsiasi coppia?**

R: Al lancio, solo alcune coppie selezionate sono supportate. Altre coppie verranno aggiunte in seguito.

**D: Qual è la dimensione minima dell'ordine?**

R: $50. Questo previene ordini minuscoli che potrebbero comportare eccesso di gas.&#x20;

**D: Cosa succede se solo una parte del mio ordine viene eseguita?**

R: Terrai entrambi i token. Puoi cancellare in qualsiasi momento e prelevare entrambi i token più le commissioni guadagnate.

**D: Il mio ordine è stato eseguito ma non ho ancora ricevuto i fondi nel mio Portafoglio?**

R: In scenari molto rari questo potrebbe accadere, ma i tuoi fondi sono sempre al sicuro. Usa semplicemente il pulsante "Withdraw" nell'UI dei dettagli dell'ordine per riscattare i fondi manualmente.
