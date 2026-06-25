# ❓ 跨链常见问题解答

<figure><img src="../../.gitbook/assets/image (144).png" alt=""><figcaption></figcaption></figure>

## 跨链之前

1.  **我可以使用移动端钱包或 MetaMask 以外的钱包来跨链转移 CAKE 吗？**

    目前，PancakeSwap CAKE 跨链支持 Coinbase Wallet、MetaMask 以及兼容 MetaMask 的钱包。更多钱包支持即将推出。

    _提示：_ 为避免有风险地复制粘贴私钥或助记词，我们建议通过桌面端钱包扩展程序创建新钱包来进行跨链。
2.  **为什么某条路由或某个代币不可用？**

    某些路由取决于跨链桥容量、代币支持情况或流动性。请稍后再试或尝试其他提供商。每条链上可用的代币会直接显示在跨链桥 UI 中。
3.  **我在提交跨链交易时遇到错误。**

    请尝试手动输入金额而不是使用"MAX"按钮，并在必要时去除金额中的小数。
4.  **为什么我的跨链报价显示"Insufficient X to cover native fee"（X 不足以支付原生费用）？**

    ![](<../../.gitbook/assets/image (9) (3).png>)

    跨链需要用源链的原生代币支付 gas 费，例如：

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    请确保你的源钱包中有足够的原生代币来支付费用以完成交易。
5.  **为什么按钮显示"X CAKE Exceeded"（X CAKE 已超额）？**

    为确保安全，在 BSC 与 Aptos 之间跨链转移 CAKE 存在每日容量限制。请尝试较小的金额，或稍后再试。限额由 Chefs 根据需求动态调整。
6.  **为什么我找不到某个特定的代币？**

    该代币可能在你所选的路由上不受支持，或者缺乏流动性。请尝试另一条链或不同的金额。
7.  **我可以从 BNB 链跨链到 Ethereum 但转到不同的地址吗？**

    不可以，出于安全原因，在 EVM 链之间跨链仅能在相同地址之间进行。
8.  **为什么我无法跨链少于 0.00000001 CAKE？**

    Aptos 代币，包括 Aptos 上的 CAKE，最多有 8 位小数。低于 0.00000001 的交易将被拒绝或向下取整。这同样适用于 Ethereum 跨链。任何剩余金额都会保留在你的源钱包中。

***

## 跨链之后

1.  **确认后我可以取消一笔跨链转账吗？**

    不可以，一旦开始，跨链交易便由提供商处理，无法取消。若要逆转，请通过一笔新交易将资产跨链转回。
2.  **如果我的交易卡在"pending"（待处理）状态怎么办？**

    跨链可能最多需要 30 分钟。可在相应跨链桥提供商的浏览器中搜索交易哈希以查看交易状态：

    * Debridge：[https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan：[https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer：[https://stargate.finance/](https://stargate.finance/)
    * cBridge：[https://celerscan.com/](https://celerscan.com/)

    如果 60 分钟后仍处于待处理状态，请通过[社交渠道](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)联系我们的管理员。
3. **我没有收到我的 CAKE。我该怎么办？**
   * 第一次将 CAKE 跨链至 Aptos 时，你可能需要**手动领取**你的 CAKE。请确保你的 Aptos 钱包有足够的 APT 用于支付 gas。请参阅 [Aptos 跨链指南](https://docs.pancakeswap.finance/bridge/bridging/aptos)和 [Aptos 说明](https://theaptosbridge.com/faq#registering-claiming-assets)。
   * 当跨链至 BNB 链或 Ethereum 时，某些钱包要求你手动添加 CAKE 的代币地址才能查看余额。例如，可参照此 [MetaMask 指南](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) - 其他钱包应有类似流程。
   * 如果 60 分钟后你仍未看到你的 CAKE，请通过[社交渠道](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)联系我们的管理员。
