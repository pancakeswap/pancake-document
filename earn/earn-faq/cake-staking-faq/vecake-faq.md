---
hidden: true
---

# FAQ de veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### ¿Cuál es la diferencia entre CAKE bloqueado y veCAKE? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE es una nueva versión del staking de CAKE a plazo fijo con más beneficios y poder para los titulares de CAKE bloqueado. Incluyendo votación de peso de gauge, incentivos adicionales, impulso de rendimiento y más.

#### ¿Qué sucede con las recompensas del pool de CAKE cuando se despliega el nuevo veCAKE? <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

Las emisiones de recompensas del pool de CAKE se redirigirán para recompensar a todos los titulares de veCAKE según su saldo de veCAKE frente al suministro total.

Las recompensas de CAKE y las recompensas semanales de distribución de ingresos ahora pueden reclamarse semanalmente los jueves.

Ten en cuenta que para seguir recibiendo recompensas, los usuarios deberán migrar al nuevo staking de veCAKE.

#### ¿Cuál es la duración máxima que puedo bloquear mi CAKE? <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

La duración máxima para bloquear tu CAKE ha sido extendida ahora a 4 años.

#### ¿veCAKE es un nuevo token? ¿Puede transferirse? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE es un número generado en tiempo real basado en la cantidad de CAKE bloqueado y el tiempo de bloqueo restante. No es un token estándar y no puede transferirse.

#### ¿Por qué cambió mi saldo de veCAKE? ¿Cómo calcular su saldo? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

El saldo de veCAKE disminuye linealmente a 0 según la duración de bloqueo restante. Por lo tanto, a medida que nos acercamos al tiempo de desbloqueo, tu saldo disminuye.

El saldo de veCAKE puede calcularse mediante:

```javascript
lockedAmount // cantidad de CAKE bloqueado
currentTime // tiempo actual
lockEndTime // el tiempo de desbloqueo
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // tiempo máximo de bloqueo (4 años)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### ¿Cómo aumentar mi veCAKE? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Una vez que tengas una posición activa de veCAKE, puedes agregar más CAKE o renovar/extender la duración de tu bloqueo para impulsar tu saldo de veCAKE.

#### ¿Qué sucede cuando la posición se desbloquea? ¿Puedo renovarla de inmediato? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Cuando la posición de staking de veCAKE se desbloquea, puedes retirar todo el CAKE en staking.

Para renovar tu posición, necesitas retirar todo el CAKE y configurar una nueva posición de staking eligiendo la cantidad a bloquear y la duración del bloqueo.

#### Bloqueé por 1 semana, ¿por qué el tiempo de bloqueo restante es menor a 1 semana? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Cuando bloqueas con el nuevo veCAKE, el tiempo de desbloqueo se redondea hacia adelante al jueves más cercano en hora UTC. Por ejemplo, cuando bloqueas por 1 semana el martes, tu tiempo real de desbloqueo será el próximo jueves, que es 2 días después.

Puedes ver tu tiempo real de desbloqueo en la parte inferior.

#### ¿Puedo bloquear más CAKE en el pool de CAKE? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

No.

Una vez que veCAKE esté desplegado, el pool de staking de CAKE quedará obsoleto y ya no aceptará ninguna extensión o depósito adicional de CAKE.

Para bloquear CAKE y disfrutar de sus beneficios, ve a la página de veCAKE.

#### ¿Por qué no puedo migrar? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

Migrar del pool de CAKE a veCAKE requiere tener una posición activa. Si tu posición de staking del pool de CAKE ya está desbloqueada, simplemente retira ese CAKE y crea una posición nativa de staking de veCAKE.

En algunos casos, la migración no se puede realizar cuando el tiempo de bloqueo restante del pool de CAKE es inferior a 7 días. En tal caso, simplemente espera el desbloqueo, retira ese CAKE y crea una posición nativa de staking de veCAKE.

#### ¿Puedo retirar anticipadamente mi CAKE bloqueado? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

No.

Una vez bloqueado, el CAKE estará en staking en el contrato de veCAKE hasta el tiempo de desbloqueo.

#### ¿Puedo migrar parcialmente mi CAKE? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

No.

Solo puedes migrar toda tu posición del pool de CAKE a la vez.

#### ¿Qué pasará con iCAKE, bCAKE, vCAKE y rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Para iCAKE:**

El iCAKE de IFO ha sido actualizado ahora para admitir veCAKE. Consulta:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Para bCAKE:**

El bCAKE de impulso de granja ha sido actualizado ahora para admitir veCAKE. Consulta:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Para vCAKE:**

El vCAKE de votación ha sido actualizado ahora para admitir veCAKE. Consulta:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Para rCAKE:**

Todos los titulares de veCAKE (ya sea nativos o migrados) se inscribirán automáticamente en el nuevo pool de distribución de ingresos. Las participaciones de ingresos se distribuyen según el cronograma existente. El antiguo pool de distribución de ingresos se discontinuará; los usuarios pueden reclamar sus recompensas pendientes yendo a la tarjeta de beneficios. Consulta:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### ¿Se pueden usar billeteras multifirma para interactuar con veCAKE?

Sí

Sin embargo, se implementó un modificador `noContract` en el contrato de staking de veCAKE para las direcciones que no están en la lista blanca. Para habilitar el staking o la migración desde el pool de staking de CAKE a plazo fijo, todas las billeteras multifirma basadas en contratos deben realizar una acción de auto-inclusión en la lista blanca de una sola vez.

Para incluirte en la lista blanca, visita cualquiera de las siguientes páginas:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Debería aparecer un aviso. Haz clic en "Whitelist" y procede con la transacción en tu billetera multifirma.

Se enviará una transacción al propietario del veCAKE, que es un contrato con una función de escritura sin permisos para permitir que cualquier contrato realice la auto-inclusión en la lista blanca.

Si el aviso no aparece, sigue estas instrucciones para ejecutar la transacción desde [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11):

```
// llamar:
VECakeOwner.setWhitelist(bool _status = true)

// Dirección de VECakeOwner:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### ¿Por qué hay múltiples APRs?

Bloquear CAKE para obtener veCAKE proporciona una serie de grandes beneficios en toda la suite de productos construidos por PancakeSwap. Los beneficios e incentivos vienen en diferentes formas y de diferentes fuentes. Por lo tanto, hay múltiples APRs.

Puedes ganar todos ellos simultáneamente, por lo que el APR combinado será la suma de todos los APRs.

Ten en cuenta que muchos otros beneficios de veCAKE no pueden cuantificarse en el formato de APRs, como el [Impulso de Rendimiento de Granja bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) o el [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). Asegúrate de revisarlos también.

#### ¿Qué es el APR del Pool de veCAKE?

Este es el incentivo proveniente de las emisiones de CAKE, con su tasa controlada por el gauge de votación del Pool de veCAKE.

Para aumentar la emisión a este gauge, consulta [Gauge Voting](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### ¿Qué es el APR de Distribución de Ingresos?

Este es el incentivo proveniente de la distribución de ingresos del protocolo, procedente de las comisiones de intercambio cobradas en los productos DEX.

Consulta [Revenue Sharing](/broken/pages/wQegezs7c6A2HzQjPEjh) para más información.
