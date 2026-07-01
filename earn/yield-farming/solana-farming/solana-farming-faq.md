# FAQ de Farming en Solana

### 1. ¿Cómo funciona el Farming en SOL?

* El Farming V3 es **basado en campañas**, lo que significa que las granjas están activas solo por una duración determinada.
* Durante la campaña:
  * Los tokens de recompensa se distribuyen **cada segundo** a las **posiciones de liquidez activas**.
  * El APR de farming se mostrará en la página de lista de pools y en la página de mis posiciones.
* Después de que termine la campaña:
  1. **No se distribuirán más recompensas**.
  2. **El APR de farming ya no se mostrará** en la página de lista de pools y en la página de mis posiciones.
  3. La granja queda **inactiva**, pero el creador puede reiniciarla agregando más recompensas.

### 2. ¿Necesito poner en staking mi NFT LP para ganar recompensas de farming?

* **No se requiere staking**.
* Mientras tu posición de liquidez esté **activa (dentro del rango)** en un pool con una granja activa, ganarás recompensas automáticamente.

### 3. ¿Hay impulsores para las granjas?

* **No**, las granjas V3 **no** admiten ningún mecanismo de impulso.
* Las recompensas se basan únicamente en tu participación de liquidez activa en el pool.

### 4. ¿Se pueden crear múltiples granjas para el mismo pool?

* **No**, solo puede existir **una granja por par de tokens y nivel de comisión**.

### 5. ¿Cómo se configuran las granjas SOL?

#### A. Tokens de Recompensa

* Se pueden asignar hasta **3 tokens de recompensa diferentes** por granja.
* Una vez establecidos, los tipos de tokens de recompensa **no se pueden cambiar**.
* El creador de la granja puede:
  * **Recargar** los tokens de recompensa asignados.
  * **Extender la duración del farming** después de que termine la campaña.

#### B. Duración de la Campaña

* Las campañas deben durar un mínimo de **7 días** y un máximo de **90 días**.

### 6. ¿Se puede editar una granja después de su creación?

Los creadores de granjas pueden editar los siguientes parámetros **después de la creación de la granja**:

1. Tasa de distribución de recompensas (por segundo)
2. Fecha de fin de la campaña
3. Agregar un token de recompensa y la cantidad correspondiente de recompensas (solo si inicialmente se asignaron menos de 3 tokens)
