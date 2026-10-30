# 🧙 Page 1

## So heben Sie Ihr NFT vom PancakeSwap NFT Marketplace ab

Die Seiten des PancakeSwap NFT Marketplace sind nicht mehr verfügbar, der Smart Contract des Marktplatzes ist jedoch weiterhin aktiv. Wenn Sie ein NFT zum Verkauf eingestellt haben und es nie verkauft wurde, wird es weiterhin vom Marketplace-Contract gehalten. Sie können es selbst zurückholen, indem Sie das Angebot direkt auf BscScan stornieren.

Das dauert nur wenige Minuten pro NFT und kostet lediglich einen kleinen Betrag an BNB für Gas.

### Bevor Sie beginnen

Sie benötigen:

* **Dieselbe Wallet, mit der Sie das NFT eingestellt haben.** Nur die Wallet, die ein Angebot erstellt hat, kann es stornieren.
* **Eine Browser-Wallet** (zum Beispiel MetaMask, die Trust Wallet Extension oder die Binance Wallet Extension), die auf **BNB Smart Chain** eingestellt ist.
* **Einen kleinen Betrag an BNB**, um Gas zu bezahlen. Jedes NFT wird in einer eigenen Transaktion abgehoben.

Halten Sie diese Adressen bereit:

| Element                    | Adresse                                      |
| -------------------------- | -------------------------------------------- |
| Marketplace-Contract       | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Pancake Squad Kollektion   | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Pancake Bunnies Kollektion | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Bleiben Sie sicher**
>
> * Interagieren Sie ausschließlich mit dem Marketplace-Contract `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Prüfen Sie immer die Adresse in der BscScan-URL.
> * Für das Abheben Ihres NFTs müssen Sie **niemals** BNB oder Token senden und auch niemals eine Freigabe (`approve` oder `setApprovalForAll`) signieren. Wenn eine Website oder Person Sie dazu auffordert, handelt es sich um Betrug.
> * PancakeSwap wird Ihnen niemals eine Direktnachricht senden oder nach Ihrer Seed-Phrase fragen.

### Schritt 1: Ihre noch eingestellten NFTs finden

Für jedes NFT, das Sie abheben möchten, benötigen Sie zwei Angaben: die **Kollektionsadresse** und die **Token-ID**.

1. Öffnen Sie auf BscScan die [Read-Contract-Seite](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) des Marketplace-Contracts.
2. Suchen Sie **`viewAsksByCollectionAndSeller`** und klappen Sie die Funktion auf.
3. Füllen Sie die Felder aus:
   * `collection`: die Kollektionsadresse aus der obigen Tabelle (zum Beispiel lautet sie bei Pancake Squad `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: Ihre Wallet-Adresse
   * `cursor`: `0`
   * `size`: `100`
4. Klicken Sie auf **Query**.
5. Sehen Sie sich das Ergebnis `tokenIds` an. Dies sind die Token-IDs, die Sie in dieser Kollektion noch eingestellt haben, und somit die NFTs, die Sie abheben können.
6. Wenn Sie NFTs in mehr als einer Kollektion eingestellt haben, wiederholen Sie die Schritte 3 bis 5 für jede Kollektion.

**Wenn `tokenIds` leer ist (`[]`)**, haben Sie in dieser Kollektion keine aktiven Angebote. Ihr NFT wurde entweder verkauft (in diesem Fall haben Sie die BNB bereits erhalten) oder Sie haben das Angebot zuvor storniert (in diesem Fall befindet es sich bereits wieder in Ihrer Wallet).

**Wenn Sie mehr als 100 Angebote** in einer Kollektion haben, ist die letzte Zahl im Ergebnis der nächste Cursor. Fragen Sie erneut ab und verwenden Sie diese Zahl als `cursor`, um die übrigen Einträge zu sehen.

**Wenn Ihr NFT aus einer anderen Kollektion als Pancake Squad oder Pancake Bunnies stammt**, klappen Sie auf derselben Seite **`viewCollections`** auf, geben Sie `cursor = 0` und `size = 100` ein und klicken Sie auf **Query**, um alle vom Marketplace unterstützten Kollektionen anzuzeigen.

### Schritt 2: Ihr NFT abheben

1. Öffnen Sie auf BscScan die [Write-Contract-Seite](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) des Marketplace-Contracts.
2. Klicken Sie auf **Connect to Web3** und verbinden Sie dieselbe Wallet, die das NFT eingestellt hat. Stellen Sie sicher, dass Ihre Wallet auf BNB Smart Chain eingestellt ist.
3. Suchen Sie **`cancelAskOrder`** und klappen Sie die Funktion auf.
4. Füllen Sie die Felder aus:
   * `_collection`: die Kollektionsadresse aus Schritt 1
   * `_tokenId`: die Token-ID aus Schritt 1, als einfache Zahl (zum Beispiel `1234`)
5. Klicken Sie auf **Write** und bestätigen Sie die Transaktion in Ihrer Wallet. Sie senden keine BNB; Sie zahlen lediglich Gas.
6. Sobald die Transaktion erfolgreich war, befindet sich das NFT wieder in Ihrer Wallet.
7. Wiederholen Sie den Vorgang für jedes NFT, das Sie abheben möchten.

Um zu überprüfen, ob es funktioniert hat, führen Sie Schritt 1 erneut aus. Die Token-ID sollte nicht mehr in der Liste erscheinen.

### Fehlerbehebung

| Problem                                                   | Bedeutung und was zu tun ist                                                                                                                                                                                                                |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fehler: `Order: Token not listed`                         | Die verbundene Wallet hat diese Token-ID in dieser Kollektion nicht eingestellt, oder das NFT wurde bereits verkauft oder abgehoben. Prüfen Sie, ob Sie die ursprüngliche Wallet sowie die richtige Kollektionsadresse und Token-ID verwenden. |
| Die Schaltfläche Write reagiert nicht                     | Ihre Wallet ist wahrscheinlich im falschen Netzwerk. Wechseln Sie zu BNB Smart Chain und verbinden Sie sich erneut.                                                                                                                         |
| Kein Gas mehr oder unzureichendes Guthaben                | Laden Sie einen kleinen Betrag an BNB in Ihre Wallet, um das Gas zu decken.                                                                                                                                                                 |
| Ich habe keinen Zugriff mehr auf die Wallet, die das NFT eingestellt hat | Nur die ursprüngliche Wallet kann das Angebot stornieren. Niemand, auch nicht PancakeSwap, kann es in Ihrem Namen abheben.                                                                                                  |
