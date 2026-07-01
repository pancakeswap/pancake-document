# Cómo Funcionan los Impuestos CAKE.PAD en las Ventas por Desbordamiento – Con Ejemplo

1. Los impuestos solo se cobran **si el** evento CAKE.PAD **tiene sobreinscripción**
   1. Sobreinscripción = Total de depósitos por todos los usuarios > Monto objetivo de recaudación.
   * El impuesto solo se deduce de los fondos comprometidos en exceso de los participantes. Ninguna comisión la paga el proyecto socio CAKE.PAD.
   * El proyecto socio CAKE.PAD recibe el 100% de su monto objetivo de recaudación.
   * Los impuestos CAKE.PAD se cobran en CAKE, y el 100% se quemará.
   * Las comisiones se basan en la **tasa de suscripción total del pool** (% del objetivo de recaudación):

**Tasa de Sobreinscripción <> Nivel de Tarifa**&#x20;

<table data-full-width="false"><thead><tr><th>Tasa de Sobreinscripción</th><th>Nivel de Tarifa</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1,00%</td></tr><tr><td>≥ 50x</td><td>0,80%</td></tr><tr><td>≥ 100x</td><td>0,60%</td></tr><tr><td>≥ 150x</td><td>0,50%</td></tr><tr><td>≥ 200x</td><td>0,40%</td></tr><tr><td>≥ 250x</td><td>0,30%</td></tr><tr><td>≥ 300x</td><td>0,25%</td></tr><tr><td>≥ 400x</td><td>0,20%</td></tr><tr><td>≥ 500x</td><td>0,15%</td></tr><tr><td>≥ 650x</td><td>0,12%</td></tr><tr><td>≥ 800x</td><td>0,10%</td></tr><tr><td>≥ 1500x</td><td>0,05%</td></tr></tbody></table>



2. **Período de tiempo – Cuándo se cobra el impuesto**

* El impuesto se cobra al **final del** evento CAKE.PAD, cuando el usuario canjea su asignación.
* Incluso si un usuario se suscribe temprano (p. ej., cuando la suscripción es del 30% del objetivo de recaudación), el impuesto final se basa en el **nivel final de sobreinscripción del pool**.
  * Ejemplo: Si el pool termina con una sobreinscripción de 50x, el impuesto aplicable es el nivel de 50x (0,8%).

#### Pasos de Cálculo

1.  **Asignación del usuario** = % del pool total de tokens del socio CAKE.PAD que recibe el usuario

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Monto a pagar por el usuario** = Porción del depósito del usuario utilizado para canjear tokens del socio CAKE.PAD

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Monto de reembolso** = Exceso del depósito del usuario no utilizado para comprar tokens del socio CAKE.PAD

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Monto del impuesto** = Deducción aplicada sobre el monto reembolsado al usuario

    * El nivel de tarifa se basa en el % del objetivo de recaudación (ver tabla arriba).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Resultado final para el usuario**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (si aplica, de lo contrario = refund_amount)
    ```

#### Ejemplo Numérico

* **Objetivo de recaudación (raisingAmountPool):** 100 CAKE
* **Tu depósito (user\_deposit\_amount):** 10 CAKE
* **Total de depósitos incl. tu depósito (totalAmountPool):** 5,100 CAKE (51x suscrito = 5,100% del objetivo de recaudación, implica una tasa de sobreinscripción de 50x)
  * Nivel de tarifa correspondiente = 0,80% (según la tabla de tasas de impuesto arriba)

**Pasos:**

1. `user_allocation = 10 / 5,100 = 0.00196 (asignación del pool del 0,196%)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**Montos finales recibidos por el usuario**

1. **Asignación de tokens:** 0,196 CAKE en valor de tokens del socio CAKE.PAD
2. **Reembolso final:** \~9,72 CAKE (de un depósito de 10 CAKE − 0,196 CAKE para la asignación de tokens − 0,0784 CAKE de impuesto)
