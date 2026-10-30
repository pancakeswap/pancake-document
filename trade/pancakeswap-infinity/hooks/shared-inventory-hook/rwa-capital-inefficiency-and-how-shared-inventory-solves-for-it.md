---
description: '2026-09-04'
---

# Inefficienza del Capitale negli RWA — e Come lo Shared Inventory la Risolve

Un esperimento di case study di PancakeSwap (Parte 1: L'Impostazione)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Questa è la prima parte di un case study in due parti. In questa parte presentiamo il vero problema di efficienza del capitale che affrontano gli emittenti di asset RWA, introduciamo come lo Shared Inventory Hook (SIH) di PancakeSwap è pensato per risolverlo e presentiamo un esperimento di case study live per metterlo alla prova con dati onchain.

Nelle prossime settimane pubblicheremo la Parte 2: I Risultati.

***

### 🧩 Qual è il Problema dell'Efficienza del Capitale?

Il settore RWA ama un numero in particolare: **quanto è stato tokenizzato.** È il titolo di quasi ogni report: una nuova classe di asset in arrivo, miliardi emessi, crescite di centinaia di punti percentuali.

C'è però un secondo numero che passa in secondo piano, e che potrebbe essere un segnale più rilevante: **quanta parte di tutto questo può effettivamente essere scambiata?**

Il divario tra questi due numeri è il punto chiave. Sul tracker di riferimento, [rwa.xyz](http://rwa.xyz), il valore _rappresentato_ onchain supera di gran lunga quello contro cui si può _transare_ in un dato momento: i dati mostrano un valore bloccato, di riferimento e distribuito **più grande di oltre un ordine di grandezza rispetto a quello presente nei book negoziabili.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Fonte: app.rwa.xyz/stocks_

Per un emittente RWA, questa è la trappola. Tokenizzare un'azione, un ETF o un titolo del Tesoro è la parte facile; farlo scambiare con spread stretti e in modo affidabile è la sfida, ed è qui che l'efficienza del capitale si vince o si perde. L'obiettivo finale è permettere ai trader di _scambiare davvero_ l'asset tokenizzato in modo semplice ed economico: è da lì che arrivano in ultima analisi volumi e commissioni.

Ed ecco perché è specificamente un problema di _efficienza del capitale_, non solo di liquidità.

#### Ogni pool quotato richiede il proprio stack esclusivo di USDT

Per rendere scambiabile una coppia RWA in un pool a liquidità concentrata (CLAMM) tradizionale, gli emittenti hanno bisogno di asset di quotazione dedicati, USDT, a disposizione di chi vuole vendere. Se quoti dieci coppie, il modello CLAMM richiede di finanziare **dieci stack di USDT separati**, uno per coppia, senza che nessuno possa aiutare gli altri. Così il capitale di quotazione viene frammentato in silos esclusivi.

Lo abbiamo misurato sul nostro book. Abbiamo preso **7 pool di azioni tokenizzate live su PancakeSwap** (ciascuno basato su un pool CLAMM V3 tradizionale) ed estratto l'USDT esclusivo.

Snapshot: **2 settembre 2026.**

<table data-search="false"><thead><tr><th>Coppia</th><th>USDT esclusivo nel pool</th><th>TVL del pool</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Totale</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Sono **\~$745k di USDT allocati in modo esclusivo.**

E questi sono solo i nomi che hanno un book.

SNXXB, KORUB, SOXSB e DJTB non hanno alcun book USDT CLAMM: sono tokenizzati, ma difficili da scambiare.

***

### 🎯 Per Cosa Dovrebbe Ottimizzare un Emittente?

Togliendo i dettagli meccanici, un emittente RWA deve risolvere tre cose fondamentali:

1. **Rendere il proprio asset davvero ed efficacemente scambiabile** — quotazioni strette su ogni asset, non solo sui token di punta.
2. **Impegnare il minor capitale possibile** per riuscirci — l'asset di quotazione è costoso; finanziare dieci stack di USDT in modo esclusivo non è molto efficiente.
3. **Non dover gestire un trading desk —** Emettere asset senza dover gestire ogni giorno un'infrastruttura di liquidità.

La domanda quindi è se la liquidità possa essere strutturata in modo diverso, ed è proprio ciò che lo Shared Inventory Hook di PancakeSwap è progettato per risolvere.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH è un hook di PancakeSwap Infinity che permette a un emittente RWA di sostenere molte coppie da un unico pozzo condiviso di USDT invece di uno stack esclusivo per ciascuna coppia.**

SIH ottiene questo fornendo liquidità just-in-time, permettendo:

* Quotazioni più profonde sulle coppie
* Minore price impact, soprattutto sui trade di grandi dimensioni
* Capitale liberato per gli emittenti RWA, dato che meno capitale impiegato quota più coppie

Vediamo queste affermazioni nella pratica.

Allo stesso snapshot del **2 settembre 2026**, SIH detiene **$635,028** di inventario in un singolo hook, quotando **11 coppie** con **$180,467** di USDT condiviso, con un utilizzo dell'**87,7%**. Con questo, SIH ha elaborato **$3,56M in 17.299 transazioni.**

Quindi è **un unico saldo di USDT condiviso di \~$700k che quota \~11 coppie contro \~$745k che quotano solo 7 coppie**.

Stesso compito, progettato solo per smettere di duplicare il capitale.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Riportato a ciò che interessa agli emittenti:

* N saldi USDT esclusivi in modo tradizionale → ✅ un unico pozzo condiviso con SIH
* Emesso ma non scambiabile → ✅ scambiabile\
  L'inventario condiviso iniettato just-in-time attorno al prezzo live significa che i token senza un book USDT V3 possono comunque essere quotati, non solo coniati.
* Gestire un desk → ✅ un operatore con permessi\
  L'emittente fornisce l'inventario; l'hook e il suo operatore si occupano della quotazione.

***

### 🔬 Prova lo Shared Inventory Simulator

Fatti un'idea di come si comporta SIH con il nostro strumento di confronto interattivo **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Questo è un **confronto di alto livello e normalizzato** tra SIH e un book CLAMM tradizionale: diversi fattori del mondo reale sono mantenuti costanti su entrambi i lati, così da isolare con chiarezza il meccanismo di efficienza del capitale. È un modello per capire, non un conto economico (P\&L).

Tre schede:

* **Scheda Simulator** - gioca con inventario, ampiezza della banda e flusso per vedere come SIH _si comporterebbe_ rispetto a un pool CLAMM comparabile in condizioni diverse.
* **Scheda Comparison** - SIH messo direttamente a confronto con un book **PancakeSwap V3 CLAMM** sugli stessi pool, così puoi vedere affiancate la differenza tra pozzo USDT condiviso ed USDT esclusivo in termini di capitale impegnato e copertura.
* **Scheda Live data** — misura come SIH sta _effettivamente_ performando in questo momento, con dati tratti dalle query onchain che alimentano questo studio.

Il simulatore ha lo scopo di aiutare a dimostrare come opera lo Shared Inventory Hook. Provalo, poi confrontalo con i risultati reali che pubblicheremo nelle prossime settimane.

***

### 🧪 L'Esperimento

Nelle **prossime settimane** faremo girare SIH live e lo misureremo rispetto alle affermazioni sull'efficienza del capitale illustrate sopra, usando fonti onchain. Ogni settimana pubblicheremo nuove pillole informative sulle performance di SIH e sulla sua architettura.

**Coppie RWA live nello studio:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Nota: SNXXB, KORUB, SOXSB e DJTB non hanno alcun book CLAMM tradizionale._

**Pubblicheremo i risultati nelle prossime settimane sul** [**Twitter**](https://x.com/PancakeSwap) **di PancakeSwap.**

I risultati pubblicati riguarderanno:

* **Il dataset completo delle performance -** Tutti i dati di SIH delle prossime settimane, riuniti in un unico quadro.
* **La questione dell'allocazione del capitale -** Quanto capitale SIH ha effettivamente fatto risparmiare a un emittente RWA.
* **Centrato / mancato -** Dove SIH ha superato le aspettative e dove ha bisogno di lavoro.
* **Il verdetto -** Una conclusione fondata su quanto SIH sia davvero efficace per l'efficienza del capitale degli RWA.

_Una nota sui dati: le cifre qui riportate provengono da query onchain live e da dati pubblici sulle coppie, citati nel testo. Alcuni confronti usano finestre temporali diverse e le abbiamo segnalate: lo studio è progettato per misurare a parità di condizioni, mentre questa introduzione poteva solo inquadrare la questione._

***

### Vuoi abilitare SIH sui tuoi asset?

Se sei un emittente RWA e sei stanco di finanziare uno stack di USDT separato per ogni pool che quoti, questo fa per te.

Stiamo facendo l'onboarding degli emittenti RWA ora. Compila questo modulo Google e ti guideremo nel far quotare il tuo asset su SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Grazie per la lettura! Seguici su [X](https://x.com/PancakeSwap) per gli ultimi aggiornamenti e unisciti alla conversazione su [Telegram](https://t.me/PancakeSwap) e [Discord](https://discord.gg/pancakeswap).

Costruiamo insieme,\
The Chefs 🥞

***

_Disclaimer: questo contenuto è fornito solo a scopo informativo ed educativo generale. Non deve essere inteso come consulenza finanziaria, legale o professionale di altro tipo. I prezzi degli asset digitali possono essere volatili. Il valore del tuo investimento può diminuire o aumentare._
