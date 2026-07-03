# FAQ e Risoluzione dei problemi Syrup Pool

## Risoluzione dei problemi

### **Non riesco a trovare il Syrup Pool in cui stavo facendo Staking!**

Dovresti trovare il Syrup Pool nella scheda "Terminati" nella pagina dei Syrup Pool.&#x20;

Selezionando "Solo in Staking", sarà più facile trovare i tuoi asset.

### **Perché non riesco a fare unstake dei miei token da un Syrup Pool?**

Se non riesci a fare unstake dal Pool Stake Cake, Guadagna CAKE, controlla di non aver venduto i token SYRUP nel tuo portafoglio. Questo token funge da \`prova di proprietà\` del tuo CAKE nel Pool CAKE manuale.&#x20;

### **Perché i miei token guadagnati sono andati a zero dopo lo Staking/unstaking?**

Non preoccuparti! Sono già nel tuo portafoglio.

Ogni volta che fai Staking o unstaking da un Syrup Pool o Farm, i tuoi token guadagnati vengono raccolti e inviati al tuo portafoglio allo stesso tempo.

## **Domande Generali**

### Come viene calcolato l'APR per i Syrup Pool?

> APR Syrup Pool = Ricompense annualizzate (USD) / Fondi dell'utente in Staking nel Syrup Pool (USD) \* 100

Come esempio di base, prendiamo un Pool di 60 giorni con 300.000 USD di ricompense e 3.000.000 USD di CAKE in Staking.

L'APR fluttua man mano che più CAKE viene messo in Staking dagli utenti, e al variare del prezzo di CAKE e del token ricompensa.

|                                                              | **Calcolo**                       | Importo                                    |
| ------------------------------------------------------------ | --------------------------------- | ------------------------------------------ |
| Ricompense totali da distribuire (valore USD)                |                                   | 300.000 USD                                |
| Periodo di distribuzione                                     |                                   | 60 giorni                                  |
| Distribuzione giornaliera                                    | 300.000 / 60 =                    | 5.000 USD al giorno                        |
| **Ricompense annualizzate (valore USD)**                     | 5.000 \* 365 =                    | **1.825.000 USD**                          |
| **Valore di CAKE in Staking dagli utenti nel Pool (USD)**    |                                   | **3.000.000 USD**                          |
| **APR**                                                      | (1.825.000 / 3.000.000) \* 100 =  | <p></p><p><strong>60,833% APR</strong></p> |

### **A cosa si riferisce il numero "Fine" nel mio Syrup Pool?**

Mostra il numero di blocchi rimanenti fino alla fine della distribuzione delle ricompense per quel Pool. Una volta che il Pool ha raggiunto quel blocco, dovresti fare unstake dei tuoi token, perché non riceverai più ricompense dopo di allora.

### **Da dove provengono le ricompense dei Syrup Pool?**

Esistono tre tipi principali di Syrup Pool.

1. Stake CAKE, guadagna CAKE
2. Stake CAKE, guadagna altri token.&#x20;
3. Stake altri token, guadagna CAKE

Le ricompense per i Syrup Pool "Stake CAKE, guadagna CAKE" provengono dalle [emissioni CAKE](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Ad ogni blocco, un numero di token CAKE viene allocato come ricompense per questi Pool.

Le ricompense per il tipo "Stake CAKE, guadagna altri token" sono fornite dai team dei progetti che sponsorizzano un Syrup Pool.

Per il tipo "Stake altri token, guadagna CAKE", il treasury di PancakeSwap riacquista CAKE dal mercato per distribuirlo come ricompense. Questi Pool sono finanziati da PancakeSwap, non dai progetti stessi.

### Cos'è il token SYRUP?

Il token SYRUP di PancakeSwap viene depositato nel tuo portafoglio quando interagisci con il Syrup Pool **Manuale** "Stake CAKE, Guadagna CAKE". Non viene messo in Staking.

È fondamentalmente un IOU che mostra quanti CAKE hai messo in Staking nel Pool.

Verrà restituito automaticamente quando fai unstake dei tuoi CAKE da quel Pool.

{% hint style="warning" %}
Non vendere i tuoi token SYRUP! Devi restituire i tuoi SYRUP per fare unstake dei tuoi CAKE dal Pool CAKE Manuale. La quantità di SYRUP che restituisci deve essere uguale alla quantità di CAKE che fai unstake.
{% endhint %}
