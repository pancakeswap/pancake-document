---
hidden: true
---

# Wormhole Bridge ガイド

### 免責事項

Wormhole Bridgeを使い始める前に、このガイドを必ずお読みください。このガイドでは、ステップごとにブリッジの使い方を説明するとともに、翻訳検索やトランザクション再開など、すぐに利用できる便利な機能についても紹介します。また、トラブルシューティングの手順についても記載しています。

### ブリッジングの実行

<figure><img src="https://lh7-us.googleusercontent.com/ZnR2zSNBpjyrzAs_JVlYdKCMDVYmOw4AVdJj_VIk0dmkvqTNxAC1ror2bEQlmSLeVGNV-PwhQSZdyquv-nCBPsHLjACy6LQsyM7M98dFrT9xKnZqC0aWYgUj0fjwC5pbZ9g1UwLalAU6DV-ORgPs-UY" alt=""><figcaption></figcaption></figure>

1. **PancakeSwap Wormhole Bridgeにアクセスする -** [**https://bridge.pancakeswap.finance/wormhole**](https://bridge.pancakeswap.finance/wormhole)
2. **送信元チェーンのウォレットを接続する** - 最初のステップはウォレットの接続です。ウィジェットを使用する場合、ブリッジしようとしているネットワークにウォレットをあらかじめ設定しておく必要はありません。Wormholeは選択したネットワークに基づいて自動的に正しいネットワークを設定します。EVMチェーンではMetamaskのみサポートされています。
3. **送信元チェーンのネットワークを選択する** - PancakeSwapは現在、Wormhole Bridgeで4つのネットワーク（Ethereum、Binance Smart Chain、Arbitrum、Base）をサポートしています。
4. **送信元チェーンのアセットを選択する** - ブリッジしたいトークンを選択します。&#x20;
5. **ステップ4、5、6について** - 送信先チェーンでステップ1、2、3を繰り返します。
6. ブリッジ金額を入力し、トランザクションの承認に進みます。ルートとブリッジは以下のように表示されます：

<figure><img src="https://lh7-us.googleusercontent.com/k6VhFctTcH__ojn3fMScEUUONGP_uPHk-s8OvVonboim7Cm37xCQhNiReTpUuo90_c81jg51pHVKsxhok50I6dwHWjBGZgB-yaIksikYP0aQB7uUaI1Wm6wK9uoYdZdygkViWnXWZcGnsBrPnivbij0" alt="" width="563"><figcaption></figcaption></figure>

7. 承認されてトランザクションが送信されると、トランザクションステータスページが表示されます：

<figure><img src="https://lh7-us.googleusercontent.com/RpERMKVOpXOJn56_-awggVO63Pl_KkkvQBzrwlD3jdEssKk7H6gznb7Np8ampHm3quG3doPGReqKFMyU1Fa4b0nlxjmSiZgSlY1WfEEAzbM_PcpZVRtESmXWol50wku4SE5oT8MgjfIwdoj8-rf-IBE" alt="" width="563"><figcaption></figcaption></figure>

ブリッジプロセスには3つのステップがあります。これらのステップには時間がかかる場合があり、通常、送信元チェーンのトランザクションで一定数のブロック確認が必要です。この確認閾値に達すると、Wormholeはトランザクションが成功したことを確認する証明を生成します。この証明は、送信先チェーンでブリッジされた資産をクレームするために必要です。

8. 検証が完了すると、表示されているクレームボタンをクリックしてブリッジされた資産をクレームできます：&#x20;

<figure><img src="https://lh7-us.googleusercontent.com/1OQVN7yTv2LcyZVpuwdZx4xxHsWFkGoSmfNSDDwJDSib47EVxmY-c_mD5EcfVGyb72KNdtZ-BC3CH_cWZtXNXVflFV8PP_577nIb4dG_Z1_O3rdoXETRWORZmgn4eUKyGAdmavmdzzA6YRA3aVA8_R8" alt="" width="563"><figcaption></figcaption></figure>
