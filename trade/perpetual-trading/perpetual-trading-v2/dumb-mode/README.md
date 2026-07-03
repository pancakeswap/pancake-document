---
hidden: true
---

# Modalità Dumb

### Panoramica

La [**Modalità Dumb**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) su PancakeSwap Perpetuals offre un'esperienza di trading semplificata, ideale per i trader che preferiscono fare trading sulle fluttuazioni minuto per minuto del valore di un asset sottostante. La Modalità Dumb semplifica il trading riducendo il rumore, consentendo agli utenti di entrare e uscire facilmente da posizioni a breve termine.

### Come Funziona

Agli utenti viene offerta una selezione di finestre di scadenza di 5 minuti, 15 minuti, 30 minuti e 1 ora con diversi rapporti di ritorno sull'investimento. Gli utenti possono scegliere di andare long o short su un asset sottostante.

Alla fine del periodo di scadenza, se l'asset sottostante è in una posizione vincente (prezzo superiore al prezzo di apertura per i long, prezzo inferiore al prezzo di apertura per i short), gli utenti potranno guadagnare un profitto.

Ogni periodo di scadenza ha un diverso ritorno sull'investimento (ROI). Più lungo è il periodo di scadenza, maggiore è il ROI. Le percentuali e le commissioni sono le seguenti:<br>

| Periodo di Scadenza | ROI Vincente (al netto delle commissioni)\* | ROI Perdente | Commissioni (sulle Vincite) |
| ----------------- | --------------------------- | ---------- | ----------------- |
| 5 minuti         | 50%                         | -100%      | 6% sul collaterale  |
| 15 minuti        | 55%                         | -100%      | 6% sul collaterale  |
| 30 minuti        | 70%                         | -100%      | 6% sul collaterale  |
| 1 ora            | 83%                         | -100%      | 6% sul collaterale  |

\*Il ROI Vincente può essere aggiornato occasionalmente a seconda delle condizioni di mercato. Controlla questa pagina per eventuali aggiornamenti

Ad esempio, nel seguente scenario:

* Posizione Selezionata: Long
* Collaterale Versato: 100 USDT
* Periodo di Scadenza: 60 secondi
* Prezzo BTCUSD all'apertura: $50.000
* Prezzo BTCUSD dopo 60s: $50.001

L'utente guadagnerà **100USDT \* 75%= 75USDT**

Per ulteriori informazioni su come aprire una posizione in Modalità Dumb, clicca [qui](dumb-mode-guide.md).

### Mercati e Asset di Margine

La Modalità Dumb supporta il trading nei seguenti mercati e asset di margine su **BNB Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Mercato</td><td>Asset di Margine</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

La Modalità Dumb supporta il trading nei seguenti mercati e asset di margine su **Arbitrum, opBNB e Base Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Mercato</td><td>Asset di Margine</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

Il supporto per altri asset/chain è in fase di sviluppo.

### Commissioni

Una commissione del **6%** del capitale o collaterale viene addebitata in caso di trade vincente. Questo viene già calcolato prima del ROI.

<br>
