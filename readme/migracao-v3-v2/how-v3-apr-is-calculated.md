# How v3 APR is calculated

In V3 Liquidity and Farms, with the new non-fungible liquidity and customizable price range ability. Each LP position will have its own LP fee and CAKE farming APR.

The total APR is combined by the LP fee APR and CAKE reward APR

Theoretically speaking, given a price range and liquidity user about to add, we can estimate the expected future 7 days fee as following

feenext7d=feeinΔLLin+ΔLfee\_{next7d} = fee\_{in} \frac{\Delta{L\}}{L\_{in} + \Delta{L\}}

*   ​

    feein fee\_{in}

    : Fee amount accrued in the user specified price range in last 7 days
*   ​

    Lin L\_{in}

    : Current liquidity in the user specified price range
*   ​

    ΔL \Delta{L}

    : Liquidity user want to add to the price range

For

feein fee\_{in}

, we use the historical trading volume data, fee tier and historical price data to estimate the price in range

​

feein=ftV7dTinT7d fee\_{in} = f\_tV\_{7d}\frac{T\_{in\}}{T\_{7d\}}

​

*   ​

    V7d V\_{7d}

    : Total trading volume of last 7 days
*   ​

    Tin T\_{in}

    : Duration, measured in seconds, of prices staying within the price range in the past 7 days
*   ​

    T7d T\_{7d}

    : 7 days measured in seconds

The total reward cake per second in MC v3 using upkeep and can be derived by `latestPeriodCakePerSecond`

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

In each pool, we can use `poolInfo` to get the `poolWeight` by dividing `poolInfo.allocPoint / totalAllocPoint`

Global APR calculated using the total amount of active & staked liquidity with the pool CAKE reward emissions.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` represents the current pool active staked liquidity in USD, composing by all the position ticks in range staked in MasterChef v3.

APRs for individual positions may vary depend on their price range settings.

ARPp=USDrUSDpLpLlmARP\_p = {\frac{USD\_{r\}}{USD\_{p\}}} {\frac{L\_{p\}}{L\_{lm\}}}

*   ​

    USDrUSD\_r

    : CAKE reward earn USD per year in pool
*   ​

    USDpUSD\_p

    : Total USD value in position
*   ​

    Lp L\_{p}

    : Position liquidity
*   ​

    Llm L\_{lm}

    : Total staking liquidity which tracked by LMPool
