# Infinity StableSwap

### Descripción General

Infinity StableSwap es un tipo de pool dentro de [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) optimizado para intercambiar activos que deberían operar cerca del mismo precio — como las stablecoins (p. ej., USDC/USDT) o activos con peg ajustado (p. ej., pares de tokens envueltos, tokens de staking líquido y tokens de restaking líquido).

Está impulsado por un hook StableSwap que funciona en la arquitectura de Infinity, inspirado en el diseño StableSwap NG de Curve. Actualmente está disponible en BNB Chain, con planes de expandirse a cadenas adicionales en el futuro.

***

### Cómo Funciona

Infinity StableSwap utiliza una curva invariante estable — un híbrido entre suma constante y producto constante:

* Cerca del peg → la curva se comporta más como suma constante, resultando en un deslizamiento muy bajo para los trades alrededor de 1:1.
* Lejos del peg → la curva gradualmente hace la transición hacia producto constante, lo que ayuda a restaurar el equilibrio y protege el pool durante grandes desequilibrios o eventos de despeg.

Esto lo hace especialmente efectivo para pares estables donde lo más importante es la fijación de precios ajustada y el bajo deslizamiento.

***

### Características Principales

Optimizado para intercambios cerca del peg: Bajo deslizamiento para trades entre activos que se espera que operen aproximadamente al mismo precio.

Provisión de liquidez simple: Los proveedores de liquidez (LPs) depositan ambos tokens proporcionalmente sin necesidad de seleccionar o gestionar rangos de precio — a diferencia de los pools CLAMM.

Tokens LP ERC-20: Tu posición LP está representada como un token ERC-20 estándar, lo que facilita su uso con programas de rendimiento, campañas de puntos y otros protocolos DeFi.

Comisiones dinámicas: Las comisiones pueden ajustarse según las condiciones de equilibrio del pool, recompensando los trades que ayuden a restaurar el pool hacia el equilibrio y desalentando los que empeoran el desequilibrio.

Soporte de enrutamiento en Infinity: Los trades se enrutan automáticamente a través de los pools de StableSwap cuando ofrecen el mejor precio — sin pasos adicionales requeridos para los traders.

Parámetro de Amplificación (A) ajustable: Los operadores del pool pueden aumentar o reducir el parámetro A gradualmente a lo largo del tiempo para adaptarse a las cambiantes condiciones del mercado, con salvaguardas para prevenir cambios abruptos.

***

### Parámetros del Pool

El comportamiento del pool de StableSwap está gobernado por un pequeño conjunto de parámetros, que normalmente se establecen en el momento de la creación del pool.

#### Coeficiente de Amplificación (A)

El parámetro A controla cuán ajustadamente el pool se mantiene cerca del peg de precio 1:1.

| Valor de A | Efecto                                                                          |
| ---------- | ------------------------------------------------------------------------------- |
| A más alto | Curva más ajustada alrededor del peg; menor deslizamiento cerca de 1:1; más sensible al desequilibrio |
| A más bajo | Curva más laxa; se comporta más como un pool estándar de producto constante     |

Regla general: Usa un A más alto para activos con un peg fuerte y fiable (p. ej., USDC/USDT). Usa un A más bajo para activos con pegs más laxos o más volátiles (p. ej., algunos pares LST).

El parámetro A puede aumentarse o reducirse gradualmente por el operador del pool durante un período de tiempo definido. Los cambios se aplican gradualmente con salvaguardas para prevenir la manipulación o cambios repentinos de precios.

#### Multiplicador de Comisión Fuera del Peg

Un parámetro adicional que ajusta las comisiones efectivas cuando el pool se aleja del equilibrio. Ayuda a desalentar los trades que desequilibrarían aún más el pool y hace que el pool sea más robusto durante el estrés del mercado o eventos de despeg.

#### Comisiones Dinámicas

Una comisión cobrada en cada intercambio, pagada a los proveedores de liquidez. Infinity StableSwap admite comisiones dinámicas — lo que significa que la comisión efectiva en un trade determinado puede variar dependiendo del estado actual del pool (p. ej., si el trade mejora o empeora el equilibrio).

***

### Infinity StableSwap vs. StableSwap Clásico

Si has usado el StableSwap existente de PancakeSwap antes, esto es lo que cambia — y lo que permanece igual.

| <p><br></p>                       | StableSwap Clásico                                         | Infinity StableSwap                                                       |
| --------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------- |
| Curva de precios                  | Invariante estable (híbrido suma constante / producto constante) | Misma curva invariante estable, mismo bajo deslizamiento cerca del peg |
| Tokens LP ERC-20                  | ✅ Sí                                                      | ✅ Sí                                                                     |
| Creación de pool                  | Con mucho trabajo; requiere configuración manual por el equipo | Sin permisos — cualquiera puede crear un pool                          |
| Comisiones de intercambio         | Fija por par (p. ej. 0,01% para USDC/USDT)                | Comisiones dinámicas — se ajusta según cómo el trade afecta el equilibrio del pool |
| Parámetro de amplificación (A)    | Estático — se establece una vez, no se puede cambiar       | Ajustable — puede aumentarse o reducirse gradualmente con el tiempo       |
| Multiplicador de comisión fuera del peg | ❌ No compatible                                     | ✅ Compatible — ayuda a proteger el pool durante eventos de despeg        |
| Eficiencia en gas                 | Estándar                                                   | Mejorada — se beneficia del Singleton y Flash Accounting de Infinity      |

