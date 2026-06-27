---
description: 如何“解开”任何卡在你 MetaMask 中处于待处理状态的交易
---

# 修复 MetaMask 上卡住的待处理交易

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

如果你的交易卡在 Metamask 的待处理状态，并且“Cancel”按钮也没有帮助，你可能需要使用此方法来清除你的积压交易。

此方法的工作原理本质上是用另一笔更高优先级的交易来覆盖卡住的交易。

### **1. 启用自定义交易 Nonce**

1\. 打开你的 MetaMask 插件。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. 点击右上角彩色圆形图标，并从下拉菜单中点击 **Settings**。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. 在 Settings 菜单中，选择 **Advanced**。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. 向下滚动，直到你看到 **Advanced gas controls**。将其切换为 ON。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. 仍在 Advanced 设置中，继续滚动，直到你看到 **Customize transaction nonce**。将其切换为 ON。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. 找到你卡住的交易**

我们现在要找到卡住的那笔交易，并记下“nonce”。它是一种标识符，我们稍后会重新使用它。

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. 返回 MetaMask 的顶部页面。在“Assets”标签中，找到你卡住交易的代币类型（在本例中为 CAKE）。

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. 在该代币的菜单中，在 Queue 区域找到你的 **Pending** 交易。点击你的交易以查看更多详情。

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. 寻找 **Nonce** 条目，并记下这个数字。

### **3. 覆盖卡住的交易**

现在我们要创建一笔新交易来替换卡住的那笔。我们将自定义 Nonce 数字，使其与你刚刚记下的那个相同。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. 创建一笔新交易来替换你卡住的交易。这一次，提高 **Transaction Fee**。这里我们将它从 9 提高到了 20。这将使你的交易更有可能被添加到区块中。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. 在确认页面上，确保你的 Gas Price 现在是你新设定的更高金额。

10\. 找到 **CUSTOM NONCE** 条目，并将 nonce 更改为你在第 7 步中记下的数字。现在点击 Confirm。

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. 你的新交易现在应该被接受并加入到一个区块中。要进行检查，打开 MetaMask 并点击 **Activity** 标签。

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. 你已完成的交易应该显示在你 Activity 列表的顶部。如果它仍然以橙色显示“Pending”，你需要再等一会儿，或者用更高的交易费用（gas 价格）再次尝试此流程。

由于没有任何钱包能够创建两笔相同 nonce 的交易，如果你创建的替换交易成功了，你卡住的交易将会被取消。<br>
