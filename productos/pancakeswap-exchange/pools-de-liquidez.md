# Liquidez

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-Mb9Zry-ZB3tPvT1CIzP%2F-Mb9ovQQQR3i7hnjxvWU%2Fdocs%20masthead%20\(4\).png?alt=media\&token=858aed46-510e-46d3-95c0-aa5a4fa5ce07)

## Exchange V3 <a href="#03e94594-5a75-4687-b260-0dc69574b953" id="03e94594-5a75-4687-b260-0dc69574b953"></a>

En el nuevo Exchange V3, la liquidez será manejada en forma de posiciones no-fungibles. Aún estará ganando su parte de los fees mientras provee liquidez.

Cuando agrega un token a un Pool de liquidez, recibirá un token NFT de proveedor de liquidez y participación en los fees.

### **Posiciones de liquidez no-fungibles**

<figure><img src="../../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

En V3, los proveedores de liquidez ahora tienen más control sobre qué rango de precios desean desplegar su liquidez. Así, cuando agregas tus tokens a un pool de liquidez en V3, crearás un nuevo token de posición de liquidez no-fungible con sus particulares configuraciones.

Por lo tanto, en V3, las posiciones de liquidez son NFTs. Tenga en cuenta que esos NFTs son transferibles, y representan la propiedad de los activos aportados y los fee de trading ganados.

En V3, los fees de trading ya no serán automáticamente agregados a la posición. Podrás reclamarlos manualmente en la página de detalles de cada posición.

También podrás retirar tus fondos en cualquier momento, removiendo la liquidez aportada.

### **Liquidez activa y rango de precios**

En V3, los proveedores de liquidez pueden configurar sus posiciones para aportar liquidez solamente cuando el precio se encuentre dentro de determinado rango. Si el precio en el mercado se mueve fuera de ese rango, la posición se quedará conformada por un token solamente y el par quedará inactivo.

Las posiciones inactivas no participarán en los trades ni ganarán fees de trading.

### **Liquidez concentrada**

En V3, dado que los proveedores de liquidez pueden concentrar sus tokens aportados en sólo en un rango de precios, con la misma cantidad de activos aportados, V3 puede soportar un volumen de trade mucho mayor.

Esto resulta en un nivel de liquidez relativa mucho más alto comparado con V2. Y los proveedores de liquidez pueden ganar más en fees de trading con el mismo capital.

Aquí un ejemplo:

> Baller y Claire both aportan liquidez en el pool de CAKE/USDT por un valor de $1,000 USD en activos. El precio actual de CAKE es 5 USDT.
>
> Como en PancakeSwap v2, Baller aportó su liquidez en la totalidad del rango de precios. Por lo tanto, él depositó todo su capital, 500 USDT y 100 CAKE.
>
> Claire usó la nueva función de liquidez concentradaen PancakeSwap v3 y creó una posición con un rango de precio de 2 a 12.5 USDT por CAKE. Ella depositó 185 USDT y 37 CAKE, por un valor total de $370. Ella puede ahora usar los restantes $630 como quiera, por ejemplo bloquearlos en CAKE en el Syrup pool para disfrutar altos rendimientos en CAKE mientras recibe una serie de beneficios del ecosistema de PancakeSwap.
>
> Mientras CAKE se mantenga dentro del rango de precios de 2 a 12.5, ambos, Baller y Claire, recibirán el mismo monto de recompensas de fees de trading, mientras que Claire aportó mucho menos al pool de liquidez.

### **Ganando fees de trading**

Aportar liquidez, te da una recompensa en forma de fees de trading cuando la gente usa tu liquidez para realizar sus swaps.

Cada vez que alguien opera en PancakeSwap, por cada salto (swap) en cada pool de liquidez del Exchange V3, dependiendo del tier de fee del pool, el trader paga un fee en el rango desde 0.01% a 1%. Los niveles y detalles de los fees que pagará son los siguientes:

|                    | 0.01% | 0.05% | 0.25% | 1%  |
| ------------------ | ----- | ----- | ----- | --- |
| Liquidity Provider | 67%   | 66%   | 68%   | 68% |
| CAKE Burn          | 10%   | 10%   | 23%   | 23% |
| Treasury           | 23%   | 24%   | 9%    | 9%  |

Pejemplo, en un pool con un tier de fee de 0.25%:

* Contando todas las posiciones activas (en-rango), hay un total de 10 CAKE y 10 BNB tokens.
* Alguien cambia 1 CAKE por 1 BNB.
* Otro cambia 1 BNB por 1 CAKE.
* Los proveedores de liquidez que están en rango activo, ganaron un total de 0.0017 CAKE y 0.0017 BNB de esos trades.
* Las posiciones con rangos de precio que no cubren el precio actual, o sea inactivas, no contribuyen al trade ni ganan ningún fee.

### **Ganando CAKE**

Para que ser proveedor de liquidez sea aún más atractivo, también puedes poner a trabajar tus posiciones de liquidez en alguno de los nuevos [CAKE Farms](https://pancakeswap.finance/farms), mientras sigues ganando recompensas por fees de trading.



## Exchange V2

### LP Tokens

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

Como ejemplo, si depositas **CAKE** y **BNB** en un pool de liquidez, recibirás tokens **CAKE-BNB LP**.

La cantidad de tokens LP que recibes, representa tu parte del pool de liquidez de CAKE-BNB.

También podrás retirar tus fondos en cualquier momento, removiendo tu liquidez.

### **Ganando fees de trading**

Cada vez que alguien opera en PancakeSwap, por cada salto (swap) en cada pool de liquidez del Exchange V2, el trader paga un fee fijo del 0.25% fee, **de los cuales el 0.17%** es devuelto al pool de liquidez en forma de fees de trading.

### **Ganando CAKE**

El antiguo Exchange V2 seguirá activo en paralelo con el nuevo Exchange V3. Entonces, algunos pares de trading permanecerán en PancakeSwap Exchange V2 y tendrán sus respectivas V2 Farms. Por favor, compruebe las etiquetas para identificar las versiones de exchange.

## Impermanent Loss <a href="#impermanent-loss" id="impermanent-loss"></a>

Proporcionar liquidez no está exento de riesgos, ya que puede estar expuesto a impermanent loss.

&#x20;[“En pocas palabras, la pérdida impermanente es la diferencia entre mantener tokens en una AMM y mantenerlos en su billetera” - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
