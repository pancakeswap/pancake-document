# ❓ Bridging FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Vor dem Bridging

1.  **Kann ich mobile Wallets oder andere Wallets als MetaMask zum Bridging von CAKE verwenden?**

    Derzeit unterstützt PancakeSwap CAKE Bridging Coinbase Wallet, MetaMask und MetaMask-kompatible Wallets. Weitere Wallet-Unterstützung folgt in Kürze.

    _Tipp:_ Um riskantes Kopieren und Einfügen von privaten Schlüsseln oder Seed-Phrasen zu vermeiden, empfehlen wir, neue Wallets über Desktop-Wallet-Erweiterungen für das Bridging zu erstellen.
2.  **Warum ist eine Route oder ein Token nicht verfügbar?**

    Einige Routen hängen von der Bridge-Kapazität, der Token-Unterstützung oder der Liquidität ab. Bitte versuchen Sie es später erneut oder wählen Sie einen anderen Anbieter. Verfügbare Token pro Chain werden direkt in der Bridge-Benutzeroberfläche angezeigt.
3.  **Beim Einreichen der Bridging-Transaktion erhalte ich einen Fehler.**

    Versuchen Sie, den Betrag manuell einzugeben, anstatt den „MAX"-Button zu verwenden, und entfernen Sie gegebenenfalls Dezimalstellen aus dem Betrag.
4.  **Warum zeigt mein Bridging-Angebot „Insufficient X to cover native fee"?**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Bridging erfordert Gasgebühren, die im nativen Token der Quell-Chain bezahlt werden, zum Beispiel:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Stellen Sie sicher, dass Sie genügend native Token in Ihrer Quell-Wallet haben, um die Gebühren für die Transaktion zu decken.
5.  **Warum zeigt der Button „X CAKE Exceeded"?**

    Es gibt ein tägliches Kapazitätslimit für das Bridging von CAKE zwischen BSC und Aptos, um die Sicherheit zu gewährleisten. Versuchen Sie einen kleineren Betrag oder warten Sie und versuchen Sie es später erneut. Die Limits werden von den Chefs dynamisch basierend auf der Nachfrage angepasst.
6.  **Warum kann ich einen bestimmten Token nicht finden?**

    Der Token wird möglicherweise auf Ihrer gewählten Route nicht unterstützt oder es fehlt Liquidität. Versuchen Sie eine andere Chain oder einen anderen Betrag.
7.  **Kann ich von BNB Chain nach Ethereum, aber an eine andere Adresse bridgen?**

    Nein, aus Sicherheitsgründen funktioniert Bridging nur zwischen der gleichen Adresse auf EVM-Chains.
8.  **Warum kann ich nicht weniger als 0,00000001 CAKE bridgen?**

    Aptos-Token, einschließlich CAKE auf Aptos, haben maximal 8 Dezimalstellen. Transaktionen unter 0,00000001 werden abgelehnt oder abgerundet. Dies gilt auch für das Bridging zu Ethereum. Verbleibende Beträge verbleiben in Ihrer Quell-Wallet.

***

## Nach dem Bridging

1.  **Kann ich eine Bridge-Übertragung nach der Bestätigung stornieren?**

    Nein, sobald die Bridge-Transaktion gestartet ist, wird sie vom Anbieter abgewickelt und kann nicht storniert werden. Um den Vorgang umzukehren, bridgen Sie die Assets über eine neue Transaktion zurück.
2.  **Was passiert, wenn meine Transaktion als „ausstehend" feststeckt?**

    Bridging kann bis zu 30 Minuten dauern. Überprüfen Sie den Status Ihrer Transaktion, indem Sie den Transaktions-Hash im jeweiligen Block-Explorer des Bridge-Anbieters suchen:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    Falls die Transaktion nach 60 Minuten noch ausstehend ist, wenden Sie sich bitte über unsere [sozialen Kanäle](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) an unsere Administratoren.
3. **Ich habe meine CAKE nicht erhalten. Was soll ich tun?**
   * Beim erstmaligen Bridging von CAKE nach Aptos müssen Sie Ihre CAKE möglicherweise **manuell abrufen**. Stellen Sie sicher, dass Ihre Aptos-Wallet genügend APT für Gas hat. Weitere Informationen finden Sie im [Aptos Bridging-Leitfaden](https://docs.pancakeswap.finance/bridge/bridging/aptos) und der [Aptos-Erklärung](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Beim Bridging nach BNB Chain oder Ethereum erfordern einige Wallets, dass Sie die Token-Adresse von CAKE manuell hinzufügen, um Ihr Guthaben anzuzeigen. Folgen Sie beispielsweise diesem [MetaMask-Leitfaden](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) – andere Wallets sollten ähnliche Abläufe haben.
   * Falls Sie Ihre CAKE nach 60 Minuten immer noch nicht sehen, wenden Sie sich über unsere [sozialen Kanäle](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) an unsere Administratoren.
