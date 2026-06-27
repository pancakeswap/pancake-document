# 虫洞跨链桥 FAQ

### 问：在哪里可以找到我操作跨链的链上交易？

#### Wormhole Explorer 网站

在跨链状态页面上，您可以看到一个链接，指向 Wormhole Explorer 上您的链上交易（transaction）。\
当您在原链上的链上操作已被写入原链区块但尚未被 Wormhole 验证完毕时，您的链上交易状态将如下所示：

<figure><img src="../../.gitbook/assets/Wormhole FAQ 01.png" alt=""><figcaption></figcaption></figure>

\
点击 FIND REDEEM 按钮是完成目标链交易的另一种方法。在虫洞跨链桥停滞或无法更新桥交易状态的情况下，您可以使用这种方法。要赎回交易，首先点击赎回按钮。\
\
当 Wormhole 跨链桥停滞、更新您的跨链链上交易状态失败时，您可以尝试点击 "find redeem" 按钮，这是一个可以完成目的链链上交易的替代方式。

<figure><img src="../../.gitbook/assets/Wormhole FAQ 02.png" alt=""><figcaption></figcaption></figure>

如要撤销跨链，可以点击 "赎回（redeem）" 按钮。

然后，将会显示一个选项，用以恢复（resume）您之前发送的链上操作。点击该选项，您就可以进入论坛（forum）（链接在下一个问题中），以完成赎回（redemption）的链上交易。

### 问：我向某个链发送了代币 - 我的代币没有到达我的目标链钱包，但已经离开了我的原链钱包。我该怎么办？

有两种情况： a) 需要赎回跨链代币 b) 如果赎回已经成功，将代币添加到您的钱包中就会显示：[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do)

#### a) 赎回（**Redeeming）**：

* &#x20;前往 [https://portalbridge.com/#/redeem ](https://portalbridge.com/advanced-tools/#/redeem)
* &#x20;您需要输入原链名称和原链上的链上交易 ID（您可以在钱包中找到，或在区块链浏览器中输入您的地址查找）

<figure><img src="../../.gitbook/assets/Wormhole FAQ 03.png" alt=""><figcaption></figcaption></figure>

* 点击 Recover
* 点击 Redeem 然后再钱包中签署链上交易

**b) 将资产添加到你的钱包:**

**Metamask:**

* 在 Metamask 资产选项卡中，点击导入代币&#x20;
* 在相关区块链浏览器中点击代币名称，即可找到合约地址。
* 点击代币名称后，会打开一个新窗口，合约地址位于代币资料的右侧。
* &#x20;您还需要一个符号--可以是任何您想识别的代币。&#x20;
* 点击添加自定义代币

点击[此处](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet/#metamask)查看视频教程--如何在 Metamask 钱包中添加代币

### 我跨链了 X 代币，但现在无法进行兑换。没有一个 DEX 有流动性。&#x20;

如果您跨链的代币在目标链上没有流动性，您需要使用 Portal 跨链桥将其跨链回来。您可以将代币合约地址（您可以在钱包中找到该地址，或在区块链浏览器中找到您需要的地址）粘贴到 Portal 网站的 "选择代币 （select a token）" 一栏中。&#x20;

您可以在[这里](https://portalbridge.com/docs/faqs/liquid-markets/)找到流动性市场的全面概述。&#x20;

### 如何在目标链上赎回我的代币？&#x20;

如果您在跨链过程中不小心刷新了页面，或者没有赎回您的代币，您可以按照[此处](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow/)的教程进行操作。
