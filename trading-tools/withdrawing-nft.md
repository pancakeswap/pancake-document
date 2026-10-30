# 🧙 Page 1

## Come prelevare il tuo NFT dal PancakeSwap NFT Marketplace

Le pagine del PancakeSwap NFT Marketplace non sono più disponibili, ma lo smart contract del marketplace è ancora attivo. Se hai messo in vendita un NFT e non è mai stato venduto, si trova ancora nel contratto del marketplace. Puoi recuperarlo da solo annullando l'inserzione direttamente su BscScan.

Ci vogliono pochi minuti per ogni NFT e costa solo una piccola quantità di BNB per il gas.

### Prima di iniziare

Ti serviranno:

* **Lo stesso portafoglio che hai usato per mettere in vendita l'NFT.** Solo il portafoglio che ha creato un'inserzione può annullarla.
* **Un portafoglio browser** (ad esempio MetaMask, l'estensione Trust Wallet o l'estensione Binance Wallet) impostato su **BNB Smart Chain**.
* **Una piccola quantità di BNB** per pagare il gas. Ogni NFT viene prelevato con una transazione separata.

Tieni a portata di mano questi indirizzi:

| Elemento                   | Indirizzo                                    |
| -------------------------- | -------------------------------------------- |
| Contratto del marketplace  | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Collezione Pancake Squad   | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Collezione Pancake Bunnies | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Resta al sicuro**
>
> * Interagisci solo con il contratto del marketplace `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Controlla sempre l'indirizzo nell'URL di BscScan.
> * Prelevare il tuo NFT **non** richiede mai di inviare BNB o token, e non richiede mai di firmare un'approvazione (`approve` o `setApprovalForAll`). Se un sito web o una persona ti chiede di farlo, è una truffa.
> * PancakeSwap non ti scriverà mai in DM e non ti chiederà mai la tua frase seed.

### Passaggio 1: Trova gli NFT che hai ancora in vendita

Per ogni NFT che vuoi prelevare ti servono due informazioni: l'**indirizzo della collezione** e il **token ID**.

1. Apri la [pagina Read Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) del contratto del marketplace su BscScan.
2. Trova ed espandi **`viewAsksByCollectionAndSeller`**.
3. Compila i campi:
   * `collection`: l'indirizzo della collezione dalla tabella sopra (ad esempio, Pancake Squad è `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: l'indirizzo del tuo portafoglio
   * `cursor`: `0`
   * `size`: `100`
4. Clicca su **Query**.
5. Guarda il risultato `tokenIds`. Questi sono i token ID che hai ancora in vendita in quella collezione, e sono gli NFT che puoi prelevare.
6. Se hai messo in vendita NFT in più di una collezione, ripeti i passaggi da 3 a 5 per ogni collezione.

**Se `tokenIds` è vuoto (`[]`)**, non hai inserzioni attive in quella collezione. Il tuo NFT è stato venduto (nel qual caso hai già ricevuto i BNB) oppure hai annullato l'inserzione in precedenza (nel qual caso è già tornato nel tuo portafoglio).

**Se hai più di 100 inserzioni** in una collezione, l'ultimo numero nel risultato è il cursor successivo. Esegui di nuovo la query usando quel numero come `cursor` per vedere le rimanenti.

**Se il tuo NFT appartiene a una collezione diversa da Pancake Squad o Pancake Bunnies**, espandi **`viewCollections`** nella stessa pagina, inserisci `cursor = 0` e `size = 100`, e clicca su **Query** per vedere tutte le collezioni supportate dal marketplace.

### Passaggio 2: Preleva il tuo NFT

1. Apri la [pagina Write Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) del contratto del marketplace su BscScan.
2. Clicca su **Connect to Web3** e collega lo stesso portafoglio che ha messo in vendita l'NFT. Assicurati che il tuo portafoglio sia su BNB Smart Chain.
3. Trova ed espandi **`cancelAskOrder`**.
4. Compila i campi:
   * `_collection`: l'indirizzo della collezione del Passaggio 1
   * `_tokenId`: il token ID del Passaggio 1, come semplice numero (ad esempio `1234`)
5. Clicca su **Write** e conferma la transazione nel tuo portafoglio. Non invii alcun BNB; paghi solo il gas.
6. Una volta che la transazione ha successo, l'NFT è tornato nel tuo portafoglio.
7. Ripeti per ogni NFT che vuoi prelevare.

Per verificare che abbia funzionato, esegui di nuovo il Passaggio 1. Il token ID non dovrebbe più comparire nell'elenco.

### Risoluzione dei problemi

| Problema                                                  | Cosa significa e cosa fare                                                                                                                                                                                                         |
| --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Errore: `Order: Token not listed`                         | Il portafoglio collegato non ha messo in vendita questo token ID in questa collezione, oppure l'NFT è già stato venduto o prelevato. Verifica di usare il portafoglio originale e l'indirizzo della collezione e il token ID corretti. |
| Il pulsante Write non fa nulla                            | Probabilmente il tuo portafoglio è sulla rete sbagliata. Passa a BNB Smart Chain e ricollega il portafoglio.                                                                                                                       |
| Gas esaurito o fondi insufficienti                        | Aggiungi una piccola quantità di BNB al tuo portafoglio per coprire il gas.                                                                                                                                                        |
| Non ho più accesso al portafoglio che ha messo in vendita l'NFT | Solo il portafoglio originale può annullare l'inserzione. Nessuno, compreso PancakeSwap, può prelevarlo per tuo conto.                                                                                                       |
