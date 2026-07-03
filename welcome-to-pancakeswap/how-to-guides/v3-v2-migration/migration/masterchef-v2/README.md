---
description: Migra a MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 è un nuovo contratto principale di Staking per i Farm, che offre maggiore flessibilità per regolare le emissioni di $CAKE, inclusi il pool CAKE, la combustione e altri prodotti PancakeSwap.

### Devo migrare?

Se stai attualmente usando PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), dovrai migrare al nuovo contratto ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Panoramica

#### Deposito&#x20;

Se stai attualmente usando `enterStaking(uint256 _amount)` sul PancakeSwap MasterChef attuale, devi migrare al nuovo contratto del pool CAKE. Consulta la documentazione correlata [qui](../cake-syrup-pool.md).

La funzione di deposito per i pool dei Farm è invariata. Tuttavia, dovrai aggiornare l'indirizzo del MasterChef e il `pid`, consulta la [lista dei Farm](list-of-farms.md) per l'elenco dei nuovi `pid` su MasterChef v2.

#### Tipi di pool

MasterChef v2 ha 2 tipi di pool: pool di Farm regolari e pool di Farm speciali, che puoi interrogare usando `poolInfo(_pid).isRegular` per il tipo di pool. Condividono un `totalAllocPoint` diverso, rendendoli due set di pool indipendenti.

Pool di Farm speciali: solo gli indirizzi in whitelist possono depositare. Sono solitamente utilizzati da prodotti interni di PancakeSwap per la distribuzione delle ricompense.

Pool di Farm regolari: i Farm di token LP regolari. Ad esempio CAKE-BNB, BNB-BUSD, ecc…

#### Prelievo

Se stai attualmente usando `leaveStaking(uint256 _amount)` sul PancakeSwap MasterChef attuale, devi migrare al nuovo contratto del pool CAKE. Consulta la documentazione correlata [qui](../cake-syrup-pool.md).

La funzione di prelievo per i pool dei Farm è invariata. Tuttavia, dovrai aggiornare l'indirizzo del MasterChef e il `pid`, consulta la [lista dei Farm](list-of-farms.md) per l'elenco dei nuovi `pid` su MasterChef v2.

#### Saldo di Staking

Usa `userInfo[_pid][_user].amount` per interrogare il saldo di Staking.

#### Token di Staking&#x20;

Tieni presente che il nuovo struct `PoolInfo` **non** contiene il campo dell'indirizzo del token lp, dovrai usare `lpToken(_pid)` per interrogare il token di Staking di qualsiasi pool.&#x20;

#### Quote/Ammontare totale in Staking

Usa `lpToken.balanceOf(MasterChef.address)` per ottenere l'ammontare totale in Staking per qualsiasi pool di Farm.

Tuttavia, in MasterChef v2, le quote degli utenti possono essere potenziate (in arrivo). Pertanto, le ricompense vengono calcolate usando un nuovo campo `totalBoostedShare` in `PoolInfo` come quote totali di ogni pool. Ad esempio, se il pool 0 ha 2 utenti, l'utente1 fa Staking di 100 LP (senza boost), l'utente2 fa Staking di 100 (con `boostMultiplier` pari a 1.05), allora `totalBoostedShare` diventerà 205. Di conseguenza l'utente2 guadagnerà più ricompense.

#### CakePerBlock

Puoi usare `cakePerBlock(bool _isRegular)` per interrogare la ricompensa CAKE per blocco che va a tutti i Farm di PancakeSwap.

### Indirizzo del Contratto Mainnet

**Nome del contratto:** MasterChef v2\
**Indirizzo del contratto:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Visualizza il contratto PancakeSwap: Main Staking Contract v2 su BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Ambiente Testnet

Puoi usare il seguente ambiente testnet per testare l'integrazione del tuo progetto con il nuovo PancakeSwap MasterChef v2. Se hai domande, contatta il nostro team tramite i canali esistenti, o scrivi a bun@pancakeswap.com via Email.

**Token Dummy:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (coniabile usando `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (coniabile usando `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory e Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Coppie LP

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: CAKE Manuale
  * pid4: Pool Dummy per MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
