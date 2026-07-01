# 🌊 Pools de Liquidez

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

En el nuevo Exchange V3, la liquidez se gestionará en forma de posiciones no fungibles. Seguirás ganando una parte de las comisiones al proporcionar liquidez.

Cuando agregas tu token a un Pool de Liquidez, recibirás tokens NFT de Proveedor de Liquidez y compartirás las comisiones.

### **Posiciones de liquidez no fungibles**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

En V3, los proveedores de liquidez ahora tienen más control sobre el rango de precios en el que desean desplegar su liquidez. Por lo tanto, cuando agregas tu token a un Pool de Liquidez en V3, crearás una nueva posición de liquidez no fungible con su configuración única.

Por lo tanto, en V3, las posiciones de liquidez son NFTs. Ten en cuenta que estos NFTs son transferibles y representan la propiedad de los activos subyacentes y las comisiones de trading que han ganado.

En V3, las comisiones de trading ya no se compondrán automáticamente en la posición. Puedes reclamarlas manualmente en cada una de las páginas de detalle de posición.

Puedes canjear tus fondos en cualquier momento eliminando tu liquidez.

### **Liquidez activa y rangos de precios**

En V3, los proveedores de liquidez pueden configurar sus posiciones para proporcionar liquidez solo cuando el precio está dentro de un cierto rango. Si el precio de trading se mueve fuera del rango, la posición consistirá solo en un tipo de token del par y quedará inactiva.

Las posiciones de liquidez inactivas no participarán en el trading ni ganarán comisiones de trading.

### **Liquidez concentrada**

En V3, porque los proveedores de liquidez pueden concentrar sus depósitos de tokens para proporcionar liquidez solo dentro de un rango de precios específico. Con la misma cantidad de activos subyacentes, V3 puede soportar un intercambio mucho mayor.

Resulta en un nivel de liquidez relativa mucho más alto en comparación con V2. Y los proveedores de liquidez pueden ganar más comisiones de trading con la misma cantidad de capital.

Aquí hay un ejemplo:

> Baller y Claire ambos proporcionaron liquidez en el pool CAKE/USDT con $1,000 USD en activos de tokens. El precio actual de CAKE es 5 USDT.
>
> Similar a PancakeSwap v2, Baller proporcionó su liquidez en todo el rango de precios. Por lo tanto, depositó todo su capital, 500 USDT y 100 CAKE.
>
> Claire utiliza la nueva función de liquidez concentrada en PancakeSwap v3 y creó una posición con un rango de precios de 2 a 12,5 USDT por CAKE. Depositó 185 USDT y 37 CAKE, con un valor total de $370. Ahora puede gastar los $630 restantes en otro lugar, como bloquear CAKE en el pool Syrup para disfrutar de un alto rendimiento de CAKE mientras recibe una serie de beneficios del ecosistema PancakeSwap.
>
> Mientras CAKE se mantenga dentro del rango de precios de 2 a 12,5, tanto Baller como Claire recibirán la misma cantidad de recompensas de comisiones de trading mientras Claire depositó mucho menos capital en el pool de liquidez.

### **Comisiones de trading**&#x20;

Proporcionar liquidez te da una recompensa en forma de comisiones de trading cuando las personas usan tu pool de liquidez para completar intercambios.

Cada vez que alguien intercambia en PancakeSwap, por cada salto (intercambio) en cada pool de liquidez de Exchange V3, dependiendo del nivel de comisión del pool de liquidez, el trader paga una comisión que va del 0,01% al 1%. Sus tasas de comisión y desgloses se muestran a continuación:

<details>

<summary>Comisiones de Trading (EVM)</summary>

| Componente de Comisión / Nivel de comisión | 0,01% | 0,05% | 0,25% | 1%  |
| ------------------------------------------ | ----- | ----- | ----- | --- |
| Proveedor de Liquidez                      | 67%   | 66%   | 68%   | 68% |
| Quema de CAKE                              | 15%   | 15%   | 23%   | 23% |
| Tesoro                                     | 18%   | 19%   | 9%    | 9%  |

Por ejemplo, en un pool con nivel de comisión del 0,25%:

