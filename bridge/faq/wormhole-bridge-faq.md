---
hidden: true
---

# Wormhole Bridge よくある質問 (FAQ)

### Q: トランザクションを確認するにはどうすればよいですか？ <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormholeエクスプローラー

ブリッジのステータスページにWormhole Explorerでトランザクションを確認できるリンクが表示されます。送信元チェーンのトランザクションが完了したもののWormholeによる検証がまだの場合、トランザクションのステータスは以下のように表示されます：

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

「find redeem」オプションは、送信先チェーンのトランザクションを完了するための代替手段です。Wormhole Bridgeがスタックしたり、ブリッジトランザクションのステータスの更新に失敗した場合に、この方法をご利用いただけます。トランザクションを換金（redeem）するには、まずredeemボタンをクリックします。

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

次に、トランザクションを再開するためのオプションが表示されます。これをクリックすると、換金トランザクションを完了できるフォーラム（次の質問のリンク）に移動します。<br>

### Q: \<chain>にトークンを送信しましたが、送信元ウォレットからは出ているのに送信先ウォレットに届いていません。どうすればよいですか？[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

a) トークンを換金する必要があるか、すでに換金が完了している場合はb) ウォレットにトークンを追加する必要があります：

**a) 換金（Redeeming）：**

* [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem) にアクセスします
* 送信元チェーンと対応するトランザクションID（ウォレットまたはブロックチェーンのエクスプローラーでアドレスを検索して確認できます）を入力します

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* 「Recover」をクリックします
* 「Redeem」をクリックし、ウォレットの承認を受け入れます

**b) ウォレットにトークンを追加する：**

**Metamask：**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* Metamaskのアセットタブで「import tokens」をクリックします
* コントラクトアドレスは、関連するブロックエクスプローラーのトランザクションでトークン名をクリックして確認できます。トークン名をクリックすると新しいウィンドウが開き、コントラクトアドレスはプロファイルサマリーの右側に表示されます。
* シンボルも必要です。認識しやすい任意の名前を設定できます。
* 「add custom token」をクリックします

ビデオチュートリアル「MetamaskウォレットにトークンをManually追加する方法」は[こちら](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)でご覧いただけます。

### Xトークンをブリッジしましたが、スワップできません。DEXに流動性のあるマーケットがありません。[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

送信先チェーンに流動性のないトークンをブリッジしました。Portal Bridgeを使用してこのトークンを元に戻す必要があります。Portalの「select a token」検索フィールドにトークンのコントラクトアドレス（ウォレットまたはブロックチェーンエクスプローラーでアドレスを検索して確認できます）を貼り付けることで対応できます。

流動性マーケットの包括的な概要は[こちら](https://portalbridge.com/docs/faqs/liquid-markets)でご確認いただけます。

#### 送信先チェーンでトークンを換金するにはどうすればよいですか？[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

送金プロセス中に誤ってページを更新した場合や、トークンを換金しなかった場合は、[こちら](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow)のチュートリアルに従ってください。
