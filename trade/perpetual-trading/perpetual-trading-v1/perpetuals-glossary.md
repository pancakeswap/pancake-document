# Perpetuals V1 用語集

**先物取引に関連するすべての用語の定義をここでご確認いただけます。**

### **無期限取引**

&#x20;パーペチュアル（無期限先物、またはパーペチュアルスワップ）とは、満期日のない特殊な先物契約の一種です。



### **レバレッジ**

レバレッジは取引の仕組みです。投資全額を支払わずに市場へのエクスポージャーを高めることができます。簡単に言うと、投資をレバレッジするためにお金を借りることです。

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **マージン**

レバレッジポジションに対して提供する担保です。以下の2つのモードがあります：

* クロスマージンモード：同一マージン資産の下にあるすべてのクロスポジションは、同じ資産クロスマージン残高を共有します。清算が発生した場合、資産の全マージン残高と、その資産の下で残っているオープンポジションが没収される可能性があります。
* アイソレートマージンモード：各ポジションに割り当てるマージン量を制限することで、個別ポジションのリスクを管理します。ポジションのマージン比率が100%に達した場合、そのポジションは清算されます。このモードではポジションへのマージン追加・削除が可能です。

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cYs59UmVIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**マージン比率**：マージン比率 = メンテナンスマージン ÷ マージン残高。マージン比率が100%に達するとポジションが清算されます。

**メンテナンス比率**：オープンポジションを維持するために必要な最低マージン残高。

**マージン残高** = ウォレット残高 + 未実現PNL。マージン残高がメンテナンスマージン以下になるとポジションが清算されます。

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### アセット：

**入金**：Futuresアカウントに資金を入金します。

**出金**：FuturesアカウントからウォレットへBに資金を出金します。

**残高**：ウォレット残高 = 総正味転送額 + 総実現利益 + 総正味ファンディングフィー - 総手数料。

**未実現PNL**：マーク価格に基づいて計算されたこのポジションの未実現損益と、自己資本利益率のパーセンテージ。

**モード：**&#x20;

* シングルアセットモード：単一のマージン資産のみを使用してUSDⓢ-M Futures取引をサポートします。同一マージン資産ポジションのPNLを相殺できます。クロスマージンモードとアイソレートマージンモードの両方をサポートします。
* マルチアセットモード：複数のマージン資産にわたるUSDⓢ-M Futures取引。異なるマージン資産ポジション間でPNLを相殺できます。クロスマージンモードのみサポートします。

{% hint style="info" %}
注意：USDⓢ-M Futuresにオープンポジションまたはオープンオーダーがある場合、マルチアセットモードを有効化できません。マルチアセットモードはUSDⓢ-M Futuresにのみ適用されます。マルチアセットモードを有効にする前に、マルチアセットモード使用時のUSDⓢ-M Futuresアカウントリスク管理について詳しくガイドをお読みください。<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### 注文

**買い/ロング：**ロング注文を建てます。この注文ではアセットを購入し、価格が上昇したときに売ることを待ちます。「Buy」と「Long」は同義で使用されます。

**売り/ショート：**ショート注文を建てます。この注文ではアセットを借りて売り、価格が下落したときに買い戻すことを期待します。「Sell」と「Short」は同義で使用されます。

**指値注文（Limit Order）：**指値注文とは、特定の価格またはそれより有利な価格で買いまたは売りを行う注文です。指値注文の約定は保証されません。

**成行注文（Market Order）：**成行注文とは、現在最も有利な価格で買いまたは売りを行う注文です。以前に注文板に置かれた指値注文に対して約定されます。成行注文を出す際はマーケットテイカーとして手数料を支払います。

**逆指値注文（Stop Limit Order）：**逆指値注文は、逆指値価格と指値価格の2つに分けて理解するのが最も簡単です。逆指値価格は指値注文を発動させるトリガー価格であり、指値価格は発動する指値注文の価格です。つまり、逆指値価格に達した瞬間に指値注文が注文板に追加されます。

**逆指値成行注文（Stop Market Order）：**逆指値注文と同様に、逆指値成行注文も逆指値価格をトリガーとして使用します。ただし、逆指値価格に達すると、指値注文ではなく成行注文が発動されます。

**トレーリングストップ：**トレーリングストップは、取引が有利に動く場合に利益を確保するかまたは損失を限定するために設計された注文タイプです。価格が有利な方向にのみ動きます。利益を確保または損失を軽減するために動いた後は、逆方向には動きません。

**ポストオンリー：**ポストオンリーモードでは、注文がメイカー注文として注文板に追加される場合のみ注文を出せます。テイカー注文として追加される注文は拒否されます。成行注文は一切出せず、注文が約定されることもありません。残存する注文はポストオンリーモードでキャンセル可能です。

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**リデュースオンリー：**リデュースオンリー注文は、ポジションの増加ではなく、減少のみを行います。

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF指定**により、注文が約定または失効するまでの有効期間を指定できます。以下のオプションから選択可能です：

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC**（Good Till Cancel / キャンセルまで有効）：注文は約定またはキャンセルされるまで有効です。&#x20;
* **IOC**（Immediate Or Cancel / 即時または取消）：注文は即時に（全部または一部）約定されます。一部のみ約定された場合、残りの部分はキャンセルされます。&#x20;
* **FOK**（Fill Or Kill / 全量約定または失効）：注文は即時に全量約定される必要があります。そうでない場合は一切約定されません。
