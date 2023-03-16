# Integración del Market Maker

![](../../.gitbook/assets/0.png)

### Integración del Market Maker en Ethereum <a href="#_s42y8amckz2s" id="_s42y8amckz2s"></a>

PancakeSwap está integrado con market makers o creadores de mercado en Ethereum para ayudar a los traders a ejecutar intercambios con el menor costo posible.

Adicional al AMM, los intercambios en PancakeSwap ahora pueden ser enrutados a market makers designados en una whitelist si ellos ofrecen la ejecución del intercambio con precios mejores que en el AMM (creador de mercado automático). Este enrutamiento o redireccionamiento es hecho por el [Smart Router](https://docs.pancakeswap.finance/v/espanol/productos/pancakeswap-exchange/smart-router), estos intercambios solamente son enrutados hacia los market makers cuando ellos proporcionan mejores precios. Cuando el AMM sea más competitivo, los traders serán enviados al AMM para su ejecución.

Hay dos escenarios en los cuales los market makers operan en PacankeSwap

**Escenario 1: Pools de liquidez existentes en el AMM**

Si PancakeSwap en Ethereum ya tiene liquidez para un token determinado (por ejemplo, WETH/USDC) en el AMM, PancakeSwap solicitara a los market makers una cotización del mismo intercambio.

El smart router de PancakeSwap hara luego el enrutamiento del intercambio requerido al AMM o a los market makers dependiendo cual fuente de liquidez brinda el mejor precio en el momento dado.

**Escenario 2: No existe liquidez en el AMM**

En algunos casos, el smart router automáticamente enrutara el intercambio a los market makers. Sin embargo, esto no impide que los proyectos establezcan sus pools de liquidez en el AMM luego y trabajen con nosotros para mantener la liquidez descentralizada del DEX.

### Fees <a href="#_cg3fry1gjjol" id="_cg3fry1gjjol"></a>

![](<../../.gitbook/assets/1 (2).png>)

PancakeSwap no cobran ningún fee a los traders por intercambios hechos a traves de nosotros y que son ejecutados por los market makers. Sin embargo, PancakeSwap recibe **0.05%** de fees por intercambio de los market makers incluidos en la whitelist por los volúmenes ejecutados por ellos. PancakeSwap recibe un fee reducido por intercambio de **0,01%** si las transacciones ejecutadas son entre pares de stablescoin.

![](<../../.gitbook/assets/2 (1).png>)

### Activos admitidos actualmente <a href="#_g5920d183iph" id="_g5920d183iph"></a>

Los siguientes activos están actualmente soportados y esta lista puede aumentar/disminuir dependiendo del market maker(s):

**Majors:** WETH, WBTC

**Stablecoins:** USDT, USDC, DAI, BUSD

**Otros tokens ERC-20 populares:** MATIC, SAND, DYDX, CRV, MANA, SUSHI, FTM, LINK, APE, CVX, STG, LDO, AAVE, MKR, UNI.

Tenga en cuenta que, a diferencia de los AMMs, los creadores de mercado no podrán negociar con cualquier cantidad y las cantidades que estén dispuestos a ejecutar dependerán de su propia liquidez. No es raro que, a veces, ordenes muy grandes no se puedan cumplir en su totalidad. Recomendamos a los usuarios que revisen las cotizaciones cuidadosamente para asegurarse de que cada operación refleje el precio y la cantidad de acuerdo con sus necesidades.

**Tiempo de inactividad del** **Market maker**

No se espera que los creadores de mercado coticen las 24 horas del día, los 7 días de la semana. Hay algunos casos (por ejemplo, eventos económicos clave, actualizaciones del sistema) en los que el creador de mercado puede no estar disponible temporalmente para proporcionar una cotización. Tenga en cuenta que, durante estos períodos, estos tokens simplemente no serán negociables, y recomendamos a los usuarios que esperen un tiempo antes de que el creador de mercado vuelva a estar en línea.

### **Preguntas más frecuentes (FAQs)** <a href="#_hpu0njsa1voe" id="_hpu0njsa1voe"></a>

**P.** ¿Se integrarán los market makers en BSC y Aptos?

**Respuesta:** Posiblemente, solo estamos lanzando la integración de market maker en Ethereum por ahora para aumentar la liquidez para una mejor experiencia de usuario. Seguiremos monitoreando otras redes.

**P.** ¿Cómo generará ingresos PancakeSwap si no cobra una tarifa o fee a los usuarios?

**Respuesta:** PancakeSwap no cobrará ninguna tarifa a los usuarios, pero PancakeSwap recibirá una pequeña comisión de los market makers y la usará para financiar la recompra y la quema de CAKE.

**P.** ¿Los proveedores de liquidez seguirán ganando recompensas por su LP?

**Respuesta:** Sí, los proveedores de liquidez continuarán ganando una recompensa por trading fees del 0,17 % (LP fees) y un rendimiento en los farms de CAKE.

**P.** ¿Los market makers agregarán liquidez al AMM? ¿Eso hará que la APR baje?

**Respuesta:** Los market makers mantienen su propia liquidez por separado y, por lo tanto, no obtendrán ningún APR de las operaciones en el AMM. Solo los proveedores de liquidez ganarán fees y APR al proporcionar liquidez a los pools del AMM.

**P.** Estoy proporcionando liquidez en Ethereum PancakeSwap. ¿Necesito hacer algo?

**Respuesta:** No, no tienes que hacer nada. Continuará ganando los fees de LP por las operaciones ejecutadas a través del AMM y continuará obteniendo las ganancias en CAKE.

**P.** ¿Cómo puede alguien convertirse en creador de mercado o market maker?

**Respuesta:** Examinamos y trabajamos con creadores de mercado de forma individual. Acérquese a nosotros directamente o a través de nuestros administradores si tiene interés en trabajar con nosotros.
