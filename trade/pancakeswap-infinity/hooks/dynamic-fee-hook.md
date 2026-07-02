# Dynamic Fee Hook

PancakeSwap’s official Dynamic Fee Hook is designed to create a fairer value exchange between Liquidity Providers and Traders. It protects LPs from excessive impermanent loss (IL) while keeping the market efficient for traders.

Built by the PancakeSwap core team, this hook is tailored specifically to offer a smart, adaptive alternative to conventional fixed-fee models.

#### 🔍 Why Dynamic Fees?

Large Arbitrage trades cause greater price divergence in pools, increasing IL for LPs. Our dynamic fee model charges proportionally higher fees on larger arbitrage trades to offset this risk — while still leaving enough room for arbitrageurs to profit and keep prices aligned.

#### 📊 How Is This Different From Other Models?

Other models in the past have used historical data to estimate volatility, other factors to adjust fees. However:

* Historical data is a lagging indicator and may not accurately predict future volatility.
* External market events (like regulatory changes or economic shifts) can render past trends unreliable.
* Complex, parameter-heavy models risk overfitting — performing well on past data but poorly on new, unseen conditions.

Our approach is simpler, adaptive, and grounded in real-time trading behaviour.

#### ⚙️ How It Works

* **We don’t predict volatility or other macro factors**\
  Instead, our model inherently benefits from the behaviour of arbitrageurs under different market regimes:
  * **High volatility:** More arbitrage trades at larger sizes → Higher fees for LPs, covering a larger share of IL.
  * **Low volatility:** Fewer, smaller trades → IL is lower by nature, but LPs still earn higher fees than in a fixed-fee model.
* **Our model uses**
  * An exponentially weighted pool price to detect arbitrage trades.
  * An exponential fee curve based on the price impact of each swap.
  * A maximum fee cap of 5% to maintain trader fairness.

{% hint style="success" %}
This ensures fees scale dynamically with trade impact while adapting automatically to changing market conditions.
{% endhint %}

* **Balanced Incentives**\
  Arbitrageurs still retain \~50% of their profits after dynamic fees, ensuring they're motivated to keep pool prices in line with the market.

#### 📌 Key Takeaways

* No reliance on volatility or other macro factor predictions.
* Adapts automatically to market volatility based on actual trade behaviour.
* Protects LPs from IL on a per-swap basis.
* Maintains strong incentives for arbitrageurs to close price gaps.
* Benefits traders with deeper liquidity and lower base fees.
