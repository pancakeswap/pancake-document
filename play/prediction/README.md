# 🔮 予測

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Predictionは、楽しくてシンプルな分散型予測マーケットです。

> **BNB、BTC、ETHの価格が上がるか下がるかを予測し、正解すると報酬が得られます！**

### プラットフォーム

PancakeSwap Predictionは以下でプレイできます：

* **デスクトップ / dApp**：[PancakeSwap Predictionガイド](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **TelegramミニApp（BNBUSDのみ）**：[Prediction Bot](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### 概要：仕組み

1. **賭けるアセットを選択**：現在、**BNB Chain**、**zkSync Era**、**Arbitrum One**で利用可能です。
2. **UPまたはDOWNを選択**：「LIVE」フェーズ終了時（各ラウンド＝5分）にアセット価格が上昇するか下落するかを予測します。
3. 賭け金額を入力：任意のBNB金額
4. **ポジションを確定**：一度賭けると変更できません。
5. **勝ちまたは負け**：
   * **UP**を選んだ場合、ラウンド終了時に_終了価格_ > _ロック価格_であれば勝ちです。
   * **DOWN**を選んだ場合、ラウンド終了時に_終了価格_ < _ロック価格_であれば勝ちです。

### 仕組みと手数料

* **対応チェーン：BNB Chain、zkSync Era、Arbitrum One**
* **ラウンド頻度**：**5分**ごと（ローリングラウンド）。
* **参加手数料**：各ラウンドの合計賞金プールの**3%**。その一部が**CAKEの買い戻し**に充てられます。
* **賞金**：結果確定後いつでも請求可能。
* **支払い**は各プールの賭け金比率に基づきます：
  * 支払い比率（UPプール）＝ _（両プールの合計額 ÷ UPプールの額）_
  * 支払い比率（DOWNプール）＝ _（両プールの合計額 ÷ DOWNプールの額）_
  * 計算例は[よくある質問 (FAQ)](prediction-faq.md)をご覧ください。

### 結果

* **勝ち**：手数料3%を差し引いた合計ポットを他の勝者と分配します。
* **負け**：賭け金全額を失います。

**特殊なケース**：

* **引き分け**（ロック価格 = 終了価格）：ハウスがすべての賭け金を獲得します。
* 反対側に賭けがない場合：
  * 勝った場合：初期賭け金の97%を取り戻せます（3%の手数料が適用されます）。
  * 負けた場合：賭け金全額がハウスに没収されます。
* **キャンセル**：例えばオラクル障害の場合、ユーザーには初期賭け金が返金されます。

### 価格フィード（オラクル）

| チェーン     | マーケット                                  | 目的                                                                 | オラクル                     |
| --------- | ---------------------------------------- | ----------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD、BTCUSD、ETHUSD、CAKEUSD（一時停止中） | _ロック価格_と_終了価格_を設定します（最大20秒ごとに更新）。 | **Chainlink**              |
| BNB Chain | すべて                                      | UI上のライブチャートを提供します（参考のみ）。                   | Binance / TradingView Feed |

#### **ChainLinkオラクル**

* 各予測マーケットラウンドのロック価格と終了価格に使用されます。最大20秒間隔で更新されます。
* 当社の予測コントラクトはBNB Chain上のChainLinkオラクル価格フィードを使用して、ユーザーが勝ったかどうかを判断する価格を設定します。
* インターフェースの「Chainlink」チャートに使用されます。

#### **Binance**

* PancakeSwap予測マーケットインターフェースのリアルタイム価格更新に使用されます。
* インターフェースの「TradingView」チャートに使用されます。

2つの異なる価格フィードを使用しているため、BinanceのリアルタイムPrice更新とChainLinkオラクルの価格は若干異なる場合があります。ただし、大きく乖離することはありません。

### コントラクトアドレス

BNB Chain：

* **BNBUSD**：[0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**：[0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**：[0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
