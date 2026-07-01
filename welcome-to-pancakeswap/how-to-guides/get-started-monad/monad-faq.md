# FAQ de Monad

#### 1. ¿Qué niveles de comisión están disponibles en los pools de liquidez de PancakeSwap?

**Niveles de comisión admitidos:**

* Los siguientes niveles de comisión están disponibles para los pools V3 (liquidez concentrada): `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Para los pools V2, solo se admiten pools con un nivel de comisión del 0.25%

#### 2. ¿Puede cualquiera crear un pool?

Sí. La creación de pools no requiere permisos, con algunas excepciones:

* Solo puede existir un pool para una combinación de **par de tokens + nivel de comisión** determinada (por ejemplo, solo puede existir un pool WMON <> USDC 0.05% a la vez)

#### 3. ¿Cuánto tiempo tarda en aparecer un pool recién creado?

* Los pools suelen aparecer en la lista de pools aproximadamente **5 minutos** después de su creación.
* Si no aparece:
  * Usa la **barra de búsqueda** para localizarlo manualmente.
  * Los pools pueden filtrarse de la lista debido a un **TVL bajo**.

#### 4. ¿Por qué el APR o TVL de mi pool sigue mostrando cero?

Esto es normal justo después de crear un nuevo pool:

* Los datos de APR y TVL solo se mostrarán una vez que se haya producido **al menos un intercambio** en el pool.
* Después de un intercambio, estas métricas comenzarán a mostrarse en aproximadamente **15 minutos**.

#### **5. ¿Por qué mis transacciones a veces fallan si mi billetera tiene menos de 10 MON?**

Monad tiene una regla de que cada cuenta debe mantener un **margen de seguridad mínimo de 10 MON**. Si tu saldo es bajo y envías demasiadas transacciones muy rápido, la red puede **dejar de aceptar nuevas**.

#### **6. ¿Por qué las primeras 1-2 transacciones funcionan, pero las siguientes fallan?**

Monad procesa bloques usando una vista ligeramente "retrasada" de tu saldo. Así que:

* Tu **primera** transacción suele estar bien.
* Tu **segunda** también puede pasar.
* Pero si envías **múltiples transacciones en poco tiempo**, la red cree que quizás no tienes suficientes MON para pagar todas las comisiones de gas.

Así que **bloquea** la siguiente transacción. Esto es normal y forma parte del sistema de seguridad.

#### **7. ¿Por qué es más estricto con cuentas inteligentes (billeteras de contrato)?**

Las cuentas inteligentes siguen **reglas más estrictas**:

* Deben **siempre** mantener al menos **10 MON** mientras ejecutan código de contrato.
* Si tu cuenta inteligente tiene menos de 10 MON, la transacción puede **revertirse de inmediato**, incluso si las EOAs aún funcionan un par de transacciones.

Por eso los usuarios de cuentas inteligentes ven fallos antes.

#### **8. ¿Esto significa que no puedo usar Monad con menos de 10 MON?**

_Puedes_ usarlo igualmente, especialmente con una EOA normal, pero:

* No envíes varias transacciones seguidas.
* Espera unos pocos bloques entre transacciones.
* Mantén un poco de MON en tu billetera para evitar problemas.

#### **9. ¿Cómo evito estos fallos?**

Consejos sencillos:

* Mantén **10 MON o más** en tu billetera si es posible.
* Si tienes poco MON, **espacía tus transacciones** (no las envíes en ráfaga).
* Los usuarios de cuentas inteligentes deben mantener **un poco más de 10 MON**, ya que las llamadas a contratos usan gas adicional.
