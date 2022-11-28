# vCAKE

### **¿Qué es vCAKE?** <a href="#_ysspck2qqbf7" id="_ysspck2qqbf7"></a>

vCAKE es un número que representa el poder de voto aumentado en función de la posición de participación en CAKE a plazo fijo de un usuario.

El número de vCAKE se agregará a su poder de voto total.

**Similar a iCAKE, vCAKE NO es un token nuevo.**

CAKE NO ES transferible ni negociable.

### **¿Cómo calcular vCAKE?** <a href="#_cxjbmydajl22" id="_cxjbmydajl22"></a>

vCAKE se calcula en base a dos variables:

1. La cantidad de CAKE ubicada en el Stake Pool de plazo fijo
2. Las duraciones de bloqueo restantes de las posiciones de Stake en plazo fijo

Para el punto 2, es importante aclarar que la duración restante del bloqueo no es (a) cuántas semanas comprometió su CAKE cuando lo bloqueó por primera vez (por ejemplo, 52 semanas), sino (b) El tiempo restante en su bloqueo. En este caso, si bloqueó CAKE durante 52 semanas hace aproximadamente 10 semanas, la duración restante del bloqueo es de 42 semanas, no de 52 semanas.

Si la duración restante de su Stake es inferior a una semana, su vCAKE es igual a la cantidad de CAKE bloqueado en el Pool de CAKE.

Si la duración restante de su Stake es más de una semana, su vCAKE es igual a la cantidad de CAKE bloqueado, multiplicada por la cantidad de semanas restantes en el Pool.

Por ejemplo:

* Alice bloqueó 100 CAKE durante 52 semanas; su posición de Stake se desbloqueará en 40 semanas. Ella tiene 100 x 40 = 4000 vCAKE
* Bob bloqueó 100 CAKE durante 52 semanas; su posición de Stake se desbloqueará en 52 semanas. Él tiene 100 x 52 = 5200 vCAKE
* Carole bloqueó 100 CAKE durante diez semanas; y su posición de Stake ha terminado. Ella tiene 100 vCAKE

![](<../../.gitbook/assets/0 (1)>)

### **¿Cómo comprobar el número de vCAKE?** <a href="#_2jlcyocwcfmp" id="_2jlcyocwcfmp"></a>

Si estas emitiendo un voto, encontraras la cantidad de vCAKE en el desglose de “Voting Power” haciendo click en el botón “>” sobre la ventana de “Confirm Vote”.

![](../../.gitbook/assets/1)

Si estás haciendo una propuesta comunitaria, puedes verificar tu poder de voto haciendo click en "Check your voting power" en la parte inferior del panel “Actions”.
