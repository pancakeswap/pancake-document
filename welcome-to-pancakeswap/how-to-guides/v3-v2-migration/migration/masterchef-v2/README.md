---
description: Migrasi ke MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 adalah kontrak staking utama baru untuk Farm sekaligus memberikan fleksibilitas lebih dalam menyesuaikan emisi $CAKE, termasuk pool CAKE, pembakaran, dan produk PancakeSwap lainnya.

### Apakah saya perlu bermigrasi?

Jika Anda saat ini menggunakan PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), Anda perlu bermigrasi ke kontrak baru ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Gambaran Umum

#### Deposit&#x20;

Jika Anda saat ini menggunakan `enterStaking(uint256 _amount)` di PancakeSwap MasterChef saat ini. Anda perlu bermigrasi ke kontrak pool CAKE baru. Lihat dokumentasi terkait [di sini](../cake-syrup-pool.md).

Fungsi deposit untuk farm pool tidak berubah. Namun, Anda perlu memperbarui alamat MasterChef dan `pid`, lihat [daftar farm](list-of-farms.md) untuk daftar `pid` baru di MasterChef v2.

#### Jenis Pool

MasterChef v2 memiliki 2 jenis pool: Pool farm reguler dan Pool farm khusus, yang dapat Anda gunakan `poolInfo(_pid).isRegular` untuk meminta jenis pool. Keduanya memiliki `totalAllocPoint` yang berbeda, menjadikan mereka dua set pool yang independen.

Pool farm khusus: hanya alamat yang masuk daftar putih yang dapat melakukan deposit. Biasanya digunakan oleh produk PancakeSwap internal untuk distribusi hadiah.

Pool farm reguler: farm token LP reguler. Misalnya CAKE-BNB, BNB-BUSD, dll…

#### Penarikan

Jika Anda saat ini menggunakan `leaveStaking(uint256 _amount)` di PancakeSwap MasterChef saat ini. Anda perlu bermigrasi ke kontrak pool CAKE baru. Lihat dokumentasi terkait [di sini](../cake-syrup-pool.md).

Fungsi penarikan untuk farm pool tidak berubah. Namun, Anda perlu memperbarui alamat MasterChef dan `pid`, lihat [daftar farm](list-of-farms.md) untuk daftar `pid` baru di MasterChef v2.

#### Saldo Staking

Gunakan `userInfo[_pid][_user].amount` untuk meminta saldo staking.

#### Token Staking&#x20;

Perlu diperhatikan bahwa struct `PoolInfo` baru **tidak** berisi kolom alamat token LP, Anda perlu menggunakan `lpToken(_pid)` untuk meminta token staking pool mana pun.&#x20;

#### Total Saham/Jumlah Staking

Gunakan `lpToken.balanceOf(MasterChef.address)` untuk mendapatkan total jumlah staking untuk farm pool mana pun.

Namun, di MasterChef v2, saham pengguna dapat ditingkatkan (segera hadir). Oleh karena itu, hadiah dihitung menggunakan kolom `totalBoostedShare` baru di `PoolInfo` sebagai total saham setiap pool. Misalnya, jika pool 0 memiliki 2 pengguna, pengguna1 melakukan staking 100 LP (tanpa boost), pengguna2 melakukan staking 100 (dengan `boostMultiplier` sebesar 1,05), maka `totalBoostedShare` akan menjadi 205. Mengakibatkan pengguna2 mendapatkan hadiah lebih banyak.

#### CakePerBlock

Anda dapat menggunakan `cakePerBlock(bool _isRegular)` untuk meminta hadiah CAKE per blok yang diberikan ke semua farm PancakeSwap.

### Alamat Kontrak Mainnet

**Nama kontrak:** MasterChef v2\
**Alamat kontrak:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Lihat Kontrak Staking Utama PancakeSwap v2 di BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Lingkungan Testnet

Anda dapat menggunakan lingkungan testnet berikut untuk menguji integrasi proyek Anda dengan PancakeSwap MasterChef v2 yang baru. Jika ada pertanyaan, hubungi tim kami melalui saluran yang ada, atau hubungi bun@pancakeswap.com melalui Email.

**Token Dummy:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (dapat dicetak menggunakan `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (dapat dicetak menggunakan `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory dan Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Pasangan LP

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: CAKE Manual
  * pid4: Pool Dummy untuk MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
