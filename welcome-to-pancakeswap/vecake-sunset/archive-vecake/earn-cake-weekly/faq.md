# FAQ

### Bloqueé mi CAKE o migré mi posición del pool de CAKE. ¿Por qué sigo teniendo 0 participaciones? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Las participaciones se actualizan en cada distribución semanal a las 00:00 UTC todos los jueves.

Las recompensas se acumulan siempre que hayas completado el Staking durante una época completa.&#x20;

Las épocas son períodos de 7 días, comenzando cada jueves a las 00:00 UTC. Por ejemplo, si haces Staking el martes. Tu primera época comenzará el jueves. Una vez que hayas terminado el Staking hasta el próximo jueves, podrás reclamar tus recompensas de este jueves al próximo jueves, es decir, la época 1.

Vuelve a revisar cada jueves para obtener los números de recompensas actualizados.

### ¿Por qué mis participaciones/recompensas son 0 a pesar de tener una posición de Staking activa? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Al calcular las recompensas, la duración restante del bloqueo se redondea hacia abajo en semanas. Por lo tanto, para recibir participaciones, debes asegurarte de que tu posición de Staking se desbloquee no antes del próximo jueves a las 00:00 UTC.

Por ejemplo, la semana 1 comienza a las 00:00 UTC del jueves, 1 de enero. Para recibir recompensas de la distribución de la semana 1. Debes:

* Unirte antes de las 00:00 UTC del 1 de enero.
* Tener una posición de Staking de veCAKE activa, que se desbloquee igual o después de las 00:00 UTC del 15 de enero. (jueves de la semana 3)

Ten en cuenta que si tu posición de Staking se desbloquea a las 00:00 UTC del 8 de enero (jueves de la semana 2). Seguirás recibiendo 0 recompensas para la semana 1 porque tu balance de veCAKE se vuelve 0 a las 00:00 UTC del 8 de enero.

### ¿Puedo unirme a un período de distribución a mitad de semana? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

No, como se mencionó, las recompensas solo pueden comenzar a acumularse cuando ya estás haciendo Staking al inicio de la época. Que es cada semana a las 00:00 UTC del jueves.&#x20;

### ¿Cómo recibo más recompensas? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Dado que tus participaciones en los pools se calculan según el balance de veCAKE en el momento de la distribución, que es a las 00:00 UTC del próximo jueves. Para recibir más recompensas, simplemente aumenta tu balance de veCAKE:

* Bloqueando más CAKE en la posición de Staking de veCAKE
* Renovando tu posición de Staking

Ten en cuenta que después de agregar CAKE o extender, tus participaciones solo se actualizarán al inicio de la próxima época, que es a las 00:00 UTC del próximo jueves.

### ¿Por qué las recompensas semanales inyectadas no coinciden al 100% con el volumen mostrado en varios rastreadores (como la página de Información)? ¿Por qué las recompensas semanales del pool de CAKE no coinciden al 100% con los resultados de la votación de gauges?

La cantidad de recompensas de CAKE inyectadas semanalmente puede no coincidir al 100% con los números calculados a partir del volumen mostrado en varios rastreadores. Múltiples factores externos pueden afectar la cantidad de recompensas de CAKE que pueden convertirse:

* Precio del token CAKE mientras la comisión de trading se convierte y procesa
* Precios de los activos subyacentes mientras la comisión de trading se convierte y procesa
* Para ahorrar gas y costos operativos, los ingresos de blockchains distintas a BNB Chain se procesan mensualmente. Se inyectarán con un retraso de un mes con promedio semanal.
* Algunos pares de trading pueden tener liquidez insuficiente mientras se procesa la comisión de trading.
* Algunos pares de trading pueden contener tokens con lógica personalizada que impide que su comisión sea procesada.
* Retrasos en las transacciones debidos al rendimiento de las infraestructuras y los sistemas de soporte.

Los chefs trabajan arduamente para aplicar herramientas y prácticas que garanticen que más comisiones de trading generadas puedan procesarse y convertirse en CAKE.
