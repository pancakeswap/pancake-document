# Classic StableSwap

Classic StableSwapはCurve FinanceのAMMをPancakeSwap上で実装したものです。流動性プールが極端に不均衡でない限り、価格をより均等に保つために、定数積公式（x\*y=k）に加えて線形不変定数和曲線（x+y=k）を追加しています。その結果、StableSwapは価格が類似したアセットに限定されているため、インパーマネントロスはそれほど問題ではなく（極端なデペグの場合を除く）、スリッページは定数積公式のみを使用する通常のAMMより低くなります。

StableSwapでスワップ（取引）を行うと、通常のPancakeSwap AMM の0.25%より低い取引手数料を支払います。手数料の内訳は以下の通りです：

* 50% LP報酬として&#x20;
* 40% CAKEの買い戻し・バーン&#x20;
* 10% PancakeSwap財務省

## StableSwap手数料

ペアの手数料は以下の表に詳細があります：

<table><thead><tr><th width="150">ステーブルペア</th><th width="132">取引手数料</th><th width="118.33333333333331">LP報酬</th><th width="124">CAKE買い戻し</th><th>PancakeSwap財務省</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-USDT</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>HAY-BUSD</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>HAY-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>axlUSDC-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>BNBx-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>stkBNB-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr></tbody></table>

Kitchenは製品をさらにテスト・改善するため、StableSwapペアを順次展開し、手数料を改定していきます。

## なぜ通常のAMM Swapの代わりにStableSwapを使うべきですか？

* 同じ取引ステップでステーブルコインや価格が類似したペアをより効率的にスワップできます&#x20;
* StableSwap機能により、スリッページは通常のAMMより低くなります&#x20;
* StableSwapの取引手数料は通常のAMMと比較して低くなっています
