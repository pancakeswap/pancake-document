# 🔮 Prediction

![](../../.gitbook/assets/prediction-header.png)

PancakeSwap Prediction is a fun and simple decentralized prediction market.

> **Predict whether BNB, BTC, or ETH price will rise or fall – guess correctly to win!**

### Platforms

You can play PancakeSwap Prediction on:

* **Desktop/ dApp**: [PancakeSwap Prediction Guide](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini App (BNBUSD only)**: [Prediction Bot](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Summary: How It Works

1. **Choose an asset to bet on**: Currently available on **BNB Chain**, **zkSync Era**, and **Arbitrum One**.
2. **Pick UP or DOWN**: Predict if the asset price will be higher or lower when the “LIVE” phase ends (each round = 5 minutes).
3. Place your bet amount: Any BNB amount
4. **Lock in your position**: Once placed, your bet cannot be changed.
5. **Win or lose**:
   * If you chose **UP**, you win if the _Closed Price_ > _Locked Price_ at the end of the round.
   * If you chose **DOWN**, you win if the _Closed Price_ < _Locked Price_ at the end of the round.

### Mechanics & Fees

* **Supported Chains: BNB Chain, zkSync Era, Arbitrum One**
* **Round frequency**: Every **5 minutes** (rolling rounds).
* **Participation fee**: **3%** of each round’s total prize pool, a portion of which goes to **CAKE buybacks**.
* **Winnings**: Claim anytime after results are finalized.
* **Payouts** are based on the ratio of bets in each pool:
  * Payout Ratio (UP Pool) = _(Total value of both pools ÷ Value of UP Pool)_
  * Payout Ratio (DOWN Pool) = _(Total value of both pools ÷ Value of DOWN Pool)_
  * See: [FAQ](prediction-faq.md) for worked example

### Outcomes

* **Win:** You share the total pot with other winners (minus 3% fee)
* **Lose:** You lose your entire bet amount

**Special Cases**:

* **Tie** (Locked Price = Closed Price): House wins all bets.
* If there are no opposing bets:
  * If you win: reclaim 97% of your initial bet (3% fee applies).
  * If you lose: forfeits your full bet to the house.
* **Cancelled:** e.g. Oracle failure, users are refunded their initial bet amount

### Price Feeds (Oracles)

| Chain     | Markets                                  | Purpose                                                                 | Oracle                     |
| --------- | ---------------------------------------- | ----------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (paused) | Sets the _Lock Price_ and _Closed Price_ (updated \~ up to 20 seconds). | **Chainlink**              |
| BNB Chain | All                                      | Powers the live chart on the UI (for reference only).                   | Binance / TradingView Feed |

#### **ChainLink Oracle**

* Used for the Lock price and End price of each prediction market round. This updates in intervals of up to 20 seconds.
* Our prediction contract uses the ChainLink Oracle price feed on BNB Chain to set the prices used to dictate whether a user has won or not.
* Used for the "Chainlink" chart on the interface.

#### **Binance**

* Used for real-time price updates on the PancakeSwap prediction market interface.
* Used for the "TradingView" chart on the interface.

Since we’re using two different price feeds, the real-time price updates from Binance and the ChainLink Oracle price may differ by a small amount. However, they shouldn’t vary significantly.

### Contract Addresses

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