#### Lo que permanece igual

* La curva de precios principal y el comportamiento de bajo deslizamiento cerca del peg no cambia.

#### Lo que es nuevo y mejor

* Creación de Pools Sin Permisos: Los pools pueden crearse sin permisos sin requerir configuración manual del equipo.
* Las comisiones dinámicas protegen a los LPs: En lugar de una única comisión fija, la comisión puede ajustarse por trade según si el trade ayuda o perjudica el equilibrio del pool — haciendo el pool más resistente durante condiciones volátiles.
* Parámetro A adaptable: El coeficiente de amplificación puede ajustarse con el tiempo a medida que cambian las condiciones del mercado, en lugar de estar bloqueado en el despliegue para siempre.

***

### Preguntas Frecuentes

¿Qué activos son adecuados para Infinity StableSwap?

Activos que se espera que operen cerca del mismo precio: stablecoins (USDC, USDT, BUSD, etc.), equivalentes envueltos del mismo activo (p. ej., WBTC/cbBTC), y tokens de staking líquido seleccionados / pares de tokens de restaking líquido (LST/LRT) donde la volatilidad del peg es baja.

<br>

¿En qué se diferencia Infinity StableSwap del antiguo StableSwap de PancakeSwap?

Infinity StableSwap está implementado como un hook en PancakeSwap Infinity, lo que significa que hereda todos los beneficios de la infraestructura de Infinity, incluyendo menores costos de gas a través de Singleton y Flash Accounting, y un sistema de comisiones más flexible. También admite nuevas capacidades como comisiones dinámicas y amplificación ajustable que el StableSwap heredado no ofrecía.

<br>

¿Necesito gestionar mi posición con el tiempo?

No. A diferencia de CLAMM, no necesitas establecer ni ajustar rangos de precio. Tu liquidez siempre está activa en toda la curva, por lo que no hay riesgo de que tu posición quede "fuera del rango".

<br>

¿Puedo proveer liquidez con un solo token?

Sí, se admiten depósitos de un solo token.

<br>

¿Cómo funcionan las comisiones dinámicas?

En Infinity StableSwap, la comisión de intercambio puede variar por trade según cómo el trade afecta el equilibrio del pool. Los trades que ayuden a llevar el pool de vuelta al equilibrio pueden pagar comisiones efectivas más bajas, mientras que los trades que empeoran el desequilibrio pueden pagar comisiones más altas. Esto está diseñado para proteger a los LPs y mantener condiciones de pool más saludables.



***



## Crear un Pool Infinity StableSwap



Los pools Infinity StableSwap son sin permisos — cualquiera puede crear uno sin necesitar aprobación del equipo de PancakeSwap.

<br>

### Paso a paso

1\. Ve a la página de Farm/Liquidez y haz clic en Crear Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Selecciona Pool de StableSwap en las opciones de tipo de pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Selecciona el par de tokens para tu pool (p. ej. USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Parámetros del Pool

| Parámetro                     | Qué hace                                                                                                                  |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Comisión de Intercambio       | Comisión cobrada en cada intercambio, pagada a los LPs. El valor predeterminado es 0,01% para pares estables ajustados.  |
| A (Amplificación)             | Controla cuán ajustadamente la curva se mantiene cerca del peg. Más alto = menor deslizamiento cerca de 1:1, pero más sensible al desequilibrio. |
| Multiplicador de Comisión Fuera del Peg | Escala las comisiones cuando el pool se aleja del equilibrio, desalentando los trades que empeoran el desequilibrio. |
| Tiempo de Media Móvil         | Ventana de tiempo usada para calcular el precio de media móvil para los ajustes de comisiones dinámicas.                 |

⚠️ Establece los parámetros con cuidado. Parámetros incorrectos — especialmente un A muy alto en un activo con peg laxo — pueden aumentar el riesgo para los LPs. Si no estás seguro, usa el preset para tu tipo de activo y evita cambiar la configuración avanzada.

<br>

Elige un Preset de Parámetros del Pool — esto establece automáticamente los parámetros recomendados para tu tipo de activo. Aun así puedes ajustarlos manualmente mediante el toggle de Avanzado.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                                     | A    | Multiplicador de Comisión Fuera del Peg | Tiempo de Media Móvil (segundos) |
| ------------------------------------------ | ---- | --------------------------------------- | -------------------------------- |
| Stablecoins Canjeables en Fiat             | 1000 | 10                                      | 600                              |
| Stablecoins Colateralizadas en Cripto      | 100  | 12,5                                    | 600                              |
| Tokens de Restaking Líquido               | 500  | 10                                      | 600                              |

<br>

&#x20; ¿No sabes cuál elegir?&#x20;

* Usa Stablecoins Canjeables en Fiat para pares como USDC/USDT
* Usa Stablecoins Colateralizadas en Cripto para stablecoins algorítmicas o respaldadas en cripto
* Usa Tokens de Restaking Líquido para pares LRT como stkBNB/WBNB.

<br>

5\. Introduce el monto de depósito para sembrar la liquidez inicial. Ambos montos de tokens deben ser iguales (p. ej. 1 USDC y 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Haz clic en Vista Previa del Pool, revisa tu configuración, marca la casilla de confirmación y luego haz clic en Crear Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
