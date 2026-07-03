# 🔁 Scénarios de Swap

Il existe 4 scénarios pour les transactions Cross-chain.

#### 1️⃣ Bridge Uniquement

* Exemple : **Bridger ETH sur Base vers ETH sur Arbitrum**
* Seuls les tokens pris en charge (USDC, USDT, WETH, etc.) peuvent être bridgés directement. Ces tokens varient selon les chaînes source et destination.

#### 2️⃣ Swap → Bridge

* Exemple : **Swap de BNB sur BNB Chain vers USDC sur Arbitrum**
* Swap de BNB vers un token de Bridge pris en charge (ex. USDC) en utilisant les pools PancakeSwap sur BNB Chain
* Bridge de USDC via Across vers Arbitrum

#### 3️⃣ Bridge → Swap

* Exemple : **Swap de USDC sur BNB Chain vers ARB sur Arbitrum**
* Bridge de USDC via Across
* Swap de USDC vers ARB en utilisant les pools PancakeSwap sur Arbitrum

#### 4️⃣ Swap → Bridge → Swap

* Exemple : **Swap de BNB sur BNB Chain vers ARB sur Arbitrum**
* Swap de BNB vers un token de Bridge (en maximisant le résultat pour l'utilisateur)
* Bridge via Across
* Swap du token bridgé vers ARB sur Arbitrum en utilisant les pools PancakeSwap

***

### ⚠️ Cas d'Échec

| Scénario                                        | Résultat                                                                                                                                                                                                              |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Échec du Swap/Tx sur la Chaîne Source**       | L'utilisateur reçoit instantanément le token d'origine sur la chaîne source                                                                                                                                           |
| **Échec de la Tx de Bridge**                    | Across traite un remboursement dans un délai de 90 minutes à 2 heures, et l'utilisateur reçoit l'actif bridgé sur la chaîne source. Relay traite le remboursement en moins d'une minute dans ce scénario entre SOL <> EVM. |
| **Échec du Swap sur la Chaîne Destination**     | L'utilisateur reçoit l'actif bridgé sur la chaîne destination                                                                                                                                                         |
