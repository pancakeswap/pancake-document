---
description: Миграция на новый CAKE Syrup Pool
---

# CAKE Syrup Pool

Новый CakePool — это новый контракт стейкинга $CAKE, созданный на основе CakeVault (текущего авто-пула CAKE) и разработанный для работы с PancakeSwap MasterChef v2 с целью предоставления функциональности «стейкируй $CAKE, зарабатывай $CAKE» с дополнительными функциями, такими как стейкинг с фиксированным сроком. Текущий Manual CAKE pool будет закрыт после миграции.

Новый CakePool будет использовать фиктивный токен для получения $CAKE из MasterChef v2 и распределения их пользователям, стейкирующим $CAKE. Пользователи, блокирующие $CAKE на более длительный срок, получат большее количество долей (линейно увеличивается в зависимости от продолжительности), что обеспечивает более высокую доходность.

### Нужно ли мне мигрировать?&#x20;

Если ты сейчас используешь `enterStaking` и `leaveStaking` на PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), тебе нужно будет мигрировать на новый контракт.

### Больше не нужно компаундировать

В новом CakePool награды распределяются пропорционально всем пользователям пула на основе долей. Аналогично «процентным токенам» или другим моделям на основе долей, баланс стейкинга пользователей будет расти по мере добавления наград в пул. Пользователям не нужно собирать и компаундировать свои награды.

### Комиссии&#x20;

В новом CakePool все пользователи гибкого стейкинга будут облагаться двумя видами комиссий.

#### Комиссия за вознаграждения при гибком стейкинге&#x20;

К всем вознаграждениям, полученным от гибкого стейкинга, будет применяться комиссия в размере 2%. Сумма комиссии рассчитывается и реализуется при следующем действии депозита или вывода, вычитаясь из долей пользователя. Для запроса суммы нереализованной комиссии за производительность используй `calculatePerformanceFee(address _user)`.

#### Комиссия за вывод&#x20;

К сумме вывода будет применяться комиссия за вывод в размере 0.1%, если ты выводишь средства в течение 72 часов после последнего действия депозита. Комиссия за вывод вычитается из итоговой суммы вывода перед переводом CAKE.

### Обзор

#### Депозит

Если ты сейчас используешь `enterStaking(uint256 _amount)` на текущем PancakeSwap MasterChef, тебе нужно перейти на `deposit(uint256 _amount, uint256 _lockDuration)`. Для гибкого стейкинга просто используй «0» в качестве `_lockDuration`.

#### Баланс стейкинга и комиссии

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

**Сумма стейкинга CAKE (до вычета всех комиссий)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Комиссия за производительность**

Запрос из контракта:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Расчёт вручную:

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

**Комиссия за просрочку: (применяется только к стейкингу с блокировкой)**

Запрос из контракта:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Расчёт вручную:

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

**Комиссия за вывод**

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

**Сумма стейкинга CAKE (после вычета всех комиссий)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Ожидающие награды&#x20;

Обрати внимание, что в новом пуле компаундирование не требуется. Награды автоматически добавляются к твоему балансу стейкинга.

Однако ты можешь запросить количество CAKE, заработанных с момента последнего действия, используя разницу между текущим балансом стейкинга (описано выше) и числом из `userInfo.cakeAtLastUserAction`.

#### Вывод

Если ты используешь метод `leaveStaking(uint256 _amount)` на текущем PancakeSwap MasterChef, тебе нужно перейти на `withdraw(uint256 _shares)`.

При гибком стейкинге обрати внимание, что при выводе ожидающие комиссии за вознаграждения будут рассчитаны и вычтены из количества долей пользователя, а фактическое количество выводимых долей будет пересчитано на основе процентного соотношения выводимых долей к общей сумме долей. Смотри пример ниже:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Обрати внимание, что итоговая сумма получения будет зависеть от комиссии за вывод. Если твоя функция критично зависит от итогового количества выводимых CAKE, рекомендуем рассчитывать это по разнице баланса CAKE до и после операции вывода:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Или рассчитывай и вычитай комиссию за вывод при оценке суммы.

#### Как рассчитать количество CAKE в блоке, распределяемых в новый пул CAKE?

Ранее в ручном пуле CAKE была фиксированная эмиссия 10 CAKE/блок. После миграции на MasterChef v2 и новый пул CAKE мы можем теперь регулировать эмиссию.

Вот как можно рассчитать количество CAKE в блоке, распределяемых в новый пул CAKE:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Ты можешь запросить `cakePool.allocPoint` через `MasterChef.poolInfo(0)`

### **Адрес контракта в основной сети**

**Название контракта:** CakePool\
**Адрес контракта:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Просмотреть контракт PancakeSwap: Cake Pool на BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Тестовая среда**

Ты можешь использовать следующую тестовую среду для проверки интеграции своего проекта с новым CAKE Pool PancakeSwap. Если у тебя есть вопросы, свяжись с нашей командой через существующие каналы или по электронной почте bun@pancakeswap.com.

**Фиктивные токены:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (можно создавать с помощью `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory и Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Новый CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
