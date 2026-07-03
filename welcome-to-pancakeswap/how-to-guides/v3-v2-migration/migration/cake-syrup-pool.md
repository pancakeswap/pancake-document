---
description: Migrasi ke CAKE Syrup Pool baru
---

# CAKE Syrup Pool

CakePool baru adalah kontrak staking $CAKE baru yang dibangun berdasarkan CakeVault (pool CAKE otomatis saat ini) dan dirancang untuk bekerja bersama PancakeSwap MasterChef v2 guna menyediakan fungsionalitas "stake $CAKE, dapatkan $CAKE" sekaligus menawarkan lebih banyak fitur seperti staking jangka tetap. Pool CAKE Manual saat ini akan dihentikan setelah migrasi.

CakePool baru akan menggunakan token dummy untuk memanen $CAKE dari MasterChef v2 dan mendistribusikannya kepada pengguna yang melakukan staking $CAKE. Pengguna yang mengunci $CAKE untuk durasi lebih lama akan menerima jumlah saham yang lebih banyak (ditingkatkan secara linier berdasarkan durasi), sehingga menikmati imbal hasil yang lebih tinggi.

### Apakah saya perlu bermigrasi?&#x20;

Jika Anda saat ini menggunakan `enterStaking` dan `leaveStaking` di PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), Anda perlu bermigrasi ke kontrak baru.

### Tidak ada lagi compounding

Dengan CakePool baru, hadiah didistribusikan secara proporsional kepada semua pengguna pool berdasarkan saham. Mirip dengan "interest-bearing tokens" atau model berbasis saham lainnya, saldo staking pengguna akan bertambah ketika lebih banyak hadiah dimasukkan ke dalam pool. Pengguna tidak perlu memanen dan melakukan compounding hadiah mereka.

### Biaya&#x20;

Di CakePool baru, semua pengguna staking fleksibel akan dikenakan dua jenis biaya.&#x20;

#### Biaya atas hadiah staking fleksibel&#x20;

Biaya 2% akan dikenakan pada semua hadiah yang dihasilkan dari staking fleksibel. Jumlah biaya akan dihitung dan direalisasikan pada tindakan deposit atau penarikan berikutnya, dipotong dari saham pengguna. Untuk meminta jumlah biaya kinerja yang belum direalisasikan, gunakan `calculatePerformanceFee(address _user)`.&#x20;

#### Biaya penarikan&#x20;

Biaya penarikan sebesar 0,1% akan dikenakan pada jumlah yang di-unstake jika Anda menarik dalam 72 jam setelah tindakan deposit terakhir. Biaya penarikan dipotong dari jumlah penarikan akhir sebelum transfer CAKE.

### Gambaran Umum

#### Deposit

Jika Anda saat ini menggunakan `enterStaking(uint256 _amount)` di PancakeSwap MasterChef saat ini. Anda perlu bermigrasi ke `deposit(uint256 _amount, uint256 _lockDuration)`. Untuk staking fleksibel, cukup gunakan "0" sebagai `_lockDuration`.

#### Saldo Staking dan Biaya

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

**Jumlah staking CAKE (sebelum dikurangi semua biaya)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Biaya Kinerja**

Kueri dari kontrak:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Hitung secara manual:

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

**Biaya Keterlambatan: (hanya berlaku untuk staking terkunci)**

Kueri dari kontrak:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Hitung secara manual:

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

**Biaya Penarikan**

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

**Jumlah staking CAKE (setelah dikurangi semua biaya)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Hadiah Tertunda&#x20;

Harap diperhatikan bahwa pool baru tidak memerlukan compounding apa pun. Hadiah dimasukkan ke saldo staking Anda secara otomatis.

Namun, Anda dapat meminta jumlah CAKE yang diperoleh sejak tindakan terakhir, menggunakan selisih antara saldo staking saat ini (disebutkan di atas) dan angka dari `userInfo.cakeAtLastUserAction`.

#### Penarikan

Jika Anda menggunakan metode `leaveStaking(uint256 _amount)` di PancakeSwap MasterChef saat ini. Anda perlu bermigrasi ke `withdraw(uint256 _shares)`.

Saat melakukan staking fleksibel. Harap diperhatikan bahwa saat penarikan, biaya hadiah yang tertunda akan dihitung dan dipotong dari jumlah saham pengguna, jumlah saham aktual yang ditarik akan dikalibrasi ulang, berdasarkan persentase saham yang Anda tarik terhadap total saham yang Anda miliki. Lihat contoh berikut:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Harap diperhatikan bahwa jumlah akhir yang diterima akan dipengaruhi oleh biaya penarikan. Jika fungsi Anda sangat bergantung pada jumlah akhir CAKE yang ditarik, kami sarankan menghitungnya menggunakan selisih saldo CAKE sebelum dan sesudah tindakan penarikan:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Atau, hitung dan kurangi biaya penarikan saat memperkirakan jumlahnya.

#### Cara menghitung CAKE per blok yang didistribusikan ke pool CAKE baru?

Sebelumnya, pool CAKE manual memiliki emisi tetap 10 CAKE/blok. Setelah bermigrasi ke MasterChef v2 dan pool CAKE baru, kini kita dapat menyesuaikan emisinya.

Berikut cara menghitung CAKE per blok yang didistribusikan ke pool CAKE baru:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Anda dapat meminta `cakePool.allocPoint` menggunakan `MasterChef.poolInfo(0)`

### **Alamat Kontrak Mainnet**

**Nama kontrak:** CakePool\
**Alamat kontrak:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Lihat Kontrak PancakeSwap: Cake Pool di BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Lingkungan Testnet**

Anda dapat menggunakan lingkungan testnet berikut untuk menguji integrasi proyek Anda dengan CAKE Pool PancakeSwap yang baru. Jika ada pertanyaan, hubungi tim kami melalui saluran yang ada, atau hubungi bun@pancakeswap.com melalui Email.

**Token Dummy:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (dapat dicetak menggunakan `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory dan Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: CAKE Manual
  * pid4: Pool Dummy untuk MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### CAKE Pool Baru

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
