---
description: 常见错误信息。 使用侧边栏快速查找您的错误代码 ➡️
---

# 故障排除指南

## **交易相关问题**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> \(交易由于此错误而无法成功：PancakeRouter：INSUFFICIENT\_OUTPUT\_AMOUNT。问题可能出自您正在兑换的其中一个代币\)

您正在尝试兑换代币，但您设置的滑点容限太低或您兑换的代币流动性太低。

{% tabs %}
{% tab title="解决方法" %}
1. 刷新页面，然后重试。
2. 尝试交易较小的金额。
3. 调高滑点容限：
   1. 点击兑换页面上的设置图标。
   2. 逐步调高滑点容限，然后重试。 ![](../.gitbook/assets/image%20%289%29%20%284%29%20%284%29.png)
4. 若还是不行，您可以尝试减少兑换金额的小数点位数。
{% endtab %}

{% tab title="原因" %}
**问题常见于尝试兑换流动性较低的代币时：**

换言之，您尝试兑换的代币，它的流动性池内有一个代币的数量不足以完成交易：有可能是因为该币的市值较低，或交易人数太少。

但是，您也有可能遇到无法出售的假币或诈骗币。 在这种情况下，PancakeSwap 无法封锁该代币或返还资金。
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'
>
> \(交易出现此错误导致失败: "PancakeRouter: A代币不足"\)
>
> 或
>
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'
>
> \(交易出现此错误导致失败: "PancakeRouter: B代币不足"\)

您正在尝试从流动性池\(LP\)添加或解除流动性，但是该交易对中的其中一个代币不足。

{% tabs %}
{% tab title="解决方法" %}
**刷新页面，然后重试，或稍后重试。**

还是不行？

1. 点击流动性页面上的设置图标。
2. 逐步调高滑点容限，然后重试。

![](../.gitbook/assets/image%20%289%29%20%284%29%20%284%29.png)
{% endtab %}

{% tab title="原因" %}
该错误是由于尝试添加或解除流动性但其交易对中的A代币或B代币数量不足而引起的。

其中一个可能的情况是，当您的滑点容限设置太低时，价格更新太快导致。

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)



![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="给学霸的解决方法" %}
好的，您或许坚决要解决此问题。但除非您知道自己在做什么，否则我们真的不建议您这样做。

PancakeSwap的网站目前没有解决此问题的简单方法：您需要直接调用智能合约。 您可以直接通过Router合约添加或解除流动性，同时将amountAMin或amountBMin设置为很小的数目。

### **批准并授权合约提取您的钱包里的LP代币**

