# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### ¿Qué debo hacer en PancakeSwap en otras blockchains?

Proporciona liquidez, intercambia y haz farming como siempre lo has hecho. Si ya eres un usuario multicadena, recuerda proporcionar liquidez en PancakeSwap en otras blockchains en las que hemos desplegado (como Ethereum), ya que tenemos recompensas de CAKE en BNB Smart Chain para ti, ¡permitiéndote ganar aún más CAKE sin tener que puentear esos activos!

### **¿Habrá más pares?**

Sí, pero desplegaremos en pasos para asegurarnos de priorizar la seguridad de los fondos de los usuarios y la inflación de CAKE. Comunícanos en los chats de la comunidad qué crees que debería agregarse a PancakeSwap en otras blockchains, así como en qué otras blockchains deberíamos desplegar PancakeSwap.

### **¿Por qué el costo de gas para hacer staking de tokens LP es alto?**

Se requiere una pequeña cantidad de token nativo (por ejemplo, ETH en Ethereum) para la configuración inicial. Por lo que la primera transacción será ligeramente costosa.

Además, hay otras comisiones (principalmente costos de gas) involucradas en el farming multicadena. Consulta [esta](faq.md#are-there-any-fees-when-i-do-crosschain-farming) sección dedicada para obtener más información.

### **¿Por qué el staking y el retiro de staking tardan 30 minutos en completarse?**

Todas las transacciones entre cadenas tardarán alrededor de 30 minutos en completarse. Esto se debe a que:

* Las transacciones deben ejecutarse tanto en la blockchain de farming (como Ethereum) como en BNB Chain.
* La entrega de mensajes entre cadenas lleva tiempo.
* Para garantizar la seguridad y que todos los datos estén sincronizados y sean consistentes entre diferentes blockchains.

### **¿Dónde están mis recompensas de CAKE cosechadas?**

Tu CAKE cosechado se distribuirá en BNB Smart Chain. Por favor, cambia la red de blockchain en tu billetera para verificar el saldo de CAKE.

### **¡No puedo cosechar porque mi billetera no admite cambiar entre diferentes blockchains!**

Por favor, intenta usar una aplicación de billetera diferente que admita multicadena y cambio de cadena.

Ten en cuenta que hacer staking y retirar el staking de tokens LP también cosechará todo el CAKE ganado en tu billetera en BNB Smart Chain. Por lo tanto, si no deseas usar una aplicación de billetera diferente, simplemente haz más staking o retira una pequeña cantidad de tokens LP para cosechar tu CAKE ganado.

### ¿Hay alguna tarifa cuando hago farming multicadena?

A diferencia del farming nativo en BNB Chain, el farming en otras blockchains requiere actividades entre cadenas. Aquí están las comisiones involucradas:

**1 - Tarifa de gas para crear un contrato proxy**

Se debe crear un contrato proxy en BNB Chain para el farming multicadena. El costo de gas para la creación del contrato proxy está incluido en la transacción.

Esta tarifa se cobra solo una vez en la primera transacción de "staking".

**2 - Tarifa de gas para llamadas en BNB Chain**

Cuando los usuarios depositan o retiran tokens LP, un ejecutor realizará transacciones llamando en nombre de los usuarios en BNB Chain. El costo de gas para estas llamadas está incluido en la transacción.

Esta tarifa se cobra en cada transacción de depósito o retiro.

**3 - Tarifa de gas para llamadas en otras blockchains**

Cuando los usuarios retiran tokens LP, un ejecutor realizará las transacciones finales llamando para liberar los tokens LP en otras blockchains (como Ethereum). El costo de gas para estas llamadas está incluido en la transacción.

Esta tarifa solo se cobra en las transacciones de retiro.

**4 - Tarifa de mensajería entre cadenas**

Utilizamos un bus de mensajes impulsado por Celer para enrutar nuestros mensajes entre cadenas. Por lo tanto, se incluye una tarifa de mensajes basada en la longitud en bytes del mensaje.

Esta tarifa se cobra en cada transacción de staking. En las transacciones de retiro de staking, esta tarifa se cobra dos veces ya que se requiere una comunicación bidireccional entre BNB Chain y otras blockchains por seguridad.

```
messagingFee = feeBase + message.length * feePerByte;
```

Puedes encontrar las variables en la fórmula dentro del contrato del bus de mensajes:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - El fondo inicial**

Esto no es estrictamente una "tarifa".

Para cada nuevo usuario que empieza a hacer farming multicadena de PancakeSwap. En la primera transacción de "staking", depositaremos 0,005 BNB en su billetera de BNB Chain. La cantidad correspondiente de tokens nativos en la cadena de farming (como ETH en Ethereum) se cobrará de la transacción de depósito, usando la tasa de mercado proporcionada por el oráculo de precios.

Esto es para ayudar a los usuarios a comenzar su camino en BNB Chain con facilidad. Entendemos la dificultad de tener todo el CAKE cosechado pero no poder explorar el vibrante ecosistema de PancakeSwap sin encontrar otra forma de adquirir BNB para el gas.

Esta tarifa solo se cobra una vez en la primera transacción de "staking".

### ¿De dónde provienen las emisiones?

_actualizado el 10 de octubre de 2022_

Por ahora, los Chefs han desviado 0,0189 CAKE por bloque del pool de CAKE a todas las granjas multicadena.

Aquí está el desglose de emisiones:

<table><thead><tr><th width="249"></th><th>Multiplicador</th><th>CAKE por bloque</th></tr></thead><tbody><tr><td><strong>Pool de CAKE</strong></td><td>-</td><td><strong>8,9811</strong></td></tr><tr><td><strong>Todas las Granjas Multicadena</strong></td><td>-</td><td><strong>0,0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0,5x</td><td>0,0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0,2x</td><td>0,0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0,2x</td><td>0,0042</td></tr></tbody></table>

### ¿Qué sucede durante el depósito, la cosecha y el retiro?

El farming multicadena de PancakeSwap es como usar un token LP "sustituto" para hacer farming en BNB Chain, con el mismo MasterChef de PancakeSwap. Las recompensas de CAKE se calculan y distribuyen en BNB Chain, controladas y protegidas por el mismo contrato MasterChef.

#### Al Depositar:

1. Los usuarios solicitan depositar tokens LP en blockchains de farming (como Ethereum).
2. Los tokens LP se transfieren a los contratos de bóveda de farming.
3. El bus de mensajes de Celer se utiliza para entregar el mensaje de "depósito" a BNB Chain.
4. Un ejecutor en BNB Chain acuña la misma cantidad de tokens de farming como "sustitutos" y luego los deposita en las granjas.

#### Al Cosechar:

Dado que las recompensas de CAKE se calculan y distribuyen en BNB Chain, los usuarios pueden reclamar sus recompensas de CAKE con una sola transacción de BNB Chain sin necesidad de operaciones entre cadenas.

#### Al Retirar:

1. Los usuarios solicitan retirar tokens LP en blockchains de farming (como Ethereum).
2. El bus de mensajes de Celer se utiliza para entregar el mensaje de "retiro" a BNB Chain.
3. Un ejecutor en BNB Chain retira los tokens de farming de las granjas, quema esos tokens, transfiere el CAKE ganado a los usuarios y utiliza el bus de mensajes de Celer para entregar el mensaje de confirmación de vuelta a la blockchain de farming original.
4. Un ejecutor en la blockchain de farming confirma todo y luego libera los tokens LP de los contratos de bóveda.
