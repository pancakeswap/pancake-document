# Social Login 常见问题解答

{% hint style="info" %}
更多信息请查看：[https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 总体概述

**1. 什么是 PancakeSwap 的 social login，我为什么要使用它？**

Social login 让您可以使用 **Google**、**X (Twitter)**、**Discord** 或 **Telegram** 账户访问 PancakeSwap —— 无需钱包扩展或助记词。系统会在后台为您创建一个自托管钱包，因此您可以即时体验 DeFi，即使只有少量资金也可以。这降低了进入门槛，尤其是在时间紧迫的时刻。

**2. social login 支持哪些链？**

您的 social login 钱包可在 PancakeSwap 当前支持的所有链上使用：

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

所有钱包均**兼容 EVM**，并可通过 PancakeSwap 在这些网络上原生使用。如果您希望我们支持其他链（包括非 EVM 链），请告诉我们！

**3. 我可以在哪里使用 social login 钱包？**

您可以通过 PancakeSwap 网页应用，直接在任何桌面或移动**浏览器**中使用它。它**不兼容**外部钱包应用或 dApp 浏览器。



### 🛠️ 钱包设置与使用

**4. 钱包是如何创建和保护的？**

您的钱包会在登录时自动创建，并通过 **2-of-2 密钥份额系统**进行保护。重建密钥并生成签名时需要两份份额。

有关份额加密的更多信息，请查看：

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. 我可以创建多少个钱包？**

每个社交账户在每个 dApp 上可获得**一个钱包**。例如，如果您在另一个同样使用 Privy 的应用上使用 Google 登录，它将创建一个独立的钱包。



### 🔐 安全与隐私

**6. 如果有人窃取了我的设备，他们能访问我的钱包吗？**

不能。即使有人获得了您设备的访问权限，他们仍然需要您的**社交登录**以及（如已设置）您的**恢复密码**。

**7. PancakeSwap 或 Privy 会存储哪些数据？**

* PancakeSwap **不会存储**任何与钱包相关的密钥份额。
* Privy 会存储**加密的认证份额（Auth Share）和恢复份额（Recovery Share，若未设置恢复流程）**。

> 如果您尚未完成恢复设置，您的恢复份额将默认存储在 Privy。更多信息请访问：[https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 恢复与会话管理

**8. 我可以在不同的设备或浏览器上使用同一个钱包吗？**

可以！只需使用相同的社交账户登录即可。如果是新设备，您将通过恢复密码（如已设置）完成恢复流程。

**9. 如果我切换设备会怎样？**

系统会要求您使用社交账户重新登录，并完成恢复流程（密码设置）。如果您尚未设置恢复密码，仅凭社交账户登录即可。

**10. 如果我同时丢失了社交登录和恢复方式的访问权限怎么办？**

如果您同时失去了社交账户和恢复方式的访问权限，**您的钱包将无法恢复**。这里没有助记词作为备用方案，且目前不支持导出私钥。

> ⚠️ 请记住：导出私钥（若未来开放此功能）将使任何持有它的人获得对您钱包的完全控制权 —— 请务必极其谨慎对待。

**11. 活动会话持续多长时间？**

会话持续 30 **天**。之后，系统会提示您**重新登录**，并（如有需要）重新输入您的恢复凭据。在活动会话期间，您可以进行交易而无需手动批准每一项操作。



### ⚙️ 兼容性与限制

**12. 我可以导出或导入钱包吗？**

* **导出**：出于安全原因，默认不支持。未来更新中可能会有所改变。
* **导入**：不支持。您无法导入 MetaMask 或 Phantom 等外部钱包。

**13. 我可以通过 WalletConnect 将此钱包连接到其他 dApp 吗？**

目前不行。该嵌入式钱包**仅限于 PancakeSwap 使用**。如果您有兴趣更广泛地使用它，请告诉我们 —— 未来有可能进行扩展。



### 🚀 高级功能

**14. social login 钱包是否支持账户抽象（Account Abstraction）？**

支持。它支持**账户抽象功能**，例如交易批处理和通过 Biconomy 等集成实现的**gas 代付**。

**15. 免签名交易是如何实现的？**

* 登录后，您的会话最长可保持 30 **天**活动状态。在此期间，PancakeSwap 可以请求 Privy 使用您的会话凭据代表您签署交易。&#x20;
* 您不会在每次操作时看到钱包弹窗 —— 一切都在后台处理。30 天后，您需要重新登录才能继续使用此免签名体验。
