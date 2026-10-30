---
description: Cómo "desatascar" las transacciones pendientes que están atascadas en tu MetaMask
---

# Solucionar transacciones pendientes atascadas en MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Si tu transacción está atascada como pendiente en Metamask y el botón “Cancel” no te ayuda, puede que necesites usar este método para despejar tu cola.

Este método consiste, básicamente, en sobrescribir la transacción atascada con otra transacción de mayor prioridad.

### **1. Activa el nonce de transacción personalizado**

1\. Abre tu extensión de MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Haz clic en el icono del círculo de colores en la parte superior derecha y selecciona **Settings** en el menú desplegable.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. En el menú Settings, selecciona **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Desplázate hacia abajo hasta ver **Advanced gas controls**. Actívalo (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Sin salir de Advanced settings, sigue desplazándote hasta ver **Customize transaction nonce**. Actívalo (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Encuentra tu transacción atascada**

Ahora vamos a encontrar la transacción atascada y a anotar el “nonce”. Es una especie de identificador que reutilizaremos más adelante.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Vuelve a la página principal de MetaMask. En la pestaña “Assets”, busca el tipo de token de tu transacción atascada (en este caso, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. En el menú del token, busca tu transacción **Pending** en el área Queue. Haz clic en tu transacción para ver más detalles.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Busca la entrada **Nonce** y anota este número.

### **3. Sobrescribe la transacción atascada**

Ahora vamos a crear una nueva transacción para reemplazar la atascada. Personalizaremos el número de Nonce para que sea el mismo que acabas de anotar.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Crea una nueva transacción para reemplazar tu transacción atascada. Esta vez, aumenta la **Transaction Fee**. Aquí la hemos aumentado de 9 a 20. Esto hará más probable que tu transacción se incluya en un bloque.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. En la página de confirmación, asegúrate de que tu Gas Price ahora tenga el nuevo importe más alto.

11\. Busca la entrada **CUSTOM NONCE** y cambia el nonce por el número que anotaste en el paso 8. Ahora haz clic en Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Tu nueva transacción ya debería ser aceptada en un bloque. Para comprobarlo, abre MetaMask y haz clic en la pestaña **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Tu transacción completada debería aparecer en la parte superior de tu lista de Activity. Si sigue diciendo “Pending” en naranja, tendrás que esperar un poco más o volver a intentar el proceso con una comisión de transacción (gas price) aún más alta.

Dado que ninguna billetera puede crear dos transacciones con el mismo nonce, si la transacción de reemplazo que hagas tiene éxito, tu transacción atascada se cancelará.<br>
