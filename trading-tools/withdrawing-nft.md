# 🧙 Page 1

## 如何从 PancakeSwap NFT Marketplace 提取你的 NFT

PancakeSwap NFT Marketplace 页面已不再提供，但市场智能合约仍在运行。如果你挂单出售了某个 NFT 但一直没有售出，它仍由市场合约持有。你可以直接在 BscScan 上取消挂单，自行取回它。

每个 NFT 只需几分钟，仅需支付少量 BNB 作为 gas 费用。

### 开始之前

你需要：

* **你挂单该 NFT 时所用的同一个钱包。** 只有创建挂单的钱包才能取消它。
* **一个浏览器钱包**（例如 MetaMask、Trust Wallet 扩展或 Binance Wallet 扩展），并设置为 **BNB Smart Chain**。
* **少量 BNB** 用于支付 gas。每个 NFT 都通过单独的一笔交易提取。

请备好以下地址：

| 项目                       | 地址                                           |
| -------------------------- | -------------------------------------------- |
| 市场合约                   | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Pancake Squad 系列         | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Pancake Bunnies 系列       | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **注意安全**
>
> * 只与市场合约 `0x17539cCa21C7933Df5c980172d22659B8C345C5A` 交互。请务必检查 BscScan URL 中的地址。
> * 提取你的 NFT **绝不**需要发送 BNB 或代币，也绝不需要签署授权（`approve` 或 `setApprovalForAll`）。如果有网站或个人要求你这样做，那就是骗局。
> * PancakeSwap 绝不会私信你，也绝不会向你索要助记词。

### 第 1 步：找到你仍在挂单的 NFT

对于每个要提取的 NFT，你需要两项信息：**系列地址**和 **token ID**。

1. 在 BscScan 上打开市场合约的 [Read Contract 页面](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract)。
2. 找到并展开 **`viewAsksByCollectionAndSeller`**。
3. 填写各字段：
   * `collection`：上表中的系列地址（例如，Pancake Squad 为 `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`）
   * `seller`：你的钱包地址
   * `cursor`：`0`
   * `size`：`100`
4. 点击 **Query**。
5. 查看 `tokenIds` 结果。这些是你在该系列中仍在挂单的 token ID，也是你可以提取的 NFT。
6. 如果你在多个系列中挂过单，请对每个系列重复第 3 至 5 步。

**如果 `tokenIds` 为空（`[]`）**，说明你在该系列中没有有效挂单。你的 NFT 要么已售出（此时你已收到 BNB），要么你之前已取消挂单（此时它已回到你的钱包）。

**如果你在同一系列中有超过 100 个挂单**，结果中的最后一个数字是下一个 cursor。请使用该数字作为 `cursor` 再次查询，以查看其余挂单。

**如果你的 NFT 属于 Pancake Squad 或 Pancake Bunnies 以外的系列**，请在同一页面展开 **`viewCollections`**，输入 `cursor = 0` 和 `size = 100`，然后点击 **Query**，即可查看市场支持的所有系列。

### 第 2 步：提取你的 NFT

1. 在 BscScan 上打开市场合约的 [Write Contract 页面](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract)。
2. 点击 **Connect to Web3**，并连接曾挂单该 NFT 的同一个钱包。请确保你的钱包处于 BNB Smart Chain。
3. 找到并展开 **`cancelAskOrder`**。
4. 填写各字段：
   * `_collection`：第 1 步中的系列地址
   * `_tokenId`：第 1 步中的 token ID，填写纯数字（例如 `1234`）
5. 点击 **Write** 并在钱包中确认交易。你无需发送任何 BNB，只需支付 gas。
6. 交易成功后，NFT 就回到你的钱包了。
7. 对每个要提取的 NFT 重复上述操作。

要确认是否成功，请再次执行第 1 步。该 token ID 应不再出现在列表中。

### 故障排除

| 问题                                                      | 含义及处理方法                                                                                                                                                                                              |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 错误：`Order: Token not listed`                           | 已连接的钱包没有在该系列中挂单此 token ID，或者该 NFT 已被售出或提取。请检查你使用的是原钱包，并且系列地址和 token ID 正确。 |
| Write 按钮没有反应                                        | 你的钱包可能处于错误的网络。请切换到 BNB Smart Chain 并重新连接。                                                                                                                                           |
| gas 不足或资金不足                                        | 向你的钱包中添加少量 BNB 以支付 gas。                                                                                                                                                                       |
| 我无法再访问挂单该 NFT 的钱包                             | 只有原钱包才能取消挂单。任何人（包括 PancakeSwap）都无法代你提取。                                                                                                                                         |
