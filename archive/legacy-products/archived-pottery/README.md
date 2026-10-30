# 🍯 \[Archivado] Pottery

{% hint style="danger" %}
\[Archivado] Pottery – A partir del 3 de noviembre de 2023
{% endhint %}

Pottery combina el lock-staking de CAKE con elementos de lotería para darte la oportunidad de ganar un rendimiento mayor sobre tu depósito de CAKE. Es fácil y seguro, ya que siempre recuperarás como mínimo todo el CAKE que deposites.

## Especificaciones:

* Deposita CAKE en la página de Pottery con un mínimo de 1 CAKE&#x20;
* El depósito se cierra el primer lunes de cada mes para una cohorte de Pottery distinta (a las 23:59 UTC de ese lunes) y se abre el viernes anterior, alrededor de las 10:00 UTC, salvo que haya disposiciones especiales que se anunciarán con antelación (la primera Pottery cierra el 8 de agosto de 2022 a las 23:59 UTC)
* Durante la fase beta del producto, hay un límite al depósito total de CAKE para cada cohorte de Pottery (el límite máximo de depósito es de 600.000 CAKE)
* El CAKE depositado se dirigirá al pool de lock-staking y se bloqueará durante diez (10) semanas. El 80% del total de las recompensas de staking se enviará al pool de Pottery para los sorteos y el 20% se reservará para tu retiro&#x20;
* Para cada cohorte de Pottery (una por mes), habrá diez (10) sorteos semanales cada viernes (al mediodía UTC) tras el depósito, que producirán ocho (8) ganadores por semana; cada dirección puede ganar más de uno de los ocho puestos de ganador cada semana \*
* Cuanto mayor sea tu depósito en relación con el pool total, mayores serán tus posibilidades de ganar; los ganadores pueden reclamar su premio justo después de cada sorteo&#x20;
* Cada cohorte de Pottery realiza el sorteo por separado&#x20;
* Solo después de 10 semanas desde la fecha de bloqueo de la cohorte de Pottery podrás retirar tu CAKE&#x20;
* Pottery utiliza la implementación de VRF de Chainlink para una aleatoriedad verdadera y segura

## Cohorte de Pottery&#x20;

El viernes anterior al primer lunes de cada mes, se abrirá una cohorte de Pottery para que deposites CAKE y participes en ella durante las siguientes 10 semanas. Este esquema combina los depósitos para dirigirlos al pool de staking bloqueado, de modo que el contrato de Pottery de la cohorte pueda coordinar las recompensas de staking del depósito procedentes del pool de staking bloqueado.

Cada depósito y fecha de bloqueo será una cohorte independiente, una por cada mes; por ejemplo, todos los depósitos del 5 de septiembre de 2022 estarán en una cohorte y todos los depósitos del 3 de octubre de 2022 estarán en otra.

Aunque los sorteos pueden realizarse de forma simultánea para distintas cohortes, los pools de premios de cada cohorte están separados para que sea justo.

![(Solo con fines ilustrativos; la fecha real de bloqueo de la cohorte de la primera Pottery se ha fijado para el 8 de agosto de 2022)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

Por ejemplo, el 9 de septiembre de 2022 hay 2 sorteos separados: uno para la cohorte del 1 de agosto, como sexto sorteo semanal, y otro para la cohorte del 5 de septiembre, como primer sorteo semanal. Si la cohorte del 1 de agosto tiene un total de 100.000 CAKE depositados y la cohorte del 5 de septiembre tiene un total de 300.000 CAKE depositados, el premio semanal de la cohorte del 1 de agosto procederá únicamente de las recompensas de staking de esos 100.000 CAKE, mientras que el premio semanal de la cohorte del 5 de septiembre procederá únicamente de las recompensas de staking de esos 300.000 CAKE. Si solo depositaste CAKE en la cohorte del 1 de agosto, tienes la oportunidad de ganar el premio semanal del 9 de septiembre basado en las recompensas de staking de 100.000 CAKE. Si depositaste CAKE en ambas cohortes, la del 1 de agosto y la del 5 de septiembre, tienes la oportunidad de ganar ambos premios semanales el 9 de septiembre.

#### ¿Por qué necesitamos el sistema de cohortes? ¿Por qué no juntamos todo?

Como Pottery interactúa con el staking de CAKE a plazo fijo, cualquier depósito solo puede retirarse una vez transcurrida la duración del bloqueo. Si quisiéramos juntar todos los depósitos, aunque podríamos añadir más depósitos después del bloqueo inicial y bloquearlos también durante 10 semanas, los primeros depositantes no podrían retirar a tiempo.

## **Financiación de premios y asignación de recompensas de staking**

Los depósitos se agrupan en cohortes mensuales para organizar de forma más eficiente las recompensas de staking, que también se agrupan por cohorte. Las recompensas de staking se utilizan para financiar el pool de premios y algunas recompensas de staking por depositar en Pottery.

El 80% de las recompensas de staking se dirigirá a financiar el pool de premios para 10 sorteos semanales y el 20% restante se reservará como recompensas de staking cuando retires tu depósito de CAKE tras 10 semanas.

Sin embargo, dado que las recompensas de staking del pool de staking bloqueado de CAKE solo se distribuyen tras la duración del bloqueo (10 semanas en este caso), para ofrecer una mejor experiencia de producto y facilitar los sorteos semanales justo después de la fecha de depósito, el contrato toma prestado de la tesorería de CAKE el 80% del total estimado de recompensas de staking de la cohorte, según el APR en el momento del bloqueo. El CAKE prestado se utiliza para el pago de cada sorteo semanal.

Al final de las 10 semanas, cuando las recompensas se distribuyan desde el pool de staking, primero se reembolsará a la tesorería de CAKE y el resto se dirigirá de vuelta a la bóveda para que los usuarios lo retiren junto con su depósito inicial en la cohorte.

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEF6IySHEmy1P1k5S3W_PvnFMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMZKuQ4TnNTfKRdU8s3UXO1n0Smnp8_6sAg)

