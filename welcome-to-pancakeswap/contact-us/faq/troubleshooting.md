---
description: Häufige Fehlermeldungen. Verwenden Sie die Seitenleiste ➡️, um direkt zum angezeigten Fehler zu springen.
---

# Fehlerbehebung

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

Manchmal stoßen Sie auf ein Problem, das keine eindeutige Lösung hat. Diese Tipps zur Fehlerbehebung können Ihnen helfen, auftretende Probleme zu lösen.

## **Probleme auf der Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

Sie versuchen, Token zu tauschen, aber Ihre Kursabweichungstoleranz ist zu gering oder die Liquidität ist zu niedrig.

{% tabs %}
{% tab title="Lösung" %}
1. Aktualisieren Sie die Seite und versuchen Sie es später erneut.
2. Versuchen Sie, jeweils einen kleineren Betrag zu handeln.
3. Erhöhen Sie Ihre Kursabweichungstoleranz:
   1. Tippen Sie auf das Einstellungssymbol auf der Liquiditätsseite.
   2. Erhöhen Sie Ihre Kursabweichungstoleranz etwas und versuchen Sie es erneut. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Versuchen Sie zuletzt, einen Betrag mit weniger Dezimalstellen einzugeben.
{% endtab %}

{% tab title="Grund" %}
**Dies geschieht in der Regel beim Handel mit Token mit geringer Liquidität.**

Das bedeutet, dass im Liquiditätspool nicht genug von einem der Token vorhanden ist, die Sie tauschen möchten: Es handelt sich wahrscheinlich um einen Token mit geringer Marktkapitalisierung, den nur wenige Personen handeln.

Es besteht jedoch auch die Möglichkeit, dass Sie versuchen, einen Betrugs-Token zu handeln, der nicht verkauft werden kann. In diesem Fall kann PancakeSwap einen Token weder sperren noch Gelder zurückerstatten.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Sie versuchen, Liquidität zu einem Liquiditätspool (LP) hinzuzufügen oder daraus zu entfernen, aber es ist nicht genug von einem der beiden Token im Paar vorhanden.

{% tabs %}
{% tab title="Lösung" %}
**Aktualisieren Sie die Seite und versuchen Sie es erneut oder versuchen Sie es später.**

Funktioniert es immer noch nicht?

1. Tippen Sie auf das Einstellungssymbol auf der Liquiditätsseite.
2. Erhöhen Sie Ihre Kursabweichungstoleranz etwas und versuchen Sie es erneut.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Grund" %}
Der Fehler wird durch den Versuch verursacht, Liquidität für einen Liquiditätspool (LP) mit einem unzureichenden Betrag von Token A oder Token B (einem der Token im Paar) hinzuzufügen oder zu entfernen.

Es könnte sein, dass die Preise zu schnell aktualisiert werden und Ihre Kursabweichungstoleranz zu gering ist.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Lösung für Fortgeschrittene" %}
Sie sind wirklich entschlossen, dieses Problem zu lösen. Wir empfehlen dies ausdrücklich nur, wenn Sie wissen, was Sie tun.

Derzeit gibt es keine einfache Möglichkeit, dieses Problem über die PancakeSwap-Website zu lösen: Sie müssen direkt mit dem Contract interagieren. Sie können Liquidität direkt über den Router-Contract hinzufügen und dabei amountAMin auf einen kleinen Betrag setzen und anschließend die gesamte Liquidität abheben.

**LP-Contract genehmigen**

Rufen Sie den Contract des LP-Tokens auf, den Sie genehmigen möchten.\
Hier ist zum Beispiel das ETH/WBNB-Paar: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Wählen Sie **Write Contract**, dann **Connect to Web3** und verbinden Sie Ihre Wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. Genehmigen Sie im **Abschnitt „1. approve"** den LP-Token für den Router, indem Sie Folgendes eingeben:
   1. spender (address): Geben Sie die Contract-Adresse des LP-Tokens ein, mit dem Sie interagieren möchten
   2. value (uint256): -1

**„balanceOf" abfragen**

1. Wechseln Sie zu **Read Contract.**
2. Geben Sie unter **5. balanceOf** Ihre Wallet-Adresse ein und klicken Sie auf **Query**.
3. Notieren Sie sich die angezeigte Zahl. Sie zeigt Ihr Guthaben im LP im uint256-Format an, das Sie im nächsten Schritt benötigen.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Liquidität hinzufügen oder entfernen**

