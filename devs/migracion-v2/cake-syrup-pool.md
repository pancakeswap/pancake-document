# CAKE Syrup Pool

El nuevo CakePool es un nuevo contrato de staking de $CAKE construido sobre la base de CakeVault (el actual pool de CAKE automático) y diseñado para trabajar con PancakeSwap MasterChef v2 y proporcionar la funcionalidad de "Stake $CAKE, gana $CAKE" al tiempo que ofrece más características, como el staking a a plazo fijo. El pool de CAKE manual actual se retirará después de la migración.

El nuevo CakePool usará un token ficticio para realizar el harvest de $CAKE de MasterChef v2 y recompensarlos a los usuarios que están haciendo staking de $CAKE. Los usuarios que bloqueen sus $CAKE durante más tiempo recibirán un número más significativo de tenencias (boosteadas linealmente en función de la duración), por lo tanto, disfrutarán de un mayor rendimiento.

### Necesito migrar?&#x20;

Si estás usando `enterStaking` y `leaveStaking` en el contrato MasterChef  de  PancakeSwap ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), necesitarás migrar al nuevo contrato.

### No más compounding

Con el nuevo CakePool, las recompensas se distribuyen proporcionalmente a todos los usuarios del pool en función de las tenencias. Al igual que los "tokens que devengan intereses" u otros modelos basados en tenencias, el staking balance de los usuarios crecerá cuando se pongan más recompensas en el pool. Los usuarios no necesitan realizar harvest y reinvertir sus recompensas.

### Fees&#x20;

En el nuevo CakePool, todos los usuarios de staking flexibles estarán sujetos a dos conjuntos de fees.

#### Fee en recompensas de staking flexible&#x20;

Se aplicará una tarifa del 2% a todas las recompensas generadas por el staking flexible. El monto de la tarifa se calculará y realizará en la próxima acción de depósito o retiro, tomada de las tenencias de los usuarios. Para consultar el número de la tarifa no realizada, utilice `calculatePerformanceFee(address _user)`.

#### Fee de Retiro

Se aplicará una tarifa de retiro del 0.1% al monto de unstake si retira dentro de las 72 horas posteriores a la última acción de depósito. La tarifa de retiro se reduce del monto final del retiro antes de la transferencia de CAKE.

### Resumen

#### Deposit

Si actualmente estás usando `enterStaking(uint256 _amount)` en el contrato MasterChef de PancakeSwap. Deberás migrar a `deposit(uint256 _amount, uint256 _lockDuration).` Para staking flexible, use “0” en`_lockDuration`.

#### Staking Balance and Fees

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

**CAKE staking amount (before subtracting all the fees)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Performance Fee**

Consulta desde contrato:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Calculado Manualmente:

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

**Overdue Fee: (only applies to locked staking)**

Consulta desde contrato::

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Consulta desde contrato::

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

**Withdraw Fee**

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

**CAKE staking amount (luego de los fees)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Pending Rewards&#x20;

Tenga en cuenta que el nuevo pool no requiere ningún interés compuesto manual. Las recompensas se colocan en su saldo de depósito automáticamente.

\
Sin embargo, puede consultar el número de CAKE obtenidos desde la última acción, utilizando la diferencia entre el saldo de depósito actual (mencionado anteriormente) y el número de `userInfo.cakeAtLastUserAction`.

#### Withdraw

Si estás usando el método `leaveStaking(uint256 _amount)` en el actual PancakeSwap MasterChef. Necesitarás migrar a`withdraw(uint256 _shares)`.

Al hacer staking flexible, tenga en cuenta que al retirar, las tarifas de recompensa pendientes se calcularán y se reducirán del número de tenencias de los usuarios, el número real de tenencias que se retiran se volverá a calibrar, en función del porcentaje de las tenencias que está retirando contra el total de tenencias que tiene. Vea el ejemplo a continuación:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Tenga en cuenta que el monto final de recepción se verá afectado por la tarifa de retiro. Si su función depende fundamentalmente del número final de CAKE que se retira, le recomendamos que calcule utilizando la diferencia en el saldo de CAKE antes y después de la acción de retiro:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

O bien, calcule y reste la tarifa de retiro al estimar la cantidad.

### **Entorno Testnet**

Puede utilizar el siguiente entorno de testnet para probar la integración de tu proyecto con el nuevo PancakeSwap Cake Pool. Si tienes alguna pregunta, comuníquese con nuestro equipo a través de los canales existentes o a través de bun@pancakeswap.com.

**Dummy Tokens:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable usando `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory & Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Nuevo CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
