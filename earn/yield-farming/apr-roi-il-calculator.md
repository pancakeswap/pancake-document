# APR/ROI/IL Calculator

v3の流動性とFarmでは、新しいノンファンジブル流動性とカスタマイズ可能な価格レンジ機能が導入されました。各LP ポジションは独自のLP手数料とCAKEファーミングAPRを持ちます。

流動性の提供をよりスムーズかつ簡単にするため、流動性提供やファーミングの際に利用できる自動APR表示と新しいROIカリキュレーターが利用可能になりました。

## 自動APR計算と表示 <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

流動性を提供する際、自動APR表示は設定の変更に反応し、設定に基づいてAPRを計算します。

例えば、ほとんどの場合、価格レンジを狭めるとAPRが上昇します。

LP手数料APRについてご注意ください：

* LP手数料報酬の見込み額は選択した手数料ティアによって異なり、手数料報酬は手動でのクレームと複利運用が必要です。
* APRの数値は過去の取引量を使用して計算されており、Subgraphに依存するためインデックス遅延が生じる場合があります。

ファーミングAPRについて：

* CAKEの見込み報酬額は、ファームへのライブCAKEエミッションに基づいています。今後のエミッション調整により変動する場合があります。

{% hint style="info" %}
数値は現在のレートとプール状況で計算されており、さまざまな外部要因によって変動する場合があります。これらはお客様の利便性のために提供された推定値であり、いかなる意味でも保証された利回りを示すものではありません。
{% endhint %}

このAPR表示は以下の場所で確認できます：

* 「流動性を追加」ページ - LP手数料APRを表示
* 既存の流動性ポジションの詳細ページ - LP手数料APRを表示\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* ファームページ、各ファームのポジション内 - LP手数料とCAKE報酬を組み合わせたAPRを表示\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## 改良されたROIカリキュレーター <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

自動APR表示が表示されている場合はいつでもクリックして新しいROIカリキュレーターを開くことができます。新しいROIカリキュレーターは、v3の集中流動性提供とファーミングのニーズに対応するため、いくつかの新機能を加えてリデザインされました。

各セクションを順番に見ていきましょう：

### 預入金額、「ステーキング期間」、「複利運用頻度」 <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

これら3つは基本的な入力項目で、以前のROIカリキュレーターにも存在していました。以下を定義するために使用します：

1. 流動性ポジションに預け入れるアセットの量（USD単位）
2. そのアセットをポジションにステーキングする期間
3. 報酬をポジションに複利で戻す頻度



⓵ **預入金額**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

USDで金額を手動入力するか、クイックアクションボタンを使用して$100、$1000、またはウォレット内のトークン残高に基づいた最大許容額を素早く入力できます。



⓶ **ステーキング期間**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

流動性ポジションにアセットをステーキングする期間を選択できます：1日、7日、30日、1年、5年から選択可能です。

リターンの数値は選択したステーキング期間に基づいて計算されます。



⓷ **複利運用**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

ポジションで生成された報酬をハーベストしてポジションに複利で戻す頻度を選択できます。12時間、1日、7日、30日から選択可能です。

リターンとAPYの数値は選択に基づいて計算されます。ポジションを複利運用する予定がない場合は、左側のチェックボックスのチェックを外してください。

{% hint style="info" %}
v3では、LP手数料と獲得したCAKEは手動でハーベストおよび複利運用する必要があります。
{% endhint %}

### &#x20;⓸ 過去の価格 <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

これは選択したペアの過去の価格変動を参照するための閲覧専用セクションです。

さまざまな時間軸での過去の価格変動を参照し、通常の価格変動幅を把握することで、高いAPRとインパーマネントロスリスクの低減のバランスを取るための適切な価格レンジ設定を考えることができます。

* MIN - 最安値
* MAX - 最高値
* AVG - 平均価格
* CURRENT - 現在価格

{% hint style="info" %}
価格チャートは実際のv3ペアのデータのみを使用しています。そのため、v3デプロイ前の価格データはご利用いただけません。4つの価格指標は現在選択されている時間軸を示しており、選択を変更すると更新されます。
{% endhint %}

### ⓹ 価格レンジ <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

このセクションを使用して、さまざまな価格レンジに預け入れられた流動性量を確認し、流動性を提供する価格レンジを設定することができます。

タイトルの下に分布チャートがあります。流動性量が多いほど、チャートが高くなります。

価格レンジの設定を変更するには：

* チャートの2つのハンドルをドラッグして最小・最大価格の上限を増減させる
* 2つのハンドル間のスペースを使用して選択範囲をシフトする
* 最小・最大価格フィールドの＋と－ボタンをクリックする
* 価格フィールドの数値をクリックして手動で入力する

分布チャートをナビゲートするには：

1. プラスとマイナスの虫眼鏡ボタンを使用してズームイン・ズームアウト
2. X軸（下部）をドラッグして左右にシフト

全価格レンジに流動性を提供したい場合は、「Full Range」をクリックしてください。

### ⓺ 異なるベースで価格を表示するための方向切り替え <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

一部のトークンペアでは、特定のベーストークンで価格を表示する方が分かりやすく直感的な場合があります。例えば、BNB/USDTペアの場合、ほとんどの人は「BNBあたり何USDT」という表示を好むでしょう。

価格表示を簡単に切り替えることができます。「View prices in:」に続くボタンをクリックするだけで、ペア内の2つのトークン間でベースを切り替えられます。

### ⓻ 設定のインポートとエクスポート（適用） <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

「流動性を追加」ウィンドウでROIカリキュレーターを開いたり、既存のポジションを閲覧したりする際、以下の設定が自動的にインポートされるため、再設定の必要はありません：

1. 預け入れるアセットの量
2. 価格レンジ
3. 選択した手数料ティア

ROIカリキュレーターでの設定が完了したら、「設定を適用」をクリックすることで、カリキュレーターの設定を「流動性を追加」ウィンドウに素早く適用できます。手動で合わせる必要はありません。

### ⓼ ファーミング報酬とAPRの計算 <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

「Farm」ページでROIカリキュレーターを開いた場合、ファーミング報酬が計算に含まれます。

詳細セクションを展開すると、報酬の内訳が確認できます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
