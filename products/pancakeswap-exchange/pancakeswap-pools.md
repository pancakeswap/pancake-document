# Liquidity Pools

![](../../.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#03e94594-5a75-4687-b260-0dc69574b953" id="03e94594-5a75-4687-b260-0dc69574b953"></a>

In the new Exchange V3, liquidity will be managed in the form of non-fungible positions. You will still earn a share in the fees while providing liquidity.

When you add your token to a Liquidity Pool you will receive Liquidity Provider (LP) tokens and share in the fees.

### **Non-fungible liquidity positions**

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

In V3, liquidity providers now have more control over what price range they want to deploy their liquidity. So, when you add your token to a Liquidity Pool in V3, you will create a new non-fungible liquidity position with its unique settings.

Therefore, in V3, liquidity positions are NFTs. Please note that these NFTs are transferable, and they represent the ownership of the underlying assets and the trading fees they earned.

In V3, trading fees will no longer be automatically compounded in the position. You can manually claim them on each of the position detail pages.

You can redeem your funds at any time by removing your liquidity.

### **Active liquidity and price ranges**

In V3, liquidity providers can configure their positions to only provide liquidity when the price is within a certain range. If the trading price moves out of the range, the position will consist of only one type of token in the pair and become inactive.

Inactive liquidity positions will not participate in trading or earn any trading fees.

### **Concentrated liquidity**

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

Whenever someone trades on PancakeSwap, for each hop (swap) in each Exchange V3 liquidity pool, depending on the liquidity pool fee tier, the trader pays a fee ranging from 0.01% to 0.1%. Their fee rates and fee breakdowns are shown as follows:

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

<figure><img src="../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

As an example, if you deposited **CAKE** and **BNB** into a Liquidity Pool, you'd receive **CAKE-BNB LP** tokens.

The number of LP tokens you receive represents your portion of the CAKE-BNB Liquidity Pool.

You can also redeem your funds at any time by removing your liquidity.

### **Earning trading fees**

Whenever someone trades on PancakeSwap, for each hop (swap) in each Exchange V2 liquidity pool, the trader pays a fixed 0.25% fee, **of which 0.17%** is added back to the Liquidity Pool in a form of trading fees.

### **Earning CAKE**

The old Exchange V2 will be running in parallel with the new Exchange V3. So, some trading pairs will remain on PancakeSwap Exchange V2 and have their corresponding V2 Farms. Please check the tags to identify the exchange versions.

##

## Impermanent Loss

Providing liquidity is not without risk, as you may be exposed to impermanent loss.

[“Simply put, impermanent loss is the difference between holding tokens in an AMM and holding them in your wallet.” - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
