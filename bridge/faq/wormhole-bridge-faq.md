---
hidden: true
---

# Wormhole 跨链桥常见问题解答

### Q: 我如何查看我的交易？ <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole 浏览器

在跨链桥状态页面上。你可以看到一个链接，它会带你前往 Wormhole Explorer 上查看你的交易。当你的源链交易已完成但尚未被 Wormhole 验证时，你的交易状态将如下所示：

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

查找赎回（find redeem）选项是你可以遵循的另一种方法，用于完成你的目标链交易。在 Wormhole 跨链桥停滞或未能更新你的跨链交易状态的情况下，你可以使用此方法。要赎回你的交易，请先点击赎回（redeem）按钮

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

它随后将显示此选项以恢复你的交易。点击它即可导航至论坛（链接在下一个问题中），你可以在那里完成你的赎回交易。<br>

### Q: 我已向 \<chain> 发送代币 - 我的代币没有到达我的目标钱包，但已离开我的源钱包。我该怎么办？[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

你需要 a) 赎回它们，或者，如果赎回已经成功，b) 将它们添加到你的钱包：

**a) 赎回：**

* 前往 [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)
* 你需要输入你的源链和相应的交易 id（你可以在你的钱包中找到，或用你的地址在区块链浏览器中找到）

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* 点击 Recover（恢复）
* 点击 Redeem（赎回）并接受钱包批准

**b) 将它们添加到你的钱包：**

**Metamask：**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* 在 Metamask 资产选项卡中，点击 import tokens（导入代币）
* 合约地址可在相关的区块浏览器交易中找到，点击代币名称即可。当你点击代币名称时，它会打开一个新窗口，合约地址位于资料摘要的右侧。
* 你还需要一个符号 - 它可以是任何你想用来识别该代币的内容。
* 点击 add custom token（添加自定义代币）

观看视频教程 - 如何将代币添加到你的 Metamask 钱包，[请点击这里。](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### 我跨链转移了 X 代币，但现在无法兑换它。没有 DEX 拥有流动市场，[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

你跨链转移了一个在目标链上没有流动性的代币。你将需要使用 Portal 跨链桥将它跨链转回。你可以通过将代币合约地址（你可以在你的钱包中找到，或用你的地址在区块链浏览器中找到）粘贴到 Portal 的"select a token"（选择代币）搜索框中来完成此操作。

你可以在[这里](https://portalbridge.com/docs/faqs/liquid-markets)找到流动市场的全面概览。

#### 我如何在目标链上赎回我的代币？[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

如果你在转账过程中不小心刷新了页面，或者没有赎回你的代币，你可以遵循[这里](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow)的教程。
