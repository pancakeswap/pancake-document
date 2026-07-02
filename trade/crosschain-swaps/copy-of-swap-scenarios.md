---
hidden: true
---

# 🔁 Cópia de Cenários de Swap

Existem 4 cenários para transações Cross-chain.

#### 1️⃣ Apenas Bridge

* Exemplo: **Bridge de ETH na Base para ETH no Arbitrum**
* Apenas tokens suportados (USDC, USDT, WETH, etc) podem ser bridgeados diretamente. Esses tokens variam conforme a blockchain de origem e destino.

**Tokens suportados para bridging pelo Across**

| Blockchains  | USDC | USDT | WETH | ETH | CAKE | DAI | BAL | POOL | WBTC |
| ------------ | :--: | :--: | :--: | :-: | :--: | :-: | :-: | :--: | :--: |
| ARB <> BNB   |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| BASE <> BNB  |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| ARB <> BASE  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> BNB   |   ✅  |   ✅  |   ✅  |  ✅  |   ✅  |   ❌ |   ❌ |   ❌  |   ❌  |
| ETH <> BASE  |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> ARB   |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ✅  |

#### 2️⃣ Swap → Bridge

* Exemplo: **Swap de BNB na BNB Chain para USDC no Arbitrum**
* Fazer swap de BNB para um token de bridge suportado (ex.: USDC) usando os pools da PancakeSwap na BNB Chain
* Fazer bridge de USDC via Across para o Arbitrum

#### 3️⃣ Bridge → Swap

* Exemplo: **Swap de USDC na BNB Chain para ARB no Arbitrum**
* Fazer bridge de USDC via Across
* Fazer swap de USDC para ARB usando os pools da PancakeSwap no Arbitrum

#### 4️⃣ Swap → Bridge → Swap

* Exemplo: **Swap de BNB na BNB Chain para ARB no Arbitrum**
* Fazer swap de BNB para um token de bridge (maximizando o resultado para o usuário)
* Fazer bridge via Across
* Fazer swap do token bridgeado para ARB no Arbitrum usando os pools da PancakeSwap

***

### ⚠️ Casos de Falha

| Cenário                                        | Resultado                                                                                                                                                                                                              |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Falha de Swap/Tx na Blockchain de Origem**   | O usuário recebe instantaneamente o token original na blockchain de origem                                                                                                                                             |
| **Falha na Tx de Bridge**                      | O Across processa um reembolso em até 90 minutos a 2 horas, e o usuário recebe o ativo bridgeado na blockchain de origem. Já o Relay processa o reembolso em menos de um minuto nesses cenários entre SOL <> EVM.     |
| **Falha de Swap na Blockchain de Destino**     | O usuário recebe o ativo bridgeado na blockchain de destino                                                                                                                                                            |
