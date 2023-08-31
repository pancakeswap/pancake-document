# Arbitrum

On 31st August 2023, PancakeSwap Perpetuals will launch the V2 Trading Rewards Program on Arbitrum. Users who stake [ALP in CAKE syrup pool](https://pancakeswap.finance/pools?chain=arb) on Arbitrum can enjoy boosting multipliers. In addition, there is no vesting period for rewards earned in this program. Users may claim their USDC rewards at any time. Details are as follows:

Starting time: 31st August 2023, 08:00 (UTC)

Activity (Epoch) period: Every Thursday 08:00:00 UTC to next Thursday 07:59:59, lasting 1 week

Reward Distribution Time: Each cycle is 00:00 (UTC) to 23:59 (UTC) daily. Rewards are issued on every Thursday at around 08:00 (UTC). After user's tier is update, rewards will be calculated and distributed. Users have to claim their rewards within 30 days after the rewards are issued. If they do not, the platform will revoke the rewards.&#x20;

Reward amount: For the first 5 weeks, 25% of trading fees (in USDC). This prize pool will then be distributed according to tiers.

Activity rules: Users who trade on PancakeSwap Perpetuals V2 on Arbitrum will qualify for the prize pool

### Tier Breakdown

Every Thursday at 08:00:00 UTC, we calculate the trading data from last Thursday 08:00:00 UTC to this Thursday at 07:59:59 and then update the user's Tier according to the Tier rules. The Tier rules are as follows (configuration is supported):

<table><thead><tr><th width="161">Tier</th><th width="249.33333333333331">Description</th><th>Weight</th></tr></thead><tbody><tr><td>Platinum</td><td>Epoch trading amount >=1M USD</td><td>2</td></tr><tr><td>Gold</td><td>Epoch trading amount >=500K USD</td><td>3</td></tr><tr><td>Diamond</td><td>Epoch trading amount >=250K USD</td><td>5</td></tr></tbody></table>

Rewards will be distributed equally across all users who qualify for a certain tier

### Trading Rewards calculation formula:&#x20;

At the end of each trading reward cycle, the user’s effective trading volume in that cycle will be calculated to determine the weightage and amount of USDC rewards.

The formula for the number of specific rewards is: r = R\*W / sum(Wi), the parameters are as follows:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Amount of USDC reward to be mined by the user for the current epoch</td></tr><tr><td>R</td><td><p>The reward of the current epoch R=(USDC value of ETH fee + USDC value of DAI fee + USDC value of BTC fee + USDC fee)*0.25, of which 1% Swap fee needs to be deducted when it comes to the settlement, for example: when the weekly ETH fee is 1 and the ETH Price is 2,000, the ETH fee for the USDC value = 1 * 2000 * 0.99</p><p></p><p>Note: Only calculating users from PancakeSwap Perpetuals V2 (Arbitrum)</p></td></tr><tr><td>W</td><td>Weight corresponding to the user's Tier level</td></tr><tr><td>Sum(Wi)</td><td>Total weight score of all users. Wi represents the weight of any user, and sum(Wi) represents sum weight scores of all users.</td></tr></tbody></table>



Terms and Conditions

* Due to the difference in trading fees for each trading pair on V2, the rewards users receive may vary even though their effective trading volumes are the same.
* The rewards to be distributed for each cycle will be stored in the following contract address:&#x20;
* PancakeSwap/ApolloX reserves the right of final interpretation for this activity.



Risk Warning: Crypto futures trading carries a substantial risk. All trading activities are done at your discretion and at your own risk. The information here should not be regarded as financial or investment advice from PancakeSwap/ApolloX. PancakeSwap/ApolloX will not be liable for any loss that might arise from your use of PancakeSwap/ApolloX.

\