Rufen Sie den Router-Contract auf: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Wählen Sie **Write Contract** und **Connect to Web3** wie oben.
2. Suchen Sie **addLiquidity** oder **removeLiquidity** (je nachdem, was Sie tun möchten)
3. Geben Sie die Token-Adressen beider Token im LP ein.
4. Geben Sie unter **liquidity (uint256)** die uint256-Zahl ein, die Sie aus „balanceOf" oben erhalten haben.
5. Setzen Sie **amountAMin** oder **amountBMin** auf einen niedrigen Wert: Versuchen Sie es mit 1 für beide.
6. Fügen Sie Ihre Wallet-Adresse unter **to (address)** hinzu.
7. Die Deadline muss eine Epoch-Zeit sein, die größer ist als die Zeit, zu der die Transaktion ausgeführt wird.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Dies kann zu sehr hoher Kursabweichung führen und dazu, dass der Nutzer einige Gelder verliert, wenn Frontrunning erfolgt
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Versuchen Sie es erneut, aber bestätigen Sie (signieren und senden Sie) die Transaktion, sobald Sie sie erstellt haben.

Dies ist passiert, weil Sie eine Transaktion gestartet haben, diese aber nicht bis zur Frist signiert und gesendet haben. Das bedeutet, dass Sie nicht schnell genug auf „Bestätigen" geklickt haben.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Versuchen Sie, den Betrag im „To"-Feld zu ändern, sodass das Symbol „(geschätzt)" auf „Von" angezeigt wird. Starten Sie dann sofort den Swap.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Dies geschieht normalerweise, wenn Sie versuchen, einen Token mit einer eigenen Gebühr zu tauschen.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Stellen Sie sicher, dass Sie 30 % mehr Token in Ihrer Wallet haben, als Sie handeln möchten, oder versuchen Sie, einen kleineren Betrag zu handeln. Wenn Sie das Maximum verkaufen möchten, versuchen Sie es mit 70 % oder 69 % statt 100 %.\
Verursacht durch das Design von Restorative-Rebase-Token wie tDoge oder tBTC.\
[Verstehen Sie, wie Restorative-Rebase-Token funktionieren](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Ein weiterer möglicher Grund für dieses Problem ist, dass der böswillige Token-Herausgeber den Handel für seinen Token gerade ausgesetzt hat oder den Verkauf nur für ausgewählte Wallet-Adressen ermöglicht. Führen Sie immer Ihre eigene Recherche durch, um potenziellem Betrug zu entgehen. Wenn der Token, den Sie zu tauschen versuchen, aber mit diesem Fehlercode scheitert, aus einem Airdrop stammt, handelt es sich höchstwahrscheinlich um einen Betrug. Führen Sie keine Token-Genehmigung durch und folgen Sie keinen Links – Ihre Gelder könnten in Gefahr sein, wenn Sie dies versuchen.

### Transaktion kann nicht erfolgreich sein

Versuchen Sie, einen kleineren Betrag zu handeln, oder erhöhen Sie die Kursabweichungstoleranz über das Einstellungssymbol und versuchen Sie es erneut. Dies wird durch geringe Liquidität verursacht.

### **Preisauswirkung zu hoch**

Versuchen Sie, einen kleineren Betrag zu handeln, oder erhöhen Sie die Kursabweichungstoleranz über das Einstellungssymbol und versuchen Sie es erneut. Dies wird durch geringe Liquidität verursacht.

### estimateGas fehlgeschlagen

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Lösung" %}
**Wenn Sie diesen Fehler beim Entfernen von Liquidität aus einem BNB-Paar erhalten haben:**

Bitte wählen Sie „Receive WBNB" und versuchen Sie es erneut.

**Wenn Sie diesen Fehler beim Tauschen erhalten haben:**

Wenden Sie sich bitte an das Projektteam des Tokens, den Sie zu tauschen versuchen. \*\*\*\* Dieses Problem muss vom Projektteam behoben werden.
{% endtab %}

{% tab title="Grund" %}
**Dieses Problem (beim Tauschen) wird durch Token verursacht, die den V1-PancakeSwap-Router fest in ihrem Contract kodiert haben.**

Obwohl diese Praxis bestenfalls nicht empfehlenswert ist, scheint der Grund dafür in der Tokenomics dieser Projekte zu liegen, bei denen jeder Kauf einen Prozentsatz des Tokens an LPs sendet.

Die betroffenen Projekte werden wahrscheinlich nicht mit dem V2-Router funktionieren: Sie müssen höchstwahrscheinlich neue Versionen ihrer Token erstellen, die auf unsere neue Router-Adresse verweisen, und alle bestehenden Token-Inhaber zu ihrem neuen Token migrieren.

Wir empfehlen, dass Projekte, die solche Token erstellt haben, auch Maßnahmen ergreifen sollten, um zu verhindern, dass ihre Nutzer diese zu V2-LP hinzufügen.

Die aktuelle Router-Adresse lautet [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Beim Versuch, Token zu tauschen, schlägt die Transaktion fehl und diese Fehlermeldung wird angezeigt. Dieser Fehler wurde auf Mobilgeräten mit Trust Wallet gemeldet.

{% tabs %}
{% tab title="Lösung" %}
1. Versuchen Sie die Transaktion erneut mit erhöhter Kursabweichungstoleranz.
2. Wenn Schritt 1 Ihr Problem nicht löst, erwägen Sie die Verwendung einer anderen Wallet, z. B. SafePal, für Ihre Transaktion.
{% endtab %}

{% tab title="Grund" %}
**Dies geschieht in der Regel beim Handel mit Token mit unzureichender Kursabweichungstoleranz in Trust Wallet.**

Die genauen Details des Problems werden noch untersucht.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Beim Versuch, Token zu tauschen, schlägt die Transaktion fehl und diese Fehlermeldung wird angezeigt. Dieser Fehler wurde auf verschiedenen Plattformen gemeldet.

{% tabs %}
{% tab title="Lösung" %}
1. Überprüfen Sie, ob ausreichende Mittel verfügbar sind.
2. Stellen Sie sicher, dass Sie dem Contract die Genehmigung erteilt haben, den Betrag der Gelder auszugeben, mit dem Sie handeln möchten.
{% endtab %}

{% tab title="Grund" %}
Dieser Fehler tritt beim Handel mit Token mit unzureichender Genehmigung auf oder wenn eine Wallet über unzureichende Mittel verfügt.\
Wenn Sie Token mit Restorative Rebase wie Tau-Assets tDoge oder tBTC handeln, stellen Sie sicher, dass Sie zunächst verstehen, wie sie funktionieren, mit dieser [Anleitung zu Rebase-Token](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Probleme mit Farms**

### Fail with error 'ds-math-sub-underflow'

Ihr LP-Token-Guthaben für den MasterChef-Contract ist aufgebraucht.

**Verwenden Sie einen Token-Genehmigungsmanager wie unrekt oder BscScan**

## **Probleme mit Syrup Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

Sie haben nicht genug SYRUP in Ihrer Wallet, um vom CAKE-CAKE-Pool zu entstaken.

**Besorgen Sie sich mindestens so viel SYRUP wie die Menge an CAKE, die Sie entstaken möchten.**

1. Kaufen Sie SYRUP auf der Exchange. Wenn Sie 100 CAKE entstaken möchten, benötigen Sie mindestens 100 SYRUP.
2. Versuchen Sie erneut zu entstaken.

Wenn dies immer noch nicht funktioniert, können Sie ein „emergencyWithdraw" direkt über den Contract durchführen, um Ihre gestakten Token zu entstaken.

1. Gehen Sie zu: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Klicken Sie auf **„Connect to Web3"** und verbinden Sie Ihre Wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Geben Sie im Abschnitt **„4. emergencyWithdraw"** „0" ein und klicken Sie auf „Write".

Dadurch werden Ihre gestakten Token entstakt und nicht geerntete CAKE-Erträge gehen verloren.

{% hint style="warning" %}
**Dadurch gehen alle noch nicht geernteten Erträge verloren.**
{% endhint %}

Um dies künftig zu vermeiden, **verkaufen Sie Ihr SYRUP nicht.** Sie benötigen es weiterhin, um vom „Stake CAKE Earn CAKE"-Pool zu entstaken.

Dieser Fehler ist aufgetreten, weil Sie SYRUP-Token verkauft oder übertragen haben. SYRUP wird im Verhältnis 1:1 zu CAKE geprägt, wenn Sie im CAKE-CAKE-Syrup-Pool staken. SYRUP muss im Verhältnis 1:1 zu CAKE beim Aufruf von leaveStaking (Entstaken Ihrer CAKE aus dem Pool) verbrannt werden. Wenn Sie daher nicht genug haben, können Sie nicht aus dem Pool entstaken.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Out-of-Gas-Fehler

> Warning! Error encountered during contract execution \[out of gas]

Sie haben beim Durchführen einer Transaktion ein zu niedriges Gas-Limit festgelegt.

{% tabs %}
{% tab title="Lösung" %}
Versuchen Sie, das **Gas-Limit** (nicht den Gas-Preis!) in Ihrer Wallet manuell zu erhöhen, bevor Sie die Transaktion signieren.

Ein Limit von 200.000 ist in der Regel ausreichend.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

Das obige Beispiel stammt aus MetaMask; lesen Sie die Dokumentation Ihrer Wallet, wenn Sie sich nicht sicher sind, wie Sie das Gas-Limit anpassen.
{% endtab %}

{% tab title="Grund" %}
Im Grunde genommen kann Ihre Wallet (MetaMask, Trust Wallet usw.) die beabsichtigte Aktion nicht abschließen.

Ihre Wallet schätzt, dass das Gas-Limit zu niedrig ist, sodass der Funktionsaufruf kein Gas mehr hat, bevor er abgeschlossen ist.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Lösung" %}
1. Verwenden Sie Unrekt.net, um die Genehmigung für den Smart Contract zu widerrufen, mit dem Sie interagieren möchten
2. Genehmigen Sie den Contract erneut, ohne eine Begrenzung des Ausgabeguthabens festzulegen
3. Versuchen Sie erneut, mit dem Contract zu interagieren.
{% endtab %}

{% tab title="Grund" %}
Dies geschieht, wenn Sie beim ersten Genehmigen des Contracts eine Begrenzung Ihres Ausgabeguthabens festgelegt haben und dann versuchen, mehr als das Limit zu tauschen.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Sie versuchen wahrscheinlich, von einem Syrup Pool mit geringen Erträgen zu entstaken. Lösung siehe unten.

Falls nicht, versuchen Sie möglicherweise, Token zu senden, die Sie nicht in Ihrer Wallet haben (z. B. einen Token zu senden, der bereits einer ausstehenden Transaktion zugewiesen ist). In diesem Fall stellen Sie einfach sicher, dass Sie die Token haben, die Sie verwenden möchten.

{% tabs %}
{% tab title="Lösung" %}
Teilen Sie zunächst [dem Team mit](../social-accounts.md), von welchem Pool Sie entstaken möchten, damit dieser die Erträge aufstocken kann. Wenn Sie es eilig haben zu entstaken und bereit sind, Ihre ausstehenden Erträge zu verlieren, versuchen Sie einen emergencyWithdraw:

Sie können ein „emergencyWithdraw" direkt über den Contract durchführen, um Ihre gestakten Token zu entstaken.

1. Suchen Sie die Contract-Adresse des Syrup Pools, von dem Sie entstaken möchten. Sie finden sie im Transaktionsprotokoll Ihrer Wallet.
2. Gehen Sie zu [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) und geben Sie in der Suchleiste die Contract-Adresse ein.
3. Wählen Sie **Write Contract.**
4. Klicken Sie auf **„Connect to Web3"** und verbinden Sie Ihre Wallet.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Klicken Sie im Abschnitt **„3. emergencyWithdraw"** auf „Write".

Dadurch werden Ihre gestakten Token entstakt und nicht geerntete Erträge gehen verloren.

{% hint style="warning" %}
**Dadurch gehen alle noch nicht geernteten Erträge verloren.**
{% endhint %}
{% endtab %}

{% tab title="Grund" %}
Dieser Fehler tritt häufig auf, wenn Sie versuchen, von einem alten Syrup Pool zu entstaken, bei dem beim Abheben nicht genügend Erträge im Pool verbleiben. Dadurch schlägt die Transaktion fehl.
{% endtab %}
{% endtabs %}

## **Probleme mit Prognose**

Überprüfen Sie [Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Sonstige Probleme**

### Provider-Fehler

> Provider Error\
> No provider was found

Dies geschieht, wenn Sie versuchen, sich über eine Browser-Erweiterung wie MetaMask oder Binance Chain Wallet zu verbinden, ohne die Erweiterung installiert zu haben.

{% tabs %}
{% tab title="Lösung" %}
Installieren Sie die offizielle Browser-Erweiterung zum Verbinden, oder lesen Sie unsere Anleitung zu [Verbinden einer Wallet mit PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### Nicht unterstützte Chain-ID

Wechseln Sie Ihre Chain zu BNB Smart Chain. Lesen Sie die Dokumentation Ihrer Wallet für eine Anleitung, wenn Sie Hilfe benötigen.

### Already processing eth\_requestAccounts. Please wait.

Stellen Sie sicher, dass Sie in Ihrer Wallet-App angemeldet sind und diese mit BNB Smart Chain verbunden ist.

### Probleme beim Kauf von SAFEMOON und ähnlichen Token

Um SAFEMOON zu handeln, müssen Sie auf das Einstellungssymbol klicken und **Ihre Kursabweichungstoleranz auf 12 % oder mehr setzen.**\
Dies liegt daran, dass **SafeMoon eine Gebühr von 10 % auf jede Transaktion erhebt**:

* 5 % Gebühr = wird an alle bestehenden Inhaber umverteilt
* 5 % Gebühr = wird zur Hinzufügung von Liquidität verwendet

Dies ist auch der Grund, warum Sie beim Kauf möglicherweise weniger Token erhalten als erwartet.\
Lesen Sie mehr unter [How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Interne JSON-RPC-Fehler

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Tritt auf, wenn Sie versuchen, Liquidität bei einigen Token über MetaMask zu entfernen. Die Ursache ist noch unbekannt. Versuchen Sie, eine alternative Wallet zu verwenden.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

Sie haben nicht genug BNB, um die Transaktionsgebühren zu bezahlen. Sie benötigen mehr BEP-20-Netzwerk-BNB in Ihrer Wallet.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Erhöhen Sie das Gas-Limit für die Transaktion in Ihrer Wallet. Lesen Sie die Dokumentation Ihrer Wallet, um zu erfahren, wie Sie das Gas-Limit erhöhen.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Ursache unklar. Versuchen Sie folgende Schritte, bevor Sie es erneut versuchen:

1. Gas-Limit erhöhen
2. Kursabweichung erhöhen
3. Cache leeren

## **Probleme mit dem Profil**

### Hoppla! In Ihrer Wallet wurden keine Pancake Collectibles gefunden.

Wir untersuchen die Logik hinter diesem Problem. Bitte versuchen Sie inzwischen die folgende Problemumgehung.

{% tabs %}
{% tab title="Problemumgehung 1" %}
1. Gehen Sie zur Seite „Collectible" und kehren Sie dann zur Profilseite zurück.\
   Wenn Sie den Link nicht finden, gehen Sie direkt zu [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles).
2. Versuchen Sie erneut, ein Profil zu erstellen.
{% endtab %}

{% tab title="Problemumgehung 2" %}
Ändern Sie die Umgebung.

* Leeren Sie den Cache und versuchen Sie es erneut.
* Versuchen Sie es in einem anderen Browser.
* Versuchen Sie es mit einer anderen Wallet-App.
* Versuchen Sie es in einem anderen Netzwerk (wechseln Sie zwischen WLAN und Mobilfunknetz).
{% endtab %}
{% endtabs %}

### Benutzernamenprüfung dreht sich endlos

Es gibt zwei mögliche Ursachen.

1. Sie haben mehrere Wallets im Browser installiert.
2. Netzwerkproblem.

{% tabs %}
{% tab title="Lösung 1" %}
Ursache: Sie haben mehrere Wallets im Browser installiert.\
\
Dies kann zu Konflikten zwischen Wallets führen. Dies liegt außerhalb der Kontrolle von PancakeSwap und wir können nichts dagegen tun.

1. Lassen Sie nur eine einzige Wallet im Browser installiert und entfernen Sie die anderen.
2. Verbinden Sie die Wallet erneut und versuchen Sie erneut, den Benutzernamen einzustellen.
{% endtab %}

{% tab title="Lösung 2" %}
Ursache: Das Netzwerk ist instabil.

Sie müssen es erneut versuchen.

1. Löschen Sie den gesamten Inhalt des Textfelds vollständig.
2. Geben Sie den Benutzernamen erneut ein und warten Sie einige Sekunden.
3. Wenn es nicht funktioniert, laden Sie die Seite neu und versuchen Sie es erneut.
{% endtab %}
{% endtabs %}
