# Cómo usar Farms (BscScan)

![](<../../.gitbook/assets/docs masthead (26).png>)

Dado que requiere varios pasos, el uso de Farms con PancakeSwap puede parecer intimidante al principio. Esta guía te guiará a través del uso del contrato de Farms directamente a través de BscScan.&#x20;

Entienda que el uso de BscScan para interactuar con contratos no se recomienda para principiantes. Si no te sientes seguro, te sugerimos que use la guía [Cómo usar Farms](https://docs.pancakeswap.finance/v/espanol/products/yield-farming/como-usar-yield-farm-en-pancakeswap) en su lugar.

## Encontrando el idetificador de proceso del Farm <a href="#finding-farm-process-identifier" id="finding-farm-process-identifier"></a>

Para interactuar correctamente con el contrato inteligente de Farming, necesitará el identificador de proceso coincidente (PID) para su par LP. Por ahora, la forma más fácil de localizar esto es verificar GitHub.

1\. Abrir el [Código de Farms de PancakeSwap en GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Ctrl**/**command** + **F** y buscar el par necesario (no por nombre de proyecto). Por ejemplo, 'CAKE-BUSD'.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MbouIhyaIRlEhCs9AjM%2Fimage.png?alt=media\&token=50c95e71-3b4e-4f72-b618-0a33bf493f89)

3\. Copiar el número de PID—en este caso 389—donde puedas acceder fácilmente. Lo necesitarás más adelante.

## Depositando LP Tokens a través de BscScan <a href="#depositing-lp-tokens-through-bscscan" id="depositing-lp-tokens-through-bscscan"></a>

Hay algunas cosas involucradas en el depósito de tokens LP usando BscScan. Lo hemos dividido en pasos para que sea más fácil de seguir.

### Obtener la dirección del contrato de Staking principal <a href="#getting-the-main-staking-contract-address" id="getting-the-main-staking-contract-address"></a>

La dirección del contrato de Staking principal es: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Pero suponiendo que quieras confirmarlo, visita la [página de BscScan de PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Verá la dirección en la parte superior izquierda. Haga clic en el icono para copiarlo en el portapapeles. Lo necesitarás pronto.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp1nXv8BY\_GqBCaIhY%2Fimage.png?alt=media\&token=d2d5c5f1-d0f8-4a16-9d5c-670ff7054441)

### Abrir el contrato de tu LP Token <a href="#open-the-contract-for-your-lp-token" id="open-the-contract-for-your-lp-token"></a>

Deberá aprobar el contrato inteligente para el token LP que desea depositar en un Farm antes de poder hacerlo.

### Desde el código fuente <a href="#from-the-source-code" id="from-the-source-code"></a>

1\. Primero abrir:  [Código de Farms de PancakeSwap en GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Ctrl**/**command** + **F** y buscar el par necesario (no por nombre de proyecto). Por ejemplo, 'CAKE-BUSD'.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McgveN\_06WzVRLK1FeR%2F-McgwmGUCIjvdfLKU9VR%2Fimage.png?alt=media\&token=a8e11b39-4458-4e87-9f17-4e01ac4d192b)

3\. Cuando tenga el código para el par LP que está buscando, busque la dirección después de "56:". Esta será la dirección de su contrato.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McgveN\_06WzVRLK1FeR%2F-McgxJyVDFAxh9cZhEqt%2Fimage.png?alt=media\&token=0638fe99-b1d5-4be3-8fd7-c1b68ca59032)

### Desde la UI <a href="#from-the-ui" id="from-the-ui"></a>

1\. Primero, visite la página de [Farms ](https://pancakeswap.finance/farms)y busque su par elegido usando el campo "SEARCH" en la parte superior derecha. Estamos usando CAKE-BUSD para este ejemplo.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MboxfvCzzhDYucewEJM%2Fimage.png?alt=media\&token=a2340e87-0ac4-4db7-8868-3c021fcabe13)

2\. Clic en **Details** para ver más información.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MboyRav88nxt7uoSMcm%2Fimage.png?alt=media\&token=4368c32c-79bf-477b-8853-bdfab36b88cb)

3\. Clic en **View Contract** para abrir el smart contract en BscScan.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mboz8UGShU9TSD7lct4%2Fimage.png?alt=media\&token=d5b90a00-3fb2-4a4f-b77f-c5709b904ee5)

### Dar permiso al contrato del LP Token  <a href="#giving-permission-to-the-lp-token-contract" id="giving-permission-to-the-lp-token-contract"></a>

Ahora que tiene el contrato de su token LP abierto en BscScan, va a aprobar el gasto de sus tokens LP en el Farm.

1\. En la página del contrato del LP Token, ir a  **Contract**, y luego en **Write Contract**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media\&token=bd3301ee-86d4-4899-8256-467a591104a8)

2\. Clic en **Connect to Web3** para conectar MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirmar la conexión.

3\. Bajo la función 1, “approve”, verás “spender:address”. Pegue la dirección del contrato del Staking principal que copió anteriormente.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp7nSuoGINXJV4b3rm%2Fimage.png?alt=media\&token=a07d5f8b-df85-4df8-8c33-8c9d74f20ff3)

