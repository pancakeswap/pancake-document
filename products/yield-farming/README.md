# 🚜 Yield Farming

![](<../../.gitbook/assets/docs masthead (1) (2).png>)

Yield Farms allow users to earn CAKE while supporting PancakeSwap by staking LP Tokens.

Check out our [How to Use Farms guide](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) to get started with farming.

Learn [how to find Farm smart contracts](./)

{% hint style="warning" %}
Yield farming can give better rewards than Syrup Pools, but it comes with a risk of **Impermanent Loss**. It’s not as scary as it sounds, but it is worth learning about the concept before you get started.

Check out this great [article about Impermanent Loss ](https://academy.binance.com/en/articles/impermanent-loss-explained)from Binance Academy to learn more.
{% endhint %}

## Reward calculations

Yield Farm APR calculations include both:

* **LP rewards APR** earned through providing liquidity and;
* **Farm base rewards APR** earned staking LP Tokens in the Farm.

Why? Because when you stake your LP tokens in a farm to earn CAKE, you're still providing liquidity to the liquidity pool, so you earn LP rewards as well!

![](<../../.gitbook/assets/Frame 1 (2).png>)

So how do we calculate those figures?

### Calculating Farm Base Reward APR

The **Farm Base APR** is calculated according to the farm multiplier and the total amount of liquidity in the farm -- this is the amount of CAKE distributed to the farm.

### Calculating LP Reward APR

On top of that, farmers receive **LP rewards** for providing liquidity. Here's an example of calculating **LP rewards**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1\_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq\_cfiBriKcl)

In the WBNB/BUSD pair above, we see these values:

**Liquidity:** $387.42M\
**Volume 24H:** $96.97M\
**Volume 7D:** 709.73M

* Calculate yearly fees
  * Use the 24H volume to calculate the **fee share** of liquidity providers in the pool (based on the 0.17% trading fee structure):\
    $96,970,000\*0.17/100 = **$164,849**
  * Next, use that **fee share** to estimate the projected **yearly fees** earned by the pool (based on the current 24h volume):\
    $164,849\*365 = **$60,169,885**
* We can now use the yearly fees to calculate the **LP rewards APR:** That's **yearly fees** divided by **liquidity:**\
  ($60,169,885/$387,420,000)\*100 = **15.53% LP reward APR**