浏览您要授权的LP代币合约地址。   
以下示范例子是ETH/WBNB对：[https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. 选择 “**Write Contract”** \(写入合约\)**，**然后点击 “**Connect to Web3”** \(连接至Web3\)以连接您的钱包。 ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. 在第一项**"1. approve"**，通过输入以下内容批准Router合约提取您的LP代币。输入完毕后点击 **Write** 按钮。
   1. spender \(address\): 输入Router合约地址
   2. value \(uint256\): -1

### 查询LP余额"balanceOf"

1. 选择 **“Read Contract”** \(读取合约\)
2. 在第五项 **"5. balanceOf"**，输入您的钱包地址然后点击 **Query** 按钮。
3. 记下显示的余额。这余额显示的格式是uint256。您的下一个步骤需要输入这余额。

![](../.gitbook/assets/image%20%2832%29.png)

### 添加或解除流动性

浏览以下Router合约网址: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f\#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. 跟之前一样，选择 **“Write Contract”** 然后点击 **“Connect to Web3”**。
2. 寻找 **addLiquidity** 或 **removeLiquidity** \(根据当下你想做的操作\)
3. 输入LP的两个代币地址，即代币A与代币B的合约地址。
4. 在 **“liquidity \(uint256\)”** 这一栏位，输入您从之前的步骤获得的uint256格式LP余额\(即"balanceOf"\)。
5. 设置低额的 **amountAMin** 或 **amountBMin**: 两个都尝试 “1” 这个值。
6. 在 **“to \(address\)”** 这一栏位输入您的钱包地址。
7. **Deadline** \(截止时间\)必须是大于执行此交易的纪元\(epoch\)时间。

![](../.gitbook/assets/image%20%2819%29.png)

{% hint style="warning" %}
这可能会导致很高的滑点，并且如果被机器人抢跑，可能会导致您损失一些资金。
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.
>
> \(交易由于此错误而无法成功: PancakeRouter: 逾期。 这可能是因为您正在兑换的一个代币存在某些问题\)

再试一次，但是在交易产生后立即确认\(即签名并往链上广播\)该交易。 

发生这种情况是因为您在交易产生后，没有足够快地点击“确认”按钮，而是等到期限过后才进行签名与链上广播。 

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.
>
> \(交易由于此错误而无法成功: Pancake: K。 这可能是因为您正在兑换的一个代币存在某些问题\)

刷新页面，然后重试，或者通过设置调高滑点容限，然后重试。

这问题的原因可能是因为您试图在价格大变动期间购买或出售代币。 前端从智能合约中获取过时的信息\(例如outAmount\)，从而导致兑换失败。

## **糖浆池相关问题**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'
>
> \(交易出现此错误导致失败: “BEP20: 销毁数量超出余额”\)

您的钱包中没有足够的SYRUP代币，无法从CAKE-CAKE池中解除质押以提出CAKE。

{% tabs %}
{% tab title="解决方法\(一\)" %}
**购买跟您想解除质押CAKE同等数量的SYRUP代币。**

1. 在交易所上购买SYRUP代币。如果您想对100个CAKE解除质押，您需要购买对应数量的100个SYRUP代币。
2. 再次尝试解除质押。
{% endtab %}

{% tab title="解决方法\(二\)" %}
如果还是失败，您可以直接调用合约的“紧急提取”\(emergencyWithdraw\)以对您质押着的代币解除质押。

1. 浏览以下网址: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E\#writeContract ](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20)
2. 点击 **“Connect to Web3”** \(连接至Web3\)以连接您的钱包。 ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. 在第4项：**“4. emergencyWithdraw”**，输入“0”，然后点击**Write**按钮。.

虽然紧急提取成功让您解除质押，但这也会导致您失去任何尚未收割的奖励代币\(即CAKE\)收益。

{% hint style="warning" %}
**紧急提出会导致您失去尚未收割的奖励代币。**
{% endhint %}
{% endtab %}

{% tab title="原因" %}
若想防止这种情况再次发生，**请不要出售您的SYRUP代币**。 您仍然需要SYRUP代币来帮您从“质押CAKE获取CAKE”池中解除质押。

发生此错误的原因是您已经出售或转让了您的SYRUP代币。 当您在CAKE-CAKE糖浆池中质押您的CAKE时，SYRUP会根据与CAKE数量“1:1”的比例铸造出来。 在调用leavesStaking\(即解除CAKE代币质押\)合约函数时，合约会销毁与CAKE数量“1:1”比例的SYRUP代币数量。因此，如果您没有足够的SYRUP代币，您就不能成功解除质押。

![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endtab %}
{% endtabs %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas\]
>
> \(警告！合约执行过程中遇到错误\[矿工费已用尽\]\)

您设置的**Gas Limit**\(矿工费限制/网络费用限制\)过低。

{% tabs %}
{% tab title="解决方法" %}
在点击交易确认前，手动调高**Gas限制**\(注意不是Gas价格!\)

一般而言，限制设为200000就很足够了。

![](../.gitbook/assets/image%20%28169%29.png)

以上的例子取自Metamask截图。 如果不确定如何设置Gas限制，请查看您钱包的文档。
{% endtab %}

{% tab title="原因" %}
基本上，您的钱包\(Metamask, Trust Wallet等\)无法完成其尝试执行的操作。

您的钱包所建议的Gas限制太低，因此在合约函数调用完成之前，矿工费已用尽。  
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'
>
> \(交易出现此错误导致失败: “BEP20: 转出数额超出余额”\)

您正试图从奖励代币不足的糖浆池中解除质押。

{% tabs %}
{% tab title="解决方法" %}
您可以直接调用合约的“紧急提取”\(emergencyWithdraw\)以对您质押着的代币解除质押。

1. 查找您要解除质押的糖浆池的合约地址。您可以在钱包的交易记录中找到该合约地址。
2. 浏览 [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20) 然后在搜索栏中输入合约地址。
3. 选择 **“Write Contract”**\(写入合约\)。
4. 点击 **"Connect to Web3"**\(连接Web3\)以便连接您的钱包。![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. 在第4项：**“4. emergencyWithdraw”**，输入“0”，然后点击**Write**按钮。

虽然紧急提取成功让您解除质押，但这也会导致您失去任何尚未收割的奖励代币收益。

{% hint style="warning" %}
**紧急提出会导致您失去尚未收割的奖励代币。**
{% endhint %}
{% endtab %}

{% tab title="原因" %}
当您尝试从已结束很久的糖浆池中解除质押时，一般会出现此错误。其原因是因为该池中没有足够的奖励代币供您收割。 这会导致解除质押操作失败。
{% endtab %}
{% endtabs %}

## \*\*\*\*

