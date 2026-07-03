---
description: Migra al nuovo CAKE Syrup Pool
---

# CAKE Syrup Pool

Il nuovo CakePool è un nuovo contratto di Staking $CAKE costruito sulla base di CakeVault (l'attuale pool CAKE automatico) e progettato per funzionare con PancakeSwap MasterChef v2 per fornire la funzionalità "stake $CAKE, guadagna $CAKE" offrendo al contempo più funzionalità come lo Staking a termine fisso. L'attuale pool CAKE manuale sarà ritirato dopo la migrazione.

Il nuovo CakePool utilizzerà un token dummy per raccogliere $CAKE da MasterChef v2 e distribuirli agli utenti che stanno facendo Staking di $CAKE. Gli utenti che bloccano il loro $CAKE per periodi più lunghi riceveranno un numero più significativo di quote (aumentato linearmente in base alla durata), godendo quindi di un rendimento più elevato.

### Devo migrare?&#x20;

Se stai attualmente usando `enterStaking` e `leaveStaking` su PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), dovrai migrare al nuovo contratto.

### Nessun compounding

Con il nuovo CakePool, le ricompense vengono distribuite proporzionalmente a tutti gli utenti del pool in base alle quote. Simile ai "token che generano interessi" o altri modelli basati su quote, il saldo di Staking degli utenti crescerà man mano che vengono aggiunte più ricompense nel pool. Gli utenti non hanno bisogno di raccogliere e fare compounding delle loro ricompense.

### Commissioni&#x20;

Nel nuovo CakePool, tutti gli utenti in Staking flessibile saranno soggetti a due serie di commissioni.&#x20;

#### Commissione sulle ricompense dello Staking flessibile&#x20;

Una commissione del 2% si applicherà a tutte le ricompense generate dallo Staking flessibile. L'ammontare della commissione verrà calcolato e realizzato alla prossima azione di deposito o prelievo, sottraendolo dalle quote degli utenti. Per verificare il numero della commissione sulle performance non ancora realizzata, usa `calculatePerformanceFee(address _user)`.&#x20;

#### Commissione di prelievo&#x20;

Una commissione di prelievo dello 0,1% si applicherà all'ammontare dell'unstake se ritiri entro 72 ore dall'ultima azione di deposito. La commissione di prelievo viene sottratta dall'ammontare finale del prelievo prima del trasferimento di CAKE.

### Panoramica

#### Deposito

Se stai attualmente usando `enterStaking(uint256 _amount)` sul PancakeSwap MasterChef attuale, devi migrare a `deposit(uint256 _amount, uint256 _lockDuration)`. Per lo Staking flessibile, usa semplicemente "0" come `_lockDuration`.

#### Saldo di Staking e Commissioni

```
Global variables: CakePoolContract // CAKE pool contract
struct UserInfo {
    uint256 shares; // number of shares for a user.
    uint256 lastDepositedTime; // timestamp of the last deposit action
    uint256 cakeAtLastUserAction; // number of CAKE at the last user action
    uint256 lastUserActionTime; // timestamp of the last user action
    uint256 lockStartTime; // timestamp of the start of the lock.
    uint256 lockEndTime; // timestamp of the end of the lock.
    uint256 userBoostedShare; // the amount of shares boosted/added to the user.
    bool locked; // status of the lock
    uint256 lockedAmount; // number of CAKE locked at the start of the lock period.
}
```

**Ammontare CAKE in Staking (prima di sottrarre tutte le commissioni)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Commissione sulle performance**

Interrogazione dal contratto:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Calcolo manuale:

```
async function calculatePerformanceFeeAmount(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user);  //normal free fee users are some special contracts , so you can set default false

    if(user.shares > 0 && !user.locked && !isFreeFee){
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 totalAmount = user.shares * PricePerFullShare / 1e18; 
        uint256 earnAmount = totalAmount - user.cakeAtLastUserAction;
        uint256 performanceFee = await  CakePoolContract.performanceFee();
        uint256 currentPerformanceFee = (earnAmount * performanceFee) / 10000;
        return currentPerformanceFee;
    }
    return 0;
}
```

**Commissione di scadenza: (si applica solo allo Staking bloccato)**

Interrogazione dal contratto:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Calcolo manuale:

