# FAQ de Pancake Gifts

Este FAQ cubre cómo funcionan los Pancake Gifts entre bastidores, qué esperar en diferentes escenarios y por qué se tomaron ciertas decisiones de diseño.

***

## 1. 🔐 Comportamiento del código de regalo y acceso

### **1.1 ¿Por qué no se almacena el código de regalo?**

**Intencionalmente no almacenamos** el código de regalo en:

* El almacenamiento local del frontend
* Las bases de datos del backend

Esto protege:

* La privacidad del usuario
* La seguridad ante el compromiso del dispositivo
* Los reclamos de regalos accidentales o maliciosos

### **1.2 ¿Puedo regenerar o recuperar el código de regalo más tarde?**

No. El código de regalo:

* Solo se muestra **una vez** durante la creación
* Está integrado en el **enlace** o **código QR** generado
* **No se mostrará de nuevo** en la interfaz de usuario ni en el historial

{% hint style="warning" %}
Si el código se pierde y no guardaste el enlace o el QR, el regalo no puede reclamarse manualmente. En su lugar, para recuperar el importe de tu regalo, puedes cancelarlo manualmente.
{% endhint %}

### **1.3 ¿El código de regalo seguirá estando integrado en el enlace de compartir o el QR?**

Sí:

* El enlace para compartir incluye el código de regalo (ej. `pancakeswap.finance/gift#code=xxxx`)
* El código QR también integra el código de regalo, pero **no puede regenerarse más tarde.**&#x20;

{% hint style="success" %}
**Consejo Pro:** Descarga la imagen una vez que se genere
{% endhint %}

* Los reclamos manuales requieren el código de regalo real — no hay alternativa si se pierde el enlace/QR

## 2. 🎁 Estado del regalo y vencimiento

### **2.1 ¿Puedo ver si un regalo ha sido reclamado, cancelado o vencido?**

Sí. La sección de **Historial de regalos** muestra:

* Estado: Pendiente / Reclamado / Cancelado / Vencido / No reclamable
* Detalles del regalo (token, cantidad, tipo, cadena, marcas de tiempo)

### **2.2 ¿Qué sucede cuando un regalo vence?**

Si un regalo no se reclama dentro del **período predeterminado de 7 días**:

* El **importe total del regalo se reembolsa** a la billetera del creador
* La **tarifa fija de gas del reclamo (\~$0.05) no se devuelve**

## 3. 🧠 Lógica de reclamo y limitaciones

### **3.1 ¿Pueden los usuarios reclamar un regalo en una cadena diferente a la que fue creado?**

No. Un regalo está **vinculado a una cadena**:

* Un regalo creado en **BSC** debe reclamarse en **BSC**
* Los regalos entre cadenas no están soportados actualmente

## 4. ⛽ Tarifas de gas y diseño

### **4.1 ¿Cómo se decide la cantidad fija de gas para la creación del regalo?**

Establecemos un precio de gas fijo basado en las condiciones actuales de BNB Chain (\~5 veces la cantidad de gas recomendada actual).

Este margen:

* Protege contra picos repentinos de gas
* Garantiza que los regalos permanezcan reclamables bajo volatilidad normal

\
Ejemplo

* **Recomendado actual: 0.1 Gwei** (ver: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Por tanto, tarifa fija de gas del reclamo = 0.1 Gwei x 5 = 0.5 Gwei**


