# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### Come vengono calcolati i moltiplicatori di bCAKE?

Potresti notare che ottieni moltiplicatori di boost bCAKE diversi quando fai Staking in Farm diverse.

Questo perché i moltiplicatori di bCAKE - Farm Booster vengono calcolati utilizzando le seguenti metriche al momento dell'attivazione o dell'aggiornamento:

* `userLpBalanceInFarm` : L'importo di Liquidità che stai mettendo in Staking nella Farm.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : L'importo totale di Liquidità in Staking nella Farm o la quantità attiva corrente di Liquidità nel pool LP V3. bCAKE sceglierà il numero minore tra i due.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : Il numero in tempo reale di veCAKE che hai
* `veCAKE.totalSupply` : La fornitura totale in tempo reale di veCAKE

Il moltiplicatore viene calcolato con il seguente metodo:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` e `constantB` sono impostati dal team e soggetti a futuri aggiustamenti in base al feedback della community e alle condizioni di mercato. `constantB` varia tra le diverse Farm per compensare le differenze di prezzo degli LP.

`constantA` e `constantB` possono essere recuperati tramite:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Ma in sintesi:

{% hint style="info" %}
**TL;DR**

Più LP (Liquidità) vuoi potenziare

Più CAKE devi bloccare per durate più lunghe
{% endhint %}

### Perché i miei moltiplicatori cambiano anche dopo l'attivazione?

Tieni presente che **qualsiasi azione dell'utente sulla posizione di farming o nel pool di Staking CAKE aggiornerà automaticamente il tuo moltiplicatore di boost** in base agli ultimi dati e statistiche delle Farm e del pool di Staking CAKE, inclusi ma non limitati a:

* Stake/Unstake della posizione nella/dalla Farm
* Riscossione delle ricompense CAKE dalla Farm
* Estensione della durata dello Staking CAKE
* Aggiunta di altri CAKE nella tua posizione di Staking a termine fisso
* Conversione della tua posizione di Staking CAKE a flessibile

{% hint style="warning" %}
Tieni presente:&#x20;

Per garantire equità e prevenire potenziali abusi e imbrogli con dati non aggiornati, il Farm Booster è progettato per essere permissionless e governato dalla community. Pertanto, **chiunque** può chiamare la funzione `updateLiquidity(address _tokenId)` sul contratto MasterChef V3 per aggiornare i moltiplicatori di boost di chiunque utilizzando gli ultimi dati.

Inoltre, il team monitorerà anche tutte le posizioni di farming abilitate a bCAKE e aggiornerà qualsiasi posizione con un moltiplicatore non aggiornato.
{% endhint %}

### Perché non riesco a potenziare una posizione?

1. Il Farm Booster è disponibile solo per Farm selezionate. In futuro saranno rese disponibili altre Farm. Per ora, **cerca la cifra APR verde con un'icona a razzo verde.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. A causa del coinvolgimento di più contratti, alcune interazioni richiedono un po' più di token gas (BNB). Assicurati quindi di avere abbastanza BNB nel tuo Portafoglio. Se l'errore persiste, prova ad aumentare manualmente il limite di gas della transazione.

### Qual è il moltiplicatore massimo di boost bCAKE che posso ottenere?

Attualmente, il boost massimo che un utente può ottenere per un Farm Booster è 2,5x, che offre 2,5x i APR originali.

Tieni presente che il boost massimo che puoi ottenere varia in base al tipo di Liquidità che stai cercando di mettere in Staking:

* V3: massimo 2x
* V2, StableSwap: massimo 2,5x
* Position Manager: massimo 2,5x

### Come posso aumentare i miei moltiplicatori di boost bCAKE?

* Aggiungere altri CAKE nella posizione di Staking veCAKE
* Estendere o rinnovare la durata della tua posizione di Staking veCAKE

In sintesi:

**Metti in Staking più CAKE, mettili in Staking per più tempo**

[Scopri di più su come vengono calcolati i moltiplicatori di boost bCAKE](faq.md#how-are-the-bcake-multipliers-calculated).

### Da dove provengono le ricompense CAKE extra potenziate?

**Tranquillo, non vengono allocate emissioni extra per rendere possibile bCAKE.**

In modo simile allo Staking CAKE con veCAKE, bCAKE aumenta la quota individuale degli utenti rispetto agli altri.

Sebbene l'APR base possa diminuire dopo il deployment di bCAKE, il team ritiene che sia un buon compromesso poiché avvantaggia i fedeli amanti di CAKE potenziando il loro rendimento di farming, crea più domanda per CAKE e rappresenta un ottimo incentivo per lo Staking di CAKE.

### Perché il moltiplicatore che ricevo è basso?&#x20;

bCAKE - Farm Booster funziona valutando sia la tua posizione di Staking veCAKE che la tua posizione di farming di Liquidità rispetto agli altri utenti. In sintesi:

> Se gli utenti vogliono potenziare più Liquidità nella Farm, devono bloccare più CAKE per durate più lunghe nel pool.

Questo design garantisce che i vantaggi non siano offerti solo ai grandi detentori, ma a qualsiasi utente che abbia una posizione di Staking CAKE considerevole rispetto alla posizione di farming.

Scopri di più su come viene calcolato il moltiplicatore [qui](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Perché ci sono solo x Farm disponibili per il boost?

Poiché bCAKE comporta l'aggiornamento di uno dei prodotti principali di PancakeSwap, ovvero il farming di Liquidità, il team vuole adottare un approccio più lento e graduale al lancio.

Pertanto, nella fase iniziale di rilascio del prodotto, molti dei parametri sono molto conservativi. Incluso il numero di Farm che gli utenti possono potenziare, quali Farm gli utenti possono potenziare, nonché il parametro di difficoltà per ricevere il moltiplicatore di boost.

**Il team regolerà i parametri in base al feedback della community.**

### **bCAKE V3 è stato sottoposto ad audit?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE è stato sottoposto ad audit sia da revisori interni che esterni.

Consulta i report di audit qui: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
