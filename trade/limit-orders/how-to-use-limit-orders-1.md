# 指値注文の使い方

PancakeSwapの手数料獲得型指値注文は従来の指値注文とは異なる仕組みで動作します。ユーザーが指値注文を出すと、PancakeSwap Infinityプールに**片側流動性**を提供することになります。

市場価格が動くにつれて、プール内のスワップがユーザーの流動性を使用できるようになります。これが起きると、預けたトークンは完全に出力トークンに変換され、ユーザーは以下を受け取ります：

* 出力トークン、および
* 流動性に対して実行されたスワップから得られる取引手数料。

***

**例：BNBをUSDTに売却する**

* **BNB/USDTプールの現在価格：** BNB当たり600 USDT
* **ユーザーの目標/指値価格：** BNB当たり700 USDT

プロセス：

1. ユーザーは700 USDTでBNBを売る指値注文を設定します。
2. BNBはプール内のBNB当たり700 USDTに最も近いティックに預けられます。
3. 外部市場価格が700 USDTに達すると、プール価格が一致するよう調整されます（裁定取引の機会/より良い価格付けにより）。
4. その時点で、ユーザーのBNBがUSDTにスワップされます。
5. このプロセス中、ユーザーは流動性を消費する各スワップから手数料を獲得します。
6. 流動性が完全に消費されると、変換されたUSDT（手数料を含む）は自動的に引き出されユーザーのウォレットに送られます。

***

### ステップバイステップガイド

売買したいトークンペア（例：BNB/CAKE）と金額を選択します

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

目標/指値価格を設定します

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

指値注文を出し「確認」します。指値価格に最も近いティックに代わりに流動性が配置されます

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

プール価格が目標に達すると、注文が実行されます。希望する出力トークンと手数料が自動的に引き出されウォレットに送られます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### 注文状況

こちらをクリックして注文状況を確認できます

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**注文は以下のいずれかの状態になります：**

| 状態 | 説明 |
| ---------------- | ---------------------------------------------------------------------------------------- |
| 保留中 | 価格が目標に達するのを待っています |
| 約定済み | 注文が実行され、資金がウォレットに送られました |
| 一部約定 | 注文の一部のみが実行されました。両方のトークンを保持しています（例：一部BNB、一部USDT） |
| キャンセル済み | 注文をキャンセルしました。すべての資金が返金されます |

### よくある質問 (FAQ)

**Q: 指値注文を出すために手数料を支払う必要がありますか？**

A: いいえ。代わりに、注文が実行されると取引手数料として0.1%を獲得します。

**Q: どのペアでも注文できますか？**

A: ローンチ時点では、選択されたペアのみがサポートされています。今後さらに多くのペアが追加される予定です。

**Q: 最小注文サイズは？**

A: $50です。過剰なガス代につながる少額注文を防ぐためです。&#x20;

**Q: 注文の一部しか約定されない場合はどうなりますか？**

A: 両方のトークンを保持します。いつでもキャンセルして、両方のトークンと獲得した手数料を引き出せます。

**Q: 注文が約定されたのに、ウォレットにまだ資金が届いていません。**

A: 非常にまれなケースで起こる可能性がありますが、資金は常に安全です。注文詳細UIの「Withdraw（引き出し）」ボタンを使って手動で資金を受け取ってください。
