# Degen Mode

<figure><img src="../../../../.gitbook/assets/Perps Degen Mode-2.jpeg" alt=""><figcaption></figcaption></figure>

Degen 交易模式（Degen Trading Mode）为交易者提供了与在传统交易模式之外的另一种交易方式。那些希望减少盯紧荧幕并进行市场分析的时间、期望减少交易频率的交易者，提供了一种交易模式选择。在价格波动剧烈的时期，交易者可以通过 0 滑点、高杠杆和极低的手续费获得最大收益。在价格低波动期，此工具可协助交易者用于微小的价格波动上。

目前 Degen 交易模式仅初步可用于 BTCUSD、ETHUSD 交易对，支持市价单多单、空单最大 1001 倍的杠杆率。交易者在开设零滑点仓位前，需要先输入本金数额（保证金数额）。

BNB 链、Arbitrum、 opBNB 和 Base链上的永续合约 V2 均提供 Degen 模式。

#### Degen 模式简介 <a href="#degen-mo-shi-de-xing-shi" id="degen-mo-shi-de-xing-shi"></a>

Degen 模式为我们的永续合约交易者提供以下玩法特色和优势：

**高杠杆，较低的预付保证金** - 因 Degen 模式具备较高的杠杆率，最高高达 1001x，用户可以杠杆放大自己的交易策略。借助此模式可以享受更高的收益，而无需支付大量的预付保证金。

**更低的手续费** - 通过零滑点交易（zero-slippage trading），用户可以享受更好的交易体验。用户无需支付开仓费用。这也增加了用户的收益，因为省下来的开仓费现在可以作为保证金使用。

**动态费用结构** - 为 Degen 模式量身定制的平仓动态费用结构，根据盈亏（PnL）收取手续费。有关动态费用结构的更多信息，请点击[此处](degen-mode-dynamic-fee.md)。

**适用的代币对** - Degen 模式目前适用于 BNB 链、Arbitrum、opBNB、Base 链上的 BTCUSD 和 ETHUSD 交易对。

### 如何使用 <a href="#ru-he-shi-yong" id="ru-he-shi-yong"></a>

1. 前往 [https://perp.pancakeswap.finance/en/futures/v2/](https://perp.pancakeswap.finance/en/futures/v2/) 或在主页上点击 "永续合约"。
2. 在屏幕右上方，选择 "做多" 或 "做空" 仓位，然后点击 "Degen 模式 (BETA) " 图标。当图标上色（浅蓝色）时，代表正在使用 Degen 模式。

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-3369173170%2Fuploads%2F0HVhehRFToTZRrJGfIhk%2Fdegen%20mode%201.png?alt=media&#x26;token=cd10922c-09d7-4fed-af8a-662044b4a62f" alt=""><figcaption></figcaption></figure>

3. 输入金额和设定适当的杠杆倍数。Degen 模式支持最高 1001 倍的杠杆率。

​

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-3369173170%2Fuploads%2FuFyt8vAMbXVPlECrevD9%2Fdegen%20mode%202.png?alt=media&#x26;token=68a31735-d7bc-45ee-8f9e-dc8e36795d38" alt=""><figcaption></figcaption></figure>

4. 选择止盈百分比（50% 至 300%），然后选择**开仓**。

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-3369173170%2Fuploads%2FDdaQICjInPdvBDnKRleu%2F%E6%B0%B8%E7%BB%AD%E5%90%88%E7%BA%A6V2%204%20.png?alt=media&#x26;token=f8cba6d8-defa-41f5-bd1b-f95583a279a0" alt=""><figcaption></figcaption></figure>

5. 您的仓位将显示在页面底部的 "仓位" 选项卡中。如您想确认 Degen 模式是否已激活，可以查看杠杆（Leverage）一栏，如出现 "Pepe" 图标，表示这是 Degen 模式的仓位。

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-3369173170%2Fuploads%2FA31vJWlZg4Ldm7hV7uiK%2Fimage.png?alt=media&#x26;token=99e8c74d-f665-4c53-b652-87d7f89436af" alt=""><figcaption></figcaption></figure>

6. 如果想要平仓，请点击仓位边上的 "平仓（close）" 按钮。否则，Degen 模式的平仓将在止盈点位或清算期时（liquidation period）自动执行。想要获取更多信息，请参阅[永续合约 V2 术语表](https://app.gitbook.com/o/-MHRKTpKSfYQBsO7YgOo/s/-MHREX7DHcljbY5IkjgJ-3369173170/\~/diff/\~/changes/758/chan-pin/yong-xu-he-yue-jiao-yi/yong-xu-he-yue-jiao-yi-v2/yong-xu-he-yue-v2-shu-yu-biao/\~/overview)和[永续合约 V2 FAQ ](https://app.gitbook.com/o/-MHRKTpKSfYQBsO7YgOo/s/-MHREX7DHcljbY5IkjgJ-3369173170/\~/diff/\~/changes/758/chan-pin/yong-xu-he-yue-jiao-yi/yong-xu-he-yue-jiao-yi-v2/yong-xu-he-yue-v2-faq/\~/overview)。
