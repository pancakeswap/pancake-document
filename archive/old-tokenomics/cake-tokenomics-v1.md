# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Tasso di emissione** <a href="#emission-rate" id="emission-rate"></a>

### **Per blocco**

| **Metrica**                                                                        | **Emissione/blocco (CAKE)** | **Emissione/giorno (CAKE)** |
| ---------------------------------------------------------------------------------- | --------------------------: | --------------------------: |
| Emissione                                                                          |                          40 |               1.152.000 |
| Bruciato settimanalmente [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                      -25,75 |                -787.600 |
| **Emissione effettiva**                                                            |            **<14,25\***     |           **364.400\*** |

\*L'emissione effettiva è in realtà leggermente inferiore a questo importo: ulteriori 45.000 CAKE al giorno vengono dirottati dall'importo assegnato alla lotteria e bruciati (PID 137 - Dettagli di seguito).

Oltre a quanto sopra, una quantità dinamica di CAKE viene anche [coniata all'indirizzo Dev](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) a un tasso del 9,09%. Ciò significa che se vengono raccolti 100 CAKE, vengono coniati altri 9,09 CAKE e inviati all'indirizzo Dev.

{% hint style="info" %}
Tutti i CAKE coniati all'indirizzo Dev vengono bruciati nel burn settimanale e non entrano mai in circolazione.&#x20;

Per questo motivo, non li abbiamo inclusi nel tasso di emissione sopra indicato.
{% endhint %}

## Distribuzione <a href="#distribution" id="distribution"></a>

| Distribuito a                        | Ricompensa/blocco (% dell'emissione) | Ricompensa/blocco (CAKE totali) |           Ricompensa/giorno |
| ------------------------------------ | -----------------------------------: | ------------------------------: | --------------------------: |
| Farm e Lotteria                      |                               10,62% |                            4,25 |     122.400 (circa) |
| di cui dirottato e bruciato          |                                      |                                 |              -46.000 |
| Syrup Pool                           |                                  25% |                              10 |     288.000 (circa) |
| **Emissione giornaliera totale CAKE** |                                      |                                 | **364.400 (circa)** |

## **Altri meccanismi deflazionistici** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Il processo di burn è attualmente manuale. [Visualizza le transazioni di burn qui](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Oltre a quanto sopra, CAKE viene bruciato anche nei seguenti modi:

* **0,05%** di ogni scambio effettuato su PancakeSwap V2
* **100%** dei CAKE inviati all'indirizzo Dev
* **100%** delle commissioni di performance in CAKE dagli IFO
* **100%** dei CAKE spesi per la creazione del Profile e il conio di NFT
* **100%** dei CAKE offerti durante le Farm Auctions
* **20%** dei CAKE spesi per i biglietti della lotteria
* **45.000** CAKE al giorno (storicamente assegnati alla lotteria) _(I CAKE per questo vengono generati da una Farm - PID 137)_
* **3%** di ogni round dei mercati di Previsione viene utilizzato per acquistare CAKE da bruciare
* **2%** di ogni raccolta di rendimento nell'Auto CAKE Pool
* **2%** di ogni vendita di NFT sul NFT Market viene utilizzato per acquistare CAKE da bruciare

## Perché il burn di CAKE è manuale?

Per partire velocemente, PancakeSwap è stato lanciato come MVP (minimum viable product) con il contratto MasterChef che emetteva 40 CAKE per blocco. Per questo motivo, il team iniziale non ha aggiunto funzioni aggiuntive come la possibilità di personalizzare la logica di conio di CAKE. Poiché la migrazione a un nuovo MasterChef richiederebbe molto tempo e impegno, il team ha scelto di ridurre le emissioni di CAKE attraverso un processo di burn manuale creando due pool:

* Legacy Lottery Pool (PID - 137) - CAKE bruciati dalla lotteria
* Burn Pool (PID - 138) - CAKE bruciati per blocco

Questi pool funzionano in modo simile alle Farm, dove i Chef possono regolare la percentuale dei 40 CAKE per blocco allocata ad essi dopo ogni voto di riduzione delle emissioni CAKE.

{% hint style="warning" %}
Nel giorno del burn, l'offerta mostrata sulla homepage potrebbe improvvisamente aumentare di diversi milioni di CAKE.&#x20;

Non preoccuparti - **QUESTI CAKE NON ENTRANO MAI EFFETTIVAMENTE IN CIRCOLAZIONE:**
{% endhint %}

Questo apparente aumento è dovuto al modo in cui tutti i CAKE assegnati al burn vengono conservati durante la settimana.&#x20;

I CAKE inviati a entrambi i pool PID-137 e PID-138 vengono raccolti prima di completare i burn settimanali di token, e questo fa aumentare l'offerta totale mostrata sul sito di circa 6 milioni. Questo accade perché i CAKE in attesa non vengono registrati nell'offerta totale fino a quando non vengono raccolti il giorno del burn. Una volta completata la transazione di burn dei token, i circa 6 milioni vengono mostrati come "Bruciati fino ad oggi".&#x20;

## Come verificare autonomamente l'offerta di CAKE

Per confermare che l'offerta circolante di CAKE mostrata sulla homepage di PancakeSwap sia corretta,&#x20;

1. Vai al contratto del token CAKE su BscScan e [guarda quanti CAKE sono detenuti dall'indirizzo di Burn.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Questo è l'importo totale di CAKE che è stato bruciato (rimosso dalla circolazione PER SEMPRE, impossibile da recuperare).
2. Quindi sottrai questo importo bruciato dall'"Offerta totale" mostrata da BscScan.
3. Questo ti dà l'offerta effettiva di CAKE.



#### **Ulteriori informazioni sui meccanismi deflazionistici di CAKE nella pagina successiva.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
