# 📈 信息站（信息页面）

## 信息页面&#x20;

在此查看 PancakeSwap 的原生分析站点：[https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

所有核心指标数据均来源于 PCS 内部索引器（Indexer），而索引器又从合约被调用时触发的事件中收集数据。&#x20;

对于 PancakeSwap 内部索引器中的日期维度，我们使用国际标准时间（UTC）进行每日统计。因此，当 Dashboard 上的横轴显示日期时，它表示的是国际标准时间（UTC）下的日期。<br>

## 核心指标

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume（交易量）：** 我们监控每个交易对的每日数据以及每个代币的每日交易数据。每日交易量的计算方式为：将当日每个代币的交易量乘以其价格。

**Total Value Locked（总锁仓价值）：** 从内部索引器获取所有池子，并读取每个池子的 reserve\_usd 或 total\_value\_locked\_usd。&#x20;

**Price（价格）：** 在 PCS 内部索引器中，我们利用多个基础池来计算与美元相关的价格。主要的池子是稳定币交易池，我们使用交易量最高的交易池作为基础池，并根据交易量权重计算稳定币的美元价格。此外，基础代币与该链稳定币的交易池也被视为基础池，用以提供美元价格。

_未被列入白名单的代币，或未与白名单代币配对的代币，将被排除在这些计算之外。_

<br>
