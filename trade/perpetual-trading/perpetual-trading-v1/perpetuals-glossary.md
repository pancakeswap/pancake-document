# Glossario Perpetuals V1

**Qui troverai definiti tutti i termini inerenti al trading futures**

### **Trading Perpetuo**

&#x20;I perpetuals, i perpetual swap, o perps sono un tipo speciale di contratto futures senza data di scadenza.



### **Leva Finanziaria**

La leva finanziaria è un meccanismo di trading. I trader possono usarla per aumentare la loro esposizione al mercato consentendo di pagare meno dell'intero importo dell'investimento. In parole semplici, prendi in prestito denaro per amplificare il tuo investimento.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Margine**

è la garanzia che metti per le tue posizioni con leva finanziaria. Ha due Modalità di utilizzo:

* Modalità Margine Cross: Tutte le posizioni cross con lo stesso asset di margine condividono lo stesso saldo di margine cross dell'asset. In caso di Liquidazione, il saldo di margine completo dei tuoi asset insieme a tutte le posizioni aperte rimanenti con quell'asset potrebbero essere confiscati.
* Modalità Margine Isolato: Gestisci il rischio sulle singole posizioni limitando l'importo del margine allocato a ciascuna. Se il rapporto di margine di una posizione raggiunge il 100%, la posizione verrà liquidata. Il margine può essere aggiunto o rimosso dalle posizioni utilizzando questa modalità.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Rapporto di Margine**: Rapporto di Margine = Margine di Mantenimento / Saldo del Margine. Le tue posizioni verranno liquidate quando il Rapporto di Margine raggiunge il 100%.

**Rapporto di Mantenimento**: L'importo minimo del saldo del margine richiesto per mantenere aperte le tue posizioni.

**Saldo del Margine** = Saldo del Portafoglio + PNL Non Realizzato. Le tue posizioni verranno liquidate quando il Saldo del Margine <= Margine di Mantenimento.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Asset:

**Deposito**: Deposita i tuoi fondi nel tuo conto futures

**Prelievo**: Preleva i tuoi fondi dal tuo conto futures al tuo Portafoglio

**Saldo**: Saldo del Portafoglio = Trasferimento Netto Totale + Profitto Realizzato Totale + Commissione di Finanziamento Netta Totale - Commissione Totale.

**PNL Non Realizzato**: Profitto e perdita non realizzati su questa posizione calcolati in base al Prezzo Mark, e percentuale di rendimento del capitale.

**Modalità:**&#x20;

* Modalità Asset Singolo: Supporta il trading USDⓈ-M Futures utilizzando solo il singolo asset di margine del simbolo. Il PNL delle posizioni con lo stesso asset di margine può essere compensato. Supporta la Modalità Margine Cross e la Modalità Margine Isolato.
* Modalità Multi-Asset: Trading USDⓈ-M Futures su più asset di margine. Il PNL può essere compensato tra le diverse posizioni con asset di margine. Supporta solo la Modalità Margine Cross.

{% hint style="info" %}
Nota: Se ci sono posizioni aperte o ordini aperti in USDⓈ-M Futures, la Modalità Multi-Asset non può essere attivata. La Modalità Multi-Asset si applica solo ai USDⓈ-M Futures. Prima di attivare la Modalità Multi-Asset, leggi la guida in dettaglio per gestire meglio il rischio del conto USDⓈ-M Futures quando usi la Modalità Multi-Asset.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Ordini

**Acquisto/Long:** Apri un ordine Long. In questo ordine acquisti un asset e aspetti di venderlo quando il prezzo sale. "Acquisto" e "long" vengono usati in modo intercambiabile.

**Vendita/Short:** Apri un ordine Short. In questo ordine prendi in prestito un asset, lo vendi e speri di riacquistarlo quando il prezzo scende. "Vendita" e "short" vengono usati in modo intercambiabile.

**Ordine Limite:** Un ordine limite è un ordine di acquisto o vendita a un prezzo specifico o migliore. Gli ordini limite non garantiscono l'esecuzione.

**Ordine di Mercato:** Un ordine di mercato è un ordine di acquisto o vendita al miglior prezzo corrente disponibile. Viene eseguito contro gli ordini limite che erano stati precedentemente inseriti nel libro degli ordini. Quando si inserisce un ordine di mercato, pagherai le commissioni come market taker.

**Ordine Stop Limite:** Il modo più semplice per capire un ordine stop limite è scomporlo in prezzo stop e prezzo limite. Il prezzo stop è semplicemente il prezzo che attiva l'ordine limite, e il prezzo limite è il prezzo dell'ordine limite che viene attivato. Ciò significa che una volta raggiunto il tuo prezzo stop, il tuo ordine limite verrà immediatamente inserito nel libro degli ordini.

**Ordine Stop di Mercato:** Simile a un ordine stop limite, un ordine stop di mercato usa un prezzo stop come trigger. Tuttavia, quando viene raggiunto il prezzo stop, attiva un ordine di mercato.

**Trailing Stop:** Un trailing stop è un tipo di ordine progettato per bloccare i profitti o limitare le perdite mentre un trade si muove favorevolmente. I trailing stop si muovono solo se il prezzo si muove favorevolmente. Una volta che si muove per bloccare un profitto o ridurre una perdita, non torna nella direzione opposta.

**Post Only:** La Modalità Post-only significa che i Trader possono inserire un Ordine solo se verrà pubblicato nel Libro degli Ordini come Ordine Maker. Un Ordine che verrebbe pubblicato come Ordine Taker verrà rifiutato. Non possono essere inseriti Ordini di Mercato e nessun Ordine verrà eseguito. Gli ordini in attesa possono essere cancellati in modalità post-only.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WDd32EG9j3ym_aSz_)

**Reduce Only:** L'ordine Reduce-Only ridurrà solo la tua posizione, non la aumenterà.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**Le istruzioni TIF** ti consentono di specificare il tempo durante cui i tuoi ordini rimarranno attivi prima di essere eseguiti o scaduti. Puoi selezionare una di queste opzioni per le istruzioni TIF:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel): L'ordine rimarrà attivo finché non viene eseguito o cancellato.&#x20;
* **IOC** (Immediate Or Cancel): L'ordine verrà eseguito immediatamente (in tutto o in parte). Se viene eseguito solo parzialmente, la parte non eseguita dell'ordine verrà cancellata.&#x20;
* **FOK** (Fill Or Kill): L'ordine deve essere eseguito completamente e immediatamente. In caso contrario, non verrà eseguito affatto.