* Entre todas las posiciones de liquidez activas (dentro del rango), hay un total de 10 CAKE y 10 BNB tokens.
* Alguien intercambia 1 CAKE por 1 BNB.
* Otra persona intercambia 1 BNB por 1 CAKE.
* Los proveedores de liquidez que están en el rango proporcionando liquidez activa ganaron un total de 0,0017 CAKE y 0,0017 BNB de los intercambios.
* Las posiciones con rangos de precios que no cubren el precio actual, siendo por lo tanto inactivas, no contribuirán al trading ni ganarán comisiones.

</details>

<details>

<summary><strong>Comisiones de trading (Solana)</strong></summary>

**Niveles de Comisión de Pool CLMM V3 disponibles:**\
0,01%, 0,02%, 0,03%, 0,04%, 0,05%, 0,1%, 0,15%, 0,16%, 0,18%, 0,2%, 0,25%, 0,4%, 0,6%, 0,8%, 1%, 2%, 3%, 4%

**Nota:** La **distribución de comisiones sigue siendo la misma** en todos los niveles de comisión.

| Componente de Comisión        | % del Total de Comisión de Intercambio | Descripción                                                    |
| ----------------------------- | -------------------------------------- | -------------------------------------------------------------- |
| **LPs (Proveedores de Liquidez)** | 84%                               | Ganado por LPs que proporcionan liquidez en el rango de precios activo |
| **Quema**                     | 8%                                     | Eliminado permanentemente para reducir el suministro de CAKE   |
| **Tesoro**                    | 8%                                     | Asignado al tesoro del protocolo PancakeSwap                   |

**Ejemplo: Distribución de Comisiones en un Pool CAKE/SOL del 0,25%**

1. **Configuración del Pool:** Liquidez activa total: 10 CAKE y 10 SOL (posiciones dentro del rango).
2. **Ocurren Intercambios:**
   * El Usuario A intercambia 1 CAKE → 1 SOL.
   * El Usuario B intercambia 1 SOL → 1 CAKE.
3. **Total de Comisiones Cobradas:**
   * 0,25% por intercambio × 2 intercambios = **0,005 CAKE + 0,005 SOL**.
4. **Distribución de Comisiones:**
   * **84% para LPs:** 0,0042 CAKE + 0,0042 SOL
   * **8% para Quema:** 0,0004 CAKE + 0,0004 SOL
   * **8% para Tesoro:** 0,0004 CAKE + 0,0004 SOL
5. **Ganancias de LP:**
   * Solo los **LPs dentro del rango** ganan comisiones. Las comisiones se distribuyen proporcionalmente según la participación de cada LP.
   * Los **LPs fuera del rango** no ganan **ninguna comisión**.

</details>

### **Ganar CAKE**

Para hacer que ser un proveedor de liquidez valga aún más la pena, también puedes poner tus posiciones de liquidez a trabajar generando algo de rendimiento fresco en las [Granjas CAKE](https://pancakeswap.finance/liquidity/pools), ¡mientras sigues ganando recompensas de comisiones de trading!

***

## Exchange V2

### Tokens LP

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Como ejemplo, si depositaste **CAKE** y **BNB** en un Pool de Liquidez, recibirías tokens LP **CAKE-BNB**.

El número de tokens LP que recibes representa tu porción del Pool de Liquidez CAKE-BNB.

También puedes canjear tus fondos en cualquier momento eliminando tu liquidez.

### **Ganar comisiones de trading**

Cada vez que alguien intercambia en PancakeSwap, por cada salto (intercambio) en cada pool de liquidez de Exchange V2, el trader paga una comisión fija del 0,25%, **de la cual el 0,17%** se agrega de vuelta al Pool de Liquidez en forma de comisiones de trading.

### **Ganar CAKE**

El antiguo Exchange V2 seguirá funcionando en paralelo con el nuevo Exchange V3. Por lo tanto, algunos pares de trading permanecerán en PancakeSwap Exchange V2 y tendrán sus Granjas V2 correspondientes. Por favor, revisa las etiquetas para identificar las versiones del exchange.



## Pérdida Impermanente

Proporcionar liquidez no está exento de riesgos, ya que puedes estar expuesto a pérdida impermanente.

["En pocas palabras, la pérdida impermanente es la diferencia entre mantener tokens en un AMM y mantenerlos en tu billetera." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
