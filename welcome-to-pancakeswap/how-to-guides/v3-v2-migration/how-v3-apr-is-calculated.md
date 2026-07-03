# v3 APRの計算方法

{% hint style="info" %}
v3の流動性とFarmでは、非代替性流動性とカスタマイズ可能な価格範囲設定により、各LPポジションが独自のLP手数料とCAKEファーミングAPRを持ちます。
{% endhint %}

合計APRはLP手数料APRとCAKE報酬APRの組み合わせによって構成されます。

### LP手数料

理論的には、ユーザーが追加しようとしている価格範囲と流動性を考慮した場合、今後7日間に期待される手数料の推定値は以下のとおりです。&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : 直近7日間にユーザーが指定した価格範囲内で発生した手数料の量
* $$L_{in}$$: ユーザーが指定した価格範囲内の現在の流動性
* $$\Delta{L}$$: ユーザーが価格範囲に追加しようとしている流動性

#### 範囲内手数料

$$fee_{in}$$については、過去の取引量データ、手数料ティア、過去の価格データを使用して価格の範囲内状況を推定します。

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: 手数料ティア
* $$V_{7d}$$: 直近7日間の合計取引量
* $$T_{in}$$: 直近7日間に価格が価格範囲内に留まっていた期間（秒単位）
* $$T_{7d}$$: 7日間（秒単位）

### Cake APR

#### プールの配分

MC v3における1秒あたりの合計報酬CAKEはアップキープを使用しており、`latestPeriodCakePerSecond`で導出できます。

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

各プールでは、`poolInfo`を使用して`poolInfo.allocPoint / totalAllocPoint`で割ることにより`poolWeight`を取得できます。

#### グローバルCake APR

グローバルAPRは、プールのCAKE報酬排出量と全アクティブ＆ステーキング流動性の合計量を使用して計算されます。

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD`は、MasterChef v3にステーキングされているすべてのポジションの範囲内ティックで構成される、現在のプールのアクティブなステーキング流動性（USD建て）を表します。

#### ポジションのCake APR

個々のポジションのAPRは価格範囲の設定によって異なる場合があります。

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: プールで年間獲得するCAKE報酬のUSD換算額
* $$USD_p$$: ポジションの合計USD価値
* $$L_{p}$$: ポジションの流動性
* $$L_{lm}$$: LMPoolが追跡するステーキング流動性の合計
