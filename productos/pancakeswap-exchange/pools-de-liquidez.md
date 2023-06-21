# Liquidez\*

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-Mb9Zry-ZB3tPvT1CIzP%2F-Mb9ovQQQR3i7hnjxvWU%2Fdocs%20masthead%20\(4\).png?alt=media\&token=858aed46-510e-46d3-95c0-aa5a4fa5ce07)

## Exchange V3 <a href="#03e94594-5a75-4687-b260-0dc69574b953" id="03e94594-5a75-4687-b260-0dc69574b953"></a>

En el nuevo Exchange V3, la liquidez será manejada en forma de posiciones no-fungibles. Aún estará ganando su parte de los fees mientras provee liquidez.

Cuando agrega un token a un Pool de liquidez, recibirá un token NFT de proveedor de liquidez y participación en los fees.

### **Posiciones de liquidez no-fungibles**

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

En V3, los proveedores de liquidez ahora tienen más control sobre qué rango de precios desean desplegar su liquidez. Así, cuando agregas tus tokens a un pool de liquidez en V3, crearás un nuevo token de posición de liquidez no-fungible con sus particulares configuraciones.

Por lo tanto, en V3, las posiciones de liquidez son NFTs. Tenga en cuenta que esos NFTs son transferibles, y representan la propiedad de los activos aportados y los fee de trading ganados.

En V3, los fees de trading ya no serán automáticamente agregados a la posición. Podrás reclamarlos manualmente en la página de detalles de cada posición.

También podrás retirar tus fondos en cualquier momento, removiendo la liquidez aportada.

### **Liquidez activa y rango de precios**

En V3, los proveedores de liquidez pueden configurar sus posiciones para aportar liquidez solamente cuando el precio se encuentre dentro de determinado rango. Si el precio en el mercado se mueve fuera de ese rango, la posición se quedará conformada por un token solamente y el par quedará inactivo.

Las posiciones inactivas no participarán en los trades ni ganarán fees de trading.

### **Liquidez concentrada**

In V3, because of liquidity providers can concentrate their token deposits to provide liquidity only within a specific price range. With the same amount of underlying assets, V3 can support a much bigger trade.

It results in a much higher relative liquidity level when compared to V2. And liquidity providers can earn more trading fees with the same amount of capital.

Here is an example:

> Baller and Claire both provided liquidity in CAKE/USDT pool with $1,000 USD worth of token assets. The current price of CAKE is 5 USDT.
>
> Similar to PancakeSwap v2, Baller provided his liquidity across the entire price range. Therefore he deposited all of his capital, 500 USDT and 100 CAKE.
>
> Claire utilize the new concentrated liquidity feature in PancakeSwap v3 and created a position with a price range of 2 to 12.5 USDT per CAKE. She deposited 185 USDT and 37 CAKE, worth a total of $370. She is now able to spend the remaining $630 elsewhere, like locking CAKE in the Syrup pool to enjoy high CAKE yield while receiving a series of PancakeSwap ecosystem benefits.
>
> As long as CAKE stays within the price range of 2 to 12.5, both Baller and Claire will receive the same amount of trading fee rewards while Claire deposited way less capital to the liquidity pool.

### **Earning trading fees**

Providing liquidity gives you a reward in the form of trading fees when people use your liquidity pool to complete swaps.

Whenever someone trades on PancakeSwap, for each hop (swap) in each Exchange V3 liquidity pool, depending on the liquidity pool fee tier, the trader pays a fee ranging from 0.01% to 1%. Their fee rates and fee breakdowns are shown as follows:

|                    | 0.01% | 0.05% | 0.25% | 1%  |
| ------------------ | ----- | ----- | ----- | --- |
| Liquidity Provider | 67%   | 66%   | 68%   | 68% |
| CAKE Burn          | 10%   | 10%   | 23%   | 23% |
| Treasury           | 23%   | 24%   | 9%    | 9%  |

For example, in a 0.25% fee tier pool:

* Among all the active (in-range) liquidity positions, there are a total of 10 CAKE and 10 BNB tokens.
* Someone trades 1 CAKE for 1 BNB.
* Someone else trades 1 BNB for 1 CAKE.
* The liquidity providers who are in the range providing active liquidity earned a total of 0.0017 CAKE and 0.0017 BNB from the trades.
* Positions with price ranges that are not covering the current price, therefore being inactive, will not contribute to trading or earn any fees.

### **Earning CAKE**

To make being a liquidity provider even more worth your while, you can also put your liquidity positions to work whipping up some fresh yield on the [CAKE Farms](https://pancakeswap.finance/farms), while still earning trading fee rewards.



## Exchange V2

### LP Tokens

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

As an example, if you deposited **CAKE** and **BNB** into a Liquidity Pool, you'd receive **CAKE-BNB LP** tokens.

The number of LP tokens you receive represents your portion of the CAKE-BNB Liquidity Pool.

You can also redeem your funds at any time by removing your liquidity.

### **Earning trading fees**

Whenever someone trades on PancakeSwap, for each hop (swap) in each Exchange V2 liquidity pool, the trader pays a fixed 0.25% fee, **of which 0.17%** is added back to the Liquidity Pool in a form of trading fees.

### **Earning CAKE**

The old Exchange V2 will be running in parallel with the new Exchange V3. So, some trading pairs will remain on PancakeSwap Exchange V2 and have their corresponding V2 Farms. Please check the tags to identify the exchange versions.

## Impermanent Loss <a href="#impermanent-loss" id="impermanent-loss"></a>

Proporcionar liquidez no está exento de riesgos, ya que puede estar expuesto a impermanent loss.

&#x20;[“En pocas palabras, la pérdida impermanente es la diferencia entre mantener tokens en una AMM y mantenerlos en su billetera” - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
