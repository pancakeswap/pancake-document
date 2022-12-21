# FAQ Crosschain farming

![](<../../../.gitbook/assets/0 (2) (2)>)

### **¿Qué puedo hacer en PancakeSwap en otras blockchains?** <a href="#_vp4dabm1sni3" id="_vp4dabm1sni3"></a>

Aporta liquidez, intercambia y haz farming como siempre lo has hecho. Si ya eres usuario en otras blockchain, recuerde aportar liquidez en PancakeSwap en otras blockchains en las que hemos implementado (como Ethereum), ya que tenemos recompensas de CAKE en BnB Smart Chain para usted, lo que le permite ganar aún más CAKE, uniendo todo en una misma blockchain (BSC).

### **¿Habra mas pares?** <a href="#_xls76paboov7" id="_xls76paboov7"></a>

Sí, pero lo implementaremos paso a paso para asegurarnos de priorizar la seguridad de los fondos de los usuarios y la inflación de CAKE. Háganos saber en los chats de la comunidad lo que cree que debería agregarse a PancakeSwap en otras blockchains y también, en que otras blockchains deberíamos implementar PancakeSwap.

### **¿Por qué el costo del gas para dejar en staking los tokens LP es alto?** <a href="#_i35ky39ztfx2" id="_i35ky39ztfx2"></a>

Se requiere una pequeña cantidad del token nativo (por ejemplo, ETH en Ethereum) para la primera configuración. Así que la primera transacción será un poco costosa.

Además, hay otras tarifas (principalmente costos de gas) involucradas en el farming crosschain.

Echa un vistazo a esta sección dedicada para obtener más información.

### **¿Por qué hacer staking y dejar de hacerlo tarda 30 minutos en completarse?** <a href="#_hvyzdrra7b8b" id="_hvyzdrra7b8b"></a>

Todas las transacciones entre cadenas tardaran alrededor de 30 minutos en completarse. Esto se debe a:

* Las transacciones deben ejecutarse en ambas blockchain, tanto en Ethereum como en la BnB Chain.
* El envío y entrega de los mensajes entre diferentes cadenas lleva tiempo.
* Para garantizar la seguridad y que todos los datos estén sincronizados y sean consistentes entre diferentes blockchain.

### **¿Dónde están mis recompensas de CAKE recolectadas?** <a href="#_buu4jfndd0dg" id="_buu4jfndd0dg"></a>

Su CAKE cosechado o recolectado se distribuirá en la BnB Smart Chain. Cambie de red en su billetera para revisar el balance de CAKE.

### **¡No puedo cosechar porque mi billetera no admite el cambio entre diferentes blockchains!** <a href="#_bena0tlorskz" id="_bena0tlorskz"></a>

Intente usar una aplicación de billetera diferente que admita diferentes blockchains y el cambio entre ellas. Tenga en cuenta que dejar en staking y retirar sus tokens LP también recolectará todo el CAKE ganado en su billetera en la BnB Smart Chain. Por lo tanto, si no desea utilizar una aplicación de billetera diferente, simplemente deposite más o retire una pequeña cantidad de sus tokens LP para recolectar su CAKE ganado.

### **¿Hay alguna tarifa cuando hago farming entre diferentes redes?** <a href="#_ikwb2ocixhef" id="_ikwb2ocixhef"></a>

A diferencia del farming nativo en la BnB Chain, hacer farming en otras blockchains requiere actividades entre cadenas. Estas son las tarifas o fees presentes:

**1 - Tarifa de gas para crear un contrato de proxy**

Se debe crear un contrato proxy en la BnB chain para el farming entre varias redes. El costo del gas para la creación del contrato proxy está incluido en la transacción.

Esta tarifa solo se cobra una vez en la primera transacción del "stake".

**2 - Tarifa de gas por llamadas o calls en BnB Chain**

Cuando los usuarios depositan o retiran tokens LP. Un ejecutor realizará transacciones solicitando el comportamiento de los usuarios en la BnB Chain. El costo del gas para estas “llamadas” o calls está incluido en la transacción.

Esta tarifa se cobra en cada transacción de depósito o retiro.

