# 🎯 PancakeSwap Auto Slippage

PancakeSwap ha introdotto lo Slippage Automatico per rendere il trading più facile ed efficiente. Lo Slippage Automatico regola automaticamente lo slippage in base alle condizioni di mercato attuali, contribuendo a prevenire transazioni fallite e a ridurre il rischio di perdere denaro a causa di errori di slippage.

## Cos'è lo Slippage?

Lo **Slippage** si verifica quando il prezzo che ti aspetti per uno scambio è diverso dal prezzo al quale lo scambio viene effettivamente completato. Questo può accadere per diversi motivi:

* Volatilità del mercato – i prezzi possono muoversi rapidamente tra quando inserisci e confermi l'ordine
* Bassa liquidità – non ci sono abbastanza token disponibili al prezzo previsto
* Ritardi della blockchain – i tempi di conferma possono causare la variazione del prezzo prima che lo scambio venga finalizzato

{% hint style="info" %}
Esempio:

Cerchi di scambiare 100 CAKE per BNB, aspettandoti 1 CAKE = 0,01 BNB. Ma quando la tua transazione viene elaborata, il prezzo è cambiato e ottieni solo 0,0098 BNB per CAKE. Questa piccola differenza è quello che chiamiamo slippage.
{% endhint %}

## Cos'è la tolleranza allo Slippage?

La **tolleranza allo slippage** è la differenza massima di prezzo che sei disposto ad accettare prima che la tua transazione venga annullata. Se il prezzo si muove oltre la tolleranza impostata, la tua transazione fallirà per evitare perdite inaspettate.

{% hint style="info" %}
Esempio:

Se imposti una tolleranza allo slippage dell'1% e il prezzo cambia di più dell'1% prima che lo scambio venga completato, lo scambio non verrà eseguito.
{% endhint %}

## Cosa succede se la mia tolleranza allo Slippage è troppo bassa?

Se la tolleranza allo slippage è **impostata troppo bassa**, c'è una maggiore probabilità che la tua transazione fallisca — specialmente quando:

* Il mercato è volatile
* Stai scambiando token con bassa liquidità
* Utilizzi token con tasse o meccaniche complesse

{% hint style="warning" %}
Importante: Anche se la transazione fallisce, consumerai comunque commissioni gas per il tentativo.
{% endhint %}

## Presentazione dello Slippage Automatico - Perché è utile?

Lo Slippage Automatico regola automaticamente il tuo slippage in base alle condizioni di mercato attuali, risparmiandoti tempo e riducendo il rischio di transazioni fallite.&#x20;

Con lo **Slippage Automatico**, non è necessario regolare manualmente la tolleranza allo slippage. Questo aiuta a prevenire problemi comuni come:

* **Impostare lo slippage troppo basso**, che può causare il fallimento delle transazioni a causa di piccole variazioni di prezzo durante l'esecuzione.
* **Impostare lo slippage troppo alto**, che può portare a ricevere meno token del previsto a causa di un range di prezzo più ampio accettato.

{% hint style="info" %}
Per garantire la migliore esperienza di trading, lo slippage automatico è stato **attivato automaticamente**. Se è stata impostata una tolleranza allo slippage manuale, verrà applicata la nuova impostazione di slippage.
{% endhint %}



## Come funziona lo Slippage Automatico?

<pre class="language-html"><code class="lang-html"><strong>Slippage Automatico (%) = (Costo Gas in USD / Valore Token Output in USD) * 100%
</strong></code></pre>

* Se il costo del gas è elevato rispetto al valore del token output, lo Slippage Automatico imposterà uno slippage più alto per garantire che lo scambio vada a buon fine.
* Se il gas è economico e il valore del token output è grande, verrà utilizzato uno slippage più piccolo.

Lo Slippage Automatico sceglierà un valore tra **0,5%** e **5,0%**, a seconda del token e delle condizioni di rete.



## Lo Slippage Automatico è disponibile su tutte le reti?

No — lo Slippage Automatico è supportato solo su chain di Layer 1 (L1) come BNB Chain, Ethereum, ecc.

Non è supportato su chain di Layer 2 (L2), perché:

* La formula dello slippage automatico si basa su valori significativi del costo del gas per calcolare un'impostazione di slippage utile
* Poiché le commissioni gas L2 sono molto basse, applicare lo slippage automatico sulle L2 non migliorerebbe i tassi di successo delle transazioni

{% hint style="success" %}
&#x20;Se lo Slippage Automatico **non è supportato** su una rete:

* Verrà applicata la tua impostazione di slippage precedentemente utilizzata
* Se non ne hai impostata una in precedenza, il valore predefinito sarà 0,5%
{% endhint %}


