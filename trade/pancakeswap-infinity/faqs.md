# FAQs

1. **How is Infinity different from PancakeSwap V3?**\
   Infinity adds new features like programmable hooks, more [pool types](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (like LBAMM and CLAMM), and gas savings. However, the core swap and liquidity provision mechanics are broadly similar to v3 except some minor differences in LBAMM pools for liquidity provisioning.\
   \

2.  **What’s the difference between LBAMM and CLAMM?**

    1. **LBAMM (Liquidity Book AMM):** Uses liquidity bins, each holding liquidity at different price levels. LPs can provide liquidity across bins, swaps are executed at a single price level within a bin.
    2. **CLAMM (Concentrated Liquidity AMM):** Allows users to provide liquidity within custom price ranges like in PancakeSwap V3.

    \
    For more details, visit [here](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    \

3. **How do I claim my farm rewards, and why is it limited to every 8 hours?**\
   You can claim farm rewards from your liquidity positions by clicking on "Harvest" button. Infinity allows for batch claiming across all active farm positions, saving gas cost. Rewards are computed and processed every 8 hours to optimise for gas costs and compute. \
   \
   For more details on farming mechanism, visit [here](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   \

4.  **How do the Infinity hooks work?**\
    Hooks are customizable smart contract extensions that add extra functionality to a pool. They can trigger additional actions during swaps or liquidity events — for example, adjusting fees, offering discounts, or applying other logic.\


    Hooks are attached to a pool when it’s created. In most cases, **users don’t need to take any extra steps**. As long as you’re swapping or providing liquidity as usual, you’ll automatically benefit from the hook’s logic if it applies to that pool.\


    👉 **You can view the active hooks and their details on each pool’s page under the "Pool Features" section.**\
    \

5.  **Why didn’t I receive any fees when withdrawing my position from an LBAMM pool?**\
    In LBAMM (Liquidity Book AMM) pools, fees are automatically added to your active liquidity bins. This means:

    1. When you withdraw your position, your earned fees are included in the total token amounts you’re withdrawing.
    2. Unlike traditional AMMs, there’s no separate “fees to collect” balance — it’s all bundled into your position’s value.

    \
    If you didn’t notice additional tokens upon withdrawal, it could be because:

    1. Your position may have incurred more impermanent loss than the fees collected due to price moves during your position’s duration.
    2. Your liquidity wasn’t in active bins where trades occurred.
