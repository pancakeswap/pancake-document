---
description: よくあるエラーメッセージ。サイドバー ➡️ から該当するエラーにジャンプできます。
---

# トラブルシューティング

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

解決策が明確でない問題に直面することがあるかもしれません。以下のトラブルシューティングのヒントが、問題解決のお役に立てるかもしれません。

## **Exchangeに関する問題**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

トークンのスワップを試みていますが、スリッページ許容値が低すぎるか、流動性が不足しています。

{% tabs %}
{% tab title="解決策" %}
1. ページを更新して、しばらく後にもう一度お試しください。
2. 一度に取引する量を減らしてみてください。
3. スリッページ許容値を上げてください：
   1. 流動性ページの設定アイコンをタップします。
   2. スリッページ許容値を少し上げて再試行してください。 ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. 最後に、小数点以下の桁数が少ない数量を入力してみてください。
{% endtab %}

{% tab title="原因" %}
**これは通常、流動性が低いトークンを取引しようとした場合に発生します。**

スワップしようとしているトークンの一方が流動性プールに十分な量がないことを意味します。取引量が少ない小規模なトークンである可能性があります。

また、売却できない詐欺トークンを取引しようとしている可能性もあります。その場合、PancakeSwapはトークンをブロックしたり資金を返還したりすることはできません。
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT または INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

流動性プール（LP）への流動性の追加・削除を試みていますが、ペアの2つのトークンのうち一方が不足しています。

{% tabs %}
{% tab title="解決策" %}
**ページを更新して再試行するか、しばらく後に再試行してください。**

それでも解決しない場合は：

1. 流動性ページの設定アイコンをタップします。
2. スリッページ許容値を少し上げて再試行してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="原因" %}
このエラーは、トークンAまたはトークンB（ペアのいずれかのトークン）の量が不足している状態で、流動性プール（LP）に流動性を追加または削除しようとした場合に発生します。

価格の更新が早すぎてスリッページ許容値が低すぎる場合に発生することがあります。

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="上級者向け解決策" %}
本当に問題を解決したい場合のみご参照ください。ご自身で操作内容を理解している方以外には強くお勧めしません。

現時点では、PancakeSwapのウェブサイトからこの問題を簡単に解決する方法はありません。コントラクトに直接アクセスする必要があります。amountAMinを小さい値に設定してルーターコントラクト経由で直接流動性を追加し、その後すべての流動性を引き出すことができます。

**LPコントラクトを承認する**

