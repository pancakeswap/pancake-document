# Solana FAQ

### V3 Pools – Häufig gestellte Fragen (FAQ)

#### 1. Welche Gebührenstufen sind verfügbar?

**Unterstützte Gebührenstufen:**\
Die folgenden Gebührenstufen sind für V3-Pools (konzentrierte Liquidität) verfügbar:

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Gebührenverteilung (gilt für alle Gebührenstufen):**

* 84% an Liquiditätsanbieter (LPs)
* 16% an das Protokoll
  * 8% werden verbrannt
  * 8% gehen in die Protokoll-Treasury

#### 2. Kann jeder einen Pool erstellen?

Ja. Die Pool-Erstellung ist genehmigungsfrei, mit einigen Ausnahmen:

* Es kann nur ein Pool für eine bestimmte **Tokenpaar + Gebührenstufen**-Kombination existieren (z.B. kann es nur einen SOL<>USDC-0,1%-Pool gleichzeitig geben)
* Derzeit werden nur **SPL-Token** und ausgewählte **Token-2022**-Token unterstützt.

#### 3. Wie lange dauert es, bis ein neu erstellter Pool angezeigt wird?

* Pools erscheinen in der Regel etwa **5 Minuten** nach der Erstellung in der Pool-Liste.
* Falls er nicht erscheint:
  * Verwenden Sie die **Suchleiste**, um ihn manuell zu finden.
  * Pools können aufgrund eines **niedrigen TVL** aus der Liste gefiltert werden.

#### 4. Warum zeigt mein Pool immer noch null als APR oder TVL?

Dies ist direkt nach der Erstellung eines neuen Pools zu erwarten:

* APR- und TVL-Daten werden erst angezeigt, sobald **mindestens ein Swap** im Pool stattgefunden hat.
* Nach einem Swap werden diese Kennzahlen innerhalb von etwa **15 Minuten** angezeigt.

#### 5. Wie füge ich ein benutzerdefiniertes Token hinzu, um einen Pool zu erstellen?

So fügen Sie ein neues Token hinzu:

* Öffnen Sie in der Pool-Erstellungsoberfläche die Token-Auswahl.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Fügen Sie die Adresse des Tokens in die Suchleiste ein.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* Klicken Sie auf **„Add Token"** (Token hinzufügen).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* Das Token ist nun in der Liste durchsuchbar.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* So verwalten Sie Token:
  * Klicken Sie auf **„View Token List"** (Token-Liste anzeigen).
  *   Aktivieren oder deaktivieren Sie verschiedene Listen, einschließlich der **User Added Token List** (vom Benutzer hinzugefügte Token-Liste), die alle manuell hinzugefügten Token enthält.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Warum scheint meine erste Transaktion auf Solana teurer zu sein?

Solana verwendet **Associated Token Accounts (ATAs)**, um Token-Guthaben für jedes Wallet zu verwalten. Wenn Sie zum ersten Mal mit einem Token interagieren, muss Ihr Wallet ein ATA erstellen, was einmalige Kosten verursacht (in SOL bezahlt).

* Diese ATA-Erstellungsgebühr ist vom Solana-Protokoll vorgeschrieben und nicht spezifisch für PancakeSwap.
* Wenn das ATA später geschlossen wird, kann das **ursprünglich verwendete SOL zurückerstattet** werden.
