---
description: Migre para a nova Pool de Syrup de CAKE
---

# Pool de Syrup de CAKE

A nova CakePool é um novo contrato de stake de $CAKE construído com base no CakeVault (o atual pool automático de CAKE) e projetado para funcionar com o MasterChef v2 da PancakeSwap para fornecer a funcionalidade "stake $CAKE, ganhe $CAKE" enquanto oferece mais recursos, como stake de termo fixo. A pool de CAKE manual atual será retirada após a migração.&#x20;

A nova CakePool usará um token fictício para coletar $CAKE do MasterChef v2 e recompensar os usuários que fizerem stake de $CAKE. Os usuários que bloquearem seu $CAKE por mais tempo receberão um número mais significativo de participações (aumentados linearmente com base na duração), portanto, desfrutam de um rendimento maior

### Preciso migrar?

Se você atualmente está usando `enterStaking` e `leaveStaking` no MasterChef da PancakeSwap ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), você vai precisar migrar para o novo contrato.

### Não precisa mais fazer o reinvestimento

Com a novo CakePool, as recompensas são distribuídas proporcionalmente a todos os usuários do pool com base nas participações. Semelhante a “tokens com juros” ou outros modelos baseados em participação(shares), o saldo em stake dos usuários aumentará quando mais recompensas forem colocadas no pool. Os usuários não precisam colher e reinvestir suas recompensas.

### Taxas

Na nova CakePool, todos os usuários do stake flexível estarão sujeitos a dois conjuntos de taxas.

#### Taxa sobre recompensas de stake flexível

Uma taxa de 2% será aplicada a todas as recompensas geradas pelo stake flexível. O valor da taxa será calculado e realizado na próxima ação de depósito ou retirada, cortada das participações dos usuários. Para consultar o número da taxa de desempenho não realizada, use `calculatePerformanceFee(address _user)`.

#### Taxa de Saque

Uma taxa de saque de 0,1% será aplicada ao valor sacado do stake se você retirar dentro de 72 horas após a última ação de depósito. A taxa de saque é cortada do valor final da retirada antes da transferência do CAKE.

### Visão Geral

#### Depósito

Se você estiver usando o `enterStaking(uint256 _amount)` no MasterChef atual da PancakeSwap MasterChef. Você precisa migrar para `deposit(uint256 _amount, uint256 _lockDuration)`. Para o stake flexível, simplesmente use “0” como `_lockDuration`.

#### Saldo de Stake e Taxas

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

**Quantidade de CAKE em stake (antes de subtrair todas as taxas)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Taxa de Performance**&#x20;

Consulte o contrato:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Calcule manualmente:

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

**Taxa de Overdue: (só se aplica ao stake bloqueado)**

Consulta do contrato:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Calcule manualmente:

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

**Taxa de Saque**

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

**Quantidade de CAKE em stakie (depois de subtrair todas as taxas)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Recompensas Pendentes

Por favor, note que a nova pool não requer qualquer reinvestimento. As recompensas estão sendo colocadas em seu saldo de stake automaticamente.&#x20;

No entanto, você pode consultar o número de CAKE ganho desde a última ação, usando a diferença entre o saldo de stake atual (mencionado acima) e o número de`userInfo.cakeAtLastUserAction`.

#### Saque

Se você está usando o método `leaveStaking(uint256 _amount)` no atual MasterChef da PancakeSwap. Você precisa migrar para  `withdraw(uint256 _shares)`.

Ao fazer stake flexível. Observe que, ao retirar, as taxas de recompensa pendentes serão calculadas e cortadas do número de participações dos usuários, o número real de participações retirados será recalibrado, com base na porcentagem de participações que você está retirando em relação ao total das participações que você tem. Veja o exemplo abaixo:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Observe que o valor final do recebimento será afetado pela taxa de saque. Se sua função depende crucialmente do número final de CAKE sendo retirado, recomendamos calcular isso usando a diferença no saldo do CAKE antes e depois da ação de saque:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Ou calcule e subtraia a taxa de saque ao estimar o valor.

### **Ambiente de Testnet**

Você pode usar o seguinte ambiente de testnet para testar a integração do seu projeto com a nova Pool de CAKE da PancakeSwap. Se você tiver alguma dúvida, entre em contato com nossa equipe pelos canais existentes ou entre em contato com bun@pancakeswap.com por e-mail.

**Tokens Fictícios:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintável usando `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory e Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Nova Pool de CAKE

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
