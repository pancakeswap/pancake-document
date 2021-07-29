# Syrup Pool FAQ & Errores Frecuentes

## Troubleshooting <a id="troubleshooting"></a>

### **I can't find the Syrup Pool I was staking in!** <a id="i-cant-find-the-syrup-pool-i-was-staking-in"></a>

You should be able to find the Syrup Pool under the “Finished” tab on the Syrup Pools page.

By selecting “Staked Only”, it will make it easier to find your assets.

### **Why can’t I unstake my tokens from a Syrup Pool?** <a id="why-cant-i-unstake-my-tokens-from-a-syrup-pool"></a>

If you are unable to unstake from the Stake Cake, Earn CAKE pools, please check to make sure that you haven’t sold the SYRUP tokens in your wallet. This token acts as a \`proof of ownership\` over your CAKE in the Manual CAKE pool.

### **Why did my earned tokens go to zero after staking/unstaking?** <a id="why-did-my-earned-tokens-go-to-zero-after-staking-unstaking"></a>

Don’t worry! They’re in your wallet already.

Whenever you stake or unstake from a Syrup Pool or farm, your earned tokens get harvested and sent to your wallet at the same time.

## **General Questions** <a id="general-questions"></a>

### How is APR for Syrup Pools calculated? <a id="how-is-apr-for-syrup-pools-calculated"></a>

> Syrup Pool APR = Annualized rewards \(USD\) / User funds staked in Syrup Pool \(USD\) \* 100

As a basic example, let's take a 60-day pool with 300,000 USD worth of rewards, and 3,000,000 USD worth of CAKE staked in it.

The APR fluctuates as more CAKE is staked by users, and as the price of CAKE, and the reward token, vary.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x200B;</th>
      <th style="text-align:left"><b>Calculation</b>
      </th>
      <th style="text-align:left">Amount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Total rewards to distribute (USD value)</td>
      <td style="text-align:left">&#x200B;</td>
      <td style="text-align:left">300,000 USD</td>
    </tr>
    <tr>
      <td style="text-align:left">Distribution period</td>
      <td style="text-align:left">&#x200B;</td>
      <td style="text-align:left">60 days</td>
    </tr>
    <tr>
      <td style="text-align:left">Daily distribution</td>
      <td style="text-align:left">300,000 / 60 =</td>
      <td style="text-align:left">5,000 USD daily</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Annualised rewards (USD value)</b>
      </td>
      <td style="text-align:left">5,000 * 365 =</td>
      <td style="text-align:left"><b>1,825,000 USD</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Value of CAKE staked by users in pool (USD value)</b>
      </td>
      <td style="text-align:left">&#x200B;</td>
      <td style="text-align:left"><b>3,000,000 USD</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>APR</b>
      </td>
      <td style="text-align:left">(1,825,000 / 3,000,000) * 100 =</td>
      <td style="text-align:left">
        <p>&#x200B;</p>
        <p><b>60.833% APR</b>
        </p>
      </td>
    </tr>
  </tbody>
</table>

### **What does the “End” number on my Syrup Pool refer to?** <a id="what-does-the-end-number-on-my-syrup-pool-refer-to"></a>

This shows the amount of blocks left until the rewards for that pool stop being distributed. Once the pool has reached that block, you should unstake your tokens, because you won’t be receiving any rewards after that.

### **Where do the rewards from Syrup Pools come from?** <a id="where-do-the-rewards-from-syrup-pools-come-from"></a>

There are three main types of Syrup Pools.

1. Stake CAKE, earn CAKE
2. Stake CAKE, earn other tokens.
3. Stake other tokens, earn CAKE

The rewards for the "Stake CAKE, earn CAKE" Syrup Pools come from the [CAKE emissions](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Each block, a number of CAKE tokens are allocated as rewards for these pools.

The rewards for the "Stake CAKE, earn other tokens" type are provided by the project teams who sponsor a Syrup Pool.

For the "Stake other tokens, earn CAKE" type, the PancakeSwap treasury buys back CAKE from the market to distribute as rewards. These pools are funded by PancakeSwap, not by the projects themselves.

### What’s SYRUP Token? <a id="whats-syrup-token"></a>

PancakeSwap’s SYRUP Token is deposited in your wallet when you interact with the **Manual** “Stake CAKE, Earn CAKE” Syrup Pool. It's not staked for

It’s basically an IOU that shows how much CAKE you’ve staked in the pool.

It’ll be returned automatically when you unstake your CAKE from that pool.

Don’t sell your SYRUP tokens! You need to return your SYRUP to unstake your CAKE from the Manual CAKE pool. The amount of SYRUP you return must be the same as the amount of CAKE you unstake.[  
](https://docs.pancakeswap.finance/products/syrup-pool/auto-compounding)

