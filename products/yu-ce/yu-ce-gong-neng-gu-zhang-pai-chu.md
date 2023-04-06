# 预测功能故障排除

{% hint style="info" %}
使用侧边快捷栏快速找到问题的答案！
{% endhint %}

### 为什么我的钱包里看不到我的奖金？&#x20;

当您收集奖金时，它们可能不会像往常一样出现在您钱包的交易日志中。这是因为他们使用了不同类型的交易：内部交易 (Internal transactions)。&#x20;

在 BscScan 上输入您的钱包地址，然后检查 “Internal Txns” 选项卡以确认您已经收到奖金。

<figure><img src="../../.gitbook/assets/pasted image 0 (1).png" alt=""><figcaption></figcaption></figure>

### 为什么我参与的回合没有显示结果？

每轮有 15 个区块缓冲区，这可能会在一轮结束后导致最长 45 秒的延迟。&#x20;

这个缓冲区考虑到一些状况，即我们可能无法准确及时地获取结束价格并立即结束一轮：各种区块链因素会影响交易在网络上得到确认的速度。&#x20;

### 我无法收集我的奖金！&#x20;

确保您的钱包中有足够的 BNB 来支付 gas 费。您需要一些 BNB 来触发智能合约。&#x20;

### 我无法在实时的预测回合中收集奖金&#x20;

您可以直接调用智能合约收集您的奖金，请按照以下 3 个选项卡中的步骤操作。

{% tabs %}
{% tab title="找到您投注的回合" %}
如何查看您投注的回合的历史记录&#x20;

1. 转到[预测合约的 BscScan 页面](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#writeContract)。&#x20;
2. 向下滚动到 “8. getUserRounds”。&#x20;
3. 在 “user(address)” 下方输入您的钱包地址。
4. 将 “cursor(uint256)” 设置为 0，将 “size(uint256)” 设置为 1000。&#x20;
5. 点击 “Query”&#x20;
6. 您投注的回合将显示在下方的第一行中（“int256\[]:”之后）
{% endtab %}

{% tab title="查看您是否可以领奖" %}
首先，检查您是否有资格领取已投注回合的奖励。&#x20;

1. 转到[预测合约的 BscScan 页面](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#writeContract)，然后转到写入选项卡&#x20;
2. 向下滚动到“4. claimable”。&#x20;
3. 在“epoch(uint256)”下输入要检查的轮次 ID。&#x20;
4. 在“user(address)”下输入您的钱包地址。&#x20;
5. 点击“Query”&#x20;
6. 如果有一轮预测是可领取的，它将显示“true”。&#x20;
7. 如果显示为“false”。 请重复上述步骤并尝试使用“19.refundable”。&#x20;
8. 注意：⬆️如果你看到一个在“4.claimable”和“19.refundable”上都显示为“false”，但它显示在网站前端上，可能是网站显示延迟的缘故实际上已经被领取了。
{% endtab %}

{% tab title="从过去的回合中收集您的奖金" %}
如何领取&#x20;

1. 转到[预测合约的 BscScan 页面](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#writeContract)，然后转到写入选项卡&#x20;
2. 点击“🔴 Connect to Web3””&#x20;
3. 使用 MetaMask 或 WalletConnect 进行连接。&#x20;
4. 向下滚动到“3. claim”&#x20;
5. 以这种格式输入您要领取的回合，包括 \[] 括号：\[12345]&#x20;
6. 如果您想从多个回合中一起领取，请用逗号分隔这些回合，如下所示：\[12345,12346,12347]&#x20;
7. 点击“Write”&#x20;
8. 在钱包上确认
{% endtab %}
{% endtabs %}
