---
hidden: true
---

# Integración con Market Makers

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Integración con Market Makers en Ethereum

PancakeSwap está integrado con market makers en Ethereum y Binance Smart Chain para ayudar a los traders a ejecutar trades a un menor costo.

Además del AMM, los trades en PancakeSwap ahora pueden enrutarse hacia market makers incluidos en una lista blanca si ofrecen una ejecución mejor que los precios actuales del AMM. Este enrutamiento se realiza automáticamente mediante un [Smart Router](smart-router-v2/) para que los trades solo se enruten hacia los market makers cuando estén cotizando activamente mejores precios. Cuando el AMM es más competitivo, los traders serán enrutados hacia los AMMs para su ejecución.

Existen 2 escenarios en los que los market makers operan en PancakeSwap.

**Escenario 1: Pools de liquidez AMM existentes**

Si PancakeSwap ya tiene liquidez para un token determinado (p. ej. WETH/USDC) en el AMM, PancakeSwap solicitará a los market makers una cotización para el mismo trade. El smart router de PancakeSwap enrutará entonces la solicitud de trade al AMM o a los market makers dependiendo de cuál fuente de liquidez ofrezca el mejor precio en cada momento.

**Escenario 2: Sin pools de liquidez AMM existentes**

En tal escenario, el smart router enrutará automáticamente el trade hacia los market makers. Sin embargo, esto no impide que los proyectos creen su pool de liquidez AMM posteriormente y trabajen con nosotros para mantener la liquidez en el DEX descentralizado.

### Comisiones

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap no cobra comisiones a los traders por las ejecuciones realizadas a través de nosotros y ejecutadas por los market makers. Sin embargo, PancakeSwap recibe un **0,05%** de **comisiones de trading** de los market makers incluidos en la lista blanca por los volúmenes ejecutados por ellos. PancakeSwap recibe una **comisión de trading** reducida del **0,01%** si los trades ejecutados son entre pares de stablecoins. Por favor, consulta el desglose de comisiones a continuación:<br>

<table><thead><tr><th width="178">Trades</th><th width="138">Comisiones de Trading</th><th width="182">Comisión PCS del MM</th><th width="147">Quema de CAKE</th><th align="center">Tesorería de PancakeSwap</th></tr></thead><tbody><tr><td>Monedas puenteadas desde otras redes</td><td>N/A</td><td>0,25%</td><td>0,083%</td><td align="center">0,167%</td></tr><tr><td>No-stablecoin en Ethereum (p. ej. ETH/USDC)</td><td>N/A</td><td>0,05%</td><td>0,017%</td><td align="center">0,033%</td></tr><tr><td>No-stablecoin en BSC (p. ej. BNB/USDT)</td><td>N/A</td><td>0,05%</td><td>0,017% </td><td align="center">0,033%</td></tr><tr><td>Stablecoin a Stablecoin en Ethereum</td><td>N/A</td><td>0,01%</td><td>0,003%</td><td align="center">0,007%</td></tr></tbody></table>

#### Activos actualmente compatibles

Los siguientes activos son actualmente compatibles y pueden aumentar/disminuir dependiendo del/los market maker(s):

**En Ethereum**

* **Principales:** WETH, WBTC
* **Stablecoins:** USDT, USDC, DAI, BUSD
* **Otros activos ERC-20 populares:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**En Binance Smart Chain:**

* **Principales:** BNB, ETH, BTCB
* Tokens no nativos de BNB: ARB, OP

Ten en cuenta que, a diferencia de los AMMs, los market makers no podrán operar con cualquier monto y los montos que están dispuestos a ejecutar dependerán de su propia liquidez. No es inusual que a veces las órdenes muy grandes no puedan cumplirse completamente. Aconsejamos a los usuarios revisar cuidadosamente las cotizaciones para asegurarse de que cada trade refleje el precio y la cantidad según sus necesidades.

**Tiempos de inactividad de los market makers**

No se espera que los market makers coticen las 24 horas del día, los 7 días de la semana. Hay algunos casos (p. ej. eventos económicos clave, actualizaciones del sistema) en los que el market maker puede no estar disponible temporalmente para proporcionar una cotización. Ten en cuenta que durante estos períodos, estos tokens simplemente no serán negociables, y aconsejamos a los usuarios esperar un tiempo hasta que el market maker vuelva a estar en línea.

#### FAQs

**P.** ¿Se integrará a los market makers en Aptos?

**R:** Es posible, por ahora solo estamos lanzando la integración de market makers en Ethereum y Binance Smart Chain para impulsar la liquidez y mejorar la experiencia del usuario. Continuaremos monitoreando otras cadenas.

**P.** ¿Cómo generará ingresos PancakeSwap si no cobra comisiones a los usuarios?

**R:** PancakeSwap no cobrará ninguna comisión a los usuarios, pero recibirá una pequeña comisión de los market makers y la usará para financiar la recompra y quema de CAKE.

**P.** ¿Los proveedores de liquidez continuarán ganando comisiones LP?

**R:** Sí, los proveedores de liquidez continuarán ganando la recompensa de comisión de trading del 0,17% (comisiones LP) y el rendimiento en los farms de CAKE.

**P.** ¿Los market makers añadirán liquidez al AMM? ¿Eso provocará una bajada del APR?

**R:** Los market makers mantienen su propia liquidez separada y, por lo tanto, no ganarán ningún APR de los trades en los pools AMM. Solo los LPs ganarán comisiones y APRs por proveer liquidez a los pools AMM.

**P.** Estoy proveyendo liquidez en PancakeSwap de Ethereum. ¿Necesito hacer algo?

**R:** No, no tienes que hacer nada. Continuarás ganando las comisiones LP por los trades ejecutados a través del AMM y seguirás obteniendo el rendimiento en CAKE.

**P.** ¿Cómo puede alguien convertirse en market maker?

**R:** Evaluamos y trabajamos con los market makers de forma individual. Por favor, contacta con nosotros directamente o a través de nuestros administradores si tienes interés en trabajar con nosotros.
