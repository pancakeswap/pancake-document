---
description: >-
  Entendemos que puedes tener preguntas sobre nuestra última actualización. Hemos compilado
  este FAQ completo para abordar todas tus consultas. Vamos a ello:
---

# FAQ de PancakeSwap Infinity

**P1 ¿Cómo beneficiará PancakeSwap Infinity a los traders y proveedores de liquidez?**

**R:** PancakeSwap Infinity aporta muchas ventajas tanto para los traders como para los proveedores de liquidez:

**1. Operaciones Optimizadas y Ahorro de Gas:** A través de funciones como Singleton y Flash Accounting, PancakeSwap Infinity reduce drásticamente las comisiones de gas. Singleton consolida todos los pools en un único contrato, reduciendo los costos de despliegue en un 99%. Flash Accounting optimiza los procesos de contabilidad calculando los saldos netos para las transacciones, minimizando el consumo de gas.

**2. Beneficios Directos de las Funciones Avanzadas:** La integración de hooks permite implementar comisiones dinámicas, tipos de órdenes personalizadas y módulos de gestión de liquidez activa. Los proveedores de liquidez pueden disfrutar de una pérdida impermanente (IL) mitigada, protección MEV y acceso a varios niveles de comisión, garantizando experiencias de trading más rentables y seguras.