**3 - Tarifa de gas para “llamadas” o calls en otras blockchains**

Cuando los usuarios retiran tokens LP. Un ejecutor realizará las transacciones finales para liberar los tokens LP en otras blockchains (como Ethereum). El costo del gas para estas llamadas está incluido en la transacción.

Esta tarifa solo se cobra en transacciones de retiro.

**4 - Tarifa por la comunicación entre cadenas**

Utilizamos un bus de mensajes impulsado por Celer para enrutar nuestros mensajes entre cadenas. Por lo tanto, se incluye una tarifa de mensajes basada en la longitud de bytes del mensaje.

Esta tarifa se cobra en cada transacción por stake. En las transacciones de retiro, esta tarifa se cobra dos veces ya que se requiere una comunicación bidireccional entre BnB Chain y otras blockchain por seguridad.

messagingFee = feeBase + message.length \* feePerByte;

Puedes encontrar las variables de la fórmula en el contrato del bus de mensajes:

* Ethereum: 0x4066d196a423b2b3b8b054f4f40efb47a74e200c
* BNB Chain: 0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b

**5 - El fondo inicial**

Esto no es estrictamente una "tarifa".

Por cada nuevo usuario que comenzó a hacer farming cross-chain en PancakeSwap. En la primera transacción de "stake", depositaremos 0.005 BNB en su billetera BnB Chain. La cantidad correspondiente de tokens nativos en la red del farming (como ETH en Ethereum) se cobrará de la transacción de depósito, utilizando la tasa de mercado proporcionada por el oráculo de precios.

Esto es para ayudar a los usuarios a comenzar su viaje en la BnB Chain con facilidad. Entendemos el dolor de tener todo el CAKE cosechado, pero no poder explorar e interactuar con todo el ecosistema de PancakeSwap por falta de BNB para el gas y sin poder tener una forma de adquirirlo.

Esta tarifa solo se cobra una vez en la primera transacción de "stake".

### **¿De dónde provienen las emisiones?** <a href="#_8ecfv27az56m" id="_8ecfv27az56m"></a>

_actualizado el 10 Oct 2022_

Por ahora, los Chefs han desviado 0.0189 CAKE por bloque del Pool de CAKE hacia los farms crosschain.

Aquí está el desglose de las emisiones:

![](<../../../.gitbook/assets/1 (3)>)

### **¿Qué sucede durante el depósito, cosecha y retiro?** <a href="#_vhmqxcrq5plk" id="_vhmqxcrq5plk"></a>

El farming entre diferentes redes de PancakeSwap es como usar un token LP "suplente" para farmear en la BnB Chain, con el mismo PancakeSwap MasterChef. Las recompensas de CAKE se calculan y distribuyen en la BnB Chain, controladas y protegidas por el mismo contrato de MasterChef.

**En el depósito:**

1. Los usuarios solicitan depositar tokens LP en las blockchain donde se puede hacer farming (como Ethereum).
2. Los tokens LP se transfieren a los contratos de bovedades para farming.
3. El bus de mensajes de Celer se utiliza para entregar el mensaje de “depósito” a la BnB Chain.
4. Un ejecutor en la BnB Chain mintea la misma cantidad de tokens para el farming que los “suplentes”, y luego los deposita en los farms.

**En la cosecha o recolecta:**

Dado que las recompensas de CAKE se calculan y distribuyen en la BnB Chain. Los usuarios pueden reclamar sus recompensas de CAKE con una sola transacción de BnB Chain sin necesidad de operaciones entre cadenas.

**En el retiro:**

1. Los usuarios solicitan retirar tokens LP en las blockchain donde se puede hacer farming (como Ethereum).
2. El bus de mensajes de Celer se utiliza para entregar el mensaje de “retiro” a la BnB Chain.
3. Un ejecutor en la BnB Chain retira los tokens del farming de los farms, quema esos tokens, transfiere el CAKE obtenido a los usuarios y utiliza el bus de mensajes de Celer para enviar el mensaje de confirmación a la blockchain original.
4. Un ejecutor en la blockchain donde se hace el farming confirma todo y luego libera los tokens LP de los contratos de la bóveda.
