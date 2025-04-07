# 📈 Analytics (Info Page)

## Info Page&#x20;

View PancakeSwap's native analytics site here: [https://pancakeswap.info](https://pancakeswap.info)

![](<../.gitbook/assets/image (9) (2).png>)

All core metrics data are sourced from the PCS internal Indexer, which, in turn, gathers data from events triggered when the contract is called.&#x20;

For the date dimension in the PancakeSwap's internal indexer, we use international standard time (UTC) for daily statistics. Therefore, when the horizontal axis on the Dashboard displays a date, it represents the date in international standard time (UTC).\


## Core Metrics

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume (Trading Volume):** We monitor the daily data for each trading pair and the daily trading data for each token. The daily trading volume is determined by multiplying the trading volume of each token for the day by its price.

**Total Value Locked:** Get all pools from internal Indexer and read the reserve\_usd or total\_value\_locked\_usd from each pool.&#x20;

**Price:** In the PCS Internal Indexer, we utilize several base pools to calculate USD-related prices. The primary pool is the stablecoin trading pool, where we use the trading pool with the highest volume as the base pool and calculate the USD price of the stablecoin based on the trading volume weight. Additionally, the trading pool of the base token to the chain's stablecoin is also considered a base pool to provide the USD price.

_Tokens that are not whitelisted or not paired with whitelisted tokens are excluded from these calculations._

\
