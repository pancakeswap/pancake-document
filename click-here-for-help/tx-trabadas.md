---
description: Como destrabar operaciones pendientes en Metamask
---

# Arreglar Transacciones Pendientes Trabadas

Si su transacción está atascada en pendiente en Metamask, y el botón "Cancelar" no está ayudando, es posible que deba usar este método para borrar su trabajo pendiente.

Este método funciona esencialmente sobrescribiendo la transacción atascada con otra transacción de mayor prioridad.

### **1. Enable Customized Transaction Nonce** <a id="1-enable-customized-transaction-nonce"></a>

1. Abrir el plugin de MetaMask .![](https://lh6.googleusercontent.com/fYsgD0BKjYVjrbCpbEQgMyWG_sW-4c2Ev7wu9bVzsOWtqIzCmYqiv6Xj8G_FY2TK5uYul3XaOY2WflfcW1W56R2KCuyW-Y5RjHH9DZDgUmATLlnOnMPn371nniPZqaaD7KAgYgMc)

2. Click en el círculo de color --&gt; **Settings \(Configuración si la usan en Español\)**.![](https://lh3.googleusercontent.com/DpSeFrHsmPNXU73C3NB9iRANEe81rJ2XUhbxs6k7PqJSVy6IkAijeX_TeIbUupalmD3mlE2G0C90XHJJy_JPk-_mswNRf4liUwR4AUhx2AWygp4yIP9kjHo1QQk_60wEtjGkfwSk)

3. En este menú, click en **Avanzado**.![](https://lh4.googleusercontent.com/F-o1qfi84wh6YNUP16b8lbyS6f8i04SYEUR2VrncMbBaoeaAjOw4Af_oOwRUfWnhZn6NFb4O1uopoc1KNego8XelHmDDWeRRAb0oMJGE_ZI_xJJeqfH-bJrai0pakyxC-235E4nq)

4. En **Advanced gas controls \(Controles avanzados de gas**\), darle a **ON**![](https://lh5.googleusercontent.com/ePraz_2Z8k1V62DMROjv0jbIjEcf8ATvaH-Lxe5wtoNo6oVTyRPelC1m7UVaizcNpW5bHByrbC9xv1KDZfjNnXvQ8J0ukHUHK7vK4rX5gpQVHmfyJr81wCGdeArvksNhshon1Btn)

5. En el mismo lugar, encuentra **Customize transaction nonce \(Personalizar nonce de transacción**\). Pasar a **ON** también

### **2. Encontrar la transacción atorada** <a id="2-find-your-stuck-transaction"></a>

Ahora vamos a encontrar la transacción que está atascada, y tomar nota de la "nonce". Ese es un tipo de identificador, que volveremos a usar más adelante.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6. Vuelve a la parte principal de Metamask. En la pestaña "Activos", busque el tipo de token de su transacción atascada \(en este caso, CAKE\).![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6. En el menú del token, busque la **transacción pendiente** en el área Cola. Click en la transacción para más detalles.![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7. Mira el **Nonce**, y toma nota de este número

### **3. Reescribir transacción pendiente** <a id="3-overwrite-the-stuck-transaction"></a>

Ahora vamos a hacer una nueva transacción para reemplazar la atascada. Personalizaremos el número de Nonce, para que sea el mismo que el que acabas de escribir.![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M_Qf9PqrqKwKENMLChq%2F-M_QfJwbI-p6skTud7_o%2Fimage.png?alt=media&token=13db2345-9ad7-46a4-9937-7f26d7187749)

8. Cree una nueva transacción para reemplazar la transacción atascada. Esta vez, **Gas Price \(Precio del Gas\)**. Aquí lo hemos aumentado de 9 a 20. Esto hará que sea más probable que su transacción se agregue a un bloque.![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M_Qf9PqrqKwKENMLChq%2F-M_Qft-wFWL0NENZfvV_%2Fimage.png?alt=media&token=14028feb-3c51-405c-bc3e-3d8e87d1d37d)

9. En la página de confirmación, asegúrate que el Gas Price \(Precio del Gas\) posee un valor más alto que antes.

10. Encontrar el **CUSTOM NONCE** y cambiar por el número que anotamos en el paso 7. Click en Confirmar.![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11. Tu nueva transacción debería aceptarse en un bloque. Para chequear, mira la pestaña de **Actividad**.![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12. La transacción completada debe mostrarse en la parte superior de la lista de actividades. Si todavía dice "Pendiente" en naranja, tendrá que esperar un poco más, o intentar el proceso de nuevo con una tarifa de gas aún más alta \(gas price\).

Dado que ninguna billetera puede crear dos transacciones del mismo nonce, si la transacción de reemplazo que realiza es exitosa, su transacción atascada se cancelará.



