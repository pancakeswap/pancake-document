# Glosario

**Aquí encontrará las definiciones de todos los términos relacionados con el trading de futuros (perpetuo).**

### **Trading Perpetuo**

Perpetuos, perpetual swaps, o perps son un tipo especial de contratos de futuros sin fecha de vencimiento.

### Apalancamiento

Apalancamiento es un mecanismo del trading. Los traders pueden usarlo para aumentar su exposición al mercado, permitiéndoles pagar menos que el importe total de la inversión. En resumen, pides dinero prestado para apalancar tu inversión.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Margen

Es la garantía (en valores) que pones para tus posiciones apalancadas. Tiene dos modalidades de uso:

* Cross Margin (Cruzado): Todas las posiciones utilizando la misma moneda como margen, comparten el mismo balance de margen cruzado. En el caso de una liquidación, la totalidad de su balance de la moneda de margen, incluyendo las demás posiciones abiertas, podría perderse.
* Isolated Margin (Aislado): Controla el riesgo de sus posiciones individualmente restringiendo la cantidad de margen asignado a cada una. Siel porcentaje de margen de una posición alcanza el 100%, sólo esa posición será liquidada. en esta modalidad, puede agregarse o quitarse margen sin cerrar la posición.

**Margin Ratio (% de margen)**: Margin Ratio = Margen de mantenimiento / Balance del margen. Sus posiciones serán liquidadas una vez que se alcance el 100%.

**Maintenance Ratio (Margen de mantenimiento)**: La cantidad mínima de balance necesario para mantener la posición abierta.

**Margin Balance (Balance)** = Balance en wallet + PNL no realizado. Su posición será liquidada cuando el Balance de margen sea <= que el de mantenimiento.

**Deposit**: Deposita sus fondos en su cuenta de futuros.

**Withdraw**: Retira sus fondos de la cuenta de futuros a su wallet.

**Unrealized PNL (No realizado)**: Ganancias o pérdidas no realizadas de la posición, calculadas en base al Precio de Marca.

* Single Asset Mode: Supports USDⓈ-M Futures trading by only using the single margin asset of the symbol. PNL of the same margin asset positions can be offset. Supports Cross Margin Mode and Isolated Margin Mode.
* Multi-Assets Mode: USDⓈ-M Futures trading across multiple margin assets. PNL can be offset among the different margin asset positions. Only supports Cross Margin Mode.

Note: If there are open positions or open orders in USDⓈ-M Futures, Multi-Assets Mode cannot be activated. Multi-Assets Mode only applies to USDⓈ-M Futures. Before activating Multi-Assets Mode, please read the guide in detail to better manage USDⓈ-M Futures account risk accordingly when using Multi-Assets Mode.

**Buy/Long:** Open a Long order. In this order you purchase an asset and wait to sell when the price goes up. "Buy" and "long" are used interchangeably.

**Sell/Short:** Open a Short order. In this order, you borrow an asset, sell it, and hope to buy it back when the price goes down. "Sell" and "short" are used interchangeably.

**Limit Order:** A limit order is an order to buy or sell at a specific price or better. Limit orders are not guaranteed to execute.

**Market Order:** A market order is an order to buy or sell at the best available current price. It is executed against the limit orders that were previously placed on the order book. When placing a market order, you will pay fees as a market taker.

**Stop Limit Order:** The easiest way to understand a stop-limit order is to break it down into stop price, and limit price. The stop price is simply the price that triggers the limit order, and the limit price is the price of the limit order that is triggered. This means that once your stop price has been reached, your limit order will be immediately placed on the order book.

**Stop Market Order:** Similar to a stop-limit order, a stop market order uses a stop price as a trigger. However, when the stop price is reached, it triggers a market order instead.

**Trailing Stop:** A trailing stop is an order type designed to lock in profits or limit losses as a trade moves favorably. Trailing stops only move if the price moves favorably. Once it moves to lock in a profit or reduce a loss, it does not move back in the other direction.

**Post Only:** Post-only Mode means that Traders can only place an Order if it would be posted to the Order Book as a Maker Order. An Order which would be posted as a Taker Order will be rejected. No Market Orders may be placed and no Orders will be filled. Resting orders may be canceled in post-only mode.

**Reduce Only:** Reduce-Only order will only reduce your position, not increase it.

**TIF instructions** allow you to specify the amount of time that your orders will remain active before they are executed or expired. You can select one of these options for TIF instructions:

* **GTC** (Good Till Cancel): The order will remain active until it is either filled or canceled.
* **IOC** (Immediate Or Cancel): The order will execute immediately (either fully or partially). If it is only partially executed, the unfilled portion of the order will be canceled.
* **FOK** (Fill Or Kill): The order must be fully filled immediately. If not, it won’t be executed at all.