5\. También tendrá que aprobar la cantidad de tokens LP que el contrato puede gastar. En el campo de valor, deberá ingresar la cantidad en Wei. Puede utilizar el [convertidor de unidades BscScan](https://www.bscscan.com/unitconverter) para cambiar fácilmente su cantidad a Wei. Aquí usaremos 5 tokens LP cake-busd.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp7ayxZbb60iG9uHfV%2Fimage.png?alt=media\&token=7fb50d56-32fc-4577-b96a-1ddf6ab74940)

También puedes usar `-1` como el valor para dar una aprobación de gasto ilimitada.  Esto no significa que gastará todo por defecto, sino solo que una transacción de cualquier tamaño usando este contrato será permitida por su billetera.

6\. Clic en **Write** y aceptar la transacción en Metamask. Ahora puede confirmar tokens LP en el Farm hasta la cantidad que haya aprobado.

### Depositar LP Tokens con el contrato de Main Staking Contract <a href="#deposit-lp-tokens-with-the-main-staking-contract-smart-contract" id="deposit-lp-tokens-with-the-main-staking-contract-smart-contract"></a>

Con el Contrato de Staking Principal ahora aprobado para gastar sus Tokens LP, es hora de hacer un depósito.

1\. Vuelve al [Main Staking Contract en BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), ir a **Contract**, y luego **Write Contract**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media\&token=bd3301ee-86d4-4899-8256-467a591104a8)

2\. Clic en **Connect to Web3** para conectar MetaMask.

3\. Ir hasta la función 2, "deposit", y poner el número PID que habíamos obtenido en el campo "\_pid".

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsxc1rAB8T2\_R8rrzR%2Fimage.png?alt=media\&token=03aeb1e2-feba-4f82-b3dc-74ff9f435a19)

Si no copió su PID anteriormente, puede obtener información sobre cómo obtenerlo en la sección **Encontrando el idetificador de proceso del Farm** más arriba en esta página.

4\. Debajo de \_pid verás "\_amount". Indique el importe a depositar de LP al pool.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbsyWOLP4b1bMdQyTnA%2Fimage.png?alt=media\&token=3cb0d014-8174-420a-ad4f-1ebd6e3619dc)

5\. Compruebe la información y haga clic en **Write**. Confirma tu acción en MetaMask.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsyp72o0h6GheA90EF%2Fimage.png?alt=media\&token=5e6148e4-a6ec-48f0-8cba-752b3b9d499e)

6\. Puedes ver que funcionó haciendo click en **View your transaction**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbt6-zveDG6pEb5on0q%2Fimage.png?alt=media\&token=28a9f6aa-25cf-4089-b111-f3486a3b88ad)

## Retirando desde un Pool <a href="#withdrawing-from-a-pool" id="withdrawing-from-a-pool"></a>

Retirar sus tokens LP de un pool es muy similar a hacer un depósito. La diferencia es con qué función interactuará.

1\. Vuelve al [Main Staking Contract en BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), ir a **Contract**, y luego **Write Contract**

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media\&token=bd3301ee-86d4-4899-8256-467a591104a8)

2\. Clic en **Connect to Web3** para conectar MetaMask.

3\. Desplácese hasta el final hacia abajo hasta la función 15, "withdraw" y escriba su PID en el campo "pid".

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbtAvbr6T5eY7FhtaMv%2Fimage.png?alt=media\&token=61031f79-8b18-4a09-9153-09d4e41703a2)

Si no copió su PID anteriormente, puede obtener información sobre cómo obtenerlo en la sección **Encontrando el idetificador de proceso del Farm** más arriba en esta página.

4\. Debajo de \_pid verás "\_amount". Indique el importe a retirar de LP desde el pool.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbtBD8bokfhbBDKKTpT%2Fimage.png?alt=media\&token=b3410b45-e71b-4881-85f5-1cb3c7e8c6c9)

5\. Compruebe la información y haga clic en **Write**. Confirma tu acción en MetaMask.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsyp72o0h6GheA90EF%2Fimage.png?alt=media\&token=5e6148e4-a6ec-48f0-8cba-752b3b9d499e)

6\. Puedes ver que funcionó haciendo click en **View your transaction.**

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbt6-zveDG6pEb5on0q%2Fimage.png?alt=media\&token=28a9f6aa-25cf-4089-b111-f3486a3b88ad)

## **Hacer un Retiro de Emergencia** <a href="#making-an-emergency-withdrawal" id="making-an-emergency-withdrawal"></a>

‌El uso de la función de retiro de emergencia le permite sacar todos sus fondos de un Pool común cuando no hay otra manera de lograrlo.

**¡El uso de la función de retiro de emergencia perderá sus recompensas en CAKE!**

El equipo de PancakeSwap sugiere encarecidamente evitar esta función a menos que el mismo equipo de PancakeSwap le aconseje hacerlo oficialmente, o si se siente muy cómodo interactuando con contratos inteligentes y entendiendo el código subyacente.

‌1. Vuelve al [Main Staking Contract en BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), ir a **Contract**, y luego **Write Contract**

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media\&token=bd3301ee-86d4-4899-8256-467a591104a8)

2\. Clic en **Connect to Web3** para conectar MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Ir hasta el punto 4, "emergencyWithdraw", y copiar nuestro PID dentro del campo "\_pid".

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbtDrETo2rkolLkREKD%2Fimage.png?alt=media\&token=6f0afd56-5d00-461d-bfd5-32290f83106c)

Si no copió su PID anteriormente, puede obtener información sobre cómo obtenerlo en la sección **Encontrando el idetificador de proceso del Farm** más arriba en esta página.

5\. Compruebe la información y haga clic en **Write**. Confirma tu acción en MetaMask.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsyp72o0h6GheA90EF%2Fimage.png?alt=media\&token=5e6148e4-a6ec-48f0-8cba-752b3b9d499e)

6\. Puedes ver que funcionó haciendo click en **View your transaction.**

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbt6-zveDG6pEb5on0q%2Fimage.png?alt=media\&token=28a9f6aa-25cf-4089-b111-f3486a3b88ad)
