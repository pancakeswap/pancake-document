# Solana よくある質問 (FAQ)

### V3 Pools — よくある質問 (FAQ)

#### 1. 利用可能な手数料ティアは何ですか？

**サポートされている手数料ティア：**\
V3（集中流動性）プールで利用できる手数料ティアは以下の通りです。

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**手数料の分配（すべての手数料ティアに適用）：**

* 84%：流動性プロバイダー（LP）に分配
* 16%：プロトコルへ
  * 8%：バーン（焼却）
  * 8%：プロトコルトレジャリーへ

#### 2. 誰でもプールを作成できますか？

はい。プールの作成はパーミッションレスですが、以下の例外があります。

* 同一の**トークンペア + 手数料ティア**の組み合わせに対してプールは 1 つのみ作成可能です（例：SOL <> USDC 0.1% プールは同時に 1 つしか存在できません）。
* 現時点では **SPL トークン**と一部の **Token-2022** トークンのみサポートされています。

#### 3. 新しく作成したプールが表示されるまでどのくらいかかりますか？

* プールはほとんどの場合、作成後約 **5 分**でプールリストに表示されます。
* 表示されない場合：
  * **検索バー**を使って手動で検索してください。
  * **TVL が低い**プールはリストからフィルタリングされる場合があります。

#### 4. プールの APR や TVL がゼロのままなのはなぜですか？

これは新しいプール作成直後には正常な状態です。

* APR と TVL のデータは、プール内で**少なくとも 1 回のスワップ**が行われた後にのみ表示されます。
* スワップ後、これらの指標は約 **15 分以内**に表示され始めます。

#### 5. カスタムトークンを追加してプールを作成するには？

新しいトークンを追加するには：

* プール作成インターフェースでトークンセレクターを開きます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* 検索バーにトークンのアドレスを貼り付けます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* **「Add Token」** をクリックします。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* トークンがリストで検索可能になります。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* トークンを管理するには：
  * **「View Token List」** をクリックします。
  * 手動で追加したトークンを含む **User Added Token List** など、さまざまなリストのオン / オフを切り替えられます。

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Solana で最初の取引が割高に感じられるのはなぜですか？

Solana は **Associated Token Accounts（ATA）** を使って各ウォレットのトークン残高を管理しています。あるトークンに初めてアクセスする際、ウォレットは ATA を作成する必要があり、これには初回のみ費用がかかります（SOL で支払い）。

* この ATA 作成費用は Solana プロトコルによって要求されるものであり、PancakeSwap 固有のものではありません。
* ATA が後で閉鎖された場合、**使用した SOL は元のウォレットに返還されます**。
