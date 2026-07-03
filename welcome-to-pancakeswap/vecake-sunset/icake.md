---
description: veCAKE ステーキングと IFO 参加枠
hidden: true
---

# iCAKE

### **新しい iCAKE とは何ですか？**

veCAKE への移行後、新しい iCAKE は veCAKE 残高に基づきます。

* 旧来の iCAKE と同様に、PancakeSwap IFO パブリックセールにおける CAKE コミット上限を決定します。例えば、200 iCAKE を持っている場合、IFO パブリックセールで最大200 CAKE をコミットできます。
* 新しい iCAKE の数値は各 IFO 終了時点の veCAKE 残高を使用して計算されます。したがって、IFO ごとに異なる iCAKE 数値になります。
* veCAKE 残高はロック残存期間に応じて徐々に減少するため、将来の IFO での iCAKE も veCAKE 残高とともに減少します。iCAKE を維持するには、ステーキングに CAKE を追加するか、ロックを更新・延長してください。

**iCAKE は新しいトークンではなく、PancakeSwap IFO システムが使用する数値指標です。**

### iCAKE はどのように計算されますか？

保有する iCAKE の数は、各 IFO 終了時点の veCAKE 残高に、あらかじめ定められた比率を掛けた値です。

veCAKE はロックする CAKE の量と残存ロック時間に基づいて動的に計算される値です。veCAKE の計算方法の詳細については、[こちら](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef)をご覧ください。

veCAKE 残高に加えて、各 IFO に対してキッチンが設定する追加の比率が適用されます。例えば、比率が2倍の場合、次の IFO 終了時点で1 veCAKE を持っていれば、最大2 CAKE をコミットできます。

例：

* 100 CAKE を2年間ロックした場合。
  * 残存ロック時間：`2 * 52 * 7 * 24 * 60 * 60 = 62899200`（秒）
  * 最大ロック時間：`(209 * 7 * 24 * 60 * 60) - 1 = 126403199`（秒）
  * 現時点での保有量：`100 * (62899200 / 126403199) ~= 49.76` veCAKE
* 次の IFO が予定されており、終了時刻がちょうど1週間後（現在から `604800` 秒後）とします。
  * その時点での残存ロック時間：`62899200 - 604800 = 62294400`（秒）
  * その時点での保有量：`100 * (62294400 / 126403199) ~= 49.28` veCAKE
* この IFO の比率は `3倍` に設定されています。
* したがって、この IFO では：`49.28 * 3 = 147.84` iCAKE となり、パブリックセールで最大147.84 CAKE をコミットできます。

### 保有する iCAKE の数量を確認するには？

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

IFO ページ（[こちら](https://pancakeswap.finance/ifo)）で保有する iCAKE の数量を確認できます。

次回の IFO がない場合、iCAKE は毎秒徐々に減少するリアルタイムの veCAKE 残高を使用して計算されることをご留意ください。

次回の IFO がある場合、iCAKE はスナップショット時刻（IFO の終了時点）の veCAKE 残高を使用して計算されます。IFO が終了するまで iCAKE は減少・変化しません。

### **保有する iCAKE を増やすにはどうすればよいですか？**

[CAKE Staking ページ](https://pancakeswap.finance/cake-staking)で以下の方法でいつでも iCAKE を増やせます。

* veCAKE ステーキングポジションに CAKE を追加する。
* veCAKE ステーキングポジションを延長する。

### iCAKE 計算における「比率」とは何ですか？

比率とは、iCAKE を計算する際に veCAKE 残高に追加で適用されるコントロール係数です。

例えば、比率が2倍で、次の IFO 終了時点で1 veCAKE を持っている場合、最大2 CAKE をコミットできます。

各 IFO 間で、キッチンはさまざまな指標に基づいて「比率」を最適化します。調整内容はすべてのソーシャルチャンネルで公開されます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

iCAKE 計算の現在の「比率」は、[IFO ページ](https://pancakeswap.finance/ifo)で確認できます。
