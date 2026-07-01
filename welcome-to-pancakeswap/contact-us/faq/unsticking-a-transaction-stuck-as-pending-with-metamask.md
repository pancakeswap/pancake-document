---
description: Cómo "desatascar" cualquier transacción pendiente que esté bloqueada en tu MetaMask
---

# Cómo Desatascar Transacciones Pendientes en MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Si tu transacción está atascada como pendiente en Metamask y el botón "Cancelar" no está funcionando, es posible que necesites usar este método para limpiar tu cartera de transacciones.

Este método funciona esencialmente sobreescribiendo la transacción atascada con otra de mayor prioridad.

### **1. Habilitar el Nonce de Transacción Personalizado**

1\. Abre tu complemento de MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Haz clic en el ícono de círculo colorido en la parte superior derecha y haz clic en **Configuración** en el menú desplegable.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. En el menú Configuración, selecciona **Avanzado**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Desplázate hacia abajo hasta ver **Controles de gas avanzados**. Cambia esto a ACTIVADO.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Aún en la configuración Avanzada, sigue desplazándote hasta ver **Personalizar nonce de transacción**. Cambia esto a ACTIVADO.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Encontrar tu Transacción Atascada**

Ahora vamos a encontrar la transacción que está atascada y a tomar nota del "nonce". Eso es una especie de identificador, que reutilizaremos más tarde.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Vuelve a la página principal de MetaMask. En la pestaña "Assets", encuentra el tipo de token de tu transacción atascada (en este caso, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. En el menú del token, encuentra tu transacción **Pendiente** en el área de Cola. Haz clic en tu transacción para obtener más detalles.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Busca la entrada **Nonce** y toma nota de este número.

### **3. Sobreescribir la Transacción Atascada**

Ahora vamos a crear una nueva transacción para reemplazar la atascada. Personalizaremos el número de Nonce, para que sea el mismo que anotaste.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. Crea una nueva transacción para reemplazar tu transacción atascada. Esta vez, aumenta la **Tarifa de Transacción**. Aquí la hemos aumentado de 9 a 20. Esto hará que sea más probable que tu transacción sea añadida a un bloque.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. En la página de confirmación, asegúrate de que tu Precio del Gas ahora esté en tu nueva cantidad más alta.

10\. Encuentra la entrada **NONCE PERSONALIZADO** y cambia el nonce al número que anotaste en el paso 7. Ahora haz clic en Confirmar.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Tu nueva transacción debería ahora ser aceptada en un bloque. Para verificarlo, abre MetaMask y haz clic en la pestaña **Actividad**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Tu transacción completada debería aparecer en la parte superior de tu lista de Actividad. Si aún dice "Pendiente" en naranja, necesitarás esperar un poco más o intentar el proceso nuevamente con una tarifa de transacción (precio del gas) aún más alta.

Dado que ninguna billetera puede crear dos transacciones con el mismo nonce, si la transacción de reemplazo que realizas tiene éxito, tu transacción atascada será cancelada.<br>
