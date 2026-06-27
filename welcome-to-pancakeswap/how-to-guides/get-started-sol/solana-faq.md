# Solana 常见问题解答

### V3 池——常见问题解答 (FAQ)

#### 1. 有哪些费率档位可用？

**支持的费率档位：**\
以下费率档位适用于 V3（集中流动性）池：

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**费用分配（适用于所有费率档位）：**

* 84% 给流动性提供者 (LP)
* 16% 给协议
  * 8% 被销毁
  * 8% 进入协议金库

#### 2. 任何人都可以创建池吗？

可以。池的创建是无需许可的，但有几个例外：

* 对于给定的**代币对 + 费率档位**组合，只能存在一个池（例如，同一时间只能存在一个 SOL<> USDC 0.1% 池）
* 目前仅支持 **SPL 代币**和精选的 **Token-2022** 代币。

#### 3. 新创建的池需要多长时间才能显示出来？

* 池通常在创建后约 **5 分钟**出现在池列表中。
* 如果它没有出现：
  * 使用**搜索栏**手动查找它。
  * 池可能因 **TVL 过低**而被从列表中过滤掉。

#### 4. 为什么我的池的 APR 或 TVL 仍然显示为零？

这在新池刚创建后是正常现象：

* APR 和 TVL 数据只有在池中发生**至少一次兑换**后才会填充。
* 兑换后，这些指标将在大约 **15 分钟**内开始显示。

#### 5. 如何添加自定义代币来创建池？

要添加新代币：

* 在池创建界面中，打开代币选择器。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* 将代币的地址粘贴到搜索栏中。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* 点击 **"Add Token"**。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* 该代币现在将可在列表中搜索到。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* 要管理代币：
  * 点击 **"View Token List"**。
  *   开启或关闭不同的列表，包括 **User Added Token List**（用户添加的代币列表），其中包含任何手动添加的代币。

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. 为什么我在 Solana 上的第一笔交易似乎更贵？

Solana 使用**关联代币账户 (ATA)** 来管理每个钱包的代币余额。当你首次与某个代币交互时，你的钱包必须创建一个 ATA，这会产生一次性的初始成本（以 SOL 支付）。

* 此 ATA 创建费用是 Solana 协议所要求的，并非 PancakeSwap 特有。
* 如果 ATA 后来被关闭，**所使用的原始 SOL 可以退还**回你的钱包。
