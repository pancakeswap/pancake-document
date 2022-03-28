---
description: よく起こりがちなエラーを紹介します。サイドバーから確認したいエラーメッセージの項目にジャンプしてください。
---

# トラブルシューティング

## トレード時のエラー

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> (PancakeRouterで”出金量の不足”エラーが発生したため、トランザクションを成功させることができません。売買するトークンのどちらかに問題があると思われます。)

このエラーは、トークンを売買する際にスリッページの許容範囲が狭かったり、トークンの流動性が低すぎたりする場合に発生します。

{% tabs %}
{% tab title="解決方法" %}
下記を試してください。

1. ページを更新してリトライしてください。
2. 一度に少額だけトレードしてみてください。
3.  スリッページの許容範囲を広げてリトライしてください。

    流動性ウィンドウにある歯車アイコンから、スリッページ設定変更画面に移動できます。\
    ![](<../.gitbook/assets/image (9) (4) (2).png>)
4. 売買時、小数点以下の数字をいくつか削ってみてください。
{% endtab %}

{% tab title="原因" %}
**多くの場合、このエラーメッセージは売買するトークンの流動性が低い場合に発生します。**

売買しようとしているトークンのいずれかが流動性プールに十分に存在していません。ほとんど取引のない小規模プロジェクトのトークンかもしれません。

もしくは、売却のできない詐欺トークンを交換しようとしている可能性があります。この場合でも、PancakeSwapはこのトークンをブロックしたり、あなたに資金を返したりすることはできません。
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> (PancakeRouterが”出金量Aの不足”エラーで失敗しました。)\
> または\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'\
> (PancakeRouterが”出金量Bの不足”エラーで失敗しました。)

このエラーは、流動性ペアのトークンAないしトークンBの量が不足している状態で、流動性プールに流動性を追加するか、流動性プールから流動性を除去するかしようとした場合に発生します。

{% tabs %}
{% tab title="解決方法" %}
**ページを更新してリトライするか、しばらく時間をあけてからリトライしてください。**

それでも解決しない場合：\
スリッページの許容範囲を広げてリトライしてください。\
流動性ウィンドウにある歯車アイコンから、スリッページ設定変更画面に移動できます。

![](<../.gitbook/assets/image (9) (4) (2).png>)
{% endtab %}

{% tab title="原因" %}
このエラーは、流動性ペアのトークンAないしトークンBの量が不足している状態で、流動性プールに流動性を追加するか、流動性プールから流動性を除去するかしようとしたことが原因です。

価格の変動速度があまりに速いか、スリッページの許容範囲が狭すぎる可能性があります。

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs\_pxdobz\_kY\_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt\_FAwpEylaIJhff5ZcYlzB\_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="技術オタク向け" %}
おや、ここに来ました？本当にこの問題を解決したいんですね。\
あなたが以下に記載された内容を完全に理解しない限り、この方法は試すことはおすすめしません。

現在のところ、PancakeSwapのウェブサイトからこのエラーを解決するシンプルな方法はありません。スマートコントラクトに直接アクセスする必要があります。具体的には、Routerのコントラクトを介してamountAMinを少額に設定した上で流動性を追加し、次に流動性を除去します。

### **1．流動性ペアトークンのコントラクトを承認する**

