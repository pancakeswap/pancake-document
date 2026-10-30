---
description: '2026-08-21'
---

# Presentiamo lo Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Quotare cinque coppie non dovrebbe costare cinque volte il capitale. Ma onchain, questo è l'accordo che ogni emittente di asset si trova ad accettare: la liquidità è legata a ciascuna coppia, quindi ogni nuova coppia significa immobilizzare un altro blocco di capitale, per lo più fermo e improduttivo finché quella esatta coppia non viene scambiata nell'esatto intervallo di prezzo. Ogni volta che vuoi quotare una nuova coppia, devi fornire nuovo capitale come LP: capitale che resta poi vincolato a quella singola coppia e non può essere usato altrove.

Lo Shared Inventory Hook (SIH) spezza questo legame. È il più recente hook di PancakeSwap Infinity, e il primo progettato per l'efficienza del capitale.

_💡 Riepilogo: un hook è uno smart contract (come un add-on) che si collega a un pool Infinity ed esegue logica personalizzata durante lo swap, senza bisogno di avviare una nuova venue._

Quindi, come funziona?

Invece di bloccare uno stack separato in ogni pool, un emittente di asset RWA finanzia **un unico inventario condiviso**, e lo shared inventory hook quota profondità da quell'inventario nella coppia che viene scambiata, just-in-time, proprio nel momento dello swap. Pensa a un'unica dispensa che rifornisce ogni piatto della cucina, invece di una dispensa separata per ciascuno. Un solo saldo fa il lavoro di molti.

Questo singolo cambiamento rende SIH efficiente in termini di capitale, e lo si vede in tre modi:

* **Il capitale resta attivo e al lavoro.** La liquidità dell'inventario dell'hook viene iniettata just-in-time durante uno swap, quindi lavora attivamente e ti fa guadagnare commissioni invece di restare inattiva.
* **Opportunità di commissioni da un unico saldo, su più coppie.** Un solo inventario guadagna su tutte le coppie che serve, così catturi il flusso di commissioni con molto meno capitale impiegato.
* **Minore price impact.** Poiché la liquidità quotata al momento dello swap è più profonda, i trade di grandi dimensioni subiscono un price impact minore ogni volta che SIH quota il prezzo migliore.
* **Maggiore efficienza del capitale.** Finanzi una volta sola; lo stesso capitale sostiene la profondità su ogni coppia abilitata a SIH. Inoltre, puoi abilitare SIH per una nuova coppia senza aggiungere capitale.

> \*\*Già convinto? Porta i tuoi asset onchain nel modo efficiente in termini di capitale: compila questo modulo → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**La prova è onchain**

SIH è andato live con le bStocks questo agosto, e il dato che conta di più è quanto intensamente lavora quel capitale. Nell'ultimo snapshot dell'hook (21 ago 2026), il 75% dell'inventario condiviso è attivamente impiegato sulle tre coppie (inventario dell'hook \~$297K, attivo \~$224K). Sulle due coppie mature, CRCLB e MUB, l'utilizzo è \~99% (98,96% / 98,95%). Il capitale che resterebbe inattivo nei tradizionali pool CLAMM V3 qui è in range e sta quotando.

Nelle sue prime settimane (fino al 21 ago), le tre coppie hanno scambiato \~$710K in 5.713 swap, serviti da un inventario condiviso di \~$297K, guadagnando commissioni LP con un livello dello 0,25%.

_**Fonti:** Dashboard Dune interna_ **Pool live:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Dove stiamo andando**

Il modello è progettato per scalare: più coppie, un unico saldo condiviso che si estende su migliaia di mercati attivi 24/7. È la via più rapida che abbiamo visto per portare onchain l'intera gamma di coppie di un token senza moltiplicare il capitale che c'è dietro.

I pool SIH live si trovano nella [pagina Earn di PancakeSwap](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001): apri **Infinity** e cerca **Shared Inventory** tra le caratteristiche del pool. SIH è attualmente abilitato su CRCLB / USDT, MUB / USDT e GMEB / USDT.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Nota: gli LP retail possono già aggiungere liquidità a questi pool da Earn: quel deposito diventa liquidità residente del pool, tenuta separata dall'inventario condiviso._

_**Importante:**_

_SIH è meno esposto al price drift rispetto a una posizione LP standard, perché l'inventario viene messo al lavoro solo nel momento di uno swap. Non è privo di rischi. L'operatore detiene comunque un inventario che si muove con il mercato. Come per qualsiasi strategia onchain, i risultati dipendono da volume, inventario, hedging e condizioni di mercato._

Pronto a massimizzare l'efficienza del capitale? Abilita subito SIH sulle tue coppie di token → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_Disclaimer: questo contenuto è fornito solo a scopo informativo ed educativo generale. Non deve essere inteso come consulenza finanziaria, legale o professionale di altro tipo. I prezzi degli asset digitali possono essere volatili. Il valore del tuo investimento può diminuire o aumentare._
