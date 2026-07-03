# ❓ FAQ sul Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Prima del Bridging

1.  **Posso usare portafogli mobile o portafogli diversi da MetaMask per fare il Bridge di CAKE?**

    Attualmente, il Bridging CAKE di PancakeSwap supporta Coinbase Wallet, MetaMask e portafogli compatibili con MetaMask. Il supporto per altri portafogli sarà disponibile a breve.

    _Suggerimento:_ Per evitare il rischio di copiare e incollare chiavi private o frasi seed, ti consigliamo di creare nuovi portafogli tramite estensioni per portafoglio desktop per il Bridging.
2.  **Perché un percorso o un token non è disponibile?**

    Alcuni percorsi dipendono dalla capacità del Bridge, dal supporto del token o dalla liquidità. Riprova più tardi o prova con un fornitore diverso. I token disponibili per chain sono mostrati direttamente nell'interfaccia Bridge.
3.  **Ricevo un errore quando invio la transazione di Bridging.**

    Prova a inserire l'importo manualmente invece di usare il pulsante "MAX", e rimuovi i decimali dall'importo se necessario.
4.  **Perché la mia quotazione Bridge mostra "Insufficient X to cover native fee"**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Il Bridging richiede commissioni gas pagate nel token nativo della chain di origine, ad esempio:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Assicurati di avere abbastanza token nativi nel portafoglio di origine per coprire le commissioni e completare la transazione.
5.  **Perché il pulsante mostra "X CAKE Exceeded"?**

    Esiste un limite di capacità giornaliero per il Bridge di CAKE tra BSC e Aptos per garantire la sicurezza. Prova con un importo inferiore o aspetta e riprova più tardi. I limiti vengono adeguati dinamicamente dai Chefs in base alla domanda.
6.  **Perché non riesco a trovare un token specifico?**

    Il token potrebbe non essere supportato sul percorso scelto o potrebbe essere privo di liquidità. Prova un'altra chain o un importo diverso.
7.  **Posso fare il Bridge da BNB Chain a Ethereum ma a un indirizzo diverso?**

    No, per ragioni di sicurezza, il Bridging funziona solo tra lo stesso indirizzo sulle chain EVM.
8.  **Perché non posso fare il Bridge di meno di 0,00000001 CAKE?**

    I token Aptos, incluso CAKE su Aptos, hanno un massimo di 8 cifre decimali. Le transazioni inferiori a 0,00000001 verranno rifiutate o arrotondate per difetto. Questo vale anche per il Bridging su Ethereum. Qualsiasi importo residuo rimarrà nel tuo portafoglio di origine.

***

## Dopo il Bridging

1.  **Posso annullare un trasferimento Bridge dopo la conferma?**

    No, una volta avviata, la transazione Bridge è gestita dal fornitore e non può essere annullata. Per invertirla, fai il Bridge degli asset indietro tramite una nuova transazione.
2.  **Cosa succede se la mia transazione è bloccata in "pending"?**

    Il Bridging può richiedere fino a 30 minuti. Controlla lo stato della transazione cercando il suo hash nell'esploratore del rispettivo fornitore Bridge:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    Se ancora in attesa dopo 60 minuti, contatta i nostri admin tramite i [canali social](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **Non ho ricevuto il mio CAKE. Cosa devo fare?**
   * Quando fai il Bridge di CAKE su Aptos per la prima volta, potresti dover **richiedere manualmente** il tuo CAKE. Assicurati che il tuo portafoglio Aptos abbia abbastanza APT per il gas. Consulta la [guida al Bridging su Aptos](https://docs.pancakeswap.finance/bridge/bridging/aptos) e la [spiegazione di Aptos](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Quando fai il Bridge verso BNB Chain o Ethereum, alcuni portafogli richiedono di aggiungere manualmente l'indirizzo del token CAKE per visualizzare il saldo. Ad esempio, segui questa [guida MetaMask](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) - altri portafogli dovrebbero avere procedure simili.
   * Se non vedi ancora il tuo CAKE dopo 60 minuti, contatta i nostri admin tramite i [canali social](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
