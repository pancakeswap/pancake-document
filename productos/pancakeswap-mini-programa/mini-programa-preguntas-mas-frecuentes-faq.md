# Mini-Programa - Preguntas más Frecuentes (FAQ)

### **¿Cuáles serán los futuros desarrollos del Mini-Programa?** <a href="#_xxypj7axv4ua" id="_xxypj7axv4ua"></a>

Desde que se lanzó la primera versión en marzo de 2022, miles de usuarios la usan a diario. Como el primer Mini-Programa a gran escala, el equipo de Binance también está descubriendo algunos problemas nuevos de infraestructura y rendimiento junto con nosotros, actualizando así su arquitectura. Antes de agregar más funciones, nos enfocamos en mejorar el rendimiento general y la experiencia del usuario en el Mini-Programa. Además, estamos trabajando con Binance para agregar gradualmente más formas de ingresar al Mini-Programa para que los usuarios de Binance puedan descubrirlo más fácilmente, como dentro de las funciones de búsqueda.

### **¿Cómo ayudará el Mini-Programa a PancakeSwap?** <a href="#_zd423lzwvl4" id="_zd423lzwvl4"></a>

PancakeSwap es actualmente la plataforma descentralizada más popular (en términos de número de usuarios), pero en la Cocina siempre están buscando más formas de invitar a nuevos usuarios a nuestra plataforma. Si bien la mayoría de los usuarios de DeFi en el mercado ya deberían haber oído hablar de PancakeSwap o haberlo usado, imagine el potencial de los recién llegados a las criptomonedas incorporados por Binance y su CEX. Es posible que estos nuevos usuarios no tengan la experiencia de crear una billetera Web3, proveer liquidez, farming, staking, trading de una amplia variedad de activos, etc. El Mini-Programa de PancakeSwap ofrece la mejor vía para invitar y educar a estos usuarios sobre la experiencia DeFi.

### **¿Está controlado por Binance o PancakeSwap?** <a href="#_35js0cpwhu70" id="_35js0cpwhu70"></a>

La interfaz del Mini-Programa se desarrolla bajo las pautas y la arquitectura del sistema de Mini-Programa de Binance, también tienen el derecho de revisar y aprobar cualquier contenido y función en el Mini-Programa. Sin embargo, los contratos inteligentes subyacentes con los que interactúan dentro del Mini-Programa son el mismo conjunto de contratos inteligentes que en nuestra web.

### **¿Cuándo se agregarán otras funciones al Mini-Programa?** <a href="#_9rg8ihyh6f5d" id="_9rg8ihyh6f5d"></a>

Debido a temas regulatorios, otras funciones como lotería, IFO y los perfiles aún no se pueden agregar al Mini-Programa. ¡Nuestro objetivo es educar a los usuarios de Binance sobre los conceptos básicos de DeFi primero y luego atraerlos gradualmente para que vengan a nuestra versión web y experimenten el conjunto completo de nuestras funciones!

### **¿Por qué debo usar el Mini-Programa cuando puedo usar la versión web con una wallet en mi navegador?** <a href="#_4x1zm78p1yrr" id="_4x1zm78p1yrr"></a>

El Mini-Programa está diseñado como una versión simplificada para atraer a los usuarios de Binance que no están familiarizados con DeFi; es posible que estos usuarios no tengan la experiencia de crear una billetera Web3, proveer liquidez, farming, staking, trading con una amplia variedad de activos, etc. Para los usuarios experimentados que están familiarizados con las billeteras en los navegadores y que interactúan con la versión web de PancakeSwap, la versión web ofrece un conjunto completo de funciones. ¡También es nuestro objetivo educar a estos nuevos usuarios sobre los conceptos básicos de DeFi primero y luego atraerlos para que vengan a nuestra versión web!

### **¿Cómo es que mi transacción no se realiza?** <a href="#_oqjlsvut88i7" id="_oqjlsvut88i7"></a>

