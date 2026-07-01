# Syrup Pool de ALP (Arbitrum)

ALP es un token que impulsa la liquidez en PancakeSwap Perpetuals V2. Los usuarios acuñan/compran ALP usando tokens de garantía como USDC, USDT, DAI, ETH y BTC. Estos tokens suministran liquidez al motor de trading de PancakeSwap Perpetuals impulsado por ApolloX. Los tokens ALP **no pueden transferirse entre billeteras** y solo pueden **acuñarse/venderse a través del contrato ALP y hacer Staking en el pool ALP**.

### Guía Paso a Paso

#### Compra/Acuñación de ALP

1. Haz clic para acceder a la página del [Pool ALP de PancakeSwap (V2)](https://perp.pancakeswap.finance/en/ALP) y conecta tu billetera
2. Después de conectar tu billetera, haz clic en **Comprar ALP**. Puedes usar cualquier activo del pool ALP para comprar ALP.
3. Después de confirmar la información, haz clic en **Comprar ALP** para completar la transacción.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Buy%20ALP%20Module.png" alt=""><figcaption></figcaption></figure>

**Staking de ALP (Arbitrum)**

1. Haz clic en **Hacer Staking Ahora** en la Página del Panel de PancakeSwap ALP, o haz clic [aquí](https://pancakeswap.finance/pools?chain=arb)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/png%20%284%29.png" alt=""><figcaption></figcaption></figure>

2. Selecciona el Syrup Pool CAKE-ALP
3. **Activa** ALP y haz clic en **Hacer Staking**
4. Selecciona la cantidad de ALP para hacer Staking y haz clic en **confirmar**

**Venta de ALP**

1. &#x20;Haz clic para acceder a la página del Pool ALP (V2) y conecta tu billetera
2. Después de conectar tu billetera, haz clic en **Vender ALP**.

Condiciones para vender ALP:

* &#x20;El usuario puede vender ALP 48 horas después del momento de la compra
* &#x20;Cantidad de tokens ALP que pueden venderse: mín\[(Valor del pool de liquidez - Valor de las posiciones del usuario)\*50%]/Precio de Mercado ALP. Por ejemplo, si el valor del pool de liquidez es 10.000.000 USDT, el valor de la posición del usuario es 5.000.000 USDT y el Precio de Mercado ALP es 2 USDT, el importe máximo que el usuario ALP puede vender es 1.250.000.&#x20;
* Al mismo tiempo, el importe de activos que los usuarios reciben después de vender sus tokens ALP no puede exceder el pool de liquidez ALP. Por ejemplo, si el pool de liquidez solo tiene 1000 USDT, el importe máximo de USDT que los usuarios recibirán será 1000 USDT y los ALP restantes pueden venderse por otras criptomonedas.
