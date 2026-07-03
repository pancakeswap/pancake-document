# 📔 ガバナンス

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
[Tokenomics 3.0アップグレード](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3)の一環として、このページは2025年5月15日に更新されました
{% endhint %}

投票はPancakeSwapコミュニティに発言権を与え、コミュニティがPancakeSwapの将来の発展に関与できるようにします。

[PancakeSwapのネイティブ投票ポータル](https://pancakeswap.finance/voting)と[フォーラム](https://forum.pancakeswap.finance/)ページをご確認ください。

## 投票の仕組み

:notebook\_with\_decorative\_cover:概要 — 変更点（[Tokenomics 3.0アップデート](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3)後）

<table><thead><tr><th width="200.6015625">ガバナンスコンポーネント</th><th width="218.01953125">Tokenomics 3.0以前</th><th width="205.1796875">Tokenomics 3.0以後</th><th>ステータス<select><option value="q1dVFsCri7zA" label="✅ 変更あり" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 変更なし" color="blue"></option></select></th></tr></thead><tbody><tr><td>投票権</td><td>1 veCAKE = 1投票権</td><td>1 CAKE = 1投票権</td><td><span data-option="q1dVFsCri7zA">✅ 変更あり</span></td></tr><tr><td>委任</td><td>許可（veCAKEの仕組みによる）</td><td>委任は不可</td><td><span data-option="q1dVFsCri7zA">✅ 変更あり</span></td></tr><tr><td>提案提出のしきい値</td><td>スナップショット 100K veCAKEが必要</td><td>スナップショット 100K CAKEが必要</td><td><span data-option="q1dVFsCri7zA">✅ 変更あり</span></td></tr><tr><td>コアと一般提案</td><td>各提案タイプに対して定義された役割と目的</td><td>変更なし</td><td><span data-option="4AGl26rwjYcI">🔁 変更なし</span></td></tr><tr><td>投票期間</td><td>一般：固定<br>コア：可変</td><td>変更なし</td><td><span data-option="4AGl26rwjYcI">🔁 変更なし</span></td></tr><tr><td>スナップショットのタイミング</td><td>提案が投稿されたブロック時点</td><td>変更なし</td><td><span data-option="4AGl26rwjYcI">🔁 変更なし</span></td></tr><tr><td>クォーラム</td><td>最小クォーラムなし</td><td>変更なし</td><td><span data-option="4AGl26rwjYcI">🔁 変更なし</span></td></tr></tbody></table>

### 1. **投票権（変更あり）**

* **すべてのCAKEホルダーに直接的な投票権があります。**
* **投票権はスナップショット時のウォレットアドレスに保有するCAKEの数に直接対応します**
  * **1 CAKE = 1投票権**
  * **シロッププールにステーキングされたCAKEは**スナップショット時のウォレット残高に含まれないため、投票権の対象になりません
  * スナップショット残高 = 提案が投稿されたブロックと同じ
* **委任はサポートされなくなりました。** すべてのCAKEホルダーは個別に投票する必要があります。

### 2. **提案の提出（変更なし）**

* **提案の提出方法**
  * [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)で提出します
  * 以下を含める必要があります：
    * タイトル
    * コンテンツ
    * 説明
    * オンチェーンアクション（必要な場合）
    * 投票期間
* 提案の種類
  1.  コア提案

      * **PancakeSwapコアチーム**のみが提案できます。
      * CAKEホルダーによる投票が必要です。
      * 可決された場合、PancakeSwapチームにより実施されます。

      例

      1. プロトコルの調整（製品の変更、手数料の変更）
      2. 以前の提案の範囲をカバーしないエコシステム成長資金の重大な用途
  2. 一般提案
     * **一般**提案はPancakeSwapコミュニティによって投稿されます。これらはアイデアを提案し、コミュニティの観点を表明するために使用されます。これらはコミュニティからの**拘束力のない提案**です。
     * **100,000 CAKE（スナップショット残高）**を持つ誰でも提出できます。
     * PancakeSwapチームは強力な提案を将来のコア提案に採用することがあります
     * コミュニティメンバーは[フォーラム](https://forum.pancakeswap.finance/)を通じてプロトコルへのフィードバックや提案を提供することもできます。

### **3. 投票期間（変更なし）**

* すべてのCAKEホルダーは各提案の**投票期間中**に投票できます。
  * 一般提案：固定で3日間
  * コア提案：PancakeSwapによって設定される可変期間
* 投票権は**提案が投稿されたブロック時点のCAKE残高のスナップショット**によって決定されます。
* **提案が投稿された後にCAKEを追加しても、その特定の投票に対する投票権は増加しません。**

詳細については[投票ガイド](https://docs.pancakeswap.finance/protocol/voting/voting-guide)をご参照ください。

### **4. 投票結果（変更なし）**

* 結果は**投じられた総投票数**（投票に使用された総CAKE数）に基づきます
* **現在、提案が可決されるための最小クォーラムは設定されていません。**

## 注：拒否権

プロトコルを保護するため、**PancakeSwapコアチームは、セキュリティの脅威やプラットフォームの安定した運営に影響する問題などの重大な状況において、コミュニティの投票やSnapshotポールを必要とせずに介入する権利を留保します**。

拒否権が行使される場合、コアチームは**判断の明確な説明を公開します**。

**拒否権の行使には以下が含まれる可能性があります：**

1. 緊急のバグや脆弱性を修正するために**スマートコントラクトを一時的に一時停止する**。
