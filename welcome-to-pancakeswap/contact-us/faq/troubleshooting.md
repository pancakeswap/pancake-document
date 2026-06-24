---
description: 常见的错误消息。使用侧边栏 ➡️ 跳转到你看到的错误。
---

# 故障排查错误

![](../../../.gitbook/assets/troubleshooting-header.png)

有时你可能会发现自己面临一个没有明确解决方案的问题。这些故障排查技巧或许能帮助你解决遇到的问题。

## **交易所上的问题**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

你正在尝试兑换代币，但你的滑点容差太低或流动性太低。

{% tabs %}
{% tab title="解决方案" %}
1. 刷新你的页面，稍后再试。
2. 尝试一次交易较小的金额。
3. 提高你的滑点容差：
   1. 点击流动性页面上的设置图标。
   2. 稍微提高你的滑点容差，然后重试。 ![](<../../../.gitbook/assets/image (9) (4).png>)
4. 最后，尝试输入一个小数位较少的金额。
{% endtab %}

{% tab title="原因" %}
**这通常发生在交易流动性较低的代币时。**

这意味着流动性池中你试图兑换的某种代币数量不足：它很可能是一种交易者很少的小市值代币。

然而，也有可能是你试图交易一种无法出售的诈骗代币。在这种情况下，PancakeSwap 无法屏蔽代币或返还资金。
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT 或 INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

你正在尝试向流动性池 (LP) 添加/移除流动性，但交易对中两种代币之一的数量不足。

{% tabs %}
{% tab title="解决方案" %}
**刷新你的页面并重试，或稍后再试。**

仍然不起作用？

1. 点击流动性页面上的设置图标。
2. 稍微提高你的滑点容差，然后重试。

![](<../../../.gitbook/assets/image (9) (4).png>)
{% endtab %}

{% tab title="原因" %}
此错误是由于试图为流动性池 (LP) 添加或移除流动性时，代币 A 或代币 B（交易对中的某种代币）的数量不足所致。

可能是价格更新得太快，而你的滑点容差又太低。

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="技术达人解决方案" %}
好吧，看来你真的下定决心要修复这个问题。除非你清楚自己在做什么，否则我们真的不建议这样做。

目前没有简单的方法可以从 PancakeSwap 网站上解决这个问题：你需要直接与合约交互。你可以通过 Router 合约直接添加流动性，同时将 amountAMin 设置为一个很小的数额，然后提取所有流动性。

**授权 LP 合约**

