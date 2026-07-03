# FAQ della Lottery

## Cosa succede se non ci sono vincitori?

Se il CAKE nei pool di premi non viene vinto, non va sprecato! Il CAKE non reclamato si accumula per il round successivo della Lottery.

## Il mio biglietto corrisponde a diversi numeri ma non riesco a riscattare un premio

I biglietti sono idonei ai premi solo se i numeri corrispondono da sinistra a destra. Consulta la [documentazione Lottery v2](./) per una spiegazione dettagliata.

## Come si differenzia la Lottery v2 dalla Lottery v1?

La Lottery v2 distribuisce i premi in modo più capillare rispetto alla Lottery v1. Dà a ogni biglietto 1 possibilità su 10 di abbinare il primo numero, il che significa che più biglietti vinceranno almeno un piccolo premio. Ha inoltre 6 numeri (in aumento rispetto a 4) che devono essere abbinati in sequenza per vincere il premio più grande.

Nel complesso, questo significa che più biglietti possono vincere un premio, ma il jackpot più grande verrà vinto meno frequentemente, portando a pool di premi molto elevati!

**La Lottery v2 introduce:**

* prezzi dei biglietti più economici (\~$5 USD in CAKE per biglietto) che non oscillano drasticamente con il prezzo di CAKE
* sconti per acquisti multipli
* fasce di pool di premi a 6 livelli con pool crescenti al crescere dei numeri abbinati
* selezione manuale dei numeri (opzionale), così puoi usare i tuoi numeri fortunati
* [l'implementazione VRF di Chainlink](https://docs.chain.link/docs/chainlink-vrf/) per una casualità vera e sicura
* commissioni totali più basse (vedi [più in basso in questa pagina](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) per maggiori informazioni)

[Scopri di più sulle funzionalità, il gameplay e i premi della Lottery v2](./)

## Come vengono ripartiti i premi tra le fasce?

Il pool di premi di ogni fascia è una porzione del CAKE totale di ogni round della Lottery.

* | Fascia (numeri abbinati in ordine) | Allocazione CAKE |
  | ---------------------------------- | ---------------- |
  | Primo 1 numero                     | 2%               |
  | Primi 2 numeri                     | 3%               |
  | Primi 3 numeri                     | 5%               |
  | Primi 4 numeri                     | 10%              |
  | Primi 5 numeri                     | 20%              |
  | Primi 6 numeri                     | 40%              |
  | Burn                               | 20%              |

## Posso ritrasformare i miei biglietti in CAKE?

No, una volta acquistati non sarà possibile convertire i biglietti in CAKE.

## Se vinco, devo riscattare il premio manualmente?

Sì, dovrai cliccare il pulsante **Controlla ora** sotto "Sei un vincitore?" nella pagina della Lottery.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## Con quale frequenza si svolge la Lottery?

Un'estrazione della Lottery avviene ogni 12 o 36 ore. Un'estrazione si svolge ogni giorno alternando le 0:00 UTC e le 12:00 UTC; i round successivi a quelli delle 0:00 UTC sono dopo 36 ore, quelli successivi alle 12:00 UTC sono dopo 12 ore.

![Lottery injection schedule](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## Quali commissioni di transazione pagherò per acquistare biglietti?

Ogni acquisto di biglietti che effettui sarà una transazione. Acquistare un singolo biglietto in un acquisto della Lottery costerà il normale importo delle commissioni di transazione.

Tuttavia, acquistare più biglietti in quell'acquisto aumenterà la commissione. Acquistare 100 biglietti invece di 1 non moltiplicherà la commissione per 100, ma potrebbe aumentarla da 5 a 6 volte (anche se può variare).

## Come funziona lo sconto per acquisti multipli?

Lo sconto per acquisti multipli premia l'acquisto di grandi quantità di biglietti con uno sconto progressivo. Se acquisti solo 2 biglietti, lo sconto è trascurabile, ma aumenta rapidamente all'aumentare del numero di biglietti acquistati in una transazione.

Lo sconto si applica solo a ogni transazione fino a 100 biglietti. Lo sconto non si trasferisce alla transazione successiva o al round successivo.

## Perché posso acquistare solo 100 biglietti?

Puoi acquistare al massimo 100 biglietti in un acquisto, ma puoi effettuare più acquisti. Nulla ti impedisce di acquistare altri biglietti dopo i primi 100.

## Se creo manualmente due o più biglietti con gli stessi numeri e vincono, ho diritto ai premi per ogni biglietto?

Sì, ogni biglietto viene trattato come una partecipazione separata alla Lottery. Tieni presente che i premi non saranno 1:1, poiché ogni biglietto vincente che possiedi diluisce la quota dei premi totali della fascia.

## Programma di iniezione: quando viene aggiunto CAKE alla Lottery?

Quando le persone acquistano biglietti, il CAKE che spendono viene aggiunto al pool della Lottery. Inoltre, ogni altro round vengono aggiunti (iniettati) al pool della Lottery 8.000 CAKE con un programma regolare nel corso di sette round a settimana come mostrato sopra nella figura del calendario della Lottery.
