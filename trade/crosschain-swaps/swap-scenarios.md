# 🔁 Scenari di Swap

Esistono 4 scenari per le transazioni Cross-chain.

#### 1️⃣ Solo Bridge

* Esempio: **Bridge ETH su Base verso ETH su Arbitrum**
* Solo i token supportati (USDC, USDT, WETH, ecc.) possono essere trasferiti direttamente tramite Bridge. Questi token variano a seconda della chain di origine e destinazione.

#### 2️⃣ Swap → Bridge

* Esempio: **Swap BNB su BNB Chain verso USDC su Arbitrum**
* Swap BNB verso un token Bridge supportato (es. USDC) utilizzando i pool PancakeSwap su BNB Chain
* Bridge USDC tramite Across verso Arbitrum

#### 3️⃣ Bridge → Swap

* Esempio: **Swap USDC su BNB Chain verso ARB su Arbitrum**
* Bridge USDC tramite Across
* Swap USDC → ARB utilizzando i pool PancakeSwap su Arbitrum

#### 4️⃣ Swap → Bridge → Swap

* Esempio: **Swap BNB su BNB Chain verso ARB su Arbitrum**
* Swap BNB verso un token Bridge (massimizzando l'output per l'utente)
* Bridge tramite Across
* Swap del token con Bridge verso ARB su Arbitrum utilizzando i pool PancakeSwap

***

### ⚠️ Casi di Fallimento

| Scenario                                       | Risultato                                                                                                                                                                                                                                       |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Fallimento Swap/Tx sulla Chain di Origine**  | L'utente riceve immediatamente il token originale sulla chain di origine                                                                                                                                                                        |
| **Fallimento Transazione Bridge**              | Across elabora un rimborso entro 90 minuti - 2 ore, e l'utente riceve l'asset con Bridge sulla chain di origine. Relay invece elabora il rimborso in circa un minuto in tali scenari tra SOL <> EVM. |
| **Fallimento Swap sulla Chain di Destinazione** | L'utente riceve l'asset con Bridge sulla chain di destinazione                                                                                                                                                                                 |
