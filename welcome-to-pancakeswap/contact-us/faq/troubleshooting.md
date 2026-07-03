---
description: Messaggi di errore comuni. Usa la barra laterale ➡️per passare all'errore che stai visualizzando.
---

# Risoluzione degli Errori

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

A volte potresti trovarti di fronte a un problema che non ha una soluzione chiara. Questi suggerimenti per la risoluzione dei problemi potrebbero aiutarti a risolvere i problemi che incontri.

## **Problemi sull'Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

Stai cercando di fare Swap di token, ma la tua tolleranza allo Slippage è troppo bassa o la Liquidità è troppo bassa.

{% tabs %}
{% tab title="Soluzione" %}
1. Aggiorna la pagina e riprova più tardi.
2. Prova a fare Scambio di un importo più piccolo alla volta.
3. Aumenta la tua tolleranza allo Slippage:
   1. Tocca l'icona delle impostazioni nella pagina della Liquidità.
   2. Aumenta leggermente la tua tolleranza allo Slippage e riprova. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Infine, prova a inserire un importo con meno cifre decimali.
{% endtab %}

{% tab title="Motivo" %}
**Di solito accade quando si fanno Scambi di token con Liquidità bassa.**

Ciò significa che non c'è abbastanza disponibilità di uno dei token che stai cercando di fare Swap nel Pool di Liquidità: probabilmente è un token a bassa capitalizzazione che poche persone stanno scambiando.

Tuttavia, c'è anche la possibilità che tu stia cercando di fare Scambio di un token truffa che non può essere venduto. In questo caso, PancakeSwap non è in grado di bloccare un token o restituire i fondi.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Stai cercando di aggiungere/rimuovere Liquidità da un Pool di Liquidità (LP), ma non c'è abbastanza disponibilità di uno dei due token nella coppia.

{% tabs %}
{% tab title="Soluzione" %}
**Aggiorna la pagina e riprova, oppure riprova più tardi.**

Non funziona ancora?

1. Tocca l'icona delle impostazioni nella pagina della Liquidità.
2. Aumenta leggermente la tua tolleranza allo Slippage e riprova.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Motivo" %}
L'errore è causato dal tentativo di aggiungere o rimuovere Liquidità da un Pool di Liquidità (LP) con un importo insufficiente del token A o del token B (uno dei token nella coppia).

Potrebbe essere il caso che i prezzi si aggiornino troppo rapidamente e la tua tolleranza allo Slippage sia troppo bassa.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Soluzione per esperti" %}
OK, quindi sei davvero determinato a risolvere questo problema. Ti sconsigliamo vivamente di farlo a meno che tu non sappia cosa stai facendo.

Al momento non esiste un modo semplice per risolvere questo problema dal sito di PancakeSwap: dovrai interagire direttamente con il contratto. Puoi aggiungere Liquidità direttamente tramite il contratto Router, impostando amountAMin su un valore basso, quindi ritirare tutta la Liquidità.

**Approva il contratto LP**

Vai al contratto del token LP che stai cercando di approvare.\
Ad esempio, ecco la coppia ETH/WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Seleziona **Write Contract**, poi **Connect to Web3** e connetti il tuo Portafoglio. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. Nella **sezione "1. approve"**, approva il token LP per il router inserendo
   1. spender (address): inserisci l'indirizzo del contratto del token LP con cui stai cercando di interagire
   2. value (uint256): -1

**Interroga "balanceOf"**

1. Passa a **Read Contract.**
2. In **5. balanceOf**, inserisci l'indirizzo del tuo Portafoglio e clicca su **Query**.
3. Tieni traccia del numero esportato. Mostra il tuo saldo nell'LP nel formato uint256, che ti servirà nel passaggio successivo.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Aggiungi o Rimuovi Liquidità**

Vai al contratto router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Seleziona **Write Contract** e **Connect to Web3** come sopra.
2. Trova **addLiquidity** o **removeLiquidity** (a seconda di quello che stai cercando di fare)
3. Inserisci gli indirizzi dei token di entrambi i token nell'LP.
4. In **liquidity (uint256)**, inserisci il numero uint256 ottenuto da "balanceOf" sopra.
5. Imposta un **amountAMin** o **amountBMin** basso: prova 1 per entrambi.
6. Aggiungi l'indirizzo del tuo Portafoglio in **to (address)**.
7. La deadline deve essere un epoch time maggiore del momento in cui la transazione viene eseguita.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Questo può causare uno Slippage molto alto e può far perdere all'utente parte dei fondi in caso di Frontrunning
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Riprova, ma conferma (firma e trasmetti) la transazione non appena la generi.

