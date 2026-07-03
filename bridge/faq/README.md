# ❓ Bridging よくある質問 (FAQ)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## ブリッジング前

1.  **モバイルウォレットやMetaMask以外のウォレットでCAKEをブリッジできますか？**

    現在、PancakeSwap CAKE BridgingはCoinbase Wallet、MetaMask、およびMetaMask対応ウォレットをサポートしています。より多くのウォレットのサポートは近日追加予定です。

    _ヒント：_ 秘密鍵やシードフレーズの危険なコピー＆ペーストを避けるため、ブリッジングにはデスクトップウォレット拡張機能で新しいウォレットを作成することをお勧めします。
2.  **ルートやトークンが利用できないのはなぜですか？**

    ルートによっては、ブリッジの容量、トークンのサポート、または流動性に依存します。後でもう一度確認するか、別のプロバイダーをお試しください。チェーンごとの利用可能なトークンはBridge UIに直接表示されます。
3.  **ブリッジングトランザクションの送信時にエラーが発生します。**

    「MAX」ボタンを使用せず、手動で金額を入力してみてください。必要に応じて金額から小数点以下を削除してください。
4.  **ブリッジングの見積もりに「Insufficient X to cover native fee」と表示されるのはなぜですか？**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    ブリッジングには、送信元チェーンのネイティブトークンでガス手数料を支払う必要があります。例：

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    トランザクションを完了するための手数料を賄えるだけのネイティブトークンが送信元ウォレットにあることを確認してください。
5.  **ボタンに「X CAKE Exceeded」と表示されるのはなぜですか？**

    安全確保のため、BSCとAptos間のCAKEブリッジには1日の上限があります。より少ない金額でお試しいただくか、時間をおいて再度お試しください。上限はChefによって需要に応じて動的に調整されます。
6.  **特定のトークンが見つかりません。**

    そのトークンは選択したルートでサポートされていないか、流動性が不足している可能性があります。別のチェーンまたは別の金額でお試しください。
7.  **BNB ChainからEthereumへのブリッジングで別のアドレスに送ることはできますか？**

    いいえ、安全上の理由から、ブリッジングはEVMチェーン間で同一アドレス間のみ機能します。
8.  **0.00000001 CAKE未満をブリッジできないのはなぜですか？**

    Aptos上のCAKEを含むAptosのトークンは、最大8桁の小数点以下しかサポートしません。0.00000001未満のトランザクションは拒否されるか切り捨てられます。これはEthereumへのブリッジングにも適用されます。余った金額は送信元ウォレットに残ります。

***

## ブリッジング後

1.  **確認後にブリッジ送金をキャンセルできますか？**

    いいえ、一度開始したブリッジトランザクションはプロバイダーによって処理されるため、キャンセルできません。元に戻すには、新しいトランザクションで資産を再度ブリッジしてください。
2.  **トランザクションが「pending（処理中）」のままスタックしている場合はどうすればよいですか？**

    ブリッジングには最大30分かかる場合があります。対応するブリッジプロバイダーのエクスプローラーでトランザクションハッシュを検索してステータスを確認してください：

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    60分経過後も処理中の場合は、[ソーシャルチャンネル](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)経由で管理者にお問い合わせください。
3. **CAKEを受け取っていません。どうすればよいですか？**
   * 初めてAptosにCAKEをブリッジする場合は、**手動でCAKEをクレームする**必要があるかもしれません。AptosウォレットにガスのためのAPTが十分にあることを確認してください。[Aptosブリッジングガイド](https://docs.pancakeswap.finance/bridge/bridging/aptos)と[Aptosの説明](https://theaptosbridge.com/faq#registering-claiming-assets)をご確認ください。
   * BNB ChainまたはEthereumへのブリッジング時、一部のウォレットでは残高を表示するためにCAKEのトークンアドレスを手動で追加する必要があります。例として、[MetaMaskのガイド](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/)をご参照ください。他のウォレットも同様の手順でご対応いただけます。
   * 60分経過後もCAKEが表示されない場合は、[ソーシャルチャンネル](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)経由で管理者にお問い合わせください。
