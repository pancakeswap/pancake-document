---
description: MasterChef v2'ye Geç
---

# MasterChef v2

PancakeSwap MasterChef v2, Farm'lar için yeni bir ana staking sözleşmesidir ve CAKE havuzu, yakma ile diğer PancakeSwap ürünleri dahil olmak üzere $CAKE emisyonlarını ayarlamada daha fazla esneklik sunar.

### Taşınmam gerekiyor mu?

Şu anda PancakeSwap MasterChef'i ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)) kullanıyorsan yeni sözleşmeye ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)) geçmen gerekecek.

### Genel Bakış

#### Yatırma&#x20;

Şu anda mevcut PancakeSwap MasterChef'te `enterStaking(uint256 _amount)` kullanıyorsan yeni CAKE havuzu sözleşmesine geçmen gerekiyor. İlgili belgelere [buradan](../cake-syrup-pool.md) bakabilirsin.

Farm havuzları için yatırma fonksiyonu değişmedi. Ancak MasterChef adresini ve `pid`'yi güncellemenin gerekecek; MasterChef v2'deki yeni `pid`'lerin listesi için [farm listesine](list-of-farms.md) bakabilirsin.

#### Havuz Türleri

MasterChef v2'nin 2 tür havuzu vardır: Normal farm havuzları ve Özel farm havuzları. Havuz türünü sorgulamak için `poolInfo(_pid).isRegular` kullanabilirsin. Farklı `totalAllocPoint`'lere sahip olduklarından birbirinden bağımsız iki set havuz oluştururlar.

Özel farm havuzları: Yalnızca beyaz listedeki adresler yatırım yapabilir. Genellikle ödül dağıtımları için dahili PancakeSwap ürünleri tarafından kullanılır.

Normal farm havuzları: Standart LP token farm'ları. Örneğin CAKE-BNB, BNB-BUSD vb.

#### Çekme

Şu anda mevcut PancakeSwap MasterChef'te `leaveStaking(uint256 _amount)` kullanıyorsan yeni CAKE havuzu sözleşmesine geçmen gerekiyor. İlgili belgelere [buradan](../cake-syrup-pool.md) bakabilirsin.

Farm havuzları için çekme fonksiyonu değişmedi. Ancak MasterChef adresini ve `pid`'yi güncellemenin gerekecek; MasterChef v2'deki yeni `pid`'lerin listesi için [farm listesine](list-of-farms.md) bakabilirsin.

#### Staking Bakiyesi

Staking bakiyesini sorgulamak için `userInfo[_pid][_user].amount` kullanabilirsin.

#### Staking Tokeni&#x20;

Yeni `PoolInfo` yapısının lp token adresi alanını **içermediğini** unutma; herhangi bir havuzun staking tokenini sorgulamak için `lpToken(_pid)` kullanman gerekecek.&#x20;

#### Toplam Staking Payları/Miktarı

Herhangi bir farm havuzunun toplam staking miktarını almak için `lpToken.balanceOf(MasterChef.address)` kullanabilirsin.

Ancak MasterChef v2'de kullanıcıların payı artırılabilir (yakında). Bu nedenle ödüller, her havuzun toplam payları olarak `PoolInfo`'daki yeni `totalBoostedShare` alanı kullanılarak hesaplanır. Örneğin, havuz 0'da 2 kullanıcı varsa, kullanıcı1 100 LP stake ediyorsa (artırma olmadan), kullanıcı2 100 stake ediyorsa (`boostMultiplier` 1,05 ise), `totalBoostedShare` 205 olur. Sonuç olarak kullanıcı2 daha fazla ödül kazanır.

#### CakePerBlock

Tüm PancakeSwap farm'larına giden blok başına CAKE ödülünü sorgulamak için `cakePerBlock(bool _isRegular)` kullanabilirsin.

### Mainnet Sözleşme Adresi

**Sözleşme adı:** MasterChef v2\
**Sözleşme adresi:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[PancakeSwap: Ana Staking Sözleşmesi v2'yi BscScan'de görüntüle.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Testnet Ortamı

Aşağıdaki testnet ortamını kullanarak projenin yeni PancakeSwap MasterChef v2 ile entegrasyonunu test edebilirsin. Herhangi bir sorun yaşarsan mevcut kanallardan ekibimizle iletişime geç ya da bun@pancakeswap.com adresine e-posta gönder.

**Sahte Tokenler:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (`mint(address _to, uint256 _amount) public` kullanılarak basılabilir)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (`mint(uint256 amount) public` kullanılarak basılabilir)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory ve Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP Çiftleri

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChef'ler

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manuel CAKE
  * pid4: MasterChef v2 için Sahte Pool
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