Questo è accaduto perché hai iniziato a effettuare una transazione, ma non l'hai firmata e trasmessa prima che scadesse il termine. Significa che non hai cliccato "Conferma" abbastanza velocemente.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Prova a modificare l'importo nel campo "A" in modo che il simbolo "(stimato)" compaia su "Da". Poi avvia lo Swap immediatamente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Di solito succede quando stai cercando di fare Swap di un token che ha una propria commissione.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Assicurati di avere nel tuo Portafoglio il 30% di token in più rispetto a quelli che intendi scambiare, oppure prova a fare Scambio di un importo inferiore. Se vuoi vendere il massimo possibile, prova con il 70% o il 69% invece del 100%.\
Causato dal design dei token Restorative Rebase come tDoge o tBTC.\
[Scopri come funzionano i token restorative rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Un'altra possibile causa di questo problema è che l'emittente del token malevolo ha semplicemente sospeso il trading per il suo token. Oppure ha reso possibile l'azione di vendita solo per indirizzi di Portafoglio selezionati. Fai sempre le tue ricerche per evitare potenziali frodi. Se il token che stai cercando di fare Swap ma che fallisce con questo codice di errore proviene da un airdrop, è molto probabilmente una truffa. Non eseguire alcuna approvazione di token né seguire alcun link: i tuoi fondi potrebbero essere a rischio se lo fai.

### La transazione non può avere successo

Prova a fare Scambio di un importo più piccolo, oppure aumenta la tolleranza allo Slippage tramite l'icona delle impostazioni e riprova. È causato da Liquidità bassa.

### **Impatto sul Prezzo troppo Alto**

Prova a fare Scambio di un importo più piccolo, oppure aumenta la tolleranza allo Slippage tramite l'icona delle impostazioni e riprova. È causato da Liquidità bassa.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Soluzione" %}
**Se hai ricevuto questo errore durante la rimozione di Liquidità da una coppia BNB:**

Seleziona "Receive WBNB" e riprova.

**Se hai ricevuto questo errore durante il tentativo di fare Swap:**

Contatta il team del progetto del token che stai cercando di fare Swap. \*\*\*\* Questo problema deve essere risolto dal team del progetto.
{% endtab %}

{% tab title="Motivo" %}
**Questo problema (durante lo Swap) è causato da token che hanno codificato il router PancakeSwap V1 nel loro contratto.**

Sebbene questa pratica sia sconsigliabile, la ragione per cui questi progetti lo hanno fatto sembra essere legata alla loro Tokenomics, in cui ogni acquisto invia una percentuale del token agli LP.

I progetti interessati probabilmente non funzioneranno con il router V2: molto probabilmente dovranno creare nuove versioni dei loro token che puntano al nostro nuovo indirizzo del router e migrare i detentori di token esistenti al loro nuovo token.

Raccomandiamo che tutti i progetti che hanno creato tali token si impegnino anche a impedire ai propri utenti di aggiungerli agli LP V2.

L'indirizzo aggiornato del router è [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Durante il tentativo di fare Swap di token, la transazione fallisce e viene visualizzato questo messaggio di errore. Questo errore è stato segnalato su dispositivi mobili che utilizzano Trust Wallet.

{% tabs %}
{% tab title="Soluzione" %}
1. Tenta nuovamente la transazione con una tolleranza allo Slippage aumentata.
2. Se il punto 1. non risolve il problema, considera di utilizzare un altro Portafoglio come SafePal per la tua transazione.
{% endtab %}

{% tab title="Motivo" %}
**Di solito accade quando si fanno Scambi di token con tolleranza allo Slippage insufficiente su Trust Wallet.**

I dettagli esatti del problema sono ancora in fase di indagine.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Durante il tentativo di fare Swap di token, la transazione fallisce e viene visualizzato questo messaggio di errore. Questo errore è stato segnalato su diverse piattaforme.

{% tabs %}
{% tab title="Soluzione" %}
1. Verifica di avere fondi sufficienti disponibili.
2. Assicurati di aver concesso al contratto l'autorizzazione a spendere l'importo di fondi con cui stai cercando di fare Scambio.
{% endtab %}

{% tab title="Motivo" %}
Questo errore si verifica quando si fanno Scambi di token con autorizzazione insufficiente, o quando un Portafoglio ha fondi insufficienti.\
Se stai facendo Scambio di token con Restorative Rebase come gli asset tau tDoge o tBTC, assicurati di capire come funzionano prima con questa [guida ai token Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Problemi con i Farm**

### Fail with error 'ds-math-sub-underflow'

Hai esaurito l'autorizzazione del tuo token LP per il contratto MasterChef.

**Usa un gestore di approvazioni token come unrekt o BscScan per**

## **Problemi con i Syrup Pool**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

Non hai abbastanza SYRUP nel tuo Portafoglio per uscire dallo Staking dal pool CAKE-CAKE.

**Procurati almeno tanti SYRUP quanti sono i CAKE che stai cercando di togliere dallo Staking.**

1. Acquista SYRUP sull'exchange. Se vuoi togliere dallo Staking 100 CAKE, hai bisogno di almeno 100 SYRUP.
2. Riprova a togliere dallo Staking.

Se fallisce ancora, puoi eseguire un "emergencyWithdraw" direttamente dal contratto per togliere dallo Staking i tuoi token.

1. Vai su: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Clicca su **"Connect to Web3"** e connetti il tuo Portafoglio. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Nella sezione **"4. emergencyWithdraw"**, inserisci "0" e clicca su "Write".

Questo toglierà dallo Staking i tuoi token e perderai qualsiasi rendimento CAKE non riscosso.

{% hint style="warning" %}
**Perderai qualsiasi rendimento che non hai ancora raccolto.**
{% endhint %}

Per evitare che questo accada di nuovo, **non vendere i tuoi SYRUP.** Ne hai ancora bisogno per uscire dallo Staking dal pool "Stake CAKE Earn CAKE".

Questo errore si è verificato perché hai venduto o trasferito token SYRUP. I SYRUP vengono coniati in rapporto 1:1 con CAKE quando fai Staking nel Syrup Pool CAKE-CAKE. I SYRUP devono essere bruciati in rapporto 1:1 con CAKE quando si chiama leaveStaking (togliendo i tuoi CAKE dallo Staking nel pool), quindi se non ne hai abbastanza, non puoi uscire dallo Staking nel pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Errore Out of Gas

> Warning! Error encountered during contract execution \[out of gas]

Hai impostato un gas limit troppo basso durante il tentativo di effettuare una transazione.

{% tabs %}
{% tab title="Soluzione" %}
Prova ad aumentare manualmente il **gas limit** (non il gas price!) nel tuo Portafoglio prima di firmare la transazione.

Un limite di 200000 è solitamente sufficiente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

L'esempio sopra è da MetaMask; consulta la documentazione del tuo Portafoglio se non sai come regolare il gas limit.
{% endtab %}

{% tab title="Motivo" %}
In pratica, il tuo Portafoglio (MetaMask, Trust Wallet, ecc.) non riesce a completare quello che sta cercando di fare.

Il tuo Portafoglio stima che il gas limit sia troppo basso, quindi la chiamata alla funzione esaurisce il gas prima che la chiamata alla funzione sia completata.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Soluzione" %}
1. Usa Unrekt.net per revocare l'approvazione per lo smart contract con cui stai cercando di interagire
2. Approva nuovamente il contratto, senza impostare un limite sull'autorizzazione di spesa
3. Riprova a interagire con il contratto.
{% endtab %}

{% tab title="Motivo" %}
Questo accade quando imposti un limite sull'autorizzazione di spesa quando approvi il contratto per la prima volta, poi cerchi di fare Swap di un importo superiore al limite.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Probabilmente stai cercando di uscire dallo Staking da un Syrup Pool con pochi premi. Soluzione di seguito.

Se no, potresti star cercando di inviare token che non hai nel tuo Portafoglio (ad esempio, cercando di inviare un token già assegnato a una transazione in attesa). In questo caso, assicurati semplicemente di avere i token che stai cercando di utilizzare.

{% tabs %}
{% tab title="Soluzione" %}
Prima di tutto,[ informa il team](../social-accounts.md) di quale pool stai cercando di uscire dallo Staking, in modo che possano ricaricare i premi. Se hai fretta di uscire dallo Staking e non ti dispiace perdere il rendimento in attesa, prova un emergencyWithdraw:

Puoi eseguire un "emergencyWithdraw" direttamente dal contratto per togliere dallo Staking i tuoi token.

1. Trova l'indirizzo del contratto del Syrup Pool da cui stai cercando di uscire dallo Staking. Puoi trovarlo nel registro delle transazioni del tuo Portafoglio.
2. Vai su [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) e nella barra di ricerca inserisci l'indirizzo del contratto.
3. Seleziona **Write Contract.**
4. Clicca su **"Connect to Web3"** e connetti il tuo Portafoglio.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Nella sezione **"3. emergencyWithdraw",** e clicca su "Write".

Questo toglierà dallo Staking i tuoi token e perderai qualsiasi rendimento non riscosso.

{% hint style="warning" %}
**Perderai qualsiasi rendimento che non hai ancora raccolto.**
{% endhint %}
{% endtab %}

{% tab title="Motivo" %}
Questo errore tende a comparire quando stai cercando di uscire dallo Staking da un vecchio Syrup Pool, ma non ci sono abbastanza premi rimasti nel pool da raccogliere durante il prelievo. Questo causa il fallimento della transazione.
{% endtab %}
{% endtabs %}

## **Problemi con Previsione**

Check [Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Altri problemi**

### Errore Provider

> Provider Error\
> No provider was found

Questo accade quando cerchi di connetterti tramite un'estensione del browser come MetaMask o Binance Chain Wallet, ma non hai installato l'estensione.

{% tabs %}
{% tab title="Soluzione" %}
Installa l'estensione ufficiale del browser per connetterti, oppure leggi la nostra guida su [come connettere un Portafoglio a PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### ID Chain Non Supportato

Cambia la tua chain in BNB Smart Chain. Consulta la documentazione del tuo Portafoglio per una guida se hai bisogno di aiuto.

### Already processing eth\_requestAccounts. Please wait.

Assicurati di essere connesso all'app del tuo Portafoglio e che sia collegata a BNB Smart Chain.

### Problemi nell'acquisto di SAFEMOON e token simili

Per fare Scambio di SAFEMOON, devi cliccare sull'icona delle impostazioni e **impostare la tua tolleranza allo Slippage al 12% o più.**\
Questo perché **SafeMoon applica una commissione del 10% su ogni transazione**:

* 5% di commissione = ridistribuita a tutti i detentori esistenti
* 5% di commissione = usata per aggiungere Liquidità

Questo è anche il motivo per cui potresti non ricevere tanti token quanti ti aspetti al momento dell'acquisto.\
Leggi di più su [Come Acquistare Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Errori JSON-RPC interni

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Si verifica quando si cerca di rimuovere Liquidità su alcuni token tramite MetaMask. La causa principale è ancora sconosciuta. Prova a utilizzare un Portafoglio alternativo.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

Non hai abbastanza BNB per pagare le commissioni di transazione. Hai bisogno di più BNB della rete BEP-20 nel tuo Portafoglio.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Aumenta il gas limit per la transazione nel tuo Portafoglio. Consulta la documentazione del tuo Portafoglio per imparare come aumentare il gas limit.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Causa non chiara. Prova questi passaggi prima di riprovare:

1. Aumenta il gas limit
2. Aumenta lo Slippage
3. Svuota la cache

## **Problemi con il Profilo**

### Ops! Non riusciamo a trovare alcun Pancake Collectibles nel tuo Portafoglio.

Stiamo investigando la logica alla base di questo problema. Nel frattempo, prova la soluzione alternativa.

{% tabs %}
{% tab title="Soluzione alternativa 1" %}
1. Vai alla pagina "Collectible", poi torna alla pagina del profilo.\
   Se non riesci a trovare il link, vai direttamente su [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles).
2. Riprova a creare il profilo.
{% endtab %}

{% tab title="Soluzione alternativa 2" %}
Cambia l'ambiente.

* Svuota la cache e riprova.
* Riprova su un browser diverso.
* Riprova su app di Portafoglio diverse.
* Riprova su una rete diversa (passa da Wi-Fi a dati mobili)
{% endtab %}
{% endtabs %}

### La verifica del nome utente continua a girare

Ci sono due possibili cause.

1. Hai più Portafogli installati sul browser.
2. Problema di rete.

{% tabs %}
{% tab title="Soluzione 1" %}
Causa principale: Hai più Portafogli installati sul browser.\
\
Potrebbe creare un conflitto tra i Portafogli. Questo è fuori dal controllo di PancakeSwap e non possiamo farci nulla.

1. Installa un solo Portafoglio sul browser, rimuovi gli altri.
2. Riconnetti il Portafoglio e riprova a impostare il nome utente.
{% endtab %}

{% tab title="Soluzione 2" %}
Causa principale: La rete è instabile.

Devi riprovare.

1. Elimina completamente tutto ciò che è stato inserito nel campo di testo.
2. Digita nuovamente il nome utente, poi attendi qualche secondo.
3. Se non funziona, ricarica la pagina e riprova.
{% endtab %}
{% endtabs %}
