---
hidden: true
---

# FAQ de Votación de Gauges

### Tengo una posición activa, ¿por qué no puedo votar? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Asegúrate de que tu tiempo de desbloqueo sea igual o posterior a 1 semana después del tiempo de instantánea de la época actual.

Si tu posición se desbloquea en el momento de la instantánea, significa que tienes 0 veCAKE en ese momento. Por lo tanto, no puedes votar.



### ¿Puedo votar justo después de configurar una posición veCAKE?

Sí.

Una vez que tu posición esté configurada, puedes usar tu CAKE para votar de inmediato.

Sin embargo:

* No se pueden emitir votos dentro de las últimas 24 horas de una época.
* No puedes actualizar tu decisión de votación en un gauge específico con más frecuencia que cada 10 días.
* Asegúrate de que tu posición no se desbloquee antes o en el momento de la instantánea.



### ¿Puedo obtener más veCAKE o votos?

Sí, simplemente agrega más CAKE o extiende tu posición de bloqueo.

Ten en cuenta que después de obtener más veCAKE al agregar CAKE o extender el tiempo de bloqueo, necesitas actualizar manualmente cada gauge volviendo a enviar la solicitud de voto.



### ¿Por qué cambiaron los resultados de la votación después del período de recuento?

Durante el período de recuento, la Cocina de PancakeSwap emitirá sus votos basándose en diversas métricas de todos los gauges.

El objetivo es:

* Garantizar que los pools de liquidez principales reciban un retorno competitivo en sus posiciones LP
* Garantizar que los acuerdos existentes con socios de Syrup Pool se cumplan antes de migrarlos completamente al sistema de votación de gauges veCAKE
* Garantizar que cualquiera de las granjas más pequeñas que no recibieron votos después del lanzamiento de veCAKE recibirá al menos alguna asignación en el despliegue inicial, limitada a sus niveles de emisión actuales.

Consulta esta propuesta para más detalles: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### ¿Por qué están disminuyendo mis números de voto?

Porque cuando votamos en los gauges, votamos usando nuestro veCAKE. Y el saldo de veCAKE disminuye gradualmente con el tiempo de bloqueo restante.

Tus votos disminuirán hasta llegar a 0 cuando tu posición veCAKE se desbloquee.

Para obtener más votos, adquiere más veCAKE agregando más CAKE al bloqueo o extendiendo el bloqueo.



### Después de obtener más veCAKE, ¿por qué no puedo votar por más gauges?

Al votar en los gauges, emitimos nuestros votos definiendo qué % de nuestro veCAKE va a cada gauge.

Por lo tanto, aunque hayas obtenido más veCAKE, si has asignado el 100% de tu veCAKE en los últimos 10 días, no puedes cambiar la decisión hasta el final del período de enfriamiento de 10 días.



### Los resultados de la votación se han contabilizado, ¿por qué no está cambiando la tasa de emisión?

Tarda aproximadamente 72 horas en aplicar los resultados de la votación a los diversos productos de emisión en PancakeSwap. Los Chefs continuarán automatizando este proceso para acortar la brecha y también mejorar la precisión.



### ¿Por qué el gauge por el que voté no recibió emisiones de CAKE en la siguiente época?

Los gauges incluidos en la lista blanca necesitan recibir votos que correspondan a un mínimo de 1 CAKE por día en emisiones, antes de poder recibir cualquier CAKE.
