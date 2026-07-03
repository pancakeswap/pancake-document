# FAQ

{% hint style="info" %}
Usa la barra laterale per trovare rapidamente le risposte alle tue domande!
{% endhint %}

## Ordini Limite e TWAP

Fai riferimento alla FAQ fornita da Orbs:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (Deprecato)

### Perché non riesco a trovare i miei ordini?

Gli ordini limite V2 sono ora deprecati; accedi usando questo link:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Perché il mio ordine non è stato eseguito?

Gli ordini limite vengono eseguiti quando raggiungono il prezzo desiderato; tuttavia, a causa delle fluttuazioni del gas, il prezzo di esecuzione effettivo potrebbe differire dal prezzo che hai specificato nell'interfaccia. Di solito, il prezzo di esecuzione e il prezzo desiderato dovrebbero essere quasi identici; tuttavia, se hai inviato un ordine particolarmente piccolo (\~<1000$), il prezzo di esecuzione potrebbe essere leggermente più alto per tenere conto delle commissioni.

Pertanto, il tuo ordine potrebbe non essere eseguito perché:

* Non è stato possibile eseguire l'intero ordine al prezzo e all'importo desiderati a causa dell'impatto sul prezzo.
* Uno dei token nell'ordine limite ha una commissione sul trasferimento (vedi sotto).

**Prima di inviare un ordine, consulta l'interfaccia che indica il prezzo di esecuzione reale.**

{% hint style="info" %}
Nota: la tabella della cronologia degli ordini riceve i dati dal Subgraph e può mostrare informazioni leggermente ritardate.
{% endhint %}

### Posso inviare un ordine limite per token con commissione sul trasferimento?

**No.** I token con una commissione sul trasferimento non dovrebbero essere usati con gli ordini limite. Procedi a tuo rischio.

### Come imposto lo Slippage quando uso gli ordini limite?

Lo Slippage non è rilevante negli ordini limite. Specifica l'importo di input (ad es. 1000 CAKE) e l'importo di output (ad es. 20 BNB). Gli ordini limite garantiscono che riceverai non meno dell'importo di output specificato (20 BNB) per il tuo importo di input (1000 CAKE) se il prezzo della coppia raggiunge il prezzo desiderato. **Nota che i token con commissione sul trasferimento non dovrebbero essere usati con gli ordini limite** (leggi sopra).

### Il prezzo di esecuzione reale mostra "non viene mai eseguito". Cosa significa?

Significa sostanzialmente che stai cercando di scambiare una quantità molto piccola di token, quindi non ci sono abbastanza token per coprire le commissioni gas. In generale, devi aumentare l'importo nel campo "input" per eliminare questo errore.

### Gli ordini limite hanno una data di scadenza?

Gli ordini aperti hanno una data di scadenza di 90 giorni. Dopo la scadenza, l'ordine potrebbe non essere mai eseguito. Cancella il tuo ordine una volta scaduto.

Una funzionalità di data di scadenza personalizzabile è pianificata per il prossimo futuro.

### Perché non posso creare ordini limite al di sotto del prezzo di mercato?

Per vendere al di sotto del prezzo di mercato, hai bisogno degli **Ordini Stop Limite**, non degli ordini limite. La funzionalità degli Ordini Stop Limite è in arrivo.

### Ho inserito un ordine ma non è mostrato nella tabella degli ordini o è bloccato allo stato "in sospeso".

La cronologia degli ordini proviene dal subgraph e pertanto potrebbe mostrare informazioni leggermente ritardate. Di solito, i ritardi non superano qualche minuto nel peggiore dei casi. Fai riferimento all'indicatore del subgraph nell'angolo in basso a destra della tabella della cronologia degli ordini.
