# 🎟️ 彩票

参与 PancakeSwap 彩票，你将有机会赢取丰厚的 CAKE 大奖！它简单、公平，只要你有足够的 CAKE 来购买彩票，就可以随心所欲地参与。

[查看智能合约](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **详情：**

* 1 张彩票的费用：约 5 美元等值的 CAKE。
* 单个用户的彩票购买上限：没有总体上限，但每次最多只能购买 100 张彩票。
* 购买一张彩票将为用户随机生成一个 6 位数字组合，每位数字介于 0-9 之间，例如 "1-9-3-2-0-4"。从左到右匹配数字即可赢取奖励——匹配的数字越多，你将分享的奖池就越大。
* 彩票使用 Chainlink 的 VRF 实现，以确保真正、安全的随机性。

## 彩票费用与批量购买折扣

彩票价格在每个新彩票回合开始时设定，目标为 5 美元（可能会因价格突然波动而略有变化）。

一次购买多张彩票可享受批量折扣。你可以一次最多购买 100 张彩票，折扣从购买 2 张时的小幅度开始，最高在购买 100 张时达到 10%。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%E2%80%AFPM.png)

## **如何中奖**

将彩票上的数字，**从左侧开始**，与彩票回合结束时抽出的中奖号码进行匹配。

* 即使只匹配第一个数字，你也能赢得一份小奖。&#x20;
* 匹配更多数字即可分享更大的奖池。

## **‌**中奖资格

‌每张彩票上共有六个彩球，数字从 0 到 9。要中奖，你的数字需要与抽出的数字按相同顺序匹配，从彩票左侧开始。例如：

抽出的号码

![Drawn Numbers](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png)

你的彩票号码

![Your Ticket A](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png)

在上面的例子中，彩票 A 有五个数字与抽出的数字按完全相同的顺序匹配：除了第四个之外全部匹配。

然而，由于第四位数字与抽出的号码**不**匹配，因此只有前三位数字算作按顺序匹配。这将赢得 "匹配前 3 个" 的奖励。

![Your Ticket B](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png)

示例彩票 B。这是个不走运的例子。尽管后五位数字都匹配，但第一位数字不匹配，因此这张彩票完全无法中奖。

你只能分享你符合资格的最高奖励等级的奖金。一张匹配前三个数字的彩票只能获得匹配三个等级的奖励，而不能获得匹配一个或匹配两个等级的奖励。

**请记住：数字必须从左到右按顺序匹配。**

## 各奖励等级之间的奖金分配

‌在一个回合开抽并确定了匹配号码的彩票后，奖金将被发放。每张彩票赢得的金额取决于在同一奖励等级中有多少其他彩票中奖。

‌例如，如果你是唯一一张按顺序匹配了三个数字的彩票，而你所在等级预定的奖池份额为 2000 CAKE，那么你将获得全部 2000 CAKE。

‌然而，如果你和另外三个人都按顺序匹配了三个数字，那么 2000 CAKE 将在四张中奖彩票之间平分，这意味着你将获得 500 CAKE。

请参阅[彩票常见问题解答中各等级奖励的细分](lottery-faq.md#how-are-prizes-broken-down-between-brackets)。