Por ejemplo, si la cohorte de Pottery del 1 de agosto de 2022 ha atraído 100.000 CAKE en depósitos en total, el rendimiento estimado de 10 semanas de staking bloqueado es de unos 3.674 CAKE. El contrato tomará prestado el 80% de esa cantidad, unos 2.940 CAKE, para el pool de premios de los 10 sorteos semanales, es decir, 294 CAKE en premios totales por cada sorteo semanal antes de comisiones.

Es importante tener en cuenta que las recompensas y el APR al final de la duración del depósito pueden cambiar a lo largo de las 10 semanas en función de otros depósitos y sus períodos de bloqueo en el pool de CAKE bloqueado, por lo que puede haber una pequeña desviación respecto a los porcentajes indicados (+/- 10%).

Todas las recompensas de staking netas de comisiones se devolverán a los depositantes a través del pool de premios o de las recompensas. Si el APR real es menor que el APR estimado en el momento del bloqueo, significa que se distribuyen más recompensas a los depositantes durante los sorteos semanales y menos para la parte de recompensas de staking. Si el APR real es mayor que el APR estimado en el momento del bloqueo, se distribuyen menos recompensas mediante los sorteos semanales y se reservan más para las recompensas de staking disponibles para retirar. En última instancia, el valor esperado es el mismo.

## **Cómo ganar: cálculo de probabilidades**

Las probabilidades se calculan según la proporción de la cantidad depositada respecto al tamaño total de depósito de la cohorte. En pocas palabras, cuanto más CAKE hayas depositado, mayor será la probabilidad de ganar en cada sorteo semanal. Por ejemplo, si has depositado 10.000 CAKE y el depósito total de la cohorte es de 100.000 CAKE, tienes un 10% de probabilidad de ganar en cada sorteo semanal.

Cada dirección puede ganar más de 1 de los 8 puestos de ganador cada semana.

En el caso extremo, si los 100.000 CAKE de la cohorte los depositas tú, ganarás todos los premios de cada sorteo semanal. Sin embargo, eso significa que el rendimiento final que obtendrás es el mismo que si pusieras 100.000 CAKE en el pool de staking bloqueado durante 10 semanas, pero además estarás pagando las comisiones de Pottery.

## **Riesgos: ¡importante!**

Tienes garantizado recuperar el 100% de lo que depositaste en 10 semanas. Sin embargo, _solo_ puedes retirar tu depósito de CAKE tras 10 semanas de bloqueo, sin ninguna otra forma de retirarlo antes.

Al participar en Pottery, arriesgas las recompensas de staking, junto con otras utilidades del CAKE bloqueado como iCAKE y vCAKE. Si no ganas nada en los 10 sorteos semanales, habrías perdido el 80% de las recompensas de staking que deberías haber obtenido si hubieras bloqueado tu CAKE en el pool de staking durante 10 semanas.

Participa según tu preferencia de riesgo: una vez depositado el CAKE, nadie puede hacer nada para ayudarte a retirarlo antes de tiempo.

## **Comisiones**

El ocho por ciento (8%) del bote de premios distribuido cada semana se cobrará como comisión para quemar. Nuestro objetivo es revisar y ajustar la estructura de comisiones en consecuencia después de la fase beta del producto.

## **¿Listo para participar?**

Si tienes clara la estructura del producto, los riesgos y las comisiones, consulta esta página sobre [cómo participar](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery/how-to-play-pottery) desde la interfaz web de PancakeSwap y las demás [FAQ de Pottery](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery/pottery-faq).
