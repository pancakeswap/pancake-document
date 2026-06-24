# v3 APR 如何计算

{% hint style="info" %}
在 V3 流动性和农场中，借助全新的非同质化流动性和可自定义价格区间的能力，每个 LP 头寸都将拥有自己的 LP 手续费和 CAKE 流动性挖矿 APR。
{% endhint %}

总 APR 由 LP 手续费 APR 和 CAKE 奖励 APR 组合而成

### LP 手续费

理论上来说，给定一个价格区间和用户即将添加的流动性，我们可以按如下方式估算预期的未来 7 天手续费&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ ：过去 7 天内在用户指定价格区间中累积的手续费金额
* $$L_{in}$$：用户指定价格区间中的当前流动性
* $$\Delta{L}$$：用户想要添加到该价格区间的流动性

#### 区间内手续费

对于 $$fee_{in}$$，我们使用历史交易量数据、手续费档位和历史价格数据来估算区间内的价格

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$：手续费档位
* $$V_{7d}$$：过去 7 天的总交易量
* $$T_{in}$$：过去 7 天内价格停留在该价格区间内的时长，以秒为单位
* $$T_{7d}$$：以秒为单位的 7 天

### Cake APR

#### 矿池分配

MC v3 中每秒的总奖励 cake 通过 upkeep 实现，可由 `latestPeriodCakePerSecond` 推导得出&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

在每个矿池中，我们可以使用 `poolInfo`，通过 `poolInfo.allocPoint / totalAllocPoint` 相除来获得 `poolWeight`

#### 全局 Cake APR

全局 APR 使用活跃且已质押流动性的总量以及矿池 CAKE 奖励释放量来计算。

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` 表示当前矿池活跃的已质押流动性（以美元计），由所有在 MasterChef v3 中质押的、处于区间内的头寸刻度组成。

#### 头寸 Cake APR

各个头寸的 APR 可能因其价格区间设置而有所不同。

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$：矿池中每年赚取的 CAKE 奖励美元价值
* $$USD_p$$：头寸中的总美元价值
* $$L_{p}$$：头寸流动性
* $$L_{lm}$$：由 LMPool 追踪的总质押流动性
