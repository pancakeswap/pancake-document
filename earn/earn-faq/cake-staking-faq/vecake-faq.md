---
hidden: true
---

# veCAKE よくある質問 (FAQ)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### ロックされたCAKEとveCAKEの違いは何ですか？ <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKEは、ロックされたCAKE保有者によりメリットと権限を提供する固定期間CAKEステーキングの新バージョンです。ゲージウェイト投票、追加インセンティブ、利回りブーストなどが含まれます。

#### 新しいveCAKEがデプロイされた際のCAKEプール報酬はどうなりますか <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

CAKEプールの報酬エミッションは、veCAKEの残高と総供給量に応じてすべてのveCAKE保有者に報酬として転用されます。

CAKE報酬と週次収益分配報酬は毎週木曜日にクレームできるようになりました。

報酬の受け取りを継続するには、ユーザーは新しいveCAKEステーキングに移行する必要がありますのでご注意ください。

#### CAKEをロックできる最長期間はどのくらいですか <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

CAKEをロックできる最長期間が4年に延長されました。

#### veCAKEは新しいトークンですか？転送できますか？ <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKEはロックされたCAKEの量と残りのロック時間に基づいてリアルタイムで生成される数値です。標準トークンではなく、転送できません。

#### veCAKE残高が変わったのはなぜですか？残高はどのように計算されますか？ <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

veCAKEの残高は、残りのロック期間に基づいて線形に0に向けて減少します。そのため、アンロック時間が近づくにつれて残高が減少します。

veCAKE残高は以下で計算できます：

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### veCAKEを増やすにはどうすればいいですか？ <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

アクティブなveCAKEポジションを持っている場合、さらにCAKEを追加するか、ロック期間を更新/延長することでveCAKE残高をブーストできます。

#### ポジションがアンロックされたらどうなりますか？すぐに更新できますか？ <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

veCAKEステーキングポジションがアンロックされると、ステーキングされたすべてのCAKEを引き出せます。

ポジションを更新するには、すべてのCAKEを引き出してから、ロック量とロック期間を選択して新しいステーキングポジションを設定する必要があります。

#### 1週間ロックしたのに、残りのロック時間が1週間未満なのはなぜですか？ <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

新しいveCAKEでロックする場合、アンロック時間はUTC時間の最も近い木曜日に切り上げられます。例えば、火曜日に1週間ロックした場合、実際のアンロック時間は2日後の次の木曜日になります。

実際のアンロック時間は下部でプレビューできます。

#### CAKEプールにさらにCAKEをロックできますか？ <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

いいえ。

veCAKEがデプロイされると、CAKEステーキングプールは廃止され、CAKEの延長や追加預け入れを受け付けなくなります。

CAKEをロックしてそのメリットを享受するには、veCAKEページに移動してください。

#### なぜ移行できないのですか？ <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

CAKEプールからveCAKEへの移行には、アクティブなポジションが必要です。CAKEプールのステーキングポジションがすでにアンロックされている場合は、CAKEを引き出してネイティブのveCAKEステーキングポジションを作成してください。

場合によっては、CAKEプールの残りのロック時間が7日未満の場合に移行を実行できないことがあります。その場合は、アンロックを待ってからCAKEを引き出してネイティブのveCAKEステーキングポジションを作成してください。

#### ロックされたCAKEを早期に引き出せますか？ <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

いいえ。

一度ロックされると、CAKEはアンロック時間までveCAKEコントラクトでステーキングされます。

#### CAKEを部分的に移行できますか？ <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

いいえ。

CAKEプールのポジション全体を一度に移行することしかできません。

#### iCAKE、bCAKE、vCAKE、rCAKEはどうなりますか？ <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**iCAKEについて：**

IFO iCAKEはveCAKEをサポートするようにアップグレードされました。詳細はこちら：

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**bCAKEについて：**

Farm boosting bCAKEはveCAKEをサポートするようにアップグレードされました。詳細はこちら：

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**vCAKEについて：**

Voting vCAKEはveCAKEをサポートするようにアップグレードされました。詳細はこちら：

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**rCAKEについて：**

すべてのveCAKE保有者（ネイティブまたは移行済み）は、新しい収益分配プールに自動的に登録されます。収益シェアは既存のスケジュールに従って配布されます。旧収益分配プールは廃止され、ユーザーはベネフィットカードに移動して保留中の報酬をクレームできます。詳細はこちら：

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[壊れたリンク](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### マルチシグウォレットはveCAKEの操作に使用できますか？

はい。

ただし、ホワイトリストに登録されていないアドレスに対して `noContract` 修飾子がveCAKEステーキングコントラクトに実装されています。固定期間CAKEステーキングプールからのステーキングまたは移行を有効にするには、すべてのコントラクトベースのマルチシグウォレットが一度だけ自己ホワイトリスト登録操作を実行する必要があります。

ホワイトリスト登録するには、以下のページのいずれかにアクセスしてください：

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

プロンプトが表示されます。「ホワイトリスト」をクリックし、マルチシグウォレットでトランザクションを進めてください。

veCAKEのオーナーに対してトランザクションが実行されます。このオーナーはコントラクトであり、任意のコントラクトが自己ホワイトリスト登録を実行できるパーミッションレスの書き込み関数を持っています。

プロンプトが表示されない場合は、[BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11)からトランザクションを実行する手順に従ってください：

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### なぜAPRが複数あるのですか？

CAKEをロックしてveCAKEを取得することで、PancakeSwapが構築した一連のプロダクトに関するさまざまな優れたメリットが得られます。メリットとインセンティブはさまざまな形式と異なるソースから提供されます。そのため、複数のAPRが存在します。

これらをすべて同時に獲得できるため、合計APRはすべてのAPRの合計になります。

veCAKEからの他の多くのメリット（[Farm Yield Booster bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)や[IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)など）はAPR形式では定量化できないことにご注意ください。ぜひこれらもご確認ください。

#### veCAKEプールAPRとは何ですか？

これはCAKEエミッションから来るインセンティブで、そのレートはveCAKEプール投票ゲージによって管理されます。

このゲージへのエミッションを増やすには、[ゲージ投票](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/)をご確認ください。

#### 収益分配APRとは何ですか？

これはDEXプロダクトで収集されたスワップ手数料から来るプロトコル収益分配によるインセンティブです。

詳細は[収益分配](/broken/pages/wQegezs7c6A2HzQjPEjh)をご覧ください。
