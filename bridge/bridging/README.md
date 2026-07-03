---
description: Bridge CAKE tra Ethereum, BNB Chain, Aptos e molte altre reti
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging verso/da EVM (nuovo sito): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging verso/da Aptos (V1 Bridge): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## Cos'è il Bridging in crypto?

* Il Bridging in crypto si riferisce al processo di trasferimento di asset tra diverse reti blockchain.
* Migliora l'interoperabilità, consentendo il trasferimento di dati e asset tra varie reti.

\
Ecco alcuni motivi per cui potresti voler fare un Bridge:

* Acquistare diversi token di criptovaluta
* Creare un NFT disponibile solo su una rete specifica
* Risparmiare denaro con transazioni più economiche
* Usare una dapp disponibile solo su un'altra rete

***

## CAKE, un token multichain

Con la nostra espansione e distribuzione multichain, CAKE è ora un token multichain nativo di BNB Chain, ma disponibile anche su Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB e Aptos.

CAKE su qualsiasi altra chain equivale a CAKE su BNB Smart Chain. Può sempre essere trasferito tramite Bridge tra queste chain con un rapporto 1:1 e senza alcuna commissione in CAKE.

**Tieni presente che esiste un solo CAKE.** Non esistono versioni diverse di CAKE su chain diverse. La fornitura totale di CAKE su tutte le blockchain è limitata a 400M, come indicato in questa [proposta di voto](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5).

***

## Cos'è il PancakeSwap Bridge?

Il PancakeSwap Bridge è uno strumento integrato nell'app che ti permette di spostare asset tra diverse blockchain direttamente tramite l'interfaccia di PancakeSwap. Invece di visitare siti Bridge esterni, puoi fare Bridge dei token supportati tra chain come BNB Chain, Ethereum, Base, Arbitrum e altre—tutto da un unico posto.

Il PancakeSwap Bridge è alimentato da fornitori terzi affidabili e funziona come un **aggregatore**—selezionando il percorso migliore in base al prezzo, alla velocità e all'affidabilità.

Per scoprire come fare Bridge di CAKE, consulta i tutorial e le FAQ nelle sezioni seguenti.

***

## 🔗 Come Funziona

### Bridging tramite Aggregatori

Il PancakeSwap Bridge agisce come uno strato intelligente sopra protocolli Bridge terzi affidabili. Quando avvii un trasferimento Bridge, PancakeSwap:

* Controlla più Bridge integrati per trovare i percorsi ottimali
* Invia la tua transazione al fornitore selezionato

Il Bridging è non-custodial—i tuoi asset non transitano dalla custodia di PancakeSwap. I trasferimenti sono gestiti direttamente dai fornitori del Bridge.

### Fornitori Bridge Supportati

Attualmente integriamo:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Nota: ogni fornitore ha meccaniche di Bridging, chain supportate, commissioni e limiti diversi.

***

### Chain e Token Supportati

#### Chain Attualmente Supportate

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (sito V1)

#### Token Disponibili per il Bridging

I token disponibili variano in base alla chain e al percorso. I token supportati più comuni includono (ma non si limitano a):

* CAKE
* USDT
* USDC
* ETH

***

#### Limitazioni ed Esclusioni

Alcuni token potrebbero non essere supportati a causa di limitazioni del Bridge o vincoli di liquidità. Questi sono stati esclusi per garantire la migliore esperienza utente. Ad esempio:

**Per cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Per deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Quelli sopra sono esempi. I token effettivamente disponibili per chain sono mostrati direttamente nell'interfaccia Bridge._

***

### 💸 Commissioni e Costi

#### Commissioni Bridge

* Addebitate dal fornitore Bridge sottostante
* Di solito includono una piccola commissione per trasferimento
* Mostrate chiaramente prima di confermare il tuo Bridge

***

#### Costi del Gas

* Paghi le commissioni del gas sulla **chain di origine** per avviare la transazione
* Alcuni fornitori potrebbero richiedere gas anche sulla **chain di destinazione**
* **Suggerimento:** tieni sempre token nativi (es. ETH, BNB) su entrambi i lati del Bridge

***

#### Importi Minimi e Restrizioni

Alcuni percorsi Bridge impongono:

* **Importi minimi/massimi per il Bridge** (es. minimo di 10 USDC)
* **Decimali o formati token supportati** (es. solo token ERC-20)

L'interfaccia rileverà e mostrerà automaticamente i trasferimenti non validi.

***

### ⏳ Tempi di Transazione e Monitoraggio

#### Quanto Tempo Richiede il Bridging?

I trasferimenti Bridge si completano tipicamente in pochi **minuti**, a seconda di:

* Chain di origine e destinazione
* Congestione della rete
* Efficienza del fornitore Bridge

#### Monitorare il Trasferimento

Una volta inviata, puoi visualizzare lo stato della transazione tramite gli esploratori specifici del fornitore:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Se una transazione è bloccata per molto tempo, controlla l'esploratore corrispondente o contatta i nostri admin tramite i [canali social](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) per [assistenza](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Consigli Prima di Fare il Bridge

* **Tieni token gas su entrambe le chain** (es. ETH + BNB)
* **Inizia con importi piccoli** se è la prima volta che fai Bridging
* Evita di fare Bridging durante periodi di alta attività sulla chain (può comportare commissioni gas più elevate)
* Verifica la compatibilità del token su entrambe le chain
* Controlla sempre due volte le reti di origine e destinazione

***

### Aggiuntivo: Indirizzi CAKE Omni-chain Fungible Token (OFT)

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
