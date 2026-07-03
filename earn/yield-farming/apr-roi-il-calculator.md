# Calcolatore APR/ROI/IL

In V3 di Liquidità e Farm, con la nuova Liquidità non fungibile e la possibilità di personalizzare l'intervallo di prezzo, ogni posizione LP avrà il proprio APR sulle commissioni LP e l'APR del farming CAKE.

Per rendere la fornitura di Liquidità più fluida e meno complessa, i nuovi display automatici di APR con un calcolatore ROI completamente rinnovato sono disponibili ogni volta che fornisci Liquidità o fai farming.

## Calcolo e visualizzazione automatica dell'APR <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Quando fornisci Liquidità, il display automatico dell'APR reagisce alle modifiche della tua configurazione e calcola l'APR in base alle tue impostazioni.

Ad esempio, nella maggior parte dei casi, se restringi le impostazioni dell'intervallo di prezzo, l'APR aumenta.

Nota per gli APR delle commissioni LP:

* La quantità stimata di ricompense sulle commissioni LP varia in base al livello di commissione selezionato; le ricompense sulle commissioni richiedono raccolta e reinvestimento manuale.
* Le cifre dell'APR sono calcolate utilizzando il volume di trading storico, che dipende dal Subgraph e potrebbe essere soggetto a ritardi di indicizzazione.

Per gli APR del farming:

* La quantità stimata di ricompense CAKE si basa sulle emissioni CAKE live verso i Farm. Sono soggette a variazioni in base a future modifiche delle emissioni.

{% hint style="info" %}
I numeri sono calcolati ai tassi attuali e alle condizioni del Pool e sono soggetti a variazioni in base a varie variabili esterne. Sono stime fornite solo per tua comodità e non rappresentano in alcun modo rendimenti garantiti.
{% endhint %}

Puoi trovare questo display dell'APR in:

* Pagina "Aggiungi Liquidità" - mostra l'APR delle commissioni LP
* Pagina di dettaglio di ciascuna posizione di Liquidità esistente - mostra l'APR delle commissioni LP\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Pagina Farm, all'interno della posizione sotto ogni Farm - mostra l'APR combinato con commissioni LP e ricompense CAKE\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Calcolatore ROI migliorato <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Ogni volta che vedi i display automatici dell'APR, puoi cliccare per aprire il nuovo calcolatore ROI. Il nuovo calcolatore ROI è stato riprogettato con diverse funzionalità aggiuntive per soddisfare le esigenze della fornitura di Liquidità concentrata e del farming V3.

Analizziamo insieme ogni sezione:

### Importo del deposito, "In Staking per" e "Reinvestimento ogni" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Questi tre sono gli input di base, presenti anche nel calcolatore ROI precedente. Servono a definire:

1. Quanti asset vengono forniti alla posizione di Liquidità, in USD.
2. Per quanto tempo quegli asset saranno in Staking nella posizione.
3. Con quale frequenza reinvestirai le ricompense nella posizione.



⓵ **Importo del deposito**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Puoi inserire manualmente l'importo in USD, oppure usare i pulsanti di azione rapida per inserire rapidamente $100, $1.000 o l'importo massimo consentito in base al saldo dei token nel tuo portafoglio.



⓶ **Durata dello Staking**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Puoi selezionare per quanto tempo gli asset sono in Staking nella posizione di Liquidità scegliendo tra: 1 giorno, 7 giorni, 30 giorni, 1 anno e 5 anni.

Il numero di rendimenti verrà calcolato in base alla durata del tuo Staking.



⓷ **Reinvestimento**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Puoi selezionare con quale frequenza raccoglierai le ricompense generate dalla posizione e le reinvestirai nella posizione stessa. Puoi scegliere un numero tra: 12 ore, 1 giorno, 7 giorni e 30 giorni.

Il numero di rendimenti e l'APY verranno calcolati in base alla tua scelta. Se non hai intenzione di reinvestire la tua posizione, deseleziona la casella di controllo a sinistra.

{% hint style="info" %}
In V3, le commissioni LP e i CAKE guadagnati devono essere raccolti e reinvestiti manualmente.
{% endhint %}

### &#x20;⓸ Prezzo storico <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Questa è una sezione di sola visualizzazione per consultare il movimento storico del prezzo del pair selezionato.

Puoi fare riferimento ai movimenti storici dei prezzi in diversi intervalli di tempo, ad esempio quanto il prezzo fluttua di solito, per poi definire impostazioni di intervallo di prezzo adeguate a bilanciare un APR più alto e un rischio minore di Impermanent Loss.

* MIN - prezzo minimo
* MAX - prezzo massimo
* AVG - prezzo medio
* CURRENT - prezzo attuale

{% hint style="info" %}
Il grafico dei prezzi utilizza solo i dati del pair V3 effettivo. Pertanto, i dati sui prezzi precedenti al deployment di V3 non sono disponibili. Le quattro metriche di prezzo rappresentano l'intervallo di tempo attualmente selezionato e cambieranno in base alla selezione.
{% endhint %}

### ⓹ Intervallo di prezzo <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Usando questa sezione, puoi verificare quanta Liquidità è stata depositata in diversi intervalli di prezzo e definire l'intervallo di prezzo in cui stai fornendo Liquidità.

Puoi trovare il grafico di distribuzione sotto il titolo. Maggiore è la quantità di Liquidità, più alto sarà il grafico.

Puoi modificare le impostazioni dell'intervallo di prezzo:

* Trascinando le due maniglie sul grafico per aumentare o ridurre il limite minimo e massimo del prezzo.
* Usando lo spazio tra le due maniglie per spostare l'intervallo selezionato.
* Cliccando il pulsante + e - sui campi del prezzo minimo e massimo.
* Cliccando i numeri nei campi del prezzo e inserendoli manualmente.

Se vuoi navigare nel grafico di distribuzione:

1. Usa i pulsanti lente d'ingrandimento più e meno per ingrandire e rimpicciolire
2. Trascina l'asse X (inferiore) per spostarti a sinistra e a destra

Se vuoi fornire Liquidità all'intero intervallo di prezzo, clicca "Intervallo completo"

### ⓺ Invertire la direzione del prezzo per visualizzare i prezzi con una base diversa <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Per alcuni pair di token, è più facile e intuitivo visualizzare i prezzi con certi token base. Ad esempio, per il pair BNB/USDT, la maggior parte delle persone preferirà visualizzare i prezzi come "quanti USDT per BNB" anziché il contrario.

Puoi facilmente invertire la visualizzazione dei prezzi. Clicca semplicemente il pulsante accanto a "Visualizza prezzi in:" per passare da un token all'altro nel pair.

### ⓻ Importa ed esporta (applica) le tue impostazioni <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Quando apri il calcolatore ROI nella finestra "Aggiungi Liquidità", o visualizzando una posizione esistente, le seguenti impostazioni verranno importate automaticamente così non dovrai impostarle di nuovo:

1. La quantità di asset che stai depositando
2. L'intervallo di prezzo
3. Il livello di commissione selezionato

Quando hai finito di configurare nel calcolatore ROI, puoi cliccare "Applica impostazioni" per applicare rapidamente le impostazioni dal calcolatore alla finestra "Aggiungi Liquidità" senza doverle abbinare manualmente.

### ⓼ Calcola le ricompense del farming e l'APR <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Le ricompense del farming saranno incluse nei calcoli se apri il calcolatore ROI dalla pagina "Farm".

Puoi espandere le sezioni di dettaglio per vedere il riepilogo delle ricompense.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
