# Cómo usar TWAP

## ¿Qué es TWAP?

TWAP (Precio Promedio Ponderado por Tiempo) es un tipo de orden común utilizado en CeFi que divide una orden en tamaños de operación más pequeños y los ejecuta a intervalos regulares. El objetivo principal de una orden TWAP es reducir el impacto en el precio de la orden. También puede ser útil si un usuario desea implementar una estrategia de promediado del costo en dólares (DCA) y comprar un determinado token de forma regular (p. ej., una vez al mes).

Por tanto, TWAP es más adecuado cuando el tamaño de la orden es grande en comparación con la liquidez disponible, o cuando el usuario anticipa un período de alta volatilidad de precios sin una tendencia clara al alza o a la baja.

## ¿Cómo configurar una orden TWAP?

1. Ve a la página de Intercambio y selecciona la opción de orden TWAP haciendo clic en TWAP
2. Selecciona los tokens "Desde" y "Hasta" e introduce el importe que deseas intercambiar.
3. La interfaz permite tanto órdenes dTWAP de mercado, que ejecutan todas las operaciones al precio de mercado disponible, como órdenes dTWAP límite, que solo ejecutan operaciones individuales si están dentro del precio límite establecido por el usuario. \
   En este ejemplo elegimos ejecutar las órdenes TWAP al precio de mercado.
4. A continuación, especificamos los parámetros de TWAP. Hay 3 parámetros principales que controlan la efectividad de la orden dTWAP:
   1. Total de operaciones: Permite al usuario especificar el número de operaciones individuales en que se dividirá su orden. El control deslizante de la interfaz comienza con 1 operación y permite al usuario aumentar el número de operaciones individuales, o permite al usuario introducir manualmente el total de operaciones en el campo de entrada directamente.\
      Los usuarios deben tener en cuenta que hay cierta compensación al especificar este parámetro: más operaciones significa un tamaño de operación individual más pequeño, lo que significa menor impacto en el precio. Sin embargo, más operaciones también significa más transacciones y mayores comisiones de gas totales.&#x20;
   2. Intervalo de operaciones: Establece el intervalo de tiempo entre cada operación individual. La interfaz comienza con el mínimo permitido (2 min), que deja el tiempo mínimo para la guerra de ofertas de ejecutores y la liquidación de bloques entre cada fragmento. El usuario puede configurarlo con cualquier duración deseada. Una operación nunca se ejecutará antes de que transcurra este tiempo tras la operación anterior.\
      De nuevo, los usuarios deben ser conscientes al configurar este parámetro: intervalos más largos permitirían a los arbitrajistas una ventana más larga para cerrar cualquier discrepancia de precios en los pools afectados y devolver las reservas al equilibrio (a la par con el precio spot). Sin embargo, llevaría más tiempo completar la orden y añadiría incertidumbre al precio final de ejecución, especialmente en momentos de mayor volatilidad
   3. Duración máxima: El tiempo máximo durante el cual se puede ejecutar el importe total de todas las operaciones individuales que componen la orden dTWAP completa. Después de esta fecha límite, la operación vence, independientemente de los importes reales intercambiados.\
      Ten en cuenta que no todos los fragmentos pueden ejecutarse en las órdenes límite, dependiendo de si el precio permanece dentro de los parámetros establecidos. \
      La duración predeterminada recomendada se calcula multiplicando el número de intervalos por el intervalo de operación, y luego duplicando este importe para servir como margen y permitir tiempo suficiente para la actividad on-chain. (Ten en cuenta que establecer una duración más corta que la predeterminada anterior puede resultar en una orden parcialmente completada).

Como se puede observar, estos parámetros ofrecen una flexibilidad significativa para personalizar cada orden, teniendo en cuenta factores como las condiciones del mercado, las comisiones de gas actuales, etc.

8. Presiona "Colocar orden". Verifica los detalles de tu orden, acepta el aviso legal y presiona "Confirmar orden".
9. Una vez procesada la transacción, podrás ver el estado de tu orden en la sección de historial de órdenes, bajo "Órdenes abiertas".
10. Las órdenes abiertas pueden cancelarse en cualquier momento expandiendo la orden y haciendo clic en el botón "Cancelar orden".

Cosas a tener en cuenta

* Las órdenes se ejecutan en operaciones más pequeñas durante un período de tiempo específico y están sujetas a las condiciones del mercado y otros riesgos.
* Tu operación puede ejecutarse a un precio significativamente diferente al precio de mercado actual (aunque no peor que tu precio límite, si estableciste uno), lo que podría resultar en pérdidas significativas. Si el precio de mercado disponible es peor que el precio límite que has establecido, algunas de las operaciones de tu orden pueden no ejecutarse, resultando en una orden parcialmente completada.
* Las operaciones se basan en un protocolo descentralizado que utiliza ejecutores off-chain que compiten para completar las órdenes. Estos ejecutores tienen derecho a solicitar una comisión, que el protocolo descuenta del ejecutor ganador de los tokens de salida.&#x20;
* Los ejecutores pueden tener en cuenta las comisiones de gas de tus transacciones al establecer sus comisiones, lo que puede resultar en fluctuaciones en los importes de las comisiones.

<br>
