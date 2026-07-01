# 📔 Gobernanza

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Como parte de la [actualización de Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), esta página fue actualizada el 15 de mayo de 2025
{% endhint %}

La votación da voz a la comunidad de PancakeSwap, permitiendo que la comunidad tenga participación en cómo PancakeSwap se desarrolla hacia el futuro.

Consulta el [portal de votación nativo de PancakeSwap](https://pancakeswap.finance/voting) y nuestra página del [Foro](https://forum.pancakeswap.finance/).

## Mecánicas de Votación

:notebook\_with\_decorative\_cover:Resumen - Qué Cambió (después de la [Actualización de Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Componente de Gobernanza</th><th width="218.01953125">Antes de Tokenomics 3.0</th><th width="205.1796875">Después de Tokenomics 3.0</th><th>Estado<select><option value="q1dVFsCri7zA" label="✅ Changed" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Unchanged" color="blue"></option></select></th></tr></thead><tbody><tr><td>Poder de Votación</td><td>1 veCAKE = 1 poder de voto</td><td>1 CAKE = 1 poder de voto</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Delegación</td><td>Permitida (a través de la mecánica de veCAKE)</td><td>La delegación no está permitida</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Umbral de Envío de Propuestas</td><td>Snapshot 100K veCAKE requerido</td><td>Snapshot 100K CAKE requerido</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Propuestas Core vs Comunitarias</td><td>Roles y propósitos definidos para cada tipo de propuesta</td><td>Sin cambio</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Período de Votación</td><td>Comunitaria: Fijo<br>Core: Variable</td><td>Sin cambio</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Momento del Snapshot</td><td>En el bloque en que se publica la propuesta</td><td>Sin cambio</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Quórum</td><td>Sin quórum mínimo</td><td>Sin cambio</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr></tbody></table>

### 1. **Poder de Votación (Cambiado)**

* **Todos los poseedores de CAKE tienen derechos de voto directos.**
* **El poder de voto corresponde directamente al número de CAKE en la dirección de billetera durante el snapshot**
  * **1 CAKE = 1 poder de voto**
  * **El CAKE en staking en Syrup Pools no cuenta** para tu poder de voto, ya que no forma parte del saldo de tu billetera en el momento del snapshot
  * Saldo del snapshot = Mismo bloque en que se publica la propuesta
* **La delegación ya no está soportada.** Cada poseedor de CAKE debe votar individualmente.

### 2. **Envío de Propuestas (Sin cambio)**

* **Cómo enviar una propuesta**
  * Envíala en [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Debe incluir:
    * Título
    * Contenido
    * Descripción
    * Acción(es) en cadena (si es necesario)
    * Duración de la votación
* Tipos de Propuestas
  1.  Propuestas Core

      * Solo pueden ser propuestas por el **Equipo Core de PancakeSwap**.
      * Requieren una votación de los poseedores de CAKE.
      * Si son aprobadas, serán implementadas por el equipo de PancakeSwap.

      Ejemplos

      1. Ajustes del protocolo (cambios en productos, cambios en comisiones)
      2. Usos significativos de los fondos de Crecimiento del Ecosistema no cubiertos por propuestas anteriores
  2. Propuestas Comunitarias
     * Las propuestas **Comunitarias** son publicadas por la comunidad de PancakeSwap. Se utilizan para proponer ideas y expresar el punto de vista de la comunidad. Son **sugerencias no vinculantes** de la comunidad.
     * Cualquier persona con **100,000 CAKE (saldo del snapshot)** puede enviar una.
     * El equipo de PancakeSwap puede adoptar propuestas sólidas en futuras Propuestas Core
     * Los miembros de la comunidad también pueden utilizar nuestro [Foro](https://forum.pancakeswap.finance/) para proporcionar retroalimentación y hacer sugerencias al protocolo.

### **3. Duración de la Votación (Sin cambio)**

* Todos los poseedores de CAKE pueden votar **durante la ventana de votación** para cada propuesta.
  * Propuesta comunitaria: Fijada en 3 días
  * Propuesta Core: Variable, establecida por PancakeSwap
* Tu poder de voto está determinado por un **snapshot de tu saldo de CAKE en el bloque en que se publica la propuesta**.
* **Agregar más CAKE después de que se publique la propuesta no aumentará tu poder de voto** para ese voto específico.

Para más detalles, consulta la [Guía de Votación](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Resultado de la Votación (Sin cambio)**

* El resultado se basa en el **total de votos emitidos** (total de CAKE usado para votar)
* **Actualmente no se requiere un quórum mínimo** para que una propuesta sea aprobada.

## Nota: Derechos de Veto

Para proteger el protocolo, el **Equipo Core de PancakeSwap se reserva el derecho de intervenir en situaciones críticas** —como amenazas de seguridad o problemas que afecten el funcionamiento estable de la plataforma— **sin requerir una votación comunitaria o una encuesta en Snapshot**.

En cualquier caso en que se tome una acción de veto, el Equipo Core **compartirá públicamente una explicación clara** de la decisión.

**Las posibles acciones de veto pueden incluir:**

1. **Pausar temporalmente los contratos inteligentes** para corregir errores o vulnerabilidades urgentes.
