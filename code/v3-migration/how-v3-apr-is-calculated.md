# How v3 APR is calculated

{% hint style="info" %}
In V3 Liquidity and Farms, with the new non-fungible liquidity and customizable price range ability. Each LP position will have its own LP fee and CAKE farming APR.
{% endhint %}

The total APR is combined by the LP fee APR and CAKE reward APR

### LP fee

Theoretically speaking, given a price range and liquidity user about to add, we can estimate the expected future 7 days fee as following&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Fee amount accrued in the user specified price range in last 7 days
* $$L_{in}$$: Current liquidity in the user specified price range
* $$\Delta{L}$$: Liquidity user want to add to the price range

#### Fee in range

For $$fee_{in}$$, we use the historical trading volume data, fee tier and historical price data to estimate the price in range

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Fee tier
* $$V_{7d}$$: Total trading volume of last 7 days
* $$T_{in}$$: Duration, measured in seconds, of prices staying within the price range in the past 7 days
* $$T_{7d}$$: 7 days measured in seconds

### Cake APR

#### Pool Allocation

The total reward cake per second in MC v3 using upkeep and can be derived by `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

In each pool, we can use `poolInfo` to get the `poolWeight` by dividing  `poolInfo.allocPoint / totalAllocPoint`

#### Global Cake APR

Global APR calculated using the total amount of active & staked liquidity with the pool CAKE reward emissions.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` represents the current pool active staked liquidity in USD, composing by all the position ticks in range staked in MasterChef v3.

#### Position Cake APR

APRs for individual positions may vary depend on their price range settings.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: CAKE reward earn USD per year in pool
* $$USD_p$$: Total USD value in position
* $$L_{p}$$: Position liquidity
* $$L_{lm}$$: Total staking liquidity which tracked by LMPool