```
async function calculateOverdueFee(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //normal free fee users are some special contracts , so you can set default false
    const UNLOCK_FREE_DURATION = 1 week seconds (or you can get from smart contract,  const UNLOCK_FREE_DURATION = await CakePoolContract.UNLOCK_FREE_DURATION())
    const DURATION_FACTOR_OVERDUE = 180 * 24 * 3600; // 180 days, in order to calculate overdue fee. you can get it from contract too.

    if (
        user.shares > 0 &&
        user.locked &&
        !isFreeFee &&
        ((user.lockEndTime + UNLOCK_FREE_DURATION) < block.timestamp)
    ) {
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 currentAmount = user.shares * PricePerFullShare / 1e18 - user.userBoostedShare;
        uint256 earnAmount = currentAmount - user.lockedAmount;
        uint256 overdueDuration = block.timestamp - user.lockEndTime - UNLOCK_FREE_DURATION;  //  you can use UTC timestamp to replace current block.timestamp.
        if (overdueDuration > DURATION_FACTOR_OVERDUE) {
            overdueDuration = DURATION_FACTOR_OVERDUE;
        }
        // Rates are calculated based on the user's overdue duration.
        uint256 overdueWeight = (overdueDuration * overdueFee) / DURATION_FACTOR_OVERDUE;
        uint256 currentOverdueFee = (earnAmount * overdueWeight) / PRECISION_FACTOR;
        return currentOverdueFee;
    }
    return 0;
}
```

**Commissione di prelievo**

```
const user = await CakePoolContract.userInfo(address);
const withdrawFee = await  CakePoolContract.withdrawFee();
const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //normal free fee users are some special contracts , so you can set default false
let WithdrawFeeAmount = 0;
// you can use UTC timestamp to replace current block.timestamp.
// withdrawFeePeriod = 72 * 3600 (S)
// _amount : withdraw amount
if (!isFreeFee && (block.timestamp < user.lastDepositedTime + withdrawFeePeriod)) {
     WithdrawFeeAmount = _amount * withdrawFee;
}
```

**Ammontare CAKE in Staking (dopo aver sottratto tutte le commissioni)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Ricompense in sospeso&#x20;

Tieni presente che il nuovo pool non richiede alcun compounding. Le ricompense vengono aggiunte automaticamente al tuo saldo di Staking.

Tuttavia, puoi interrogare il numero di CAKE guadagnati dall'ultima azione, usando la differenza tra il saldo di Staking attuale (menzionato sopra) e il numero da `userInfo.cakeAtLastUserAction`.

#### Prelievo

Se stai usando il metodo `leaveStaking(uint256 _amount)` sul PancakeSwap MasterChef attuale, devi migrare a `withdraw(uint256 _shares)`.

Quando si fa Staking flessibile, tieni presente che al momento del prelievo, le commissioni sulle ricompense in sospeso verranno calcolate e sottratte dal numero di quote degli utenti, il numero effettivo di quote che vengono prelevate verrà ricalibrato in base alla percentuale delle quote che stai prelevando rispetto alle quote totali che hai. Vedi l'esempio qui sotto:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Tieni presente che l'ammontare finale ricevuto sarà influenzato dalla commissione di prelievo. Se la tua funzione dipende in modo cruciale dal numero finale di CAKE prelevati, ti consigliamo di calcolarlo usando la differenza nel saldo CAKE prima e dopo l'azione di prelievo:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Oppure, calcola e sottrai la commissione di prelievo quando stimi l'ammontare.

#### Come calcolare il CAKE per blocco distribuito al nuovo pool CAKE?

In precedenza, il pool CAKE manuale aveva un'emissione fissa di 10 CAKE/blocco. Dopo la migrazione a MasterChef v2 e il nuovo pool CAKE, possiamo ora regolarne le emissioni.

Ecco come puoi calcolare il CAKE per blocco distribuito al nuovo pool CAKE:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Puoi interrogare `cakePool.allocPoint` usando `MasterChef.poolInfo(0)`

### **Indirizzo del Contratto Mainnet**

**Nome del contratto:** CakePool\
**Indirizzo del contratto:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Visualizza il contratto PancakeSwap: Cake Pool su BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Ambiente Testnet**

Puoi usare il seguente ambiente testnet per testare l'integrazione del tuo progetto con il nuovo CAKE Pool di PancakeSwap. Se hai domande, contatta il nostro team tramite i canali esistenti, o scrivi a bun@pancakeswap.com via Email.

**Token Dummy:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (coniabile usando `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory e Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: CAKE Manuale
  * pid4: Pool Dummy per MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Nuovo CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
