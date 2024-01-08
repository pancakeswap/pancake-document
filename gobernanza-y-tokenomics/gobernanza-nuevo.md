# Gobernanza (Nuevo)

{% hint style="info" %}
Estamos haciendo la transición de vCAKE a veCAKE para nuestro sistema de gobernanza. Antes de que finalice la migración, no toda la información contenida en esta página será precisa.
{% endhint %}

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Descripción general&#x20;

Los holders de veCAKE tienen derecho a voto en el sistema de gobernanza de PancakeSwap. Estos son los temas que están dentro del alcance de la gobernanza:&#x20;

1. \[Principal] Ajustes de emisiones de CAKE de alto nivel (asignando CAKE a los Pools principales y otras categorías de alto nivel)&#x20;
2. \[Principal] Ajustes de protocolo (cambios de producto, cambios de fees)&#x20;
3. \[Principal] Gastos del warchest multicadena&#x20;
4. \[Comunidad] Aprobaciones de gauges
5. \[Comunidad] Votación periódica del valor del gauge (cada 2 semanas)

Los holders de veCAKE deben votar los temas principales, pero solo pueden ser propuestos por el equipo de PancakeSwap.&#x20;

Cualquiera puede proponer temas de la comunidad y los holders de veCAKE también deben votarlos. Se requiere un mínimo de 10,000 veCAKE para iniciar una encuesta instantánea (esto se implementará más adelante cuando migremos de vCAKE a veCAKE). El resultado de la encuesta será ejecutado por el Equipo de PancakeSwap.&#x20;

#### Veto&#x20;

El equipo de PancakeSwap tiene derechos de veto y puede realizar acciones correctivas en lo que respecta a la seguridad o el funcionamiento adecuado del protocolo, sin pasar por una encuesta instantánea. En caso de cualquier acción de veto, el equipo de PancakeSwap proporcionará la explicación del caso.&#x20;

Las posibles acciones incluyen, entre otras:&#x20;

1. Pausar contratos inteligentes relevantes mientras se corrige un error crítico en el protocolo
2. &#x20;Rechazar un gauge que fue votado exitosamente si los tokens en cuestión se consideran inseguros, maliciosos y/o perjudiciales para el ecosistema PancakeSwap.

#### Proceso de gobernanza&#x20;

La descripción general del proceso de gobernanza de PancakeSwap es la siguiente:&#x20;

1. Publicar un control de temperatura en el foro&#x20;
2. Debatir
3. Iniciar una encuesta instantánea (período de votación mínimo de 24 horas)&#x20;
4. Ejecutar&#x20;

#### Paso 1: Publicar un control de temperatura en el foro&#x20;

* El propósito de una verificación de temperatura es medir el consenso aproximado de la comunidad sobre la propuesta antes de comenzar una encuesta instantánea oficial.&#x20;
* Si bien PancakeSwap da la bienvenida a comunidades de diversos orígenes, actualmente el foro solo aceptará propuestas escritas en inglés. Hable con nuestros embajadores en nuestros [diversos grupos regionales de Telegram](../contacto/redes.md) si necesita ayuda con la traducción.&#x20;
* Los proponentes deben incluir \[Temp Check] en el título al publicar en el foro.&#x20;

#### Paso 2: Debatir

* Recomendamos que todas las propuestas de control de temperatura pasen por 48 horas de discusión en el foro antes de que se inicie una encuesta instantánea, aunque no es estrictamente necesario.&#x20;
* Esto es para dar tiempo suficiente para medir el sentimiento de la comunidad e incorporar cualquier comentario a la propuesta.&#x20;

#### Paso 3: Iniciar una encuesta instantánea&#x20;

* Cualquiera con un poder de voto de 10,000 veCAKE (se implementará en una fecha posterior) puede iniciar una encuesta instantánea y publicar el enlace al tema respectivo en el foro.&#x20;
* El requisito de veCAKE desalienta las propuestas de baja calidad y garantiza que solo los miembros de la comunidad alineados con PancakeSwap puedan iniciar una encuesta.&#x20;
* La encuesta instantánea debe durar un mínimo de 48 horas, o un mínimo de 24 horas si es un tema principal.&#x20;
* El quórum para una encuesta instantánea es de 250.000 votos de veCAKE (se implementará en una fecha posterior), incluidos los votos de abstención (este requisito está sujeto a revisiones adicionales para garantizar propuestas de alta calidad).&#x20;

#### Paso 4: Ejecutar&#x20;

* Si la encuesta instantánea alcanza el quórum al final del período de votación y recibe >50% de aprobación de los votos, el equipo de PancakeSwap la ejecutará en función del resultado de la votación.&#x20;
* Fórmula para medir el porcentaje de aprobación de votos: Votos a favor / (Votos a favor + Votos en contra)
