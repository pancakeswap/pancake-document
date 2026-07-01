# 🔁 Escenarios de Intercambio

Existen 4 escenarios para las transacciones multicadena.

#### 1️⃣ Solo Puente

* Ejemplo: **Puentear ETH en Base a ETH en Arbitrum**
* Solo los tokens compatibles (USDC, USDT, WETH, etc.) pueden puentearse directamente. Estos tokens varían según la cadena de origen y destino.

#### 2️⃣ Intercambio → Puente

* Ejemplo: **Intercambiar BNB en BNB Chain a USDC en Arbitrum**
* Intercambiar BNB por un token de puente compatible (p. ej. USDC) usando los pools de PancakeSwap en BNB Chain
* Puentear USDC a través de Across hacia Arbitrum

#### 3️⃣ Puente → Intercambio

* Ejemplo: **Intercambiar USDC en BNB Chain a ARB en Arbitrum**
* Puentear USDC a través de Across
* Intercambiar USDC por ARB usando los pools de PancakeSwap en Arbitrum

#### 4️⃣ Intercambio → Puente → Intercambio

* Ejemplo: **Intercambiar BNB en BNB Chain a ARB en Arbitrum**
* Intercambiar BNB por un token de puente (maximizando el resultado del usuario)
* Puentear a través de Across
* Intercambiar el token puenteado por ARB en Arbitrum usando los pools de PancakeSwap

***

### ⚠️ Casos de Fallo

| Escenario                                        | Resultado                                                                                                                                                                                                                          |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Fallo de Intercambio/Tx en la Cadena de Origen**  | El usuario recibe inmediatamente el token original en la cadena de origen                                                                                                                                                         |
| **Fallo de Tx de Puente**                           | Across procesa un reembolso en un plazo de 90 minutos a 2 horas, y el usuario recibe el activo puenteado en la cadena de origen. Relay procesa el reembolso en menos de un minuto en dicho escenario entre SOL <> EVM. |
| **Fallo de Intercambio en la Cadena de Destino**    | El usuario recibe el activo puenteado en la cadena de destino                                                                                                                                                                      |
