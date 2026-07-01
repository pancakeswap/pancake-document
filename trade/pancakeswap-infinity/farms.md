# Farms

El farming en PancakeSwap Infinity es una forma simple y eficiente en gas para que los usuarios ganen recompensas de liquidez sin necesidad de hacer staking de sus tokens LP. Una vez que se añade liquidez a un pool elegible, las recompensas comienzan a acumularse automáticamente.

#### ⚙️ Cómo Funciona

Aquí tienes un resumen rápido de cómo el sistema rastrea y distribuye las recompensas:<br>

**✅ Sin Necesidad de Staking**

* Solo mantén tu posición LP en tu billetera.
* No necesitas bloquear tus activos ni interactuar con contratos inteligentes adicionales.
* Empiezas a ganar recompensas automáticamente cuando añades liquidez.

#### 📈 Distribución de Recompensas

* Solo las posiciones dentro del rango (las que proveen liquidez activa) reciben recompensas.
* Las recompensas son proporcionales a las comisiones generadas por tu posición durante cada período, llamado epoch.

#### ⏳ ¿Qué es un Epoch?

* Un epoch es una ventana de tiempo fija — actualmente establecida en 8 horas.
* Las recompensas se calculan y distribuyen después de cada epoch.
* Los epochs están programados actualmente a las 00:00, 08:00 y 16:00 UTC.

***

#### 🔄 Proceso de Farming y Reclamación

1. **Seguimiento de Posiciones:** El sistema backend monitorea tus posiciones LP en todos los farms.
2. **Cálculo de Recompensas:** Al final de cada epoch,
   1. El sistema calcula tus recompensas en función de tu liquidez y las comisiones generadas.
   2. Procesa las recompensas en un árbol Merkle y envía un Merkle root a un contrato inteligente.
3. **Período de Disputa:**
   1. Después de publicarse el Merkle root, comienza el período de disputa de 1 hora.
   2. Durante el período de disputa:
      1. Las recompensas recién calculadas no se pueden reclamar.
      2. Las recompensas de epochs anteriores siguen disponibles para reclamar.
      3. Herramientas de verificación automatizadas y operadas por la comunidad comprueban la exactitud de los datos publicados. Si se detectan discrepancias, se puede plantear una disputa para evitar distribuciones incorrectas.
4. **Reclamación de Recompensas:**
   1. Una vez que finaliza el período de disputa, puedes reclamar tus recompensas del último epoch.
   2. Todas las recompensas pendientes en todos los farms pueden reclamarse en una única transacción eficiente en gas.
5. **Las Recompensas No Reclamadas se Acumulan:**
   1. Cualquier recompensa no reclamada se acumula para los epochs posteriores. Cada actualización incorpora las recompensas anteriores, garantizando que no se pierdan ni expiren las ganancias.

{% hint style="info" %}
Los rangos de liquidez más ajustados generalmente conducen a mayores ganancias, pero aumentan la probabilidad de que una posición salga del rango y deje de ser elegible para las recompensas.
{% endhint %}

#### 🌱 Resumen

✅ Sin staking\
✅ Reclamación eficiente en gas\
✅ Actualizaciones regulares de recompensas\
✅ Proceso de disputa justo y transparente\
✅ Las recompensas se acumulan hasta que estés listo para reclamar