前往你试图授权的 LP 代币的合约。\
例如，这是 ETH/WBNB 交易对：[https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. 选择 **Write Contract**，然后点击 **Connect to Web3** 并连接你的钱包。 ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. 在 **section "1. approve"** 中，通过输入以下内容为 router 授权 LP 代币
   1. spender (address)：输入你试图交互的 LP 代币的合约地址
   2. value (uint256)：-1

**查询 "balanceOf"**

1. 切换到 **Read Contract.**
2. 在 **5. balanceOf** 中，输入你的钱包地址并点击 **Query**。
3. 记录下导出的数字。它以 uint256 格式显示你在 LP 中的余额，这是你下一步需要用到的。

![](<../../../.gitbook/assets/image (74).png>)

**添加或移除流动性**

前往 router 合约：[https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. 如上所述，选择 **Write Contract** 和 **Connect to Web3**。
2. 找到 **addLiquidity** 或 **removeLiquidity**（取决于你想要执行哪一个）
3. 输入 LP 中两种代币的代币地址。
4. 在 **liquidity (uint256)** 中，输入你从上面 "balanceOf" 获得的 uint256 数字。
5. 设置一个较低的 **amountAMin** 或 **amountBMin**：两者都尝试设为 1。
6. 在 **to (address)** 中添加你的钱包地址。
7. Deadline 必须是一个大于交易执行时间的纪元时间。

![](<../../../.gitbook/assets/image (136).png>)

{% hint style="warning" %}
这可能会导致非常高的滑点，并且如果被抢先交易，可能会导致用户损失一些资金
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

重试，但在生成交易后立即确认（签名并广播）该交易。

发生这种情况是因为你开始进行一笔交易，但直到超过截止时间才签名并广播它。这意味着你没有足够快地点击“Confirm”。

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

尝试修改“To”字段中的金额。这样会在“From”上出现“(estimated)”符号。然后立即发起兑换。

![](<../../../.gitbook/assets/Pancake-K-Solution (2).png>)

这通常发生在你尝试兑换一种带有自身手续费的代币时。

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

确保你钱包中的代币比你打算交易的数量多出 30%，或者尝试交易较低的金额。如果你想尽可能卖出最大数量，尝试使用 70% 或 69% 而不是 100%。\
此问题由 tDoge 或 tBTC 等修复性 Rebase 代币的设计所致。\
[了解修复性 rebase 代币的工作原理](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)。

此问题的另一个可能原因是恶意的代币发行者刚刚暂停了其代币的交易。或者他们只允许选定的钱包地址进行出售操作。请始终做好你自己的研究，以避免任何潜在的欺诈。如果你尝试兑换但出现此错误代码的代币来自空投，那很可能是一个骗局。请不要执行任何代币授权或点击任何链接，如果你这样做，你的资金可能会面临风险。

### 交易无法成功

尝试交易较小的金额，或通过设置图标提高滑点容差，然后重试。这是由流动性低所致。

### **价格影响过高**

尝试交易较小的金额，或通过设置图标提高滑点容差，然后重试。这是由流动性低所致。

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="解决方案" %}
**如果你在从 BNB 交易对中移除流动性时遇到此错误：**

请选择“Receive WBNB”并重试。

**如果你在尝试兑换时遇到此错误：**

请联系你试图兑换的代币的项目团队。\*\*\*\* 此问题必须由项目团队解决。
{% endtab %}

{% tab title="原因" %}
**此问题（在兑换时发生）是由那些将 V1 PancakeSwap router 硬编码进其合约的代币所导致的。**

虽然这种做法充其量也是不明智的，但这些项目这样做的原因似乎是由于其代币经济学，即每次购买都会将一定百分比的代币发送给 LP。

受影响的项目很可能无法使用 V2 router：它们很可能需要创建指向我们新 router 地址的代币新版本，并将任何现有的代币持有者迁移到他们的新代币上。

我们建议任何创建了此类代币的项目也应努力防止其用户将它们添加到 V2 LP。

最新的 router 地址是 [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

在尝试兑换代币时，交易失败并显示此错误消息。此错误已在使用 Trust Wallet 的移动设备上被报告。

{% tabs %}
{% tab title="解决方案" %}
1. 提高滑点限额后再次尝试该交易。
2. 如果第 1 步未能解决你的问题，考虑使用其他钱包（如 SafePal）进行你的交易。
{% endtab %}

{% tab title="原因" %}
**这通常发生在 Trust Wallet 上交易滑点限额不足的代币时。**

该问题的确切细节仍在调查中。
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

在尝试兑换代币时，交易失败并显示此错误消息。此错误已在各个平台上被报告。

{% tabs %}
{% tab title="解决方案" %}
1. 检查以确保你有足够的可用资金。
2. 确保你已授予合约花费你试图交易的资金数额的限额。
{% endtab %}

{% tab title="原因" %}
此错误发生在交易限额不足的代币时，或者钱包资金不足时。\
如果你正在交易带有修复性 Rebase 的代币，如 tau 资产 tDoge 或 tBTC，请务必先通过这份 [Rebase 代币指南](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)了解它们的工作原理。
{% endtab %}
{% endtabs %}

## **农场相关问题**

### Fail with error 'ds-math-sub-underflow'

你的 LP 代币对 MasterChef 合约的授权额度已用完。

**使用诸如 unrekt 或 BscScan 之类的代币授权管理工具来**

## **糖浆池相关问题**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

你钱包中没有足够的 SYRUP 来从 CAKE-CAKE 池中解除质押。

**获取至少与你试图解除质押的 CAKE 数量相等的 SYRUP。**

1. 在交易所购买 SYRUP。如果你想解除质押 100 CAKE，你至少需要 100 SYRUP。
2. 再次尝试解除质押。

如果仍然失败，你可以直接从合约执行“emergencyWithdraw”来解除质押你已质押的代币。

1. 前往：[https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. 点击 **“Connect to Web3”** 并连接你的钱包。 ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. 在 **“4. emergencyWithdraw”** 部分中，输入 "0" 并点击 “Write”。

这将解除质押你已质押的代币，并失去任何未领取的 CAKE 收益。

{% hint style="warning" %}
**这将失去你尚未收割的任何收益。**
{% endhint %}

为了防止这种情况再次发生，**请不要出售你的 SYRUP。**你仍然需要它来从“Stake CAKE Earn CAKE”池中解除质押。

发生此错误是因为你出售或转移了 SYRUP 代币。当你在 CAKE-CAKE 糖浆池中质押时，SYRUP 会以 1:1 的比例铸造给 CAKE。在调用 leaveStaking（从池中解除质押你的 CAKE）时，SYRUP 必须以 1:1 的比例对应 CAKE 被销毁，所以如果你没有足够的 SYRUP，你就无法从池中解除质押。

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]

你在尝试进行交易时设置了过低的 gas 上限。

{% tabs %}
{% tab title="解决方案" %}
在签署交易之前，尝试在你的钱包中手动提高 **gas 上限**（不是 gas 价格！）。

200000 的上限通常就足够了。

![](<../../../.gitbook/assets/image (21).png>)

上面的示例来自 Metamask；如果你不确定如何调整 gas 上限，请查看你钱包的文档。
{% endtab %}

{% tab title="原因" %}
基本上，你的钱包（Metamask、Trust Wallet 等）无法完成它试图执行的操作。

你的钱包估算的 gas 上限太低，所以在函数调用完成之前，gas 就耗尽了。
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="解决方案" %}
1. 使用 Unrekt.net 撤销对你试图交互的智能合约的授权
2. 再次授权该合约，不要对花费限额设置上限
3. 再次尝试与合约交互。
{% endtab %}

{% tab title="原因" %}
当你首次授权合约时对你的花费限额设置了上限，然后又试图兑换超过该上限的数量时，就会发生这种情况。
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

你可能正在尝试从一个奖励较少的糖浆池中解除质押。解决方案如下。

如果不是，你可能正在尝试发送你钱包中没有的代币（例如，尝试发送一个已分配给待处理交易的代币）。在这种情况下，只需确保你拥有你试图使用的代币即可。

{% tabs %}
{% tab title="解决方案" %}
首先，[告知团队](../social-accounts.md)你试图从哪个池中解除质押，以便他们补充奖励。如果你急于解除质押，并且不介意损失你的待领取收益，可以尝试 emergencyWithdraw：

你可以直接从合约执行“emergencyWithdraw”来解除质押你已质押的代币。

1. 找到你试图解除质押的糖浆池的合约地址。你可以在你钱包的交易记录中找到它。
2. 前往 [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)，并在搜索栏中输入合约地址。
3. 选择 **Write Contract.**
4. 点击 **“Connect to Web3”** 并连接你的钱包。![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. 在 **“3. emergencyWithdraw”** 部分，点击 “Write”。

这将解除质押你已质押的代币，并失去任何未领取的收益。

{% hint style="warning" %}
**这将失去你尚未收割的任何收益。**
{% endhint %}
{% endtab %}

{% tab title="原因" %}
当你试图从一个旧的糖浆池中解除质押时，往往会出现此错误，但池中剩余的奖励不足以让你在提取时收割。这会导致交易失败。
{% endtab %}
{% endtabs %}

## **预测相关问题**

查看 [Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **其他问题**

### Provider Error

> Provider Error\
> No provider was found

当你尝试通过 MetaMask 或 Binance Chain Wallet 等浏览器扩展程序连接，但你尚未安装该扩展程序时，就会发生这种情况。

{% tabs %}
{% tab title="解决方案" %}
安装官方浏览器扩展程序进行连接，或阅读我们关于[如何将钱包连接到 PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide) 的指南。
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

将你的链切换到 BNB Smart Chain。如果你需要帮助，请查看你钱包的文档以获取指南。

### Already processing eth\_requestAccounts. Please wait.

确保你已登录你的钱包应用程序，并且它已连接到 BNB Smart Chain。

### 购买 SAFEMOON 及类似代币的问题

要交易 SAFEMOON，你必须点击设置图标并**将你的滑点容差设置为 12% 或更高。**\
这是因为 **SafeMoon 对每笔交易征收 10% 的费用**：

* 5% 费用 = 重新分配给所有现有持有者
* 5% 费用 = 用于添加流动性

这也是为什么你在购买时可能不会收到你预期那么多代币的原因。\
在[如何购买 Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742) 上阅读更多内容。

### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

在尝试通过 Metamask 移除某些代币的流动性时发生。根本原因仍然未知。尝试使用其他钱包。

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

你没有足够的 BNB 来支付交易费用。你的钱包中需要更多的 BEP-20 网络 BNB。

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

在你的钱包中提高交易的 gas 上限。查看你钱包的文档，了解如何提高 gas 上限。

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

原因不明。在重试之前尝试以下步骤：

1. 提高 gas 上限
2. 提高滑点
3. 清除缓存

## **个人资料相关问题**

### Oops! We couldn't find any Pancake Collectibles in your wallet.

我们正在调查此问题背后的逻辑。与此同时，请尝试变通方法。

{% tabs %}
{% tab title="变通方法 1" %}
1. 前往“Collectible”页面，然后返回个人资料页面。\
   如果你找不到链接，请直接前往 [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles)。
2. 重试创建个人资料。
{% endtab %}

{% tab title="变通方法 2" %}
更换环境。

* 清除缓存并重试。
* 在不同的浏览器上重试。
* 在不同的钱包应用程序上重试。
* 在不同的网络上重试（在 Wi-Fi 和蜂窝网络之间切换）
{% endtab %}
{% endtabs %}

### 检查用户名时一直转圈

有两个可能的原因。

1. 你的浏览器上安装了多个钱包。
2. 网络问题。

{% tabs %}
{% tab title="解决方案 1" %}
根本原因：你的浏览器上安装了多个钱包。\
\
这可能会造成钱包之间的冲突。这超出了 PancakeSwap 的控制范围，我们对此无能为力。

1. 浏览器上只安装单个钱包，移除其他的。
2. 重新连接钱包并再次重试设置用户名。
{% endtab %}

{% tab title="解决方案 2" %}
根本原因：网络不稳定。

你必须重试。

1. 完全删除文本字段中输入的所有内容。
2. 重新输入用户名，然后请等待几秒钟。
3. 如果它不起作用，重新加载页面并再次重试。
{% endtab %}
{% endtabs %}
