# 🎁 Pancake Gifts

### 🎯 Cos'è Pancake Gifts?

**Pancake Gifts** permette a chiunque di inviare token — incluso gas opzionale — ad amici, utenti o community usando semplicemente un **link** o un **codice QR**. È un'esperienza semplice, sicura e senza gas per il destinatario.

È stato costruito per rendere l'onboarding nel mondo crypto facile come inviare un messaggio — senza finanziamento del portafoglio, senza Bridging, senza commissioni anticipate.

### 🤝 Perché abbiamo costruito Pancake Gifts

L'onboarding nel Web3 è ancora pieno di ostacoli. I nuovi utenti spesso si arrendono prima ancora di iniziare a causa di:

* **Nessun gas nel portafoglio** → impossibile eseguire qualsiasi azione on-chain
* **Nessun fondo sulla chain corretta** → è necessario il Bridging prima di usare le dApp
* **Bisogno di acquistare crypto solo per iniziare** → richiede la registrazione su un Exchange Centralizzato o un on-ramp fiat

Pancake Gifts elimina questi ostacoli:

* ✅ **Includendo token gas nativi** nel regalo così i destinatari possono interagire immediatamente
* ✅ **Sponsorizzando la commissione gas in anticipo** (il mittente paga una piccola commissione)
* ✅ **Abilitando il riscatto tramite un semplice link o QR** — nessun onboarding complesso



È uno strumento sia per:

* Nuovi utenti che iniziano on-chain
* Community native Web3 che vogliono **aumentare l'adozione, premiare gli utenti o gestire campagne** in modo più amichevole

***

### ⚙️ Riepilogo delle funzionalità

| Funzionalità              | Descrizione                                                         |
| ------------------------- | ------------------------------------------------------------------- |
| **Supporto chain**        | BNB Chain (lancio iniziale)                                         |
| **Tipi di codice regalo** | Link **o** codice QR                                                |
| **Uso singolo**           | Ogni codice può essere riscattato solo una volta                    |
| **Supporto token**        | Max 2 token: 1 BEP-20 (obbligatorio), 1 token gas nativo (opzionale) |
| **Importi personalizzati**| Imposta valori diversi per token                                    |
| **Commissione gas regalo**| Il mittente prepaga il gas (\~$0,05 in BNB)                         |
| **Cronologia regali**     | Gli utenti possono visualizzare tutti i regali inviati, lo stato del riscatto, la scadenza |
| **Controlli di sicurezza**| I token con commissioni di trasferimento e logica complessa sono bloccati |

### 🚫 Limitazioni

1. **Un regalo per codice** — i regali di massa non sono ancora supportati.
2. **I regali non possono essere ripristinati** — una volta annullati o scaduti, non possono essere riutilizzati.
3. **I token non supportati sono bloccati** — i token con commissioni di trasferimento o logica speciale mostreranno un errore durante la creazione.
4. **I tentativi di riscatto falliti vengono ripetuti** — il backend riprova alcune volte. Se ancora fallisce, il regalo viene contrassegnato come **non riscattabile** e deve essere annullato manualmente per recuperare i fondi.
5. **Il regalo deve essere riscattato sulla stessa chain** — ad es. un regalo ETH deve essere riscattato su Ethereum. Il riscatto cross-chain non è ancora supportato.

***

### 🕒 Logica di annullamento e scadenza

I regali seguono un ciclo di vita definito in base allo stato e al tempo:

#### Annullamento manuale

* Il **creatore** può annullare qualsiasi regalo ancora **non riscattato** e **entro la finestra di scadenza**.
* I token (meno la commissione gas iniziale del riscatto) verranno restituiti al mittente.
* I regali annullati **non possono** essere riattivati o riutilizzati.

#### Scadenza automatica

* I regali **scadono automaticamente** dopo un periodo definito dall'utente (predefinito: 7 giorni).
* I token non riscattati verranno **restituiti automaticamente** al portafoglio del mittente.
* Anche i regali scaduti non sono riutilizzabili.

***

### 🔄 Stati dei regali e loro significato

| Stato             | Descrizione                                                                 |
| ----------------- | --------------------------------------------------------------------------- |
| **In attesa**     | Il regalo è stato creato e attende il riscatto                              |
| **Riscattato**    | Il regalo è stato riscattato con successo da un destinatario                |
| **Annullato**     | Il regalo è stato annullato manualmente dal mittente                        |
| **Scaduto**       | Il regalo ha superato il tempo di scadenza senza essere riscattato          |
| **Non riscattabile** | Numero di tentativi superato; il regalo deve essere annullato per recuperare i fondi |

***

### ⚠️ Gestione degli errori e casi limite

1. **Token non supportato**
   * La creazione del regalo è bloccata per token con commissioni di trasferimento o logica speciale.
2. **Mancata corrispondenza del gas**
   * Se il **costo effettivo del gas per il riscatto ≥** alla commissione prepagata dal mittente, il riscatto fallisce automaticamente per evitare abusi. Verrà riprovato una volta che i livelli di commissione del gas rientrano nel range.
3. **Tentativi di riscatto falliti**
   * Verranno effettuati nuovi tentativi dopo il primo riscatto fallito.
   * Se ancora senza successo:
     * Il destinatario vede "Non riscattabile"
     * Il mittente deve annullare manualmente il regalo per recuperare i fondi e il destinatario dovrà richiedere un nuovo codice regalo.
