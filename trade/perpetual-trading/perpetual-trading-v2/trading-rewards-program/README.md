---
description: ApolloX lancerà il Programma di Ricompense di Trading su V2
hidden: true
---

# Programma di Ricompense di Trading

### Panoramica del Programma di Ricompense

I dettagli sono i seguenti:

Periodo di attività: Le date variano da ciclo a ciclo e per diverse chain

Orario di Distribuzione delle Ricompense: Ogni ciclo è dalle 00:00 (UTC) alle 23:59 (UTC) giornaliero. Le ricompense vengono emesse il giorno successivo intorno alle 03:00 (UTC). Gli utenti devono riscattare le loro ricompense entro 30 giorni dall'emissione. In caso contrario, la piattaforma revocherà le ricompense.&#x20;

Importo della ricompensa: Limitato a $15.000 USD in APX al giorno

Regole dell'attività: Gli utenti che fanno trading su V2 guadagnano da un pool di premi. Coloro che mettono in Staking APX nel DAO per ottenere veNFT godranno di moltiplicatori di potenziamento corrispondenti al valore Power calcolato dal veNFT.&#x20;

| Valore Power               | Moltiplicatore di Potenziamento  |
| ------------------------- | -------------------- |
| 50.000 < Power =<100.000  | 1,5                  |
| 100.000 < Power =<300.000 | 2                    |
| Power > 300.000           | 2,5                  |

Formula di calcolo delle Ricompense di Trading:&#x20;

Al termine di ogni ciclo di ricompense di trading, le commissioni di trading effettive dell'utente e l'importo in Staking in quel ciclo verranno calcolati per determinare il peso e l'importo delle ricompense APX. La formula è la seguente:

r = R\*W / sum(Wi)



Parametri:

| r       | Ricompensa APX dell'utente per questo ciclo                                                                                                                                                                                                                                                                                        |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Determinato dal contributo di commissioni di trading V2 dell'utente nel giorno precedente e dall'ultimo prezzo del token APX                                                                                                                                                                                                                                     |
| W       | <p>Punteggio di peso totale individuale W=f*w, dove;</p><p>f si riferisce alle commissioni di trading effettive contribuite dall'utente in questo ciclo, che verranno convertite in USD.</p><p>w è il Moltiplicatore di Potenziamento ottenuto dall'utente in questo ciclo dallo Staking di APX nel DAO. (Fare riferimento alla tabella sopra per ulteriori informazioni)</p> |
| sum(Wi) | Il punteggio totale di tutti gli utenti. Wi rappresenta il punteggio di qualsiasi singolo utente, e sum(Wi) rappresenta la somma di tutti i punteggi degli utenti                                                                                                                                                                                                                                                            |

&#x20;

La formula di calcolo per R è la seguente:

R=Min(Moltiplicatore valore in dollari \* Commissione di Trading, Limite valore in dollari)/ Max(Ultimo Prezzo APX, Prezzo Floor APX)

* Moltiplicatore valore in dollari: 0,70 questa epoch
* Commissione di Trading: Valore del reddito da commissioni V2 del giorno precedente convertito in USD
* Limite valore in dollari: 15.000 in base alla configurazione del sistema
* Ultimo Prezzo APX: Basato sull'ultimo prezzo del token APX
* Prezzo Floor APX: 0,04 questa epoch

Termini e Condizioni

* Dopo la fine di ogni ciclo, ApolloX può adeguare le regole del programma in base al feedback degli utenti e alle condizioni di mercato. Le ricompense verranno rilasciate in modo non lineare.
* Durante l'attività, la piattaforma ridurrà la percentuale del reddito da commissioni di trading V2 iniettato nel pool ALP dal 50% al 20%. Il restante 30% verrà utilizzato per riacquistare APX.
* A causa della differenza nelle commissioni di trading per ogni coppia di trading su V2, le ricompense ricevute dagli utenti possono variare anche se i loro volumi di trading effettivi sono gli stessi.
* Le ricompense da distribuire per ogni ciclo verranno archiviate nel seguente indirizzo contratto: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX si riserva il diritto di interpretazione finale per questa attività.

Avvertenza sul Rischio: Il trading di crypto futures comporta un rischio sostanziale. Tutte le attività di trading vengono eseguite a tua discrezione e a tuo rischio. Le informazioni qui contenute non devono essere considerate come consigli finanziari o di investimento da parte di ApolloX. ApolloX non sarà responsabile per eventuali perdite che potrebbero derivare dall'uso di ApolloX.

### Riscatto delle Ricompense

Poiché il programma di ricompense di trading è ospitato dai nostri amici di ApolloX, procedi con i seguenti passaggi per riscattare la tua ricompensa:\
\
Passo 1: Vai alla nostra [Pagina PancakeSwap Perpetuals](https://perp.pancakeswap.finance/en/futures/v2/)

Passo 2: Clicca sulla scheda Trading Reward (V2) nella parte superiore della pagina

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Passo 3: Verrai reindirizzato alla pagina di riscatto delle ricompense di ApolloX per controllare il tuo stato attuale della ricompensa. Clicca su "Claim" per riscattare le tue ricompense durante il periodo di attività.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
