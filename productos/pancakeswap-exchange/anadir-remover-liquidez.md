# Añadir/Remover Liquidez

![](<../../.gitbook/assets/docs-masthead (2).png>)

La liquidez es fundamental para el funcionamiento del Exchange PancakeSwap. Puede agregar liquidez para cualquier par de tokens a través de la página Liquidez.

A cambio de agregar liquidez, recibirás fees de trading por ese par y recibirás tokens LP que puedes depositar en [Farms ](https://pancakeswap.finance/farms)para ganar recompensas cake.

### **Exchange V3** <a href="#adding-liquidity" id="adding-liquidity"></a>

Para proveer liquidez, deberás aportar un monto de cualquier par de tokens que quieras. El menor valor de los dos tokens (en USD) será el límite de la liquidez que puede aportar.

Puedes fácilmente intercambiar cualquier token que necesites. Visita nuestra guía [Cómo hacer un Trade](how-to-trade-on-the-pancakeswap-exchange.md) si lo necesitas.

En este ejemplo, aportaremos liquidez en V3 usando ETH y USDC.



1 - Visita la página [Liquidez](https://pancakeswap.finance/liquidity).

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

2 - Clic en el botón “Add Liquidity” (Agregar liquidez).



3 - Elige los dos tokens del par de trading que quieras aportar liquidez. Aquí, usaremos ETH y USDC como ejemplo.

![](<../../.gitbook/assets/image (12).png>)



4 - La interfaz eligirá automáticamente el tier de fee más popular y configurará el rango de precios por tí.



5 - Puedes confirmar la versión así como el tier de fee del pool de liquidez al que estás aportando observando la indicación de “V3 LP - x% fee tier” como se ve en la siguiente imagen.

![](<../../.gitbook/assets/image (13).png>)

* Si quieres personalizar el tier del fee, clic en “More” (más), y elije el tier deseado.
* Ten en cuenta que siempre es aconsejable aportar liquidez con el tier más popular.



6 - Puedes revisar y confirmar el rango de precios en la ventana de a la derecha de la pantalla.

![](<../../.gitbook/assets/image (2) (5).png>)

* El gráfico muestra los niveles de liquidez a través de todo el rango de precios. Puedes acercar y alejar con el zoom usando los botones correspondientes. Puedes hacer un paneo y navegar por el gráfico, arrastrando horizontalmente los ejes.
* Si quieres personalizar el rango de precios, simplemente arrastra las barras, clic en los botones + y - en los precios, o ingresa manualmente los dos precios.
* Aunque no es recomendable, puedes aportar liquidez en todo el rango entero, haciendo clic en el botón “Full Range” (rango completo).



7 - Ingrese la cantidad de uno de los tokens bajo “Deposit Amount” (Monto de depósito). El otro valor será calculado y completado automáticamente. Si uno de los tokens no tuviera suficiente saldo, verás un error y el botón se grisará. Por favor ingresa un monto menor, o usa el botón “MAX” para ingresar el valor máximo disponible.

![](<../../.gitbook/assets/image (4).png>)



8 - Clic en el botón “Enable USDC”. Si estás aportando liquidez junto con algún token que no sea ETH, deberás hacer clic en enable (habilitar) dos veces por cada token en tu par. Tu wallet te pedirá que confirmes.

![](<../../.gitbook/assets/image (7).png>)



9 - El botón “Add” (agregar) se encenderá. Clic para continuar.

![](<../../.gitbook/assets/image (5).png>)



10 - Una nueva ventana emergente aparecerá para que veas tu posición de liquidez. Si todo luce bien, clic "Add" (agregar) otra vez para continuar.

![](<../../.gitbook/assets/image (3).png>)



11 - Tu wallet te pedirá confirmación. Confirma la transacción desde tu wallet.



12 - Enseguida, verás tu nueva posición de liquidez en la página “My Liquidity” (mi liquidez). Y podrás acceder a los detalles al hacer clic en la posición.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### **Remover liquidez**

Para remover la liquidez.

1 - Visita la página [Liquidez](https://pancakeswap.finance/liquidity)**.**

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



2 - Clic en la posición de la que quieras remover la liquidez, de la lista en “Your Liquidity" (tu liquidez). Puedes usar el filtro para revisar rápidamente todas las posiciones en V3.

![](<../../.gitbook/assets/image (11).png>)



3 - Clic en “Remove”. Aparecerá una nueva ventana.

![](<../../.gitbook/assets/image (10).png>)



4 - Usa los botones o desliza la barra para elegir cuánta liquidez vas a remover. Elige “MAX” para remover la totalida de la liquidez del par en cuestión.

5 - Clic “Remove” para continuar.

6 - Aparecerá una ventana mostrando cuántos tokens recibirás.  Clic “Remove” otra vez. Tu wallet te pedirá que confirmes la acción.

7 - Una vez confirmada la transacción, recibirás los dos tokens de tu par. Y si no retiraste la totalidad de la liquidez, el saldo se actualizará en la página de liquidez.

### **Exchange V2** <a href="#adding-liquidity" id="adding-liquidity"></a>

**Agregar Liquidez**

En este ejemplo, añadiremos liquidez V2 usando BNB y CAKE.

{% hint style="warning" %}
Ten en cuenta que el ejemplo es sólo a título ilustrativo, el par CAKE/BNB ha sido migrado a V3. Siempre aporte liquidez en V3, salvo que alguno de los tokens no soporte la V3. O que la mayoría de la liquidez del par no haya sido migrada.
{% endhint %}

1. Visita la página [Liquidez](https://pancakeswap.finance/liquidity).
2. Clic en el botón “Add Liquidity” (Agregar liquidez).
3. Elige los dos tokens del par de trading que quieras aportar liquidez. Aquí, usaremos BNB y CAKE como ejemplo.
4. La interfaz selecciona agregar liquidez en V3 por defecto, con algunas excepciones:
   1. Si el par tiene un Farm activo en PancakeSwap V2, seteará por defecto en V2.
   2. Si el par tiene un pool de liquidez V2 actual, presentará un link para agregar liquidez a V2. Clic en ese link para cambiar a V2.
5. Confirma que estás aportando en V2, chequeando que se muestre “V2 LP - 0.25 fee tier”.
6. Ingrese la cantidad de uno de los tokens bajo “Deposit Amount” (Monto de depósito). El otro valor será calculado y completado automáticamente. Si uno de los tokens no tuviera suficiente saldo, verás un error y el botón se grisará. Por favor ingresa un monto menor, o usa el botón “MAX” para ingresar el valor máximo disponible.
7. Clic en el botón “Enable CAKE”. Si estás aportando liquidez junto con algún token que no sea BNB, deberás hacer clic en enable (habilitar) dos veces por cada token en tu par. Tu wallet te pedirá que confirmes.
8. El botón “Add” (agregar) se encenderá. Clic para continuar.
9. Tu wallet te pedirá confirmación. Confirma desde allí tu transacción.
10. Enseguida, verás tu saldo de tokens LP en la página de liquidez, junto con las demás posiciones de liquidez en V3 o StableSwap.



### **Remover liquidez**

Para remover la liquidez.

1 - Visita la página [Liquidez](https://pancakeswap.finance/liquidity)**.**

2 - Clic en la posición de la que quieras remover la liquidez, de la lista en “Your Liquidity" (tu liquidez). Puedes usar el filtro para revisar rápidamente todas las posiciones en V2.

3 - Clic en “Remove”. Aparecerá una nueva ventana.

4 - Usa los botones o desliza la barra para elegir cuánta liquidez vas a remover. Elige “MAX” para remover la totalida de la liquidez del par en cuestión.

5 - Clic en "Enable" (habilitar). Tu wallet te pedirá que confirmes.

6 - El botón “Remove” se encenderá. Clic para continuar.

7 - Aparecerá una ventana mostrando cuántos tokens recibirás.  Clic “Remove” otra vez. Tu wallet te pedirá que confirmes la acción.

8 - Una vez confirmada la transacción, recibirás los dos tokens de tu par. Y si no retiraste la totalidad de la liquidez, el saldo se actualizará en la página de liquidez.
