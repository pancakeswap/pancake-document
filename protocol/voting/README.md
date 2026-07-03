# 📔 Governance

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Come parte dell'[aggiornamento Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), questa pagina è stata aggiornata il 15 maggio 2025
{% endhint %}

Il voto dà voce alla community di PancakeSwap, permettendo alla community di avere voce in capitolo su come PancakeSwap si svilupperà in futuro.

Consulta il [portale di voto nativo di PancakeSwap](https://pancakeswap.finance/voting) e la nostra pagina del [Forum](https://forum.pancakeswap.finance/).

## Meccanismi di voto

:notebook\_with\_decorative\_cover:Riepilogo - Cosa è cambiato (dopo l'[Aggiornamento Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Componente di Governance</th><th width="218.01953125">Prima di Tokenomics 3.0</th><th width="205.1796875">Dopo Tokenomics 3.0</th><th>Stato<select><option value="q1dVFsCri7zA" label="✅ Modificato" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Invariato" color="blue"></option></select></th></tr></thead><tbody><tr><td>Potere di voto</td><td>1 veCAKE = 1 potere di voto</td><td>1 CAKE = 1 potere di voto</td><td><span data-option="q1dVFsCri7zA">✅ Modificato</span></td></tr><tr><td>Delega</td><td>Consentita (tramite meccaniche veCAKE)</td><td>La delega non è consentita</td><td><span data-option="q1dVFsCri7zA">✅ Modificato</span></td></tr><tr><td>Soglia di invio proposta</td><td>Snapshot 100K veCAKE richiesto</td><td>Snapshot 100K CAKE richiesto</td><td><span data-option="q1dVFsCri7zA">✅ Modificato</span></td></tr><tr><td>Proposte Core vs Community</td><td>Ruoli e scopi definiti per ogni tipo di proposta</td><td>Nessun cambiamento</td><td><span data-option="4AGl26rwjYcI">🔁 Invariato</span></td></tr><tr><td>Periodo di voto</td><td>Community: Fisso<br>Core: Variabile</td><td>Nessun cambiamento</td><td><span data-option="4AGl26rwjYcI">🔁 Invariato</span></td></tr><tr><td>Tempistica Snapshot</td><td>Al blocco in cui viene pubblicata la proposta</td><td>Nessun cambiamento</td><td><span data-option="4AGl26rwjYcI">🔁 Invariato</span></td></tr><tr><td>Quorum</td><td>Nessun quorum minimo</td><td>Nessun cambiamento</td><td><span data-option="4AGl26rwjYcI">🔁 Invariato</span></td></tr></tbody></table>

### 1. **Potere di voto (Modificato)**

* **Tutti i detentori di CAKE hanno diritti di voto diretti.**
* **Il potere di voto corrisponde direttamente al numero di CAKE detenuti nell'indirizzo del portafoglio durante lo snapshot**
  * **1 CAKE = 1 potere di voto**
  * **I CAKE in staking nelle Syrup Pool non contano** verso il tuo potere di voto, poiché non fanno parte del saldo del tuo portafoglio al momento dello snapshot
  * Saldo snapshot = Stesso blocco in cui viene pubblicata la proposta
* **La delega non è più supportata.** Ogni detentore di CAKE deve votare individualmente.

### 2. **Invio di proposte (Invariato)**

* **Come inviare una proposta**
  * Invia su [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Deve includere:
    * Titolo
    * Contenuto
    * Descrizione
    * Azione/i on-chain (se necessario)
    * Durata del voto
* Tipi di proposte
  1.  Proposte Core

      * Possono essere proposte solo dal **Team Core di PancakeSwap**.
      * Richiedono un voto da parte dei detentori di CAKE.
      * Se approvate, verranno implementate dal team di PancakeSwap.

      Esempi

      1. Aggiustamenti del protocollo (modifiche ai prodotti, modifiche alle commissioni)
      2. Utilizzi significativi dei fondi per la Crescita dell'Ecosistema non coperti da proposte precedenti
  2. Proposte Community
     * Le proposte **Community** sono pubblicate dalla community di PancakeSwap. Vengono utilizzate per proporre idee ed esprimere il punto di vista della community. Sono **suggerimenti non vincolanti** della community.
     * Chiunque con **100.000 CAKE (saldo snapshot)** può inviarle.
     * Il team di PancakeSwap può adottare proposte valide in future Proposte Core
     * I membri della community possono anche utilizzare il nostro [Forum](https://forum.pancakeswap.finance/) per fornire feedback e fare suggerimenti al protocollo.

### **3. Durata del voto (Invariata)**

* Tutti i detentori di CAKE possono votare **durante la finestra di voto** per ogni proposta.
  * Proposta Community: Fissa a 3 giorni
  * Proposta Core: Variabile, impostata da PancakeSwap
* Il tuo potere di voto è determinato da uno **snapshot del tuo saldo CAKE al blocco in cui viene pubblicata la proposta**.
* **Aggiungere più CAKE dopo la pubblicazione della proposta non aumenterà il tuo potere di voto** per quel voto specifico.

Per i dettagli completi, consulta la [Guida al Voto](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Esito del voto (Invariato)**

* L'esito è basato sul **totale dei voti espressi** (CAKE totali utilizzati per votare)
* **Al momento non è richiesto un quorum minimo** affinché una proposta venga approvata.

## Nota: Diritti di veto

Per proteggere il protocollo, il **Team Core di PancakeSwap si riserva il diritto di intervenire in situazioni critiche** — come minacce alla sicurezza o problemi che influenzano il funzionamento stabile della piattaforma — **senza richiedere un voto della community o un sondaggio Snapshot**.

In qualsiasi caso in cui venga esercitata un'azione di veto, il Team Core **condividerà pubblicamente una spiegazione chiara** della decisione.

**Le possibili azioni di veto possono includere:**

1. **Sospensione temporanea degli smart contract** per correggere bug urgenti o vulnerabilità.