承認しようとしているLPトークンのコントラクトにアクセスします。\
例えば、ETH/WBNBペアはこちらです：[https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. **Write Contract**を選択し、**Connect to Web3**でウォレットを接続します。 ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. **セクション「1. approve」**で、以下の情報を入力してルーターのLPトークンを承認します：
   1. spender (address): 操作対象のLPトークンのコントラクトアドレスを入力
   2. value (uint256): -1

**「balanceOf」を照会する**

1. **Read Contract**に切り替えます。
2. **5. balanceOf**にウォレットアドレスを入力し、**Query**をクリックします。
3. 表示された数値を記録しておいてください。これはuint256形式のLP内残高で、次のステップで使用します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**流動性の追加または削除**

ルーターコントラクトにアクセスします：[https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. 上記と同様に**Write Contract**を選択し、**Connect to Web3**でウォレットを接続します。
2. **addLiquidity**または**removeLiquidity**（実行したい操作）を見つけます。
3. LP内の両方のトークンアドレスを入力します。
4. **liquidity (uint256)**に、上記「balanceOf」で取得したuint256の数値を入力します。
5. **amountAMin**または**amountBMin**を低い値に設定します：両方とも1を試してください。
6. **to (address)**にウォレットアドレスを入力します。
7. Deadlineはトランザクションが実行される時刻より大きいエポック時間を設定してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
これにより非常に高いスリッページが発生する可能性があり、フロントランニングされた場合に一部の資産を失うことがあります。
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

再試行してください。ただし、トランザクションを生成したらすぐに署名してブロードキャストしてください。

トランザクションを開始したものの、デッドラインを過ぎるまで署名・ブロードキャストを行わなかったために発生します。「Confirm」ボタンを押すのが遅れた場合に起こります。

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

「To」フィールドの数量を変更してみてください。これにより「From」フィールドに「(estimated)」マークが付きます。その後すぐにスワップを実行してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

これは通常、独自の手数料を持つトークンをスワップしようとした場合に発生します。

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

取引しようとしている量より30%以上多くのトークンをウォレットに保有していることを確認するか、取引量を減らしてみてください。最大量を売却したい場合は、100%ではなく70%または69%をお試しください。\
これはtDogeやtBTCのようなRestorative Rebaseトークンの設計によって引き起こされます。\
[Restorative Rebaseトークンの仕組みを理解する](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)。

この問題のもう一つの原因として、悪意のあるトークン発行者がそのトークンの取引を停止した場合や、特定のウォレットアドレスのみ売却可能に設定している場合があります。詐欺被害を避けるため、常に自己調査を行ってください。このエラーコードで失敗しているトークンがエアドロップから来たものであれば、詐欺の可能性が高いです。トークンの承認やリンクへのアクセスは絶対に行わないでください。実行した場合、資産が危険にさらされる可能性があります。

### トランザクションが成功しない

取引量を減らすか、設定アイコンからスリッページ許容値を上げて再試行してください。流動性不足が原因です。

### **価格影響が高すぎる**

取引量を減らすか、設定アイコンからスリッページ許容値を上げて再試行してください。流動性不足が原因です。

### estimateGasの失敗

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="解決策" %}
**BNBペアから流動性を削除する際にこのエラーが発生した場合：**

「Receive WBNB」を選択して再試行してください。

**スワップ試行中にこのエラーが発生した場合：**

スワップしようとしているトークンのプロジェクトチームにお問い合わせください。この問題はプロジェクトチームが解決する必要があります。
{% endtab %}

{% tab title="原因" %}
**この問題（スワップ時）は、V1のPancakeSwapルーターアドレスをコントラクトにハードコードしているトークンによって引き起こされます。**

この実装は推奨されませんが、このようなプロジェクトがこれを行っている理由は、各購入時にトークンの一定割合をLPに送るトークノミクスによるものと思われます。

影響を受けるプロジェクトはおそらくV2ルーターでは機能しません。新しいルーターアドレスを指定したトークンの新バージョンを作成し、既存のトークン保有者を移行する必要があります。

このようなトークンを作成したプロジェクトは、ユーザーがV2 LPに追加できないよう対策を講じることをお勧めします。

最新のルーターアドレスは[https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)です。
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

トークンのスワップを試みると、トランザクションが失敗し、このエラーメッセージが表示されます。このエラーはTrust WalletをインストールしたモバイルデバイスでもReportされています。

{% tabs %}
{% tab title="解決策" %}
1. スリッページ許容値を上げてトランザクションを再試行してください。
2. それで解決しない場合は、SafePalなど別のウォレットでトランザクションをお試しください。
{% endtab %}

{% tab title="原因" %}
**これは通常、Trust Walletでスリッページ許容値が不足しているトークンを取引する際に発生します。**

問題の詳細については現在調査中です。
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

トークンのスワップを試みると、トランザクションが失敗し、このエラーメッセージが表示されます。このエラーは複数のプラットフォームでReportされています。

{% tabs %}
{% tab title="解決策" %}
1. 十分な残高があることを確認してください。
2. 取引しようとしている金額をコントラクトが使用できるよう、適切な承認（allowance）が設定されていることを確認してください。
{% endtab %}

{% tab title="原因" %}
このエラーは、承認（allowance）が不十分な状態でトークンを取引しようとした場合、またはウォレットの残高が不足している場合に発生します。\
tau assetsのtDogeやtBTCのようなRestorative Rebaseトークンを取引する場合は、事前に[Rebaseトークンガイド](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)でその仕組みを理解しておいてください。
{% endtab %}
{% endtabs %}

## **Farmに関する問題**

### Fail with error 'ds-math-sub-underflow'

MasterChefコントラクトへのLPトークンのallowanceが不足しています。

**unrektまたはBscScanなどのトークン承認管理ツールを使用してください**

## **Syrup Poolに関する問題**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

CAKE-CAKEプールからのステーキング解除に必要なSYRUPがウォレットに不足しています。

**アンステーキングしようとしているCAKEの量と少なくとも同量のSYRUPを用意してください。**

1. Exchangeで SYRUPを購入してください。100 CAKEをアンステーキングしたい場合は、少なくとも100 SYRUPが必要です。
2. アンステーキングを再試行してください。

それでも失敗する場合は、コントラクトから直接「emergencyWithdraw」を実行してステーキングを解除できます。

1. こちらにアクセスしてください：[https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. **「Connect to Web3」**をクリックしてウォレットを接続します。 ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. セクション**「4. emergencyWithdraw」**で「0」を入力し、「Write」をクリックします。

これによりステーキングされたトークンが引き出されますが、まだ収集していないCAKEの報酬は失われます。

{% hint style="warning" %}
**まだ収穫していない報酬はすべて失われます。**
{% endhint %}

再発防止のため、**SYRUPを売却しないでください。**「Stake CAKE Earn CAKE」プールからアンステーキングするには引き続きSYRUPが必要です。

このエラーはSYRUPトークンを売却または送金したために発生しています。SYRUPはCAKE-CAKE Syrup PoolでCAKEをステーキングする際に1:1の比率でMintされます。SYRUPはleaveStaking（プールからのCAKEのアンステーキング）を呼び出す際にCAKEと1:1の比率でバーンする必要があります。SYRUPが不足している場合はプールからアンステーキングできません。

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### ガス不足エラー

> Warning! Error encountered during contract execution \[out of gas]

トランザクションを実行しようとした際に、ガスリミットを低く設定しすぎています。

{% tabs %}
{% tab title="解決策" %}
トランザクションに署名する前に、ウォレットで手動で**ガスリミット**（ガス価格ではなく）を上げてみてください。

通常、200000のリミットで十分です。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

上記の例はMetaMaskのものです。ガスリミットの調整方法については、お使いのウォレットのドキュメントをご確認ください。
{% endtab %}

{% tab title="原因" %}
基本的に、ウォレット（MetaMask、Trust Walletなど）が処理を完了できない状態です。

ウォレットがガスリミットを低く見積もっており、関数の処理が完了する前にガスが不足してしまいます。
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="解決策" %}
1. Unrekt.netを使用して、操作しようとしているスマートコントラクトの承認を取り消します。
2. 支出上限を設定せずにコントラクトを再承認します。
3. コントラクトの操作を再試行します。
{% endtab %}

{% tab title="原因" %}
これは、最初にコントラクトを承認した際に支出上限を設定し、その後その上限を超えるスワップを試みた場合に発生します。
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

報酬が少なくなっているSyrup Poolからアンステーキングしようとしている可能性があります。以下の解決策をご参照ください。

それ以外の場合は、ウォレットに保有していないトークンを送信しようとしている可能性があります（例：すでに保留中のトランザクションに割り当てられているトークンを送信しようとしている場合）。その場合は、使用しようとしているトークンが実際に手元にあることを確認してください。

{% tabs %}
{% tab title="解決策" %}
まず、どのプールからアンステーキングしようとしているか[チームに連絡](../social-accounts.md)して、報酬を補充してもらいましょう。急いでアンステーキングしたい場合で、保留中の報酬を失っても構わない場合は、emergencyWithdrawをお試しください：

コントラクトから直接「emergencyWithdraw」を実行してステーキングを解除できます。

1. アンステーキングしようとしているSyrup Poolのコントラクトアドレスをウォレットのトランザクション履歴から確認します。
2. [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)にアクセスし、検索バーにコントラクトアドレスを入力します。
3. **Write Contract**を選択します。
4. **「Connect to Web3」**をクリックしてウォレットを接続します。![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. セクション**「3. emergencyWithdraw」**で「Write」をクリックします。

これによりステーキングされたトークンが引き出されますが、まだ収集していない報酬は失われます。

{% hint style="warning" %}
**まだ収穫していない報酬はすべて失われます。**
{% endhint %}
{% endtab %}

{% tab title="原因" %}
このエラーは、古いSyrup Poolからアンステーキングしようとした際に、引き出し時に収穫できる報酬がプールに十分残っていない場合に発生します。これによりトランザクションが失敗します。
{% endtab %}
{% endtabs %}

## **予測（Prediction）に関する問題**

[Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")をご確認ください。

## **その他の問題**

### プロバイダーエラー

> Provider Error\
> No provider was found

MetaMaskやBinance Chain WalletなどのブラウザExtensionで接続しようとしているが、Extensionがインストールされていない場合に発生します。

{% tabs %}
{% tab title="解決策" %}
接続するには公式のブラウザExtensionをインストールするか、[PancakeSwapへのウォレット接続方法](https://docs.pancakeswap.finance/get-started/connection-guide)のガイドをご参照ください。
{% endtab %}
{% endtabs %}

### サポートされていないChain ID

BNB Smart Chainにネットワークを切り替えてください。手順についてはお使いのウォレットのドキュメントをご確認ください。

### Already processing eth\_requestAccounts. Please wait.

ウォレットアプリにサインインしており、BNB Smart Chainに接続されていることを確認してください。

### SAFEMOONや類似トークン購入時の問題

SAFEMOONを取引するには、設定アイコンをクリックして**スリッページ許容値を12%以上に設定する必要があります。**\
これは**SafeMoonが各トランザクションに10%の手数料を課している**ためです：

* 5%の手数料 = 既存の全保有者に再分配
* 5%の手数料 = 流動性追加に使用

そのため、購入時に期待した量より少ないトークンを受け取ることがあります。\
詳しくは[How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742)をご覧ください。

### Internal JSON-RPC エラー

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

一部のトークンでMetaMask経由の流動性削除を試みた際に発生します。根本的な原因はまだ不明です。別のウォレットをお試しください。

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

トランザクション手数料を支払うためのBNBが不足しています。ウォレットにBEP-20ネットワークのBNBを追加する必要があります。

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

ウォレットでトランザクションのガスリミットを上げてください。ガスリミットの上げ方についてはウォレットのドキュメントをご確認ください。

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

原因は不明です。再試行する前に以下の手順をお試しください：

1. ガスリミットを上げる
2. スリッページを上げる
3. キャッシュをクリアする

## **プロフィールに関する問題**

### Oops! We couldn't find any Pancake Collectibles in your wallet.

この問題の原因を調査中です。その間、以下の回避策をお試しください。

{% tabs %}
{% tab title="回避策1" %}
1. 「Collectible」ページに移動してから、プロフィールページに戻ります。\
   リンクが見つからない場合は、[https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles)に直接アクセスしてください。
2. プロフィール作成を再試行します。
{% endtab %}

{% tab title="回避策2" %}
環境を変更してみてください。

* キャッシュをクリアして再試行する。
* 別のブラウザで再試行する。
* 別のウォレットアプリで再試行する。
* 別のネットワーク（Wi-Fiとモバイルデータ通信を切り替え）で再試行する。
{% endtab %}
{% endtabs %}

### ユーザー名の確認がくるくる回り続ける

考えられる原因は2つあります。

1. ブラウザに複数のウォレットがインストールされている。
2. ネットワークの問題。

{% tabs %}
{% tab title="解決策1" %}
原因：ブラウザに複数のウォレットがインストールされている。\
\
ウォレット間で競合が発生している可能性があります。これはPancakeSwapの管理範囲外です。

1. ブラウザにインストールするウォレットを1つにして、他を削除します。
2. ウォレットを再接続してユーザー名の設定を再試行します。
{% endtab %}

{% tab title="解決策2" %}
原因：ネットワークが不安定。

再試行してください。

1. テキストフィールドに入力された内容をすべて削除します。
2. ユーザー名を再入力し、数秒待ちます。
3. 解決しない場合は、ページを再読み込みして再試行してください。
{% endtab %}
{% endtabs %}
