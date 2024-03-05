# Aptos 常见问题解答

<figure><img src="../../.gitbook/assets/Aptos-faq-header.png" alt=""><figcaption></figcaption></figure>

此常见问题解答页面回答了来自于 PancakeSwap 社区对于 Aptos 部署的一些常见的问题。

## 常见问题

### 如何将资产从 BSC（币安智能链）跨链到 Aptos？&#x20;

请查看我们的[跨链指南](huo-qu-aptos-dai-bi.md)，了解各种跨链解决方案。&#x20;

如果您想要跨链 CAKE 代币，请查看 [CAKE 跨链指南](broken-reference)以获取更多讯息。

### 我应该在Aptos链上使用哪个钱包？&#x20;

查看我们的[创建钱包指南](chuang-jian-qian-bao.md)，下载并设置您的 Aptos 钱包。&#x20;

### 兑换代币时显示“Price Impact Too High”&#x20;

这可能是由于与区块链节点的网络连接不良。请尝试刷新页面，并检查您的网络连接。&#x20;

如果该错误提示仍然存在，则意味着您尝试兑换的代币对对于您尝试兑换的金额而言没有足够的流动性。随着时间的推移，一些主要代币的流动性将逐步而稳定得到改善，当我们的 Aptos 农场部署时，流动性不足的问题应该会得到解决。 （即将到来！）

### 我找不到我想要兑换的代币&#x20;

Aptos Swap 上的默认列表仅显示来自知名项目且具有足够流动性的代币。&#x20;

如果您想兑换不在默认列表中的其他代币，请输入它们的代币合约地址导入它们。&#x20;

### 为什么我不能在 Aptos Swap 上交易 CAKE？&#x20;

更新于 2022-12-13&#x20;

CAKE 代币现已在 Aptos 上线。查看我们的 CAKE 跨链指南，了解更多关于在 Aptos 和 BNB 智能链之间跨链 CAKE 代币的讯息。

### 我是否需要在 Aptos 上质押 CAKE 才能参与 Aptos 链上的 IFO？&#x20;

PancakeSwap IFO 尚未在 Aptos 上部署。（即将到来！）请继续质押您的 CAKE 代币，并持续关注更多新消息。

## CAKE 跨链相关问题

### 为什么弹出的窗口和进度条都显示很长的等待时间？

请注意，对于 CAKE 以外的资产，从 Aptos 向外跨链要经过 50 万个区块的确认，估计要持续大约 2 天时间。这个时间可能会因为区块时间的波动而改变。

#### 对于 CAKE 的跨链，等待时间应该为大约 3-10 分钟。

### 我可以使用移动端钱包来进行 CAKE 的跨链吗？我可以使用 MetaMask 以外的钱包吗？

截止写此篇文章时，PancakeSwap Aptos 跨链桥只在桌面浏览器上支持 MetaMask（以及任何与 MetaMask 兼容的钱包）。之后将会支持更多的钱包。

为了尽量避免在你的设备之间复制和粘贴私钥或助记词带来的潜在风险。我们建议在桌面钱包扩展程序上创建一组新的钱包进行跨链。

### 为什么按钮上显示 "X CAKE Exceeded"？&#x20;

为了安全起见，BSC 和 Aptos 之间每天可以跨链多少 CAKE 是有容量限制的。如果遇到这个问题，请减少 CAKE 的数量再次尝试，或者换一个时间之后再试。&#x20;

大厨们会根据需求动态调整这个限制。

### 如果交易卡在 "Pending 待处理 "状态该怎么办？&#x20;

跨链交易将需要 30 分钟的时间来处理。请耐心等待，您可以在 [LayerZero scan](https://layerzeroscan.com/) 中输入交易的哈希值/ID 来搜索。&#x20;

如果 60 分钟后，跨链交易仍然显示为待处理。请通过我们的[社交渠道/群组](../../sheng-tai-xi-tong-he-zuo-huo-ban-guan-xi/contact-us/telegram.md)联系我们的管理员[寻求帮助](../click-here-for-help/)。&#x20;

请注意，对于 CAKE 以外的资产，从 Aptos 向外跨链要经过 50 万个区块的确认，估计会持续大约 2 天。这个时间可能会因为区块时间的波动而改变。

### 跨链操作后我一直没有收到我的 CAKE，怎么回事？&#x20;

跨链交易将需要 30 分钟的时间来处理。请耐心等待，您可以在 [LayerZero scan](https://layerzeroscan.com/) 中输入交易的哈希值/ID 来搜索。&#x20;

当第一次将 CAKE 跨链到 Aptos 时，您必须手动领取您的 CAKE。请确保您已经启用了 "Gas on destination （目的地支付 gas）" ，并且您的 Aptos 地址有足够的 APT 用于支付 gas。请查看此[指南](broken-reference)，了解跨链的详细步骤。&#x20;

将 CAKE 跨链到 BNB智能链时，针对部分钱包，您需要手动添加 CAKE 代币合约地址到钱包，才能够检查其余额。

如果您在跨链操作60分钟后还没有收到您的 CAKE，请通过我们的[社交渠道/群组](../../sheng-tai-xi-tong-he-zuo-huo-ban-guan-xi/contact-us/telegram.md)联系我们的管理员[寻求帮助](../click-here-for-help/)。&#x20;

### 为什么我不能跨链数量小于 0.00000001 的 CAKE？&#x20;

Aptos 上的代币最大小数点位数为8位，这也适用于 Aptos 上的 CAKE 代币。因此，当您将 CAKE 跨链到 Aptos 时，总数量小于 0.00000001 的链上交易将被拒绝。

如果您跨链的 CAKE 数量的小数点位数大于8位，任何小于0.00000001 部分的数量将被四舍五入，忽略不计并且不会进行跨链。未跨链的部分数量将留在您的 BNB 智能链钱包里。
