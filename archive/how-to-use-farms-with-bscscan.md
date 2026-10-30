# 如何通过 BscScan 使用农场

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

由于需要多个步骤，在 PancakeSwap 使用农场起初可能会让人望而生畏。本指南将带你直接通过 BscScan 使用农场合约。

{% hint style="warning" %}
请注意，不建议初学者使用 BscScan 与合约交互。如果你信心不足，我们建议改用[如何使用农场指南](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms)。
{% endhint %}

## 查找农场进程标识符

要正确与农场智能合约交互，你需要你的 LP 交易对对应的进程标识符（PID）。目前最简单的查找方式是查看 GitHub。

1\. 打开 [GitHub 上 PancakeSwap 网站的农场代码](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts)。

2\. 按 **Control**/**command** + **F**，用代币符号（而非项目名称）搜索你的交易对。例如 'CAKE-BUSD'。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. 记下或复制 PID 编号（此例中为 389），保存在方便查看的地方。稍后你会用到它。

## 通过 BscScan 存入 LP 代币

通过 BscScan 存入 LP 代币涉及几个环节。我们将其拆分为若干步骤，方便你跟着操作。

### 获取主质押合约地址

主质押合约的地址是：**0x73feaa1eE314F8c655E354234017bE2193C9E24E**

如果你想确认这一点，请访问 [PancakeSwap: Main Staking Contract BscScan 页面](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)。你会在左上角看到该地址。点击**页面图标**将其复制到剪贴板。你很快就会用到它。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### 打开你的 LP 代币合约

在花费你打算投入农场的 LP 代币之前，你需要先为该 LP 代币授权智能合约。

### 从源代码获取

1\. 首先，打开 [GitHub 上的 farms.ts](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts)。

2\. 按 **Control**/**command** + **F**，用代币符号（而非项目名称）搜索你的交易对。例如 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. 找到你要查找的 LP 交易对的代码后，查看 "56:" 之后的地址。这就是你的合约地址。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### 从界面获取

1\. 首先，访问 [PancakeSwap 农场页面](https://pancakeswap.finance/farms)，使用右上角的 "SEARCH" 字段搜索你选择的交易对。本例中我们使用 CAKE-BUSD。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. 点击 **Details** 展开该行以显示更多信息。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. 点击 **View Contract** 在 BscScan 上打开该智能合约。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### 授权 LP 代币合约

现在你已在 BscScan 上打开了 LP 代币的合约，接下来你要授权将你的 LP 代币花费到农场中。

1\. 在 LP 代币的合约页面，前往 **Contract**，然后点击 **Write Contract**。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. 点击 **Connect to Web3** 连接 MetaMask。

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

确认连接。

3\. 在函数 1 “approve” 下，你会看到 “spender:address”。粘贴你之前复制到剪贴板的主质押合约的合约地址。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. 你还需要授权合约可以花费的 LP 代币数量。在 value 字段中，你需要输入以 Wei 为单位的数量。你可以使用 [BscScan 单位转换器](https://www.bscscan.com/unitconverter)轻松将你的数量转换为 Wei。这里我们使用 5 个 CAKE-BUSD LP 代币。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
你也可以使用 `-1` 作为值，授予无限额度的花费授权。这并不意味着默认会花费你的全部代币，只是意味着你的钱包将允许使用该合约的任意金额的交易。
{% endhint %}

6\. 点击 **Write** 并在你的 MetaMask 钱包中确认该操作。现在你可以向农场投入 LP 代币，最多不超过你已授权的数量。

### 使用主质押合约智能合约存入 LP 代币

主质押合约现已获授权花费你的 LP 代币，是时候存入了。

1\. 回到 [PancakeSwap: Main Staking Contract BscScan 页面](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)，前往 **Contract**，然后点击 **Write Contract**。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. 点击 **Connect to Web3** 连接 MetaMask。

3\. 滚动到函数 2 "deposit"，在 "\_pid" 字段中输入你的 PID。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

如果你之前没有记下 PID，可以在本页上方的**查找农场进程标识符**部分了解如何获取。

4\. 在 \_pid 下方你会看到 "\_amount"。输入你之前授权的、LP 合约可花费的数量。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. 检查信息并点击 **Write**。在 MetaMask 中确认你的操作。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. 你可以点击 **View your transaction** 确认存入是否成功。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## 从资金池中提取

从资金池中提取你的 LP 代币与存入非常相似。区别在于你要交互的函数不同。

1\. 回到 [PancakeSwap: Main Staking Contract BscScan 页面](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)，前往 **Contract**，然后点击 **Write Contract**。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. 点击 **Connect to Web3** 连接 MetaMask。

3\. 一直滚动到函数 15 "withdraw"，在 "\_pid" 字段中输入你的 PID。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

如果你之前没有记下 PID，可以在本页上方的**查找农场进程标识符**部分了解如何获取。

4\. 在 \_pid 下方你会看到 "\_amount"。输入你想从资金池中提取的 LP 数量。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. 检查信息并点击 **Write**。在 MetaMask 中确认你的操作。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. 你可以点击 **View your transaction** 确认提取是否成功。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **紧急提取**

当其他方式都行不通时，使用紧急提取功能可以让你把所有资金从资金池中取出。

{% hint style="danger" %}
**使用紧急提取功能将放弃你的 CAKE 奖励！**

PancakeSwap 团队强烈建议避免使用此功能，除非 PancakeSwap 团队正式建议你这样做，或者你非常熟悉与智能合约交互并理解底层代码。
{% endhint %}

‌1. 在 [PancakeSwap: Main Staking Contract BscScan 页面](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)，前往 **Contract**，然后点击 **Write Contract**。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. 点击 **Connect to Web3** 连接 MetaMask。

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. 向下滚动到函数 4 "emergencyWithdraw"，在 "\_pid" 字段中输入你的 PID。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

如果你之前没有记下 PID，可以在本页上方的**查找农场进程标识符**部分了解如何获取。

5\. 检查信息并点击 **Write**。在 MetaMask 中确认你的操作。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. 你可以点击 **View your transaction** 确认提取是否成功。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
