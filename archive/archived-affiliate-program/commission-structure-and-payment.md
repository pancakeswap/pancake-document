# コミッション構造と支払い

### コミッション

コミッション構造は以下の通りです：

<table><thead><tr><th width="198">プロダクト</th><th width="142">PancakeSwap V2</th><th width="140">PancakeSwap V3</th><th width="146">PancakeSwap StableSwap</th><th>PancakeSwap 無期限取引</th></tr></thead><tbody><tr><td>コミッション率（取引手数料に基づく）</td><td>3%*</td><td>3%*</td><td>3%*</td><td>20%**</td></tr><tr><td>ユーザーとの収益分配（カスタマイズ可能）</td><td>最大100%</td><td>最大100%</td><td>最大100%</td><td>ユーザーはコミッションの20%を固定で受け取る<strong>***</strong></td></tr></tbody></table>

**\*** コミッションの対象となるには、スワップ取引のトークンペアが以下の条件を満たす必要があります：

* **「PancakeSwap Extended」**[**公式トークンリスト**](https://tokenlists.org/token-list?url=https://tokens.pancakeswap.finance/pancakeswap-extended.json)に含まれていること
* 少なくとも**1つのメジャートークン**（BNB、BTC、BUSD、ETH、USDT、USDCのいずれか）を含むこと
* **BNB Smart ChainおよびEthereumチェーンのみ**のスワップ取引であること

**\*\*** 無期限取引は一部の地域では禁止されています。このプラットフォームでデリバティブ取引を行う資格があるかどうか確認してください。

\*\*\*無期限取引の取引手数料（または清算手数料が発生する可能性のあるリファラルのポジション）には、リファラルのポジションを清算するための清算手数料は含まれていません。**BNB Smart ChainおよびEthereumチェーンのみ**の無期限取引に限定されます。

### 支払い

上記の構造に基づいて、ユーザーが対象取引を積み上げたアフィリエイトに対して支払いが行われます。各オンチェーントランザクション後、コミッションをUSDで計算し、配布時点のCAKEトークンに変換します。これは取引のUSD価値を算出し、支払い時の現在のCAKEトークン価格に基づいてコミッションをCAKEトークンに変換することで行われます。詳細は[プログラムルールとガイドラインページ](program-rules-and-guidelines.md)をご覧ください。

[ダッシュボードページ](https://pancakeswap.finance/affiliates-program/dashboard)（近日公開予定！）から収益を確認できます。また同ページで月に一度コミッションを換金できます。換金プロセスに関するガイドをこちらに掲載予定です。

<br>