\
**3. Flexibilidad en los Diseños AMM:** PancakeSwap Infinity admite múltiples tipos de pool, incluyendo CLAMM y LBAMM, permitiendo a los traders y LPs elegir diferentes tipos de pool. Este enfoque inclusivo también permite admitir cualquier activo futuro que requiera nuevas curvas de precios. Consulta este blog para [aprender más](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2016.16.56.png" alt=""><figcaption></figcaption></figure>

**P2** ¿Cómo beneficiará PancakeSwap Infinity a los desarrolladores y protocolos DeFi?

**R:** PancakeSwap Infinity abre un mundo de posibilidades para los desarrolladores y protocolos DeFi.&#x20;

**1. Posibilidades de Personalización Ilimitadas:** Con PancakeSwap Infinity, los desarrolladores pueden crear Hooks para introducir funcionalidades personalizadas; desde comisiones dinámicas hasta órdenes limitadas en cadena y oráculos personalizados. PancakeSwap Infinity admite el despliegue de nuevos tipos de pool (CLAMM, LBAMM y cualquier otro tipo de pool en el futuro), mejorando la eficiencia de capital y la flexibilidad de trading.

**2. Acceso a Liquidez Robusta y Base de Usuarios:** Con más de 1,8 millones de usuarios activos y 2.100 millones de dólares en liquidez, los desarrolladores y protocolos DeFi tienen una oportunidad sin igual para aprovechar una comunidad vasta y activa, fomentando el desarrollo de productos y la adopción.

**3. Oportunidades de Generación de Ingresos:** Los desarrolladores pueden establecer un flujo de ingresos consistente a través de comisiones de hooks, permitiéndoles establecer comisiones por el uso de sus hooks. Al monetizar sus innovaciones con comisiones, los desarrolladores pueden contribuir al crecimiento y desarrollo del ecosistema de PancakeSwap. Consulta este blog para [aprender más](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2009.40.42.png" alt=""><figcaption></figcaption></figure>

**P3** ¿Qué mejoras aporta PancakeSwap Infinity en comparación con v3?

**R:** PancakeSwap Infinity introduce la capacidad de mejorar las funcionalidades de los pools de liquidez con características personalizadas sin reimplementar el protocolo principal. También admite la implementación de cualquier curva de precios al momento y ofrece sustanciales ahorros de gas para los usuarios.

**P4** ¿Habrá cambios en la interfaz de usuario o en la experiencia de usuario en PancakeSwap Infinity?

**R:** Los usuarios pueden intercambiar en Infinity a través de la página de intercambio de PancakeSwap, igual que la experiencia habitual. Los traders y proveedores de liquidez tienen múltiples opciones para añadir liquidez en los tipos de pool compatibles, incluyendo CLAMM y LBAMM.

**P5** ¿Cómo puede la comunidad participar en las pruebas o proporcionar comentarios sobre PancakeSwap Infinity?

**R:** Si eres miembro de la comunidad, no dudes en compartir tus comentarios a través de nuestras redes sociales en [Telegram](https://t.me/PancakeSwapAnn), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) y [Twitter](https://twitter.com/PancakeSwap). Si eres desarrollador, únete a nuestra comunidad de Discord para desarrolladores y comparte tus ideas.

**P6** ¿Dónde pueden los usuarios encontrar más información sobre PancakeSwap Infinity y mantenerse actualizados sobre su progreso de desarrollo?

**R:** Visita nuestro [sitio web](https://pancakeswap.finance/v4?utm_source=v4announcementblog\&utm_medium=blog\&utm_campaign=v4announcementblog\&utm_id=v4announcementblog) oficial, lee nuestro [whitepaper](https://github.com/pancakeswap/pancake-v4-core/blob/main/docs/whitepaper-en.pdf) y síguenos en las redes sociales para obtener las últimas actualizaciones y desarrollos. Si eres desarrollador, únete a nuestra comunidad de Discord para desarrolladores.\
\
**P7** ¿Cuál es el mecanismo de licenciamiento de PancakeSwap Infinity?

**R:** PancakeSwap Infinity está comprometido con los principios de código abierto. Nuestro código se lanzará bajo una licencia de código abierto, permitiendo a los desarrolladores innovar libremente. Sin embargo, como parte de nuestra [iniciativa de Afiliados](https://forum.pancakeswap.finance/t/discussion-on-pancakeswap-affiliates-a-multichain-expansion-strategy/395), los protocolos DeFi que hagan un fork de PancakeSwap serán bienvenidos y reconocidos oficialmente por la Kitchen.\
\
**P8** ¿Cómo reduce PancakeSwap Infinity las comisiones de gas?

**R:** PancakeSwap Infinity aprovecha los mecanismos de Singleton y Flash Accounting para reducir significativamente las comisiones de gas. Al consolidar todos los pools en un único contrato (singleton), las transacciones de múltiples pools se simplifican, haciéndolas más rentables. Flash Accounting reemplaza las transferencias individuales con saldos netos, calculados colectivamente al final de cada transacción, lo que resulta en sustanciales ahorros de gas. ERC-6909 reduce aún más el gas para los usuarios frecuentes permitiéndoles mantener sus fondos dentro del protocolo y usarlos cuando sea necesario, eliminando las transferencias hacia y desde sus billeteras.\
\
**P9** ¿Qué son los Hooks en PancakeSwap Infinity y cómo permiten la innovación?

**R:** Los hooks son complementos personalizables que mejoran la funcionalidad de los pools de liquidez, permitiendo a los desarrolladores introducir características personalizadas y opciones de gestión de comisiones. Desplegados externamente, los Hooks pueden ejecutar lógica predefinida durante acciones clave del pool, ofreciendo posibilidades ilimitadas, incluyendo comisiones dinámicas, tipos de órdenes, oráculos personalizados y estrategias de gestión de liquidez activa. Consulta este blog para [aprender más](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)\
\
**P10** ¿Qué oportunidades presenta PancakeSwap Infinity para los desarrolladores?

**R:** Los desarrolladores pueden crear soluciones innovadoras, generar ingresos a través de comisiones de hooks y aprovechar la extensa base de usuarios y la profunda liquidez de PancakeSwap. Lee nuestra [publicación de blog](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks) dedicada sobre por qué los desarrolladores deberían construir en PancakeSwap.

**P11** ¿Cómo contribuye PancakeSwap Infinity al ecosistema DeFi más amplio?

**R:** PancakeSwap Infinity tiene como objetivo abordar las deficiencias de los AMMs actuales, mejorar la experiencia DEX y evolucionar hacia la plataforma DeFi de mayor funcionalidad apoyada por nuestro enfoque de código abierto. Lee la [visión del Head Chef, Chef Mochi para Infinity](https://blog.pancakeswap.finance/articles/chef-mochi-s-vision-for-pancake-swap-v4-a-leap-forward-in-de-fi-innovation) para aprender más\
\
**P12** ¿Dónde podemos encontrar el repositorio de plantillas de hooks?

**R:** Las plantillas de hooks se pueden encontrar en [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) y los hooks de ejemplo en [https://github.com/pancakeswap/infinity-hooks](https://github.com/pancakeswap/infinity-hooks)\
\
**P13** ¿Puedes explicar los ciclos de vida de los hooks y sus ejemplos?

**R:** Los hooks pueden implementarse antes / después de 5 acciones clave: initialize, swap, addLiquidity, removeLiquidity, donate. Por ejemplo, cuando un usuario inicia un intercambio, el contrato PoolManager verifica si existe un callback de hook `beforeSwap`. Si existe, se ejecuta la lógica del método `beforeSwap` en el contrato de hook; de lo contrario, el intercambio continúa como de costumbre. Después de completarse el intercambio, el mismo proceso ocurre para el callback `afterSwap`.\
\
**P14:** ¿Necesitamos realizar minería de direcciones para asegurarnos de que los hooks se desplieguen en una dirección específica?\
**R:** Los hooks pueden desplegarse en cualquier dirección como otros contratos. Los permisos de callback se establecen en PoolKey. Para más información, consulta el FAQ de hooks aquí&#x20;

[https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook](https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook)\
\
**P15:** ¿Cómo podemos verificar un contrato de hook en Etherscan?&#x20;

**R:** Si usas foundry, puedes consultar la guía de foundry aquí [https://book.getfoundry.sh/reference/forge/forge-verify-contract](https://book.getfoundry.sh/reference/forge/forge-verify-contract) \
O si usas hardhat, consulta la guía de hardhat aquí [https://hardhat.org/hardhat-runner/docs/guides/verifying](https://hardhat.org/hardhat-runner/docs/guides/verifying)\
\
**P16:** ¿Debemos usar foundry o hardhat para el desarrollo de hooks?

**R:** La plantilla [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) está basada en foundry; por lo tanto, recomendamos usar foundry. ¡Además, foundry ha ido ganando popularidad!&#x20;

**P17:** ¿Qué son las claves de pool?&#x20;

**R:** PoolKey es un struct que describe cada pool. Ver más [aquí](https://developer.pancakeswap.finance/contracts/infinity/overview/amm-layer-poolmanager).\
\
\
PancakeSwap Infinity representa un hito significativo en el espacio DeFi, ofreciendo beneficios sin igual para traders, desarrolladores, proveedores de liquidez y la comunidad en general. Estamos entusiasmados de embarcarnos en este viaje contigo y esperamos dar forma al futuro de DeFi juntos. Esperamos que este FAQ haya respondido tus preguntas sobre PancakeSwap Infinity. Si tienes más preguntas, no dudes en contactarnos a través de ([Twitter](https://twitter.com/PancakeSwap), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) y [Telegram](https://t.me/PancakeSwap)) o consulta nuestra [documentación](https://developer.pancakeswap.finance) para desarrolladores.
