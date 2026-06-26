# 跨链桥接你的 veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

要在其他链上享受 veCAKE 带来的好处，例如 bCAKE（农场收益加成）和 iCAKE（IFO 公售配额），你需要在 BNB Chain 上执行一个简单的桥接请求，将你的 veCAKE 余额和 PancakeProfile 同步到其他链。

## 如何桥接？ <a href="#id-734b8113-0e00-40ff-bccb-9c129460e2e2" id="id-734b8113-0e00-40ff-bccb-9c129460e2e2"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29.png" alt=""><figcaption></figcaption></figure>

前往 [CAKE Staking](https://pancakeswap.finance/cake-staking) 页面，在 veCAKE 好处下方找到 veCAKE Sync 卡片。点击"View Details"打开同步弹窗。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

在弹窗中，你可以查看你在 BNB Chain 上拥有的 veCAKE 数量，以及目标链列表，你可以将你的 veCAKE 和 Pancake Profile 桥接到每条链上对应的 veCAKE 和 Pancake Profile 状态。

要进行同步，请选择链，点击"Sync"，然后在你的钱包弹窗中确认。

完成桥接可能最多需要 20 分钟。你可以在同步弹窗中查看桥接进度。&#x20;

注意：

* 你一次只能桥接一条链。要将你的 veCAKE 同步到多条链，请重复上述流程。
* 桥接请求会收取 BNB，以支付目标链上的 gas 费用。BNB 的数额取决于目标链。由于 gas 费用较高，像 Ethereum 主网这样的链同步起来会明显更昂贵。
* 为避免不必要的 gas 花费，请仅将你的 veCAKE 同步到你想要享受好处的链上。
* 在添加更多 CAKE 或延长你的 veCAKE 质押仓位后，请重复上述流程以更新目标链上的 veCAKE 余额，确保你的好处保持最新。

## 常见问题解答 <a href="#id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad" id="id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad"></a>

**问：我需要多久同步一次我的 veCAKE 和 Pancake Profile？**

答：对于 veCAKE，你只需在添加更多 CAKE、延长锁定时长或执行重新锁定时进行同步。你在目标链上的 veCAKE 余额将随着 BNB Chain 上的余额线性减少。

对于 Pancake Profile 及其 NFT，你需要执行两次同步才能参与私售。第一次应在 IFO 发布并可在 UI 上查看时执行。另一次应在 IFO 销售结束后执行，以启用领取功能。

**问：桥接需要多长时间？**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

取决于目标链。通常大约需要 2-5 分钟来桥接并完全同步。对于一些较慢的链，可能最多需要 30 分钟。要追踪你的桥接请求，请在同步弹窗中查看 LayerZero 浏览器链接。或前往 [https://layerzeroscan.com/](https://layerzeroscan.com/) 并通过 BNB Chain 交易 ID 搜索。

**问：为什么 BNB Chain 上的桥接交易失败了？**

答：

* 这可能是因为目标链的 gas 估算已过期。请刷新页面并重试。
* 另请确保钱包中有足够数量的 BNB 来支付目标链所需的 gas 费用。

**问：为什么我的 veCAKE 或 Pancake Profile 没有被桥接？**

答：

* 剩余锁定时间少于 1 天的 veCAKE 仓位将不会被桥接。请先延长锁定并重试同步。
* 同步可能最多需要 30 分钟才能完成。请前往 https://layerzeroscan.com/ 并通过 BNB Chain 交易 ID 搜索，以确认桥接状态为"Delivered"（已送达）。
* 如果桥接状态为"Failed"（失败）或"Blocked"（已阻止），请通过公开渠道联系我们的某位大使了解更多详情。
