# 🔀 Swap Cross-chain

Gli Swap Cross-chain permettono agli utenti di scambiare token tra chain diverse — tutto in un'unica transazione semplificata.

Gli Swap Cross-chain sono supportati tra:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Le transazioni sono velocissime — di solito si completano in pochi secondi o meno di un minuto.**
{% endhint %}

***

### 🔍 Come Funziona

1. L'utente seleziona la chain e il token Di partenza / Di destinazione
2. Il router di PancakeSwap calcola il percorso più efficiente
3. Gli Swap vengono eseguiti utilizzando i pool di liquidità di PancakeSwap (v2, v3, Infinity, StableSwap) sulle chain di origine e destinazione
4. Il Bridging è gestito tramite i nostri protocolli partner: [Across](https://across.to/) (per EVM <> EVM), [Relay](https://relay.link/bridge) (per SOL <> EVM)

{% hint style="success" %}
**Gli Swap Cross-chain sono disponibili per qualsiasi token con liquidità adeguata sia sulla chain di origine che su quella di destinazione.**
{% endhint %}

***

### 💸 Commissioni

* **PancakeSwap non addebita alcuna commissione per le transazioni Cross-chain.**
* Le commissioni sono composte da:
  1. **Commissione di Trading:** Applicata per gli Swap all'interno dei pool di liquidità sulle chain di origine e destinazione
  2. **Commissione Bridge:** Pagata ai relayer per il Bridging degli asset

***

### 🎯 Cosa Sono gli Intent?

Gli intent permettono agli utenti di definire il risultato desiderato senza preoccuparsi di come verrà ottenuto.

Esempi di Intent:

* "Converti 1 ETH su Base in almeno 3000 USDC su Arbitrum"

Senza gli intent, un utente dovrebbe manualmente:

* Fare il Bridge di ETH su Arbitrum
* Trovare un DEX con il miglior prezzo ETH → USDC

{% hint style="success" %}
**Con gli intent — il sistema gestisce tutto automaticamente.**
{% endhint %}

**Vantaggi del design basato sugli intent:**

* Esperienza utente senza interruzioni
* Tempi di transazione più veloci
* Transazioni singole con un solo clic

***

### 🔐 Audit

Abbiamo condotto diversi cicli di audit con nomi rispettati nel settore della sicurezza cross-chain:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
