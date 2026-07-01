# Hook de Comisión Dinámica

El Hook de Comisión Dinámica oficial de PancakeSwap está diseñado para crear un intercambio de valor más justo entre los Proveedores de Liquidez y los Traders. Protege a los LPs de la pérdida impermanente (IL) excesiva mientras mantiene el mercado eficiente para los traders.

Desarrollado por el equipo principal de PancakeSwap, este hook está diseñado específicamente para ofrecer una alternativa inteligente y adaptativa a los modelos convencionales de comisiones fijas.

#### 🔍 ¿Por Qué Comisiones Dinámicas?

Los grandes trades de arbitraje provocan mayor divergencia de precios en los pools, aumentando la IL para los LPs. Nuestro modelo de comisiones dinámicas cobra comisiones proporcionalmente más altas en los grandes trades de arbitraje para compensar este riesgo — dejando aun así suficiente margen para que los arbitrajistas obtengan beneficios y mantengan los precios alineados.

#### 📊 ¿En Qué se Diferencia de Otros Modelos?

Otros modelos en el pasado han utilizado datos históricos para estimar la volatilidad y otros factores para ajustar las comisiones. Sin embargo:

* Los datos históricos son un indicador rezagado y pueden no predecir con precisión la volatilidad futura.
* Los eventos del mercado externo (como cambios regulatorios o económicos) pueden hacer que las tendencias pasadas sean poco fiables.
* Los modelos complejos con muchos parámetros corren el riesgo de sobreajuste — funcionando bien con datos pasados pero mal con condiciones nuevas y no vistas.

Nuestro enfoque es más simple, adaptativo y basado en el comportamiento de trading en tiempo real.

#### ⚙️ Cómo Funciona

* **No predecimos la volatilidad ni otros factores macroeconómicos**\
  En cambio, nuestro modelo se beneficia inherentemente del comportamiento de los arbitrajistas bajo diferentes regímenes de mercado:
  * **Alta volatilidad:** Más trades de arbitraje de mayor tamaño → Comisiones más altas para los LPs, cubriendo una mayor proporción de la IL.
  * **Baja volatilidad:** Menos trades más pequeños → La IL es menor por naturaleza, pero los LPs aun así ganan comisiones más altas que con un modelo de comisiones fijas.
* **Nuestro modelo utiliza**
  * Un precio de pool ponderado exponencialmente para detectar trades de arbitraje.
  * Una curva de comisiones exponencial basada en el impacto en el precio de cada intercambio.
  * Un límite máximo de comisión del 5% para mantener la equidad con los traders.

{% hint style="success" %}
Esto garantiza que las comisiones escalen dinámicamente con el impacto del trade mientras se adaptan automáticamente a las cambiantes condiciones del mercado.
{% endhint %}

* **Incentivos Equilibrados**\
  Los arbitrajistas aun así retienen \~50% de sus ganancias después de las comisiones dinámicas, asegurando que estén motivados para mantener los precios del pool alineados con el mercado.

#### 📌 Puntos Clave

* Sin dependencia de predicciones de volatilidad u otros factores macroeconómicos.
* Se adapta automáticamente a la volatilidad del mercado basándose en el comportamiento real de los trades.
* Protege a los LPs de la IL en base por-intercambio.
* Mantiene fuertes incentivos para que los arbitrajistas cierren las brechas de precio.
* Beneficia a los traders con mayor liquidez y comisiones base más bajas.
