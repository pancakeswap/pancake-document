# 糖浆池常见问题解答与排错指南

## 排错指南

### 我质押的糖浆池消失了！

您可以在「已完成」页面内找到之前质押的糖浆池。

选择「仅限已质押」，更方便快捷地找到您质押的资产。

### **为什么我无法从糖浆池内解质押？**

如果您无法从手动 CAKE 糖浆池解质押，请检查您的钱包内是否有足够的 SYRUP 代币。这个代币是您在手动 CAKE 糖浆池中质押的凭证，请妥善保管，不要出售或转出。

### **为什么在追加质押/提取后，我的收益变成了 0 ？**

别担心，它们已经在您的钱包内。

每当您对农场或糖浆池，进行质押或解质押操作。待收获收益将被自动收获至您的钱包内。

## **常见问题**

### 糖浆池的年化利率 \(APR\) 是怎么计算的？

> 糖浆池年化利率 \(APR\) = 年化收益 \(USD美金\) / 糖浆池中质押资产 \(USD美金\) \* 100

让我们来举一个简单的例子：一个为期 60 天，拥有价值 300,000 美金奖励的糖浆池，然后用户们一共质押了价值 3,000,000 美金的 CAKE 在里面。

年化利率无时无刻在改变，它受该糖浆池质押量、CAKE 币价、奖励代币币价的共同影响。

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"><b>&#x8BA1;&#x7B97;</b>
      </th>
      <th style="text-align:left">&#x6570;&#x91CF;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x5956;&#x52B1;&#x603B;&#x91CF; (USD&#x7F8E;&#x91D1;)</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">300,000 USD</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5956;&#x52B1;&#x5468;&#x671F;</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">60 &#x5929;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6BCF;&#x65E5;&#x5956;&#x52B1;&#x6570;</td>
      <td style="text-align:left">300,000 / 60 =</td>
      <td style="text-align:left">&#x6BCF;&#x65E5;
        <br />5,000 USD</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#x5E74;&#x5316;&#x6536;&#x76CA; (USD&#x7F8E;&#x91D1;)</b>
      </td>
      <td style="text-align:left">5,000 * 365 =</td>
      <td style="text-align:left"><b>1,825,000 USD</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#x5728;&#x6C60;&#x4E2D;&#x8D28;&#x62BC;&#x7684; CAKE (USD&#x7F8E;&#x91D1;)</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><b>3,000,000 USD</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5E74;&#x5316;&#x5229;&#x7387; (APR)</td>
      <td style="text-align:left">(1,825,000 / 3,000,000) * 100 =</td>
      <td style="text-align:left">
        <p></p>
        <p><b>60.833% APR</b>
        </p>
      </td>
    </tr>
  </tbody>
</table>

### **糖浆池中的「**结束倒计时**」指的是什么？**

「结束倒计时」显示距离奖励分发结束，还有多少个区块。一旦到达该区块，您需要从糖浆池中解开质押，因为该糖浆池将不再分发奖励。

### **糖浆池中的奖励从哪里来？**

糖浆池总共分为三种：

1. 质押 CAKE，赚取 CAKE
2. 质押 CAKE，赚取其他代币 
3. 质押其他代币，赚取 CAKE

「质押 CAKE，赚取 CAKE」糖浆池中的奖励来自 [CAKE 生产](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)。每当有一个新的区块，一定数量的 CAKE 会被生产并按比例分发，作为奖励。

「质押 CAKE，赚取其他代币」的奖励来自于其他项目团队的赞助。

「质押其他代币，赚取 CAKE」，我们将使用 PancakeSwap 储备金库，从市场中回购 CAKE 作为奖励。这些糖浆池由 PancakeSwap 自己出资，与其他项目无关。

### 什么是 SYRUP 代币？

每当您质押至**手动**「质押 CAKE，赚取 CAKE」糖浆池，PancakeSwap’s SYRUP 代币会被分发至您的钱包内。

您可以将它视作「借条」，它代表您质押了多少 CAKE 入糖浆池中。

当您从手动 CAKE 糖浆池中解质押时，它需被退回并被销毁。

{% hint style="warning" %}
请不要出售您的 SYRUP 代币！当您从手动 CAKE 糖浆池中解除质押时，您需要退回**同等数量**的 SYRUP 代币。
{% endhint %}

