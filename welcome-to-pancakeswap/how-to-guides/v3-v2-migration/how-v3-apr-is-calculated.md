# Come viene calcolato l'APR di v3

{% hint style="info" %}
In Liquidità v3 e Farm, con la nuova Liquidità non fungibile e la capacità di personalizzare il range di prezzo, ogni posizione LP avrà il proprio APR sulle commissioni LP e il proprio APR di Yield Farming CAKE.
{% endhint %}

L'APR totale è combinato dall'APR sulle commissioni LP e dall'APR sulle ricompense CAKE

### Commissioni LP

In linea teorica, dato un range di prezzo e la Liquidità che l'utente sta per aggiungere, possiamo stimare le commissioni previste per i prossimi 7 giorni come segue&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Ammontare delle commissioni maturate nel range di prezzo specificato dall'utente negli ultimi 7 giorni
* $$L_{in}$$: Liquidità attuale nel range di prezzo specificato dall'utente
* $$\Delta{L}$$: Liquidità che l'utente vuole aggiungere al range di prezzo

#### Commissioni nel range

Per $$fee_{in}$$, utilizziamo i dati storici sul volume di Trading, il livello di commissione e i dati storici sui prezzi per stimare il prezzo nel range

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Livello di commissione
* $$V_{7d}$$: Volume di Trading totale degli ultimi 7 giorni
* $$T_{in}$$: Durata, misurata in secondi, in cui i prezzi sono rimasti nel range di prezzo negli ultimi 7 giorni
* $$T_{7d}$$: 7 giorni misurati in secondi

### APR CAKE

#### Allocazione del Pool

La ricompensa totale CAKE al secondo in MC v3 usando upkeep può essere derivata da `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

In ogni pool, possiamo usare `poolInfo` per ottenere il `poolWeight` dividendo `poolInfo.allocPoint / totalAllocPoint`

#### APR CAKE Globale

L'APR globale viene calcolato usando l'ammontare totale di Liquidità attiva in Staking con le emissioni di ricompense CAKE del pool.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` rappresenta la Liquidità attiva in Staking nel pool in USD, composta da tutti i tick di posizione nel range messi in Staking in MasterChef v3.

#### APR CAKE per Posizione

Gli APR per le singole posizioni possono variare in base alle impostazioni del range di prezzo.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Ricompensa CAKE guadagnata in USD all'anno nel pool
* $$USD_p$$: Valore totale in USD della posizione
* $$L_{p}$$: Liquidità della posizione
* $$L_{lm}$$: Liquidità totale in Staking tracciata da LMPool
