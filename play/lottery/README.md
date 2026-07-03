# 🎟️ Lottery

Giocare alla Lottery di PancakeSwap ti dà la possibilità di vincere enormi premi in CAKE! È semplice, equa, e puoi partecipare quante volte vuoi finché hai CAKE per comprare un biglietto.

[Visualizza lo smart contract](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Specifiche:**

* Costo del biglietto della Lottery per 1 biglietto: \~$5 USD in CAKE.
* Limite di acquisto individuale: nessun limite complessivo, ma puoi acquistare solo 100 biglietti alla volta.
* Pagando un biglietto riceverai una combinazione casuale di 6 cifre, ognuna tra 0 e 9, ad esempio "1-9-3-2-0-4". Abbina i numeri da sinistra per vincere premi — più numeri corrispondono, più grande sarà il pool di premi a cui parteciperai.
* La Lottery utilizza l'implementazione VRF di Chainlink per una casualità vera e sicura.

## Costi dei biglietti e sconti per acquisti multipli

I prezzi dei biglietti della Lottery vengono fissati all'inizio di ogni nuovo round e mirano a $5 USD (possono variare leggermente in caso di fluttuazioni improvvise dei prezzi).

Acquistare più biglietti contemporaneamente dà diritto a uno sconto per acquisto multiplo. Puoi comprare fino a 100 biglietti in un solo acquisto: lo sconto parte da un importo minimo con 2 biglietti e sale fino al 10% con 100 biglietti.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%20PM.png)

## **Come vincere**

Abbina i numeri, **dal lato sinistro del tuo biglietto**, ai numeri vincenti estratti alla fine di un round della Lottery.

* Abbinare anche solo il primo numero ti farà vincere un piccolo premio.&#x20;
* Abbina più numeri per vincere una quota di un pool di premi più grande.

## **‌**Idoneità ai premi

‌Ogni biglietto ha in totale sei palline della Lottery, da 0 a 9. Per vincere, i tuoi numeri devono corrispondere ai numeri estratti nello stesso ordine delle palline della Lottery, partendo dal lato sinistro del biglietto. Ad esempio:

Numeri estratti

![Drawn Numbers](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png)

I numeri del tuo biglietto

![Your Ticket A](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png)

Nell'esempio sopra, il Biglietto A: cinque dei numeri del biglietto corrispondono agli stessi numeri estratti, nello stesso ordine: tutti tranne il quarto.

Tuttavia, poiché la quarta cifra **non** corrisponde al numero estratto, solo le prime tre cifre contano come corrispondenti in ordine. Questo varrebbe un premio "Abbina i primi 3".

![Your Ticket B](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png)

Biglietto B di esempio. Questo è sfortunato: anche se le ultime cinque cifre corrispondono, la prima cifra non corrisponde, quindi questo biglietto non vince nulla.

Potrai partecipare solo ai premi della fascia più alta per cui sei idoneo. Un biglietto che abbina i primi tre numeri sarà idoneo solo ai premi della fascia "abbina tre", e non a quelle "abbina uno" o "abbina due".

**Ricorda: le cifre devono corrispondere in ordine, da sinistra a destra.**

## Ripartizione dei premi tra le fasce

‌Dopo che un round è stato estratto e i biglietti con numeri corrispondenti sono stati identificati, vengono assegnati i premi. L'importo vinto da ciascun biglietto dipenderà da quanti altri biglietti hanno vinto nella stessa fascia di premi.

‌Ad esempio, se hai l'unico biglietto che ha abbinato tre numeri in ordine e la quota predeterminata del pool di premi per la tua fascia era 2000 CAKE, riceverai i 2000 CAKE completi.

‌Se invece tu e altre tre persone abbinate tre numeri in ordine, i 2000 CAKE verranno divisi tra i quattro biglietti vincenti, quindi riceverai 500 CAKE.

Consulta le [FAQ della Lottery per una ripartizione dei premi](lottery-faq.md#how-are-prizes-broken-down-between-brackets) per ogni fascia.
