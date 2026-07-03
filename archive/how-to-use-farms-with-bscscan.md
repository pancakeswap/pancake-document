# Come usare le Farm con BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Dato che richiede diversi passaggi, usare le Farm con PancakeSwap può sembrare intimidatorio all'inizio. Questa guida ti accompagnerà nell'utilizzo diretto del contratto Farm tramite BscScan.

{% hint style="warning" %}
Tieni presente che usare BscScan per interagire con i contratti non è consigliato per i principianti. Se non ti senti sicuro, ti suggeriamo di usare invece la [guida Come usare le Farm](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms).
{% endhint %}

## Trovare l'identificatore di processo della Farm

Per interagire correttamente con lo smart contract di farming, avrai bisogno dell'identificatore di processo (PID) corrispondente alla tua coppia LP. Per ora, il modo più semplice per trovarlo è controllare GitHub.

1\. Apri il [codice delle Farm sul sito di PancakeSwap su GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Usa **Ctrl**/**Command** + **F** e cerca la tua coppia tramite il ticker (non il nome del progetto). Ad esempio, 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Annota o copia il numero PID — in questo caso 389 — in un posto facilmente accessibile. Ti servirà in seguito.

## Depositare token LP tramite BscScan

Ci sono alcuni passaggi coinvolti nel deposito di token LP usando BscScan. Li abbiamo suddivisi per rendere più semplice seguirli.

### Ottenere l'indirizzo del contratto di Staking principale

L'indirizzo per il contratto di staking principale è: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Ma supponendo che tu voglia confermare, visita la [pagina BscScan del contratto di Staking principale di PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Vedrai l'indirizzo in alto a sinistra. Clicca sull'icona **pagine** per copiarlo negli appunti. Ti servirà a breve.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Apri il contratto per il tuo token LP

Dovrai approvare lo smart contract per il token LP che desideri depositare in una farm prima di poterlo spendere.

### Dal codice sorgente

1\. Prima, apri [farms.ts su GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Usa **Ctrl**/**Command** + **F** e cerca la tua coppia tramite il ticker (non il nome del progetto). Ad esempio, 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Quando hai trovato il codice per la coppia LP che stai cercando, trova l'indirizzo dopo "56:". Questo sarà il tuo indirizzo del contratto.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Dall'interfaccia UI

1\. Prima, visita la [pagina Farm di PancakeSwap](https://pancakeswap.finance/farms) e cerca la tua coppia scelta usando il campo "SEARCH" in alto a destra. Usiamo CAKE-BUSD per questo esempio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Clicca **Details** per espandere la riga e mostrare ulteriori informazioni.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Clicca **View Contract** per aprire lo smart contract su BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Concedere il permesso al contratto del token LP

Ora che hai aperto il contratto del tuo token LP su BscScan, approverai la spesa dei tuoi token LP nella Farm.

1\. Nella pagina del contratto del token LP, vai su **Contract**, poi su **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clicca **Connect to Web3** per connettere MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Conferma la connessione.

3\. Sotto la funzione 1, "approve", vedrai "spender:address". Incolla l'indirizzo del contratto di Staking principale copiato negli appunti in precedenza.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Dovrai anche approvare l'importo di token LP che il contratto può spendere. Nel campo del valore, dovrai inserire l'importo in Wei. Puoi usare il [Convertitore di unità BscScan](https://www.bscscan.com/unitconverter) per convertire facilmente il tuo importo in Wei. Qui useremo 5 token LP CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Puoi anche usare `-1` come valore per dare approvazione illimitata alla spesa. Questo non significa che spenderai tutto per impostazione predefinita, ma solo che qualsiasi transazione di qualsiasi dimensione che utilizza questo contratto sarà consentita dal tuo portafoglio.
{% endhint %}

6\. Clicca **Write** e accetta l'azione nel tuo portafoglio MetaMask. Ora puoi depositare token LP nella Farm fino all'importo che hai approvato.

### Deposita token LP con lo smart contract del contratto di Staking principale

Con il contratto di Staking principale ora approvato per spendere i tuoi token LP, è tempo di effettuare un deposito.

1\. Torna sulla [pagina BscScan del contratto di Staking principale di PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vai su **Contract**, poi su **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clicca **Connect to Web3** per connettere MetaMask.

3\. Scorri fino alla funzione 2, "deposit", e digita il tuo PID nel campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Se non hai copiato il tuo PID in precedenza, puoi scoprire come ottenerlo nella sezione **Trovare l'identificatore di processo della Farm** più in alto in questa pagina.

4\. Sotto \_pid troverai "\_amount". Inserisci l'importo per il contratto LP da spendere che hai approvato in precedenza.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Controlla le informazioni e clicca **Write**. Conferma l'azione in MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Puoi confermare che il tuo deposito ha funzionato cliccando su **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Prelevare da un Pool

Prelevare i tuoi token LP da un Pool è molto simile al deposito. La differenza è con quale funzione interagisci.

1\. Torna sulla [pagina BscScan del contratto di Staking principale di PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vai su **Contract**, poi su **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clicca **Connect to Web3** per connettere MetaMask.

3\. Scorri fino alla funzione 15, "withdraw", e digita il tuo PID nel campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Se non hai copiato il tuo PID in precedenza, puoi scoprire come ottenerlo nella sezione **Trovare l'identificatore di processo della Farm** più in alto in questa pagina.

4\. Sotto \_pid troverai "\_amount". Inserisci l'importo di LP che desideri prelevare dal Pool.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Controlla le informazioni e clicca **Write**. Conferma l'azione in MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Puoi confermare che il tuo prelievo ha funzionato cliccando su **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Effettuare un prelievo d'emergenza**

‌Usare la funzione di prelievo d'emergenza ti permette di ritirare tutti i tuoi fondi da un pool quando nessun altro modo funziona.

{% hint style="danger" %}
**Usare la funzione di prelievo d'emergenza farà perdere i tuoi premi CAKE!**

Il team di PancakeSwap consiglia vivamente di evitare questa funzione a meno che non sia ufficialmente consigliato dal team di PancakeSwap, o se sei molto a tuo agio nell'interagire con gli smart contract e capisci il codice sottostante.
{% endhint %}

‌1. Nella [pagina BscScan del contratto di Staking principale di PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vai su **Contract**, poi su **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clicca **Connect to Web3** per connettere MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Scorri fino alla funzione 4, "emergencyWithdraw", e digita il tuo PID nel campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Se non hai copiato il tuo PID in precedenza, puoi scoprire come ottenerlo nella sezione **Trovare l'identificatore di processo della Farm** più in alto in questa pagina.

5\. Controlla le informazioni e clicca **Write**. Conferma l'azione in MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Puoi confermare che il tuo prelievo ha funzionato cliccando su **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
