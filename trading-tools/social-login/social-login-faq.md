# FAQ di Social Login

{% hint style="info" %}
Per ulteriori informazioni consulta: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Panoramica generale

**1. Cos'è il social login di PancakeSwap e perché dovrei usarlo?**

Il social login ti permette di accedere a PancakeSwap usando il tuo account **Google**, **X (Twitter)**, **Discord** o **Telegram** — senza estensione del portafoglio o frase seed. Un portafoglio auto-custodiale viene creato in background, così puoi provare il DeFi immediatamente, anche con piccoli importi. Questo abbassa la barriera all'ingresso, specialmente nei momenti in cui il tempo è fondamentale.

**2. Quali chain supporta il social login?**

Il tuo portafoglio con social login funziona su tutte le chain attualmente supportate da PancakeSwap:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Tutti i portafogli sono **compatibili con EVM** e possono essere utilizzati su queste reti nativamente tramite PancakeSwap. Se vuoi vedere il supporto per altre chain (incluse quelle non-EVM), faccelo sapere!

**3. Dove posso usare il portafoglio con social login?**

Puoi usarlo direttamente in qualsiasi **browser** desktop o mobile tramite l'app web di PancakeSwap. **Non è compatibile** con app di portafoglio esterne o browser dApp.



### 🛠️ Configurazione e utilizzo del portafoglio

**4. Come viene creato e protetto il portafoglio?**

Il tuo portafoglio viene creato automaticamente al momento dell'accesso e protetto utilizzando un **sistema di condivisione della chiave 2-di-2**. Entrambe le condivisioni sono necessarie per ricostruire la chiave e generare una firma.

Per ulteriori informazioni sulla crittografia della condivisione consulta:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Quanti portafogli posso creare?**

Hai **un portafoglio per account social per dApp**. Ad esempio, se usi il tuo login Google su un'altra app che utilizza anche Privy, verrà creato un portafoglio separato.



### 🔐 Sicurezza e privacy

**6. Qualcuno può accedere al mio portafoglio se ruba il mio dispositivo?**

No. Anche se qualcuno ottiene accesso al tuo dispositivo, avrebbe comunque bisogno sia del tuo **social login** che (se impostata) della tua **password di recupero**.

**7. Quali dati vengono memorizzati da PancakeSwap o Privy?**

* PancakeSwap **non memorizza** nessuna condivisione di chiave relativa al portafoglio.
* Privy memorizza la **condivisione Auth crittografata e la condivisione di recupero (se il flusso di recupero non è configurato)**.

> Se non hai completato la configurazione del recupero, la tua condivisione di recupero rimane memorizzata da Privy per impostazione predefinita. Per ulteriori informazioni visita: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>


### 🔄 Recupero e gestione delle sessioni

**8. Posso usare lo stesso portafoglio su un dispositivo o browser diverso?**

Sì! Effettua semplicemente l'accesso con lo stesso account social. Se è un nuovo dispositivo, eseguirai il processo di recupero usando la tua password di recupero (se configurata).

**9. Cosa succede se cambio dispositivo?**

Ti verrà chiesto di accedere di nuovo con il tuo account social e di completare il flusso di recupero (configurazione della password). Se non hai impostato una password di recupero, l'accesso con l'account social è sufficiente.

**10. Cosa succede se perdo l'accesso sia al mio social login che al metodo di recupero?**

Se perdi l'accesso sia al tuo account social che al tuo metodo di recupero, **il tuo portafoglio non potrà essere recuperato**. Non c'è un fallback con frase seed e l'esportazione della chiave privata non è attualmente supportata.

> ⚠️ Ricorda: esportare la tua chiave privata, se abilitata in futuro, concederebbe pieno controllo del tuo portafoglio a chiunque la possieda — trattala con estrema cautela.

**11. Quanto durano le sessioni attive?**

Le sessioni durano 30 **giorni**. Dopo di ciò, ti verrà chiesto di **accedere di nuovo** e (se necessario) di reinserire le tue credenziali di recupero. Durante una sessione attiva, puoi effettuare transazioni senza dover approvare manualmente ogni azione.



### ⚙️ Compatibilità e limitazioni

**12. Posso esportare o importare portafogli?**

* **Esportazione**: non supportata per impostazione predefinita, per ragioni di sicurezza. Potrebbe cambiare in aggiornamenti futuri.
* **Importazione**: non supportata. Non puoi importare portafogli esterni come MetaMask o Phantom.

**13. Posso connettere questo portafoglio ad altre dApp usando WalletConnect?**

Non al momento. Il portafoglio integrato è **limitato solo a PancakeSwap**. Se sei interessato a usarlo più ampiamente, faccelo sapere — future espansioni sono possibili.



### 🚀 Funzionalità avanzate

**14. Il portafoglio con social login supporta l'Account Abstraction?**

Sì. Supporta le **funzionalità di Account Abstraction** come il raggruppamento delle transazioni e la **sponsorizzazione del gas** tramite integrazioni come Biconomy ecc.

**15. Come vengono abilitate le transazioni senza firma?**

* Dopo l'accesso, la tua sessione è attiva per un massimo di 30 **giorni**. Durante questo periodo, PancakeSwap può richiedere a Privy di firmare le transazioni per tuo conto usando le tue credenziali di sessione.&#x20;
* Non vedrai un popup del portafoglio per ogni azione — tutto viene gestito in background. Dopo 30 giorni, dovrai accedere di nuovo per continuare a usare questa esperienza senza firma.
