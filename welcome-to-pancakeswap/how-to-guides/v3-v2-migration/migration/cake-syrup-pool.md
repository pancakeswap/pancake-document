---
description: Yeni CAKE Syrup Pool'a Geç
---

# CAKE Syrup Pool

Yeni CakePool, CakeVault (mevcut otomatik CAKE havuzu) temel alınarak oluşturulmuş yeni bir $CAKE staking sözleşmesidir ve "CAKE stake et, CAKE kazan" işlevselliği sunarken sabit vadeli staking gibi ek özellikler sunmak amacıyla PancakeSwap MasterChef v2 ile birlikte çalışmak üzere tasarlanmıştır. Mevcut Manuel CAKE havuzu migrasyon sonrasında kullanımdan kaldırılacaktır.

Yeni CakePool, MasterChef v2'den $CAKE hasatlamak ve $CAKE stake eden kullanıcılara ödül dağıtmak için bir sahte token kullanacaktır. CAKE'ini daha uzun süre kilitleyen kullanıcılar daha fazla pay alacak (süreye göre doğrusal olarak artırılmış) ve dolayısıyla daha yüksek getiri elde edecektir.

### Taşınmam gerekiyor mu?&#x20;

Şu anda PancakeSwap MasterChef'te ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)) `enterStaking` ve `leaveStaking` kullanıyorsan yeni sözleşmeye geçmen gerekecek.

### Artık bileşik faiz yok

Yeni CakePool ile ödüller, tüm havuz kullanıcılarına paylarına orantılı olarak dağıtılır. "Faiz getiren tokenler" veya diğer pay tabanlı modellere benzer şekilde, havuza daha fazla ödül eklendiğinde kullanıcıların staking bakiyesi otomatik olarak büyüyecektir. Kullanıcıların ödüllerini hasat edip bileştirmesine gerek yoktur.

### Ücretler&#x20;

Yeni CakePool'da tüm esnek staking kullanıcıları iki set ücrete tabi olacaktır.&#x20;

#### Esnek staking ödülleri ücreti&#x20;

Esnek staking ile elde edilen tüm ödüllere %2 ücret uygulanacaktır. Ücret miktarı, bir sonraki yatırma veya çekme işleminde hesaplanıp gerçekleştirilecek ve kullanıcıların paylarından kesilecektir. Gerçekleşmemiş performans ücretinin miktarını sorgulamak için `calculatePerformanceFee(address _user)` kullanabilirsin.&#x20;

#### Çekme ücreti&#x20;

Son yatırma işleminden itibaren 72 saat içinde çekim yapılırsa çekilen tutara %0,1 çekme ücreti uygulanacaktır. Çekme ücreti, CAKE transferinden önce nihai çekim tutarından kesilir.

### Genel Bakış

#### Yatırma

Şu anda mevcut PancakeSwap MasterChef'te `enterStaking(uint256 _amount)` kullanıyorsan `deposit(uint256 _amount, uint256 _lockDuration)` fonksiyonuna geçmen gerekiyor. Esnek staking için `_lockDuration` olarak "0" kullan.

#### Staking Bakiyesi ve Ücretler

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

**CAKE staking miktarı (tüm ücretler düşülmeden önce)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Performans Ücreti**

Sözleşmeden sorgulama:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Manuel hesaplama:

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

**Gecikme Ücreti: (yalnızca kilitli staking için geçerli)**

Sözleşmeden sorgulama:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Manuel hesaplama:

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

**Çekme Ücreti**

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

**CAKE staking miktarı (tüm ücretler düşüldükten sonra)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Bekleyen Ödüller&#x20;

Yeni havuzun herhangi bir bileşik işleme ihtiyaç duymadığını unutma. Ödüller otomatik olarak staking bakiyene eklenir.

Ancak son işlemden bu yana kazanılan CAKE miktarını, yukarıda belirtilen mevcut staking bakiyesi ile `userInfo.cakeAtLastUserAction` değeri arasındaki farkı kullanarak sorgulayabilirsin.

#### Çekme

Şu anda mevcut PancakeSwap MasterChef'te `leaveStaking(uint256 _amount)` yöntemini kullanıyorsan `withdraw(uint256 _shares)` fonksiyonuna geçmen gerekiyor.

Esnek staking yaparken çekim sırasında bekleyen ödül ücretlerinin hesaplanıp kullanıcıların pay sayısından kesileceğini; çekilen gerçek pay sayısının, toplam paylara karşı çektiğin pay yüzdesine göre yeniden düzenleneceğini unutma. Aşağıdaki örneğe bakabilirsin:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Son alınan tutarın çekme ücretinden etkileneceğini unutma. Fonksiyonun çekilen nihai CAKE miktarına kritik ölçüde bağlı olması durumunda, bunu çekim işleminden önce ve sonra CAKE bakiyesindeki farkı kullanarak hesaplamani öneririz:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Ya da tutarı tahmin ederken çekme ücretini hesaplayıp düş.

#### Yeni CAKE havuzuna blok başına dağıtılan CAKE miktarı nasıl hesaplanır?

Daha önce manuel CAKE havuzunun sabit 10 CAKE/blok emisyonu vardı. MasterChef v2 ve yeni CAKE havuzuna geçtikten sonra artık emisyonlarını ayarlayabiliriz.

Yeni CAKE havuzuna blok başına dağıtılan CAKE miktarını şu şekilde hesaplayabilirsin:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

`cakePool.allocPoint`'i `MasterChef.poolInfo(0)` kullanarak sorgulayabilirsin.

### **Mainnet Sözleşme Adresi**

**Sözleşme adı:** CakePool\
**Sözleşme adresi:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[PancakeSwap: Cake Pool Sözleşmesini BscScan'de görüntüle.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Testnet Ortamı**

Aşağıdaki testnet ortamını kullanarak projenin yeni PancakeSwap CAKE Pool ile entegrasyonunu test edebilirsin. Herhangi bir sorun yaşarsan mevcut kanallardan ekibimizle iletişime geç ya da bun@pancakeswap.com adresine e-posta gönder.

**Sahte Tokenler:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (`mint(address _to, uint256 _amount) public` kullanılarak basılabilir)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory ve Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChef'ler

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manuel CAKE
  * pid4: MasterChef v2 için Sahte Pool
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Yeni CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
