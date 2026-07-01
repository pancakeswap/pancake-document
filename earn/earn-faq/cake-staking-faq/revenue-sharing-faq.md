---
hidden: true
---

# FAQ de Distribución de Ingresos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### ¿Cómo se calculan las participaciones (rCAKE)? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

En cada distribución semanal, las participaciones de cada usuario se recalculan basándose en:

1. La cantidad de CAKE bloqueado que tienen
2. La duración de bloqueo restante de su CAKE bloqueado redondeada hacia abajo a semanas, y el tiempo máximo de bloqueo permitido (actualmente 52 semanas)

Por ejemplo:

Si un usuario tiene 50 CAKE bloqueados y el tiempo de bloqueo restante es de 10,3 semanas, entonces el usuario tiene `50 * (10 / 52 ) ~= 9,61` participaciones.

### Actualicé mi posición, ¿por qué todavía tengo 0 participaciones? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Las participaciones (rCAKE) se actualizan en cada distribución semanal a las 23:59 UTC todos los miércoles. Vuelve después de la próxima distribución semanal para ver tus participaciones actualizadas.

### ¿Por qué mis participaciones son 0 a pesar de tener una posición de staking activa? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Al calcular las participaciones (rCAKE), la duración de bloqueo restante se redondea hacia abajo a semanas. Por lo tanto, para recibir participaciones, debes asegurarte de que tu posición de staking se desbloquee no antes de la próxima distribución.

Por ejemplo, para recibir participaciones para la distribución de la semana 1. Debes:

* Unirte antes de las 23:59 UTC del 2 de agosto.
* Tener una posición activa de staking de CAKE a plazo fijo que se desbloquee después de las 23:59 UTC del 9 de agosto.

Si tu posición de staking se desbloquea antes de las 23:59 UTC del 9 de agosto, recibirás 0 participaciones para la semana 1.

### ¿Puedo unirme a un período de distribución a mitad de semana? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

No, como se mencionó, las participaciones se calculan al comienzo del período de distribución a las 23:59 UTC todos los miércoles. Por lo tanto, recibirás participaciones a partir de la próxima distribución y comenzarás a acumular recompensas entonces.

### ¿Cómo recibo más participaciones? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Dado que las participaciones se calculan en base al monto de CAKE y la duración de bloqueo restante, para recibir más participaciones puedes:

* Bloquear más CAKE
* Extender tu posición de staking

Ten en cuenta que después de agregar CAKE o extender, las participaciones NO se actualizan en tiempo real y solo se actualizan en cada distribución semanal.

### ¿Necesito actualizar mi posición de staking cuando agrego más CAKE o extiendo el staking? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

No, solo necesitas inscribirte una vez. Todas las operaciones posteriores en el pool de staking de CAKE informarán automáticamente al pool de distribución de ingresos y actualizarán tus participaciones en las próximas distribuciones semanales.

### ¿Por qué las recompensas inyectadas semanalmente no coinciden al 100% con el volumen mostrado en varios rastreadores (como la página de Información)?

El número de recompensas de CAKE inyectadas semanalmente puede no coincidir al 100% con los números calculados del volumen mostrado en varios rastreadores. Múltiples factores externos pueden impactar el número de recompensas de CAKE que se pueden convertir:

* El precio del token CAKE mientras se convierte y procesa la comisión de trading
* Los precios de los activos subyacentes mientras se convierte y procesa la comisión de trading
* Para ahorrar gas y costos operativos, los ingresos de blockchains distintas a BNB Chain se procesan mensualmente. Se inyectarán con un retraso de un mes con un promedio semanal.
* Algunos pares de trading pueden tener liquidez insuficiente mientras se procesa la comisión de trading.
* Algunos pares de trading pueden contener tokens con lógica personalizada que impide que su comisión sea procesada.

Los Chefs están trabajando duro para aplicar herramientas y prácticas que garanticen que más comisiones de trading generadas puedan ser procesadas y convertidas en CAKE.
