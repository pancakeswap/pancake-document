---
description: FAQ Trading Reward
---

# FAQ

{% hint style="danger" %}
\[Archiviato] Trading Reward – A partire dal 23 agosto 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Generale

#### Perché il mio volume di trading non è stato tracciato?

* I numeri del volume richiedono tempo per aggiornarsi e sono soggetti ai ritardi del SubGraph. Ricontrolla più tardi.
* Il tuo scambio deve essere instradato attraverso la **esatta** coppia di trading evidenziata nella [pagina Trading Reward](https://pancakeswap.finance/trading-reward#rewards-breakdown), incluso il livello di commissione. Consulta [questo tutorial](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) per vedere i tuoi percorsi di trading.
* Solo le coppie di trading V3 sono idonee per questo programma.
* Usa lo stesso indirizzo del portafoglio idoneo per il programma di trading reward sia su Ethereum che su BNB Chain.
* Se il tuo volume di trading in una coppia è troppo piccolo, potresti non essere idoneo a rivendicare alcuna ricompensa.
* L'uso di aggregatori di trading di terze parti potrebbe comportare che gli scambi vengano instradati attraverso altri fornitori di liquidità e non vengano tracciati.

#### Perché ho fatto molto trading ma ho ricevuto solo una piccola quantità di ricompense?

L'importo della trading reward è basato sulla commissione di trading pagata in quelle operazioni.

Se le tue operazioni vengono instradate attraverso coppie con un livello di commissione basso, ad esempio lo 0,01%, stai pagando una commissione molto bassa per la tua operazione. Pertanto, il numero di ricompense diminuirà di conseguenza.

## Campagna Top Traders

#### Devo rimanere all'interno della classifica richiesta per tutto il tempo per vincere la campagna?

No, devi solo essere classificato più in alto della classifica richiesta **alla fine della campagna**. Ma è consigliato classificarsi più in alto e mantenere il rango. E assicurati di controllare spesso per non scendere al di sotto della classifica richiesta.

#### Su cosa si basa la classifica?

La classifica si basa sul numero di ricompense che ogni utente accumula facendo trading. L'importo della ricompensa equivale a una percentuale fissa delle commissioni di trading che paga nelle operazioni.

## Campagna CAKE Stakers

#### Il mio indirizzo era idoneo per la campagna precedente. Perché non è idoneo per l'ultima?

Ogni campagna ha i propri requisiti di idoneità, come la soglia minima per la quantità di veCAKE al momento dello snapshot.

Inoltre, il tempo dello snapshot è impostato all'ora di fine di ogni campagna. Con veCAKE che diminuisce nel tempo, il tuo saldo veCAKE potrebbe scendere al di sotto della soglia per le campagne future.

Potrebbe essere necessario aumentare il tuo veCAKE. Segui semplicemente le istruzioni nella pagina.

#### Perché mi dice che ho ricompense aggiuntive che non possono essere rivendicate?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

La quantità di veCAKE al momento dello snapshot determinerà l'importo massimo di ricompense che puoi guadagnare dalla campagna. Consulta la nota a piè di pagina dalla sezione "Max Reward Cap".

Mentre una campagna è attiva, puoi aumentare il tuo veCAKE e alzare questo limite in qualsiasi momento.

#### Cos'è il "veCAKE al momento dello snapshot"?

Il veCAKE diminuisce gradualmente nel tempo man mano che il tempo di blocco rimanente decresce. Pertanto, analogamente a IFO iCAKE, un saldo veCAKE di snapshot — il saldo veCAKE a un momento specifico, che è statico — è più adatto ad essere utilizzato come metrica di qualificazione.

In Trading Reward, il tempo dello snapshot si riferisce alla fine di ogni campagna. Quindi, il tuo "saldo veCAKE al momento dello snapshot" significa "il tuo saldo veCAKE all'ora di fine della campagna".

#### In che modo il "veCAKE al momento dello snapshot" è correlato alla campagna?

* Il tuo numero di saldo veCAKE al momento dello snapshot è superiore alla soglia richiesta.
* L'importo massimo di ricompense che puoi guadagnare è collegato a y% del tuo saldo veCAKE al momento dello snapshot.

Ad esempio:

1. Alice ha bloccato 300 CAKE per 2 anni (104 settimane) il giorno 1. Il giorno 1, Alice avrà un saldo veCAKE di `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149`.
2. Una campagna di trading reward viene lanciata il giorno 1, con una soglia veCAKE di 100 e un cap di ricompensa dell'1%. La campagna termina tra 30 giorni.
3. Dopo 30 giorni, la posizione di Alice avrà un tempo di blocco rimanente di circa 99,71 settimane, quindi un saldo veCAKE di `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Quindi, per questa campagna, Alice avrà `143` veCAKE al momento dello snapshot.
5. 143 è maggiore di 100, quindi Alice è idonea per la campagna; può iniziare a fare trading di coppie idonee per guadagnare trading reward.
6. Con un cap di ricompensa dell'1%, l'importo massimo di CAKE che Alice può guadagnare da questa campagna è `143 * 1% = 1,43` CAKE.
7. Alice può aumentare il suo veCAKE in qualsiasi momento prima della fine della campagna, bloccando più CAKE o estendendo la sua posizione.

#### Come posso controllare il mio veCAKE al momento dello snapshot durante la campagna?

Puoi controllare nella pagina Trading Reward.

La pagina ti avviserà quando il tuo veCAKE al momento dello snapshot è inferiore alla soglia o le tue ricompense sono attualmente limitate da essa.

In questi casi, puoi cliccare il pulsante "Increase veCAKE" per aumentare il tuo veCAKE senza lasciare la pagina.

#### Posso aumentare il mio veCAKE durante la campagna?

Sì, puoi aumentare il tuo veCAKE in qualsiasi momento prima della fine della campagna. Il tuo "veCAKE al momento dello snapshot" verrà aggiornato di conseguenza.