操作したい流動性ペアトークンのコントラクトに向かいましょう。 \
ここでは例としてETH-WBNBペアを挙げます： [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. **Write Contract**を選択し、**Connect to Web3**をクリックしてウォレットを接続してください。\
   ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
2. 「**1. approve**」項目で下記を記入し、流動性ペアトークンを承認します。
   1. spender (address) \
      あなたが操作したい流動性ペアトークンのコントラクトアドレス
   2. value (uint256)\
      「-1」を入力してください。

### 2．"balanceOf"を入手する

1. **Read Contract**に移動してください。
2. 「**5. balanceOf**」項目にあなたのウォレットアドレスを入力し「**Query**」をクリックします。\
   ここで表示された数値をメモしてください。\
   これは次のステップで必要となる流動性ペアトークンの残高をuint256形式で表したものです。

![](<../.gitbook/assets/image (7).png>)

### 3．流動性を追加/除去する

Routerコントラクトに移動します： [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. **Write Contract**を選択し、**Connect to Web3**をクリックしてウォレットを接続してください。
2. 流動性を追加したい場合は「**addLiquidity**」項目を、流動性を除去したい場合は「**removeLiquidity**」項目で以下を記入してください。
   1. tokenA (address)/tokenB (address) \
      流動性ペアトークンそれぞれのトークンアドレス
   2. liquidity (uint256)\
      ****先ほどメモした数値
   3. amountAMin (unit256) / amountBMin (unit256)\
      ****少量を設定します。両方1にしてみましょう。
   4. to (address)\
      ****あなたのウォレットアドレス
   5. deadline (unit256) \
      トランザクションが実行されるより大きなエポックタイム

![](<../.gitbook/assets/image (5).png>)

{% hint style="warning" %}
この方法は非常に高いスリッページを引き起こす恐れがあり、フロントランした場合、ユーザーはいくらかの資金を失う可能性があります。
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.
>
> (PancakeRouterで”期限切れ”エラーが発生したため、トランザクションを成功させることができません。売買するトークンのどちらかに問題があると思われます。)

このエラーは、トランザクションが作成された後、既定のタイムリミットまでに承認プロセスが完了しなかった場合に発生します。言い換えると、あなたは「確認」ボタンをすぐに押さなかったということです。

解決方法はリトライです。トランザクション作成後できるだけすぐに確認し、処理を進めてください。

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.
>
> (PancakeRouterで”Pancake: K”エラーが発生したため、トランザクションを成功させることができません。売買するトークンのどちらかに問題があると思われます。)

このエラーは、価格変動が大きなタイミングでトークンを売買しようとした場合に発生します。

ページを更新するか、スリッページの許容範囲を広げるかした後リトライしてください。スリッページ設定変更画面に移動するには流動性ウィンドウにある歯車アイコンをクリックします。

### Transaction cannot succeed

より少額でトレードしてみるか、スリッページの許容範囲を広げるかした後リトライしてください。これはトークンの流動性が低いことが原因です。

### **Price Impact too High**

より少額でトレードしてみるか、スリッページの許容範囲を広げるかした後リトライしてください。これはトークンの流動性が低いことが原因です。

### estimateGas failed

> This transaction would fail. Please contact support.
>
> (トランザクション が失敗した場合はサポートに問い合わせてください。）

{% tabs %}
{% tab title="解決方法" %}
**あなたがトレードしようとしたトークンのプロジェクトチームに問い合わせてください。**

この問題はプロジェクトチームによって解決されなくてはなりません。
{% endtab %}

{% tab title="原因" %}
この問題は、コントラクトにV1 PancakeSwap Routerアドレスをハードコーディングしているトークンが原因です。

この実装は望ましいものではありませんが、当該プロジェクトがそのようにした理由は、トークンが購入される際にいくらかの割合をLPに送るというトークノミクスによるものだと思われます。

この影響を受けるプロジェクトはV2 PancakeSwap Routerとはうまくいかない可能性が高く、新規にV2 Routerアドレスを指すコントラクトとそれを用いた新トークンを発行し、既存トークン保有者を新トークンに移行させる必要があります。 このようなトークンを発行したプロジェクトには、ユーザーがV2 LPにトークンを追加できないように処置することをお勧めします。

最新のRouterアドレスはこちら[https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

## **シロッププールでのエラー**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'
>
> (”BEP20:バーン量が残高を超過”エラーによる失敗)&#x20;

このエラーは、あなたのウォレットにCAKEプールからCAKEをアンステークするのに十分なSYRUPがない場合に発生します。

{% tabs %}
{% tab title="解決方法その１" %}
アンステークしたいCAKEと同量のSYRUPを用意してください。

1. ExchangeでSYRUPを購入しましょう。\
   もしあなたがプールから100CAKEをアンステークしたいのであれば、少なくとも100SYRUPが必要です。
2. 十分なSYRUPを確保した後、もう一度アンステークを試してください。
{% endtab %}

{% tab title="解決方法その２" %}
「解決方法その１」でも解決しない場合は、コントラクトに直接アクセスして「emergencyWithdraw」を実行することでステークしたCAKEをアンステークすることができます。

1. CAKEコントラクトに移動します： [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract ](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. **Write Contract**を選択し、**Connect to Web3**をクリックしてウォレットを接続してください。\
   ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
3. 「**4. emergencyWithdraw**」項目に"0"を入力し、“Write”をクリックします。

この方法でステークしていたCAKEをアンステークすることができますが、まだ収穫していない報酬は失われます。

{% hint style="warning" %}
**まだ収穫していない報酬は失われます。**
{% endhint %}
{% endtab %}

{% tab title="原因" %}
このエラーを防ぐためにも、**SYRUPは決して売却しないでください**。\
CAKEプールにCAKEをステークした際に受け取るSYRUPは、プールからCAKEをアンステークするときにも必要です。

このエラーの原因は、あなたがSYRUPトークンを売却または譲渡したためです。\
SYRUPは、CAKE-CAKEプールにステークするCAKEと1対1の比率で発行されます。コントラクトを実行してleaveStaking（プールからCAKEをアンステークする）機能を呼び出す際、SYRUPはCAKEと1:1の割合で燃やさる必要があります。この時SYRUPが足りなければ、プールからCAKEを外すことができません。

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi\_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endtab %}
{% endtabs %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]
>
> (注意！コントラクト実行中に”ガス欠”エラーが発生しました。)

このエラーは、トランザクションを行う際のガス上限が低く過ぎる場合に発生します。

{% tabs %}
{% tab title="解決方法" %}
トランザクションを承認する前に、ウォレット設定にて手動でガス上限を調節してください。\
ガス上限は使用されるガスの上限値であって、ガス代そのものではありません。&#x20;

通常、上限値は20万で充分です。

![](<../.gitbook/assets/image (2).png>)

上記はMetamaskの例です。\
ガス制限の調節方法がわからない場合は、お使いのウォレットの説明書を確認してください。
{% endtab %}

{% tab title="原因" %}
お使いのウォレット（Metamask、Trust Walletなど）がガス上限を低く見積もっていたため、関数呼び出しが終了する前にガスがなくなってしまいました。ウォレットはやろうとしていたことを完了させることができず、トランザクションが失敗しました。
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'
>
> (”BEP20:転送量が残高を超過”エラーによる失敗)&#x20;

このエラーは、あなたが報酬の少ないシロッププールからアンステークを試みた場合に発生します。

{% tabs %}
{% tab title="解決方法" %}
コントラクトに直接アクセスして「emergencyWithdraw」を実行することでステークしたトークンをアンステークすることができます。&#x20;

1. トークンをアンステークしようとしているシロッププールのコントラクトアドレスを見つけてください。このアドレスはウォレットのトランザクション履歴に記載されています。
2. [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) に移動し、検索バーに見つけたコントラクトアドレスを入力します
3. **Write Contract**を選択し、**Connect to Web3**をクリックしてウォレットを接続してください。\
   ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
4. 「**4. emergencyWithdraw**」項目に"0"を入力し、“Write”をクリックします。

この方法でステークしていたトークンをアンステークすることができますが、まだ収穫していない報酬は失われます。

{% hint style="warning" %}
**まだ収穫していない報酬は失われます。**
{% endhint %}
{% endtab %}

{% tab title="原因" %}
このエラーは、古いシロッププールから報酬を取り出そうとしたときに表示されがちです。\
アンステークする際に収穫できるだけの十分な報酬がプールに残っていません。そのため、トランザクションが失敗します。
{% endtab %}
{% endtabs %}

## その他のエラー

### Provider Error: No provider was found

* キャッシュとCookieをクリアしてください
* ウォレットをいったん切断し、再度接続してください
* 利用デバイスを再起動してください

### Unsupported Chain ID

利用するチェーンを「Binance Smart Chain」に切り替えてください。\
方法が不明な場合、ウォレットのガイド資料を参照してください。

### SAFEMOONや類似トークン購入時のエラーについて

SAFEMOONをトレードする際は、歯車アイコンからス**リッページを12％以上許容するように設定変更してください**。これは、**SAFEMOONがトランザクションごとに10％の手数料を取るため**です。

* 5%の手数料 = 既存SAFEMOONホルダーへの分配
* 5%の手数料 = LPへの追加

また、SAFEMOON購入時にあなたが期待したほどの量のトークンを受け取れなかった場合はこちらを確認してみてください。\
[How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).
