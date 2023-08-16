# FAQ

![](<../../../.gitbook/assets/image (14) (1).png>)

**¿Cómo se calculan los multiplicadores bCAKE?**&#x20;

Puede notar que obtiene diferentes multiplicadores de boost de bCAKE cuando participa en diferentes farms.&#x20;

Eso es porque los multiplicadores de bCAKE - Farm Boosters se calculan utilizando las siguientes métricas al momento de la activación o actualización:

* `userLpStakedAmount`: la cantidad de tokens LP que está depositando en la farm
* `totalLpStakedAmount`: el número total de tokens LP en la farm
* `userLockedAmount`: la cantidad de CAKE que está depositando en el pool de CAKE a plazo fijo&#x20;
* `userLockedDuration`: la duración del plazo de bloqueo de su pool de CAKE
* `totalLockedAmount`: El número total de CAKE bloqueados en el pool CAKE de plazo fijo&#x20;
* `averageLockedDuration`: La duración promedio del plazo de bloqueo en el pool de CAKE de plazo fijo

El multiplicador se calcula utilizando el siguiente método:&#x20;

1. `resultA = constantA * userLpStakedAmount`&#x20;
2. `resultB = (totalLpStakedAmount * userLockedAmount * userLockedDuration / constantB) / (totalLockedAmount * averageLockedDuration)`&#x20;
3. `boostMultiplier = min(userLpStakedAmount, (resultA + resultB)) / resultA`&#x20;

`constantA y constantB` las establece la cocina y están sujetas a futuros ajustes según los comentarios de la comunidad y las condiciones del mercado.&#x20;

Estos son algunos ejemplos del cálculo:

![](<../../../.gitbook/assets/image (55).png>)

![](<../../../.gitbook/assets/image (12) (2).png>)

{% hint style="info" %}
**TL;DR (Resumen nivel: Conejo degen)**

Cuantos más LP quieras potenciar...

... más CAKE necesitas bloquear por más tiempo&#x20;
{% endhint %}

**¿Por qué mis multiplicadores cambian incluso después de la activación?**&#x20;

Tenga en cuenta que cualquier acción del usuario en las farms o el pool de staking de CAKE actualizará automáticamente su multiplicador de boost en función de los últimos datos y estadísticas de las farms y el pool de CAKE, que incluyen, entre otros:&#x20;

* Stake/Unstake de tokens LP a/desde Farm&#x20;
* Cosecha de las recompensas de CAKE de Farm&#x20;
* Extender la duración de su pool CAKE bloqueado
* Agregar más CAKE a su pool bloqueado&#x20;
* Convertir su pool de CAKE en flexible&#x20;

{% hint style="info" %}
Tenga en cuenta:&#x20;

Con el fin de garantizar la equidad y evitar posibles abusos y trampas utilizando datos desactualizados, el Farm booster está diseñado para ser de gobernanza de la comunidad.&#x20;

Por lo tanto, cualquiera puede llamar a la función `refresh(address _user, uint256 _pid)` en el contrato de Farm Booster para actualizar los multiplicadores de boost de cualquier persona utilizando los datos más recientes.&#x20;
{% endhint %}

**¿Dónde están mis recompensas de CAKE después de activar o desactivar el potenciador?**

![](<../../../.gitbook/assets/image (4) (3).png>)

Mientras farmea con bCAKE - Farm Boosters, algunas de sus recompensas de CAKE cosechadas pueden almacenarse temporalmente en el contrato de Farm Boosters. Cada vez que esto suceda, verá una línea de puntos debajo de sus "CAKE EARNED" (CAKE ganados), lo que indica que, además del número que se muestra, tiene más recompensas de CAKE en el contrato de Farm Boosters.&#x20;

**Esta parte de las recompensas de CAKE se enviará automáticamente a su billetera en la próxima cosecha, depósito o retiro.**&#x20;

Para cosecharlos ahora mismo, simplemente haga clic en el botón "Harvest"(Cosechar).

![](<../../../.gitbook/assets/image (3) (1) (1) (2).png>)

Para verificar la cantidad de recompensas adicionales en el contrato de Farm Boosters, desplace el cursor o mantenga presionado el número con la línea de puntos.&#x20;

