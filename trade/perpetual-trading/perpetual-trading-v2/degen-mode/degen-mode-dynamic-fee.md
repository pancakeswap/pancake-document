# Commissione Dinamica Modalità Degen

PancakeSwap Perpetuals Modalità Degen utilizza un modello di commissione dinamica. Questa commissione è progettata per addebitare commissioni in base al PnL e proteggere gli utenti dalle perdite.\
**Come funziona?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

dove:

* Pnl è il profitto o la perdita sulla posizione
* shareRate è il tasso di condivisione, ovvero la percentuale del nozionale pagata in commissioni (15% per impostazione predefinita)
* Notional è l'importo di denaro utilizzato per aprire la posizione
* closeMinRate è il tasso minimo di commissione di chiusura, ovvero l'importo minimo che puoi pagare per chiudere una posizione (0,03% per impostazione predefinita)

\
**Esempio:**

Se hai una posizione con un profitto di $100, un tasso di condivisione del 15% e un nozionale di $600, allora il tasso di commissione di chiusura sarebbe:

Tasso di commissione di chiusura = Max(100 \* 15% / 600, 0,03%) = 0,03%

In questo caso, il tasso di commissione di chiusura sarebbe dello 0,03%, il tasso minimo di commissione di chiusura.<br>

Nota:

La commissione di esecuzione verrà addebitata solo quando una posizione viene aperta. È fissata a 0,3 USD (BNB Chain)/ 0,2 USD (Arbitrum)/ 0,01 USD (opBNB)/ 0,3 USD (Base), simile a quanto addebitato quando si fa trading su coppie di trading perpetual classic. Non è prevista alcuna commissione di apertura posizione.

In caso di Liquidazione, il tasso di perdita liquida del 90% include la commissione di chiusura.
