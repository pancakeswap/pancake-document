---
description: Migrar al nuevo CAKE Syrup Pool
---

# CAKE Syrup Pool

El nuevo CakePool es un nuevo contrato de Staking de $CAKE construido basándose en CakeVault (el actual pool automático de CAKE) y diseñado para funcionar con PancakeSwap MasterChef v2 para proporcionar la funcionalidad "haz Staking de $CAKE, gana $CAKE" mientras ofrece más funciones como el Staking de plazo fijo. El pool Manual de CAKE actual será retirado después de la migración.

El nuevo CakePool usará un token ficticio para cosechar $CAKE de MasterChef v2 y recompensarlos a los usuarios que están haciendo Staking de $CAKE. Los usuarios que bloqueen su $CAKE por más tiempo recibirán una mayor cantidad de participaciones (potenciadas linealmente según la duración), disfrutando así de un mayor rendimiento.

### ¿Necesito migrar?&#x20;

Si actualmente usas `enterStaking` y `leaveStaking` en el PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), necesitarás migrar al nuevo contrato.

### Sin más compounding

Con el nuevo CakePool, las recompensas se distribuyen proporcionalmente a todos los usuarios del pool según sus participaciones. Similar a los "tokens con interés" u otros modelos basados en participaciones, el saldo de Staking de los usuarios crecerá cuando se agreguen más recompensas al pool. Los usuarios no necesitan cosechar y hacer compounding de sus recompensas.

### Comisiones&#x20;

En el nuevo CakePool, todos los usuarios de Staking flexible estarán sujetos a dos conjuntos de comisiones.&#x20;

#### Comisión sobre las recompensas de Staking flexible&#x20;

Se aplicará una comisión del 2% a todas las recompensas generadas por el Staking flexible. La cantidad de la comisión se calculará y realizará en la próxima acción de depósito o retiro, descontada de las participaciones del usuario. Para consultar el número de la comisión de rendimiento no realizada, usa `calculatePerformanceFee(address _user)`.&#x20;

#### Comisión de retiro&#x20;

Se aplicará una comisión de retiro del 0.1% al monto del retiro de Staking si retiras dentro de las 72 horas desde la última acción de depósito. La comisión de retiro se descuenta del monto final de retiro antes de la transferencia de CAKE.

### Descripción general

#### Depósito

Si actualmente usas `enterStaking(uint256 _amount)` en el PancakeSwap MasterChef actual, necesitas migrar a `deposit(uint256 _amount, uint256 _lockDuration)`. Para el Staking flexible, simplemente usa "0" como `_lockDuration`.

#### Saldo de Staking y comisiones

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

**Cantidad de Staking de CAKE (antes de restar todas las comisiones)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Comisión de rendimiento**

Consultar desde el contrato:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Calcularla manualmente:

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

**Comisión por vencimiento: (solo aplica al Staking bloqueado)**

Consultar desde el contrato:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Calcularla manualmente:

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

**Comisión de retiro**

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

**Cantidad de Staking de CAKE (después de restar todas las comisiones)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Recompensas pendientes&#x20;

Ten en cuenta que el nuevo pool no requiere ningún compounding. Las recompensas se agregan automáticamente a tu saldo de Staking.

Sin embargo, puedes consultar el número de CAKE ganados desde la última acción, usando la diferencia entre el saldo de Staking actual (mencionado anteriormente) y el número de `userInfo.cakeAtLastUserAction`.

#### Retiro

Si usas el método `leaveStaking(uint256 _amount)` en el PancakeSwap MasterChef actual, necesitas migrar a `withdraw(uint256 _shares)`.

Al hacer Staking flexible, ten en cuenta que al retirar, las comisiones de recompensas pendientes se calcularán y descontarán del número de participaciones del usuario. El número real de participaciones que se retiran se recalibrará según el porcentaje de las participaciones que retiras respecto al total de participaciones que tienes. Ve el ejemplo a continuación:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Ten en cuenta que el monto final recibido se verá afectado por la comisión de retiro. Si tu función depende críticamente del número final de CAKE retirados, te recomendamos calcularlo usando la diferencia en el saldo de CAKE antes y después de la acción de retiro:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

O calcula y resta la comisión de retiro al estimar el monto.

#### ¿Cómo calcular el CAKE por bloque distribuido al nuevo pool de CAKE?

Anteriormente, el pool Manual de CAKE tenía una emisión fija de 10 CAKE/bloque. Después de migrar a MasterChef v2 y al nuevo pool de CAKE, ahora podemos ajustar sus emisiones.

Y así es como puedes calcular el CAKE por bloque distribuido al nuevo pool de CAKE:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Puedes consultar `cakePool.allocPoint` usando `MasterChef.poolInfo(0)`

### **Dirección del contrato en Mainnet**

**Nombre del contrato:** CakePool\
**Dirección del contrato:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Ver el contrato PancakeSwap: Cake Pool en BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Entorno de Testnet**

Puedes usar el siguiente entorno de testnet para probar la integración de tu proyecto con el nuevo CAKE Pool de PancakeSwap. Si tienes alguna pregunta, contáctanos a través de los canales existentes, o comunícate con bun@pancakeswap.com por correo electrónico.

**Tokens ficticios:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (acuñable usando `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory y Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Pool ficticio para MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Nuevo CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
