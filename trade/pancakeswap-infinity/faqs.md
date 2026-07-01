# FAQs

1. **¿En qué se diferencia Infinity de PancakeSwap V3?**\
   Infinity añade nuevas funciones como hooks programables, más [tipos de pools](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (como LBAMM y CLAMM), y ahorro de gas. Sin embargo, la mecánica principal de intercambio y provisión de liquidez es en general similar a la de v3, salvo algunas diferencias menores en los pools LBAMM para la provisión de liquidez.\
   <br>
2.  **¿Cuál es la diferencia entre LBAMM y CLAMM?**

    1. **LBAMM (Liquidity Book AMM):** Utiliza bins de liquidez, cada uno con liquidez a diferentes niveles de precio. Los LPs pueden proveer liquidez entre bins, y los intercambios se ejecutan a un único nivel de precio dentro de un bin.
    2. **CLAMM (Concentrated Liquidity AMM):** Permite a los usuarios proveer liquidez dentro de rangos de precio personalizados, como en PancakeSwap V3.

    \
    Para más detalles, visita [aquí](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **¿Cómo reclamo mis recompensas de farm y por qué está limitado a cada 8 horas?**\
   Puedes reclamar las recompensas de farm de tus posiciones de liquidez haciendo clic en el botón "Harvest". Infinity permite la reclamación masiva en todas las posiciones de farm activas, ahorrando costos de gas. Las recompensas se calculan y procesan cada 8 horas para optimizar los costos de gas y el cómputo. \
   \
   Para más detalles sobre el mecanismo de farming, visita [aquí](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **¿Cómo funcionan los hooks de Infinity?**\
    Los hooks son extensiones de contratos inteligentes personalizables que añaden funcionalidad extra a un pool. Pueden activar acciones adicionales durante los intercambios o eventos de liquidez — por ejemplo, ajustando comisiones, ofreciendo descuentos u aplicando otra lógica.<br>

    Los hooks se adjuntan a un pool cuando se crea. En la mayoría de los casos, **los usuarios no necesitan realizar ningún paso adicional**. Siempre que intercambies o proveas liquidez como de costumbre, te beneficiarás automáticamente de la lógica del hook si aplica a ese pool.<br>

    👉 **Puedes ver los hooks activos y sus detalles en la página de cada pool en la sección "Características del Pool".**\
    <br>
5.  **¿Por qué no recibí ninguna comisión al retirar mi posición de un pool LBAMM?**\
    En los pools LBAMM (Liquidity Book AMM), las comisiones se añaden automáticamente a tus bins de liquidez activos. Esto significa:

    1. Cuando retiras tu posición, las comisiones ganadas se incluyen en los montos totales de tokens que estás retirando.
    2. A diferencia de los AMMs tradicionales, no hay un saldo separado de "comisiones por cobrar" — todo está incluido en el valor de tu posición.

    \
    Si no notaste tokens adicionales al retirar, podría deberse a que:

    1. Tu posición puede haber sufrido más pérdida impermanente que las comisiones cobradas debido a movimientos de precio durante la duración de tu posición.
    2. Tu liquidez no estaba en bins activos donde ocurrieron trades.
