---
description: Staking veCAKE e allocazioni IFO
hidden: true
---

# iCAKE

### **Cos'è il nuovo iCAKE?**

Dopo la transizione a veCAKE, il nuovo iCAKE sarà basato sul saldo di veCAKE

* Come il vecchio iCAKE, determina il limite massimo di commit di CAKE nelle vendite pubbliche IFO di PancakeSwap. Ad esempio, se hai 200 iCAKE, puoi commettere 200 CAKE nelle vendite pubbliche IFO.
* Il nuovo numero di iCAKE viene calcolato utilizzando il saldo di veCAKE alla fine di ogni IFO. Pertanto, avrai numeri di iCAKE diversi per ogni IFO.
* Poiché il saldo di veCAKE diminuisce gradualmente con il tuo tempo di blocco rimanente, il tuo iCAKE nei futuri IFO diminuirà con il tuo saldo di veCAKE. Per mantenere il tuo numero di iCAKE, aggiungi altri CAKE allo Staking o rinnova/estendi il tuo blocco.

**iCAKE NON è un nuovo token, è una metrica numerica utilizzata dal sistema IFO di PancakeSwap.**

### Come viene calcolato iCAKE?

Il numero di iCAKE che hai è basato sul saldo di veCAKE alla fine di ogni IFO, moltiplicato per un rapporto predefinito.

veCAKE è un valore calcolato dinamicamente in base a quanti CAKE blocchi e quanto tempo rimane nel blocco. Per saperne di più su come viene calcolato veCAKE, consulta [qui](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Viene applicato un rapporto aggiuntivo sul saldo di veCAKE, che viene adeguato dal team per ogni IFO. Ad esempio, se il rapporto è 2x e hai 1 veCAKE alla fine del prossimo IFO, puoi commettere fino a 2 CAKE.

Esempio:

* Hai bloccato 100 CAKE per 2 anni.
  * Il tuo tempo di blocco rimanente è: `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (secondi)
  * Il tempo massimo di blocco è: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (secondi)
  * Al momento attuale hai: `100 * (62899200 / 126403199) ~= 49,76` veCAKE
* Il prossimo IFO è programmato; il suo tempo di fine è esattamente 1 settimana dopo, ovvero `604800` secondi dopo il momento attuale.
  * A quel momento, il tuo tempo di blocco rimanente sarà: `62899200 - 604800 = 62294400` (secondi)
  * A quel punto avrai: `100 * (62294400 / 126403199) ~= 49,28` veCAKE
* Per questo IFO, il rapporto è impostato su `3x`
* Pertanto, per questo IFO, hai: `49,28 * 3 = 147,84` iCAKE, il che significa che puoi commettere fino a 147,84 CAKE nella vendita pubblica.

### Come controllare il numero di iCAKE che ho?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Puoi controllare il numero di iCAKE che hai sulla pagina IFO [qui](https://pancakeswap.finance/ifo).

Tieni presente che quando non c'è un IFO imminente, il tuo iCAKE verrà calcolato utilizzando il saldo di veCAKE in tempo reale, che diminuisce gradualmente secondo dopo secondo.

Quando c'è un IFO imminente, il tuo iCAKE verrà calcolato utilizzando il saldo di veCAKE al momento dello snapshot, ovvero la fine dell'IFO. Il tuo iCAKE non diminuirà né cambierà fino alla fine dell'IFO.

### **Come posso aumentare il numero di iCAKE che ho?**

Puoi aumentare il numero di iCAKE in qualsiasi momento:

* Aggiungendo altri CAKE alla tua posizione di Staking veCAKE.
* Estendendo la tua posizione di Staking veCAKE.

sulla [Pagina di Staking CAKE](https://pancakeswap.finance/cake-staking)

### Cos'è il "Rapporto" nel calcolo di iCAKE?

Il Rapporto è un fattore di controllo aggiuntivo applicato al saldo di veCAKE nel calcolo di iCAKE.

Ad esempio, se il rapporto è 2x e hai 1 veCAKE alla fine del prossimo IFO, puoi commettere fino a 2 CAKE.

Tra un IFO e l'altro, il team ottimizzerà il "Rapporto" in base a varie metriche. L'aggiustamento verrà pubblicato su tutti i canali social.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Puoi controllare il numero attuale del "Rapporto" per i calcoli di iCAKE andando sulla [pagina IFO](https://pancakeswap.finance/ifo).
