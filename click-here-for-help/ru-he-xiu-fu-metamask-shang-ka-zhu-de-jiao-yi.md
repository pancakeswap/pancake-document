---
description: 如何在 MetaMask 上「清理」卡住的交易
---

# 如何修复 MetaMask 上卡住的交易

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbGTDNZ6xd3_Q-qSEP5%2F-MbJqpp1p79V-5V3Lv1m%2Fdocs%20masthead%20%2812%29.png?alt=media&token=760ddc2a-1dd9-46ab-8a2f-a2ca54a29043)

如果您在 MetaMask 上的交易卡在了「等待中」，并且无法通过「取消」按钮清除，请根据该教程清除您的钱包交易记录。

这个方法将使用一个优先级更高的交易去覆盖卡住的交易。

### **1. 启用「**自定义交易 nonce**」**  <a id="1-enable-customized-transaction-nonce"></a>

1. 打开您的 MetaMask 插件。 ![](https://lh6.googleusercontent.com/fYsgD0BKjYVjrbCpbEQgMyWG_sW-4c2Ev7wu9bVzsOWtqIzCmYqiv6Xj8G_FY2TK5uYul3XaOY2WflfcW1W56R2KCuyW-Y5RjHH9DZDgUmATLlnOnMPn371nniPZqaaD7KAgYgMc)
2. 点击右上角彩色头像，并在菜单中点击**设置**。 ![](https://lh3.googleusercontent.com/DpSeFrHsmPNXU73C3NB9iRANEe81rJ2XUhbxs6k7PqJSVy6IkAijeX_TeIbUupalmD3mlE2G0C90XHJJy_JPk-_mswNRf4liUwR4AUhx2AWygp4yIP9kjHo1QQk_60wEtjGkfwSk)
3. 在菜单中，选择**高级** .![](https://lh4.googleusercontent.com/F-o1qfi84wh6YNUP16b8lbyS6f8i04SYEUR2VrncMbBaoeaAjOw4Af_oOwRUfWnhZn6NFb4O1uopoc1KNego8XelHmDDWeRRAb0oMJGE_ZI_xJJeqfH-bJrai0pakyxC-235E4nq)
4. 滚动至 **高级燃料控制**，点击启用它。 ![](https://lh5.googleusercontent.com/ePraz_2Z8k1V62DMROjv0jbIjEcf8ATvaH-Lxe5wtoNo6oVTyRPelC1m7UVaizcNpW5bHByrbC9xv1KDZfjNnXvQ8J0ukHUHK7vK4rX5gpQVHmfyJr81wCGdeArvksNhshon1Btn)
5. 不要离开，继续往下滚动，直至 **自定义交易 nonce** ，点击启用它。

### **2. 找到卡住的交易** <a id="2-find-your-stuck-transaction"></a>

1. 我们现在要找到卡住的交易，并记录它的 "nonce"。它是该交易的标识号吗，我们之后将会用到。 ![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)
2. 回到最初的页面，在「资产」选项卡处，找到「活动」并点击。之后，在下方找到卡住的交易。 ![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)
3. 点击卡住的交易，查看更多信息。 ![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)
4. 找到 **Nonce** 一栏，并记录数值。

### **3. 覆盖卡住的交易** <a id="3-overwrite-the-stuck-transaction"></a>

现在我们要发起一个新的交易去覆盖之前卡住的交易。我们将自定义 Nonce 值，让它与卡住的交易一致。（即您刚刚记录的数值）  
![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M_Qf9PqrqKwKENMLChq%2F-M_QfJwbI-p6skTud7_o%2Fimage.png?alt=media&token=13db2345-9ad7-46a4-9937-7f26d7187749)

1. 新建一个新的交易去覆盖之前的交易，它可以是任何交易（您也可以自己转账给自己）。这次，将 **燃料价格** \(Gas Price\) 增加至 20。这将大幅度增加该笔交易上链的几率和速度。 ![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M_Qf9PqrqKwKENMLChq%2F-M_Qft-wFWL0NENZfvV_%2Fimage.png?alt=media&token=14028feb-3c51-405c-bc3e-3d8e87d1d37d)
2. 在确认页面，请确认燃料价格 \(Gas Price\) 被设置为 20。
3. 找到 **自定义 NONCE** 一栏，并将它的值改为之前记录的数值。
4. 点击确认。 ![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)
5. 新的交易将被纳入区块并覆盖之前的交易，请回到「活动」页面检查。 ![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)
6. 新的交易将显示在最上方，如果仍显示橙色的「等待中」，请稍等片刻，或使用更高的 Gas Price 重试。

每笔交易的 nonce 值都应为独一无二。所以，您新的交易将覆盖旧的、卡住的交易。

