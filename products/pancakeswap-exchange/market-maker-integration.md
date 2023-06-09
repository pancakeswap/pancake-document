# Market Maker Integration

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Market Maker Integration on Ethereum

PancakeSwap is integrated with market makers on Ethereum and Binance Smart Chain to help traders execute trades at a lower cost.

In addition to the AMM, trades on PancakeSwap can now be routed to designated white-listed market makers if they offer trade execution that is better than the AMM’s current prices. This routing is done automatically by a [Smart Router](smart-router-v2/) so that trades are only routed to market makers when they are actively quoting better prices. Where the AMM is more competitive, traders will be routed to the AMMs for execution.

There are 2 scenarios in which market makers operate on PancakeSwap.

**Scenario 1: Existing AMM liquidity pools**

If PancakeSwap already has liquidity for a given token (e.g. WETH/USDC) in the AMM, PancakeSwap will ask market makers for a quote on the same trade. PancakeSwap’s smart router will then route the trade request to the AMM or the market makers depending on which source of liquidity is giving the best price at any given time.

**Scenario 2: No existing AMM liquidity pools**

In such a scenario, the smart router will automatically route the trade to the market makers. However, this does not stop projects from setting up their AMM liquidity pool subsequently and working with us to maintain decentralized DEX liquidity.

### Fees

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap does not charge traders any fees executed through us and which are executed by the market makers. However, PancakeSwap receives **0.05%** **trading fees (0.0375% on BSC)** from whitelisted market makers for volumes executed by them. PancakeSwap receives a reduced **0.01%** **trading fee** if the trades executed are between stablecoin pairs. Please refer to the fee breakdown below:\


<table><thead><tr><th width="178">Trades</th><th width="138">Trading Fees</th><th width="182">PCS fee from MM</th><th width="147">Cake Burn</th><th align="center">Pancakeswap Treasury</th></tr></thead><tbody><tr><td>Non-stablecoin on Ethereum (e.g. ETH/USDC)</td><td>N/A</td><td>0.05%</td><td>0.017%</td><td align="center">0.033%</td></tr><tr><td>Non-stablecoin on BSC (e.g. BNB/USDT)</td><td>N/A</td><td>0.0375%</td><td>0.013% </td><td align="center">0.025%</td></tr><tr><td>Stablecoin to Stablecoin on Ethereum</td><td>N/A</td><td>0.01%</td><td>0.003%</td><td align="center">0.007%</td></tr></tbody></table>

#### Assets currently supported&#x20;

The following assets are currently supported and may increase/decrease depending on the market maker(s):

**On Ethereum**

* **Majors:** WETH, WBTC&#x20;
* **Stablecoins:** USDT, USDC, DAI, BUSD
* **Other popular ERC-20 assets:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**On Binance Smart Chain:**&#x20;

* **Majors:** BNB, ETH, BTCB
* Non-native BNB tokens: ARB, OP

Please note that unlike AMMs, market makers will not be able to trade at any amount and the amounts they are willing to execute will depend on their own liquidity. It is not unusual that sometimes very large orders cannot be totally fulfilled. We advise users to please review the quotes carefully to ensure that each trade reflects the price and quantity according to their needs.&#x20;

**Market maker downtimes**&#x20;

Market makers are not expected to quote 24-7. There are some instances (e.g. key economic events, system upgrades) where the market maker may be temporarily unavailable to provide a quote. Please note during these periods, these tokens will simply not be tradable, and we advise users to wait for some time before the market maker comes back online.

#### FAQs&#x20;

**Q.** Will the market makers be integrated on Aptos?&#x20;

**Ans:** Possibly, we are only launching market makers integration on Ethereum and Binance Smart Chain for now to boost the liquidity for a better user experience. We will continue to monitor other chains.

**Q.** How will PancakeSwap generate revenue if it does not charge users a fee?&#x20;

**Ans:** PancakeSwap will not charge any fees from users, but PancakeSwap will receive a small commission from market makers and use that to fund the CAKE buyback and burn.

**Q.** Will Liquidity providers continue to earn LP fees?&#x20;

**Ans:** Yes, liquidity providers will continue to earn 0.17% trading fee reward (LP fees) and yield on the CAKE farms.

**Q.** Will the market makers add liquidity to the AMM? Will that cause APR to go down?&#x20;

**Ans:** Market makers maintain their own separate liquidity, and hence won’t be earning any APR from trades on the AMM. Only LPs will earn fees and APRs from providing liquidity to the AMM pools.

**Q.** I’m providing liquidity on Ethereum PancakeSwap. Do I need to do anything?&#x20;

**Ans:** No, You don’t have to do anything. You will continue to earn the LP fees for the trades executed through AMM and will continue to make the yield in CAKE.

**Q.** How can someone become a market maker?

**Ans:** We screen and work with market makers on an individual basis. Please approach us directly or through our admins if you have an interest in working with us.
