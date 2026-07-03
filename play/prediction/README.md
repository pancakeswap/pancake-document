# 🔮 Prediction

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction è un mercato di previsione decentralizzato, divertente e semplice.

> **Prevedi se il prezzo di BNB, BTC o ETH salirà o scenderà – indovina correttamente per vincere!**

### Piattaforme

Puoi giocare a PancakeSwap Prediction su:

* **Desktop/ dApp**: [Guida a PancakeSwap Prediction](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini App (solo BNBUSD)**: [Prediction Bot](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Riepilogo: come funziona

1. **Scegli un asset su cui scommettere**: attualmente disponibile su **BNB Chain**, **zkSync Era** e **Arbitrum One**.
2. **Scegli SU o GIÙ**: prevedi se il prezzo dell'asset sarà più alto o più basso quando la fase "LIVE" termina (ogni round = 5 minuti).
3. Inserisci l'importo della tua scommessa: qualsiasi importo in BNB
4. **Blocca la tua posizione**: una volta inserita, la tua scommessa non può essere modificata.
5. **Vinci o perdi**:
   * Se hai scelto **SU**, vinci se il _Prezzo di chiusura_ > _Prezzo di blocco_ alla fine del round.
   * Se hai scelto **GIÙ**, vinci se il _Prezzo di chiusura_ < _Prezzo di blocco_ alla fine del round.

### Meccanismi e commissioni

* **Chain supportate: BNB Chain, zkSync Era, Arbitrum One**
* **Frequenza dei round**: ogni **5 minuti** (round continui).
* **Commissione di partecipazione**: **3%** del pool premi totale di ogni round, una parte del quale va per i **riacquisti di CAKE**.
* **Vincite**: riscuotibili in qualsiasi momento dopo che i risultati sono finalizzati.
* **I pagamenti** si basano sul rapporto delle scommesse in ciascun pool:
  * Rapporto di pagamento (Pool SU) = _(Valore totale di entrambi i pool ÷ Valore del Pool SU)_
  * Rapporto di pagamento (Pool GIÙ) = _(Valore totale di entrambi i pool ÷ Valore del Pool GIÙ)_
  * Vedi: [FAQ](prediction-faq.md) per un esempio pratico

### Risultati

* **Vinci:** Condividi il pot totale con gli altri vincitori (meno il 3% di commissione)
* **Perdi:** Perdi l'intero importo della tua scommessa

**Casi speciali**:

* **Pareggio** (Prezzo di blocco = Prezzo di chiusura): la casa vince tutte le scommesse.
* Se non ci sono scommesse opposte:
  * Se vinci: recuperi il 97% della tua scommessa iniziale (si applica il 3% di commissione).
  * Se perdi: la tua scommessa viene ceduta interamente alla casa.
* **Annullato:** ad es. per guasto dell'Oracle, agli utenti viene rimborsato l'importo della scommessa iniziale

### Feed di prezzo (Oracoli)

| Chain     | Mercati                                  | Scopo                                                                    | Oracolo                    |
| --------- | ---------------------------------------- | ------------------------------------------------------------------------ | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (paused) | Imposta il _Prezzo di blocco_ e il _Prezzo di chiusura_ (aggiornamento fino a ~20 secondi). | **Chainlink**              |
| BNB Chain | Tutti                                    | Alimenta il grafico live nell'interfaccia (solo di riferimento).         | Binance / TradingView Feed |

#### **Oracolo ChainLink**

* Utilizzato per il prezzo di blocco e il prezzo finale di ogni round del mercato di previsione. Si aggiorna a intervalli fino a 20 secondi.
* Il nostro contratto di previsione utilizza il feed di prezzi dell'Oracolo ChainLink su BNB Chain per impostare i prezzi usati per determinare se un utente ha vinto o meno.
* Utilizzato per il grafico "Chainlink" nell'interfaccia.

#### **Binance**

* Utilizzato per aggiornamenti dei prezzi in tempo reale nell'interfaccia del mercato di previsione di PancakeSwap.
* Utilizzato per il grafico "TradingView" nell'interfaccia.

Poiché utilizziamo due feed di prezzo diversi, gli aggiornamenti dei prezzi in tempo reale di Binance e il prezzo dell'Oracolo ChainLink possono differire di una piccola quantità. Tuttavia, non dovrebbero variare significativamente.

### Indirizzi dei contratti

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
