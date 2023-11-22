# FAQ

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

#### ¿Cuál es la diferencia entre CAKE bloqueado y veCAKE?&#x20;

veCAKE es una nueva versión de staking de CAKE a plazo fijo con más beneficios y poder para los poseedores de CAKE bloqueados. Incluyendo votación por niveles, incentivos adicionales, aumento del rendimiento y más.&#x20;

#### ¿Qué sucede con las recompensas del pool de CAKE cuando se implementa el nuevo veCAKE?&#x20;

Las emisiones de recompensa del pool de CAKE se desviarán para recompensar a todos los poseedores de veCAKE de acuerdo con su saldo de veCAKE frente al suministro total.&#x20;

Las recompensas CAKE y las recompensas semanales de reparto de ingresos ahora se pueden reclamar semanalmente los jueves.&#x20;

Tenga en cuenta que para seguir recibiendo recompensas, los usuarios deberán migrar al nuevo pool de veCAKE.&#x20;

#### ¿Cuál es la duración máxima que puedo bloquear mi CAKE?&#x20;

La duración máxima que puedes bloquear tu CAKE ahora se ha ampliado a 4 años.&#x20;

#### ¿Es veCAKE un nuevo token? ¿Se puede transferir?&#x20;

veCAKE es una cantidad calculada en el momento, basado en la cantidad de CAKE bloqueados y el tiempo de bloqueo restante. No es un token estándar y no se puede transferir.&#x20;

#### ¿Por qué cambió mi saldo de veCAKE? ¿Cómo calcular su saldo?&#x20;

El saldo de veCAKE disminuye linealmente a 0 según la duración restante del bloqueo. Por lo tanto, cuando nos acercamos al tiempo de desbloqueo, su saldo disminuye.&#x20;

El saldo de veCAKE se puede calcular mediante:&#x20;

lockedAmount // cantidad de CAKE bloqueada&#x20;

currentTime // hora actual&#x20;

lockEndTime // el tiempo de desbloqueo&#x20;

maxLockTime = 209 \* 7 \* 24 \* 60 \* 60 - 1 = 126403199 // tiempo máximo de bloqueo (4 años)

remainingLockTime = lockEndTime - currentTime&#x20;

veCAKE = lockedAmount \* (remainingLockTime / maxLockTime)&#x20;

#### ¿Cómo aumentar mi veCAKE?&#x20;

Una vez que tenga una posición veCAKE activa, puede agregar más CAKE o renovar/extender la duración de su bloqueo para aumentar su saldo de veCAKE.&#x20;

#### ¿Qué sucede cuando la posición se desbloquea? ¿Puedo renovar de inmediato?&#x20;

Cuando la posición de staking de veCAKE esté desbloqueada, podrá retirar todo el CAKE depositado.&#x20;

Para renovar su posición, debe retirar todo el CAKE y configurar una nueva posición de staking eligiendo la cantidad a bloquear y la duración del bloqueo.&#x20;

#### Bloqueé durante 1 semana, ¿por qué el tiempo de bloqueo restante es inferior a 1 semana?&#x20;

Cuando bloquea con el nuevo veCAKE, la hora de desbloqueo se redondea al jueves más cercano con hora UTC. Por ejemplo, cuando bloqueas durante 1 semana el martes, tu hora de desbloqueo real será el próximo jueves, que es 2 días después.&#x20;

Puede obtener una vista previa de su tiempo de desbloqueo real en la parte inferior.&#x20;

#### ¿Puedo bloquear más CAKE en el grupo CAKE?&#x20;

No.&#x20;

Una vez que se implemente veCAKE, el pool de staking de CAKE quedará obsoleto y ya no aceptará más extensiones o depósitos de CAKE.&#x20;

Para bloquear CAKE y disfrutar de sus beneficios, vaya a la página de veCAKE.&#x20;

#### ¿Por qué no puedo migrar?&#x20;

Migrar del pool de CAKE al pool de veCAKE requiere que tengas una posición activa. Si su posición de staking en el pool de CAKE ya está desbloqueada, simplemente retire esos CAKE y cree una posición de staking de veCAKE nativa.&#x20;

En algunos casos, la migración no se puede realizar cuando el tiempo restante de bloqueo del pool de CAKE es inferior a 7 días. En tal caso, simplemente espere a que se desbloquee, retire esos CAKE y cree una posición de staking nativa de veCAKE.&#x20;

#### ¿Puedo retirar anticipadamente mi CAKE bloqueado?&#x20;

No.&#x20;

Una vez bloqueado, CAKE se depositará en el contrato veCAKE hasta el momento de desbloqueo.&#x20;

#### ¿Puedo migrar parcialmente mi CAKE?&#x20;

No.&#x20;

Solo puedes migrar toda tu posición del pool de CAKE a la vez.&#x20;

#### ¿Qué pasará con iCAKE, bCAKE, vCAKE y rCAKE?&#x20;

**Para iCAKE:** La cocina está trabajando arduamente para actualizar iCAKE para que sea compatible con el nuevo veCAKE. Esperamos que todas las IFO futuras se ejecuten con veCAKE como una versión mejorada de iCAKE.&#x20;

**Para bCAKE:** bCAKE de impulso de farming también se actualizará para admitir veCAKE. Los usuarios pronto podrán aumentar no solo V3 sino también otros tipos de liquidez de PancakeSwap con su veCAKE.&#x20;

**Para vCAKE:** El poder de votación instantánea pronto se actualizará para utilizar únicamente el número de saldo de veCAKE.&#x20;

**Para rCAKE:** Todos los titulares de veCAKE (ya sean nativos o migrados) se inscribirán automáticamente en el nuevo grupo de reparto de ingresos. La participación en los ingresos se distribuye según el cronograma existente. El antiguo grupo de reparto de ingresos se suspenderá y los usuarios podrán reclamar sus recompensas pendientes accediendo a la pestaña de beneficios.
