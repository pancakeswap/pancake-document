# EVM 链与 Aptos 之间跨链

<figure><img src="../../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
下方的指南将以 BNB 链为 EVM 链跨链的例子。同样的步骤可以通用于以太链。
{% endhint %}

## 将 CAKE 从 BNB 智能链 跨链到 Aptos 上

1 - 确保你的钱包同时支持 BNB 智能链和 Aptos 主网。或者你需在电脑浏览器中分别安装支持这两个链的钱包插件。

然后打开 [PancakeSwap CAKE 跨链桥](https://bridge.pancakeswap.finance/)。

2 - 首先，我们需要连接我们的 BNB 智能链钱包。

点击 "Connect 连接"，在 "EVM" 那栏选择你的钱包。然后在你的钱包弹出窗口确认并批准（approve）。(目前只支持 MetaMask。之后将会逐步支持更多的钱包。)

<figure><img src="../../.gitbook/assets/bridging-wallet-connect-modal (1).png" alt=""><figcaption></figcaption></figure>

3 - 然后，我们需要连接我们的 Aptos 钱包。在钱包连接模式中，在 "Aptos" 栏选择你的钱包。然后在你的钱包弹出窗口中确认并批准（approve）。

<figure><img src="../../.gitbook/assets/跨链 1 (2).png" alt=""><figcaption></figcaption></figure>

4 - 点击上面 Token 符号选择栏中的 "v"，选择 "CAKE"。

<figure><img src="../../.gitbook/assets/跨链 2.png" alt=""><figcaption></figcaption></figure>

5 - 输入你想要跨链到 Aptos 的 CAKE 数量。

<figure><img src="../../.gitbook/assets/跨链 3.png" alt=""><figcaption></figcaption></figure>

6 - 如果你的 Aptos 钱包是新创建的，并且没有任何 APT（Aptos 代币）余额。我们建议将 "gas on destination" 选项维持在默认状态。跨链桥将向你的钱包中存入少量 APT，不仅是为了帮助开启你的Aptos 链上之旅，而且你还需要 APT 作为 gas 来注册和领取跨链后的 CAKE。

修改这个选项可能会导致跨链失败。

<figure><img src="../../.gitbook/assets/跨链 4.png" alt=""><figcaption><p>.</p></figcaption></figure>

7 - 通过点击 "Transfer (转移)" 来发起跨链操作，在钱包弹出的窗口中确认此链上操作。

请注意，根据你的 BNB 智能链钱包和 Aptos 钱包的实际情况。你可能需要点击**多个**从钱包中弹出的确认。例如，如果你是第一次将 CAKE 跨链到 Aptos，你将需要：

* 授权 CAKE 在跨链合约上的输出（来自你的 BNB 智能链钱包）。&#x20;
* 注册 CAKE（来自你的 Aptos 钱包）&#x20;

了解更多细节，请查看[此处说明](evm-lian-yu-aptos-zhi-jian-kua-lian.md#shou-ci-jiang-cake-kua-lian-dao-aptos-lian-xu-yao-zhu-yi-de)。

8 - 现在只需要放松等待。CAKE 的跨链应该只需要几分钟时间。一旦跨链完成，CAKE 将被存入你的Aptos 钱包。你可以通过进度条追踪进度。

<figure><img src="../../.gitbook/assets/跨链 5.png" alt=""><figcaption></figcaption></figure>

## 首次将 CAKE 跨链到 Aptos 链需要注意的

将 CAKE 跨链至 Aptos 后，Aptos 钱包需要进行注册和领取的链上操作。这样做是为了强化用户安全性，也是 Aptos 独有的。&#x20;

### 如果你的钱包里已经有 APT（Aptos 代币）&#x20;

在这种情况下，如果尚未注册 CAKE，你将会被提示需要在你的 Aptos 钱包上进行注册。通常你不会被要求要提交一个额外领取（claim）的链上操作。

### 如果你的钱包中没有 APT（Aptos 代币）&#x20;

你只需要跨链完成后领取你的 CAKE。你将在 Aptos 钱包上收到 APT 代币（作为 gas 费），以支付领取其资产的费用。这些 APT 是由你的发送端钱包支付的，并转移到接收端钱包。&#x20;

记住，以上注册和领取要求只适用于你与代币第一次交互时。同一代币的后续转移将不再需要这些链上操作。

## 将CAKE 从 Aptos 链 跨链到 BNB 智能链

1 - 确保你的钱包同时支持 BNB 智能链和 Aptos 主网。或者你需在电脑浏览器中安装分别支持两个链的钱包插件。

然后打开 [PancakeSwap CAKE 跨链桥](https://bridge.pancakeswap.finance/)。

2 - 首先，我们需要连接我们的 BNB 智能链钱包。

点击 "Connect 连接"，在 "EVM" 那栏选择你的钱包。然后在你的钱包弹出窗口确认并批准（approve）。(目前只支持 MetaMask。之后将会逐步支持更多的钱包。)

<figure><img src="../../.gitbook/assets/bridging-wallet-connect-modal (1).png" alt=""><figcaption></figcaption></figure>

3 - 然后，我们需要连接我们的 Aptos 钱包。在钱包连接模式中，在 "Aptos" 栏选择你喜欢的钱包。然后在你的钱包弹出窗口中确认和批准（approve）。

<figure><img src="../../.gitbook/assets/aptos -bsc 2.png" alt=""><figcaption></figcaption></figure>

4 - 点击上面 Token 符号选择栏中的 "v"，选择 "CAKE"。然后点击中间的双向箭头按钮来转换跨链方向。

注意确保 Aptos 链在上方。

<figure><img src="../../.gitbook/assets/aptos -bsc 3.png" alt=""><figcaption></figcaption></figure>

5 - 输入你想要跨链到 BNB 智能链的 CAKE 数量。

<figure><img src="../../.gitbook/assets/aptos -bsc 4.png" alt=""><figcaption></figcaption></figure>

6 - 如果你的 BNB 智能链钱包是新创建的，并且没有任何 BNB（gas代币）余额。我们建议将 "gas on destination" 选项维持在默认状态。跨链桥将会把少量的 BNB 存入你的钱包。它将帮助开启你在 BNB 智能链上的旅程，探索生动的 PancakeSwap 生态系统。

7 - 点击 "Transfer 转移"，确认你的钱包中弹出的上链请求。

8 - 现在只需要放松等待。CAKE 的跨链应该只需要几分钟时间。一旦跨链完成，CAKE 将被存入你的 BNB 智能链钱包。你可以通过进度条追踪进度。