El Mini-Programa sigue siendo completamente una aplicación DeFi, por lo que funciona igual que la interfaz web del usuario final. Interactúa con la billetera (billetera DeFi de Binance en este caso) para completar transacciones dentro de la cadena para hacer intercambios, crear LPs, staking en farms y pools.

#### **Tarifas de gas** <a href="#_3e6nl81gat93" id="_3e6nl81gat93"></a>

Lo primero es asegurarse de tener suficiente BNB para pagar la tarifa de gas de las transacciones. Por lo general, la tarifa de gas fluctúa según la cantidad de transacciones en cola en la red; si hay más transacciones, es posible que se requiera una tarifa de gas más alta para llevar a cabo la transacción. En la BNB Smart Chain donde opera el Mini-Programa, la tarifa del gas generalmente varía de centavos a un dólar (USD) en BNB. Aprende más sobre la[ tarifa de gas](https://academy.binance.com/es/glossary/gas).

#### **Tarifas de transacción** <a href="#_b99o54srafko" id="_b99o54srafko"></a>

Si su intercambio aún no se realiza y muestra un error para que revise el deslizamiento (slippage), es posible que deba verificar si los tokens que está tratando de intercambiar tienen tarifas y restricciones internas en su código.

No es raro que los tokens en la BNB Smart Chain incluyan una tarifa de transacción en sus contratos, por lo general, estas tarifas podrían usarse para quemar, financiar una tesorería de un proyecto, por ejemplo,[ APX tiene una tarifa de 1% sobre cada transacción](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) para enviar a una dirección de quema, de modo que más transacciones significarán más quema, acumulando valor para los poseedores de tokens APX.

Con la tarifa de transacción, ya sea inclusiva (una parte del monto del intercambio se envía a otra parte que no sea su dirección, por lo que la salida estimada es menor a lo estimado según la entrada) o exclusiva (requiere una transferencia adicional desde su dirección para enviar tokens adicionales por lo que la entrada es más de lo esperado para la salida estimada), todo esto, por supuesto, afecta la cantidad de entrada y salida que acepta al firmar la transacción. En muchos casos, la transacción no puede cumplir con los requisitos de entrada y salida debido al impuesto.

#### **Intercambio con una comisión interna** <a href="#_xjr142tfsg5w" id="_xjr142tfsg5w"></a>

Antes de intercambiar tokens, asegúrese de haber visitado su sitio web para comprender si tienen un mecanismo de tarifa o comisión de transacción (o impuestos, como dicen muchos proyectos). Si lo hay, asegúrese de establecer un slippage que sea suficiente para acomodar la tarifa de transacción, por ejemplo: si hay una tarifa de transacción del 5 %, su slippage deberá establecerse en al menos un 5 % más el deslizamiento (slippage) normal de negociación, según el monto de su negociación y la liquidez del token, digamos entre 5,5 % y 6 %. En algunos casos extremos, incluidas algunas estafas, algunos tokens incluso tienen un bloqueo en la mayoría o en todas las transferencias en la red, o solo permiten la venta a ciertas direcciones, en tal caso, es imposible intercambiar el token con éxito. ¡Infórmese sobre el token que está tratando de intercambiar y tenga en cuenta las tarifas o comisiones y restricciones!

### **¿Dónde puedo dejar un feedback o comentario sobre el Mini-Programa?** <a href="#_1qh3dr5exyui" id="_1qh3dr5exyui"></a>

Damos la bienvenida a todos los comentarios y siempre estamos tratando de mejorar para nuestra comunidad. Para cualquier comentario sobre el Mini-Programa, te invitamos a hacerlo en nuestro[ Telegram](https://t.me/PancakeSwapES) o[ Discord](https://discord.gg/pancakeswap), también pueden enviar sus comentarios dentro del Mini-Programa, en el botón de feedback después de hacer clic en los tres puntos en la esquina superior derecha.

![](../../.gitbook/assets/0.png)
