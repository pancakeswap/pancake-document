# 🔁 Swap-Szenarien

Es gibt 4 Szenarien für Cross-Chain-Transaktionen.

#### 1️⃣ Nur Bridge

* Beispiel: **ETH auf Base zu ETH auf Arbitrum bridgen**
* Nur unterstützte Token (USDC, USDT, WETH usw.) können direkt überbrückt werden. Diese Token variieren je nach Quell- und Ziel-Chain.

#### 2️⃣ Swap → Bridge

* Beispiel: **BNB auf BNB Chain zu USDC auf Arbitrum swappen**
* BNB gegen einen unterstützten Bridge-Token (z. B. USDC) mithilfe von PancakeSwap-Pools auf BNB Chain swappen
* USDC über Across zu Arbitrum bridgen

#### 3️⃣ Bridge → Swap

* Beispiel: **USDC auf BNB Chain zu ARB auf Arbitrum swappen**
* USDC über Across bridgen
* USDC gegen ARB mithilfe von PancakeSwap-Pools auf Arbitrum swappen

#### 4️⃣ Swap → Bridge → Swap

* Beispiel: **BNB auf BNB Chain zu ARB auf Arbitrum swappen**
* BNB gegen einen Bridge-Token swappen (maximale Nutzerausbeute)
* Über Across bridgen
* Überbrückten Token gegen ARB auf Arbitrum mithilfe von PancakeSwap-Pools swappen

***

### ⚠️ Fehlerfälle

| Szenario                                    | Ergebnis                                                                                                                                                                                                   |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Swap-/Tx-Fehler auf der Quell-Chain**     | Der Nutzer erhält den ursprünglichen Token sofort auf der Quell-Chain zurück                                                                                                                               |
| **Bridge-Tx-Fehler**                        | Across verarbeitet eine Rückerstattung innerhalb von 90 Minuten bis 2 Stunden, und der Nutzer erhält das überbrückte Asset auf der Quell-Chain zurück. Relay verarbeitet die Rückerstattung in solchen Szenarien zwischen SOL <> EVM innerhalb einer Minute. |
| **Swap-Fehler auf der Ziel-Chain**          | Der Nutzer erhält das überbrückte Asset auf der Ziel-Chain                                                                                                                                                 |
