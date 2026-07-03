# 🤖 BNB AI Agent Studio

> BNB Smart Chain üzerindeki PancakeSwap V3 likidite havuzları ve Farm'larla etkileşim kuran otonom ajanlar geliştiren geliştiriciler için bir rehber — [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) veya herhangi bir çerçeve kullanarak.
>
> Sen bir strateji tanımlarsın; ajanın onu zincir üzerinde, denetimsiz olarak yürütür. Bu sayfa PancakeSwap tarafını kapsar: çağrılacak sözleşmeler, güvenli çağrı sırası ve eksiksiz bir çalışma örneği (otomatik V3 aralık yeniden dengeleyici). Ajanın kendisini nasıl tanımlayacağın, oluşturacağın ve dağıtacağın için BNB Agent Studio belgelerine bakabilirsin.

Bunun çalışması için PancakeSwap **entegrasyon gerektirmez**. V3 havuzları ve Farm'lar, ajanının doğrudan çağırdığı izinsiz akıllı sözleşmelerdir — aynı şekilde PancakeSwap ön yüzü de bunları çağırır. Aşağıdakilerin tümü zincir üzerinde kamuya açık bir alandır.

***

### 1. Bir ajanın PancakeSwap'a karşı neler yapabileceği

Yoğunlaştırılmış likidite (V3), LP'lere V2'ye kıyasla çok daha iyi sermaye verimliliği sağlar; ancak bunun bedeli aktif yönetimdir: Bir pozisyon yalnızca fiyat tick aralığının içindeyken ücret kazanır ve ödüller/getiriler sürekli değişir. Bu operasyonel yükü tam olarak bir ajan ortadan kaldırır. Yaygın stratejiler:

* **Aralık yeniden dengeleyici** — Bir LP pozisyonunu izle; fiyat aralığın kenarına doğru sürüklendiğinde çek ve yeni fiyatın etrafında yeniden oluştur; böylece pozisyon ücret kazanmaya devam eder. _(§6'da çalışma örneği.)_
* **Farm APR yönlendiricisi** — Havuzlar arasında CAKE + ücret getirisini takip et ve likiditeni en yüksek toplam getiriye taşı.
* **Swap/fiyat teklifi botları** — V2 + V3 genelinde en iyi yürütme için işlemleri Smart Router üzerinden yönlendir.

Bunların tümü aşağıdaki aynı birkaç sözleşme çağrısının bileşimidir.

***

### 2. Sözleşme yüzeyi (BNB Smart Chain, chainId 56)

| Sözleşme                              | Adres                                        | Ajanın kullanım amacı                                                                                          |
| ------------------------------------- | -------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | LP pozisyonları oluştur/yönet — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn`            |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | V2+V3 yönlendirmesiyle en iyi şekilde Swap yürüt                                                              |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | CAKE Farm'lamak için pozisyon NFT'sini stake et — `harvest`, `withdraw`                                        |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Göndermeden önce Swap fiyatı al                                                                                |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | `(token0, token1, fee)` çiftinden havuz adresi çöz                                                             |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | **Smart Router swap'ları** için gassız/toplu token onayları (bkz. §5.1)                                        |

> ⚠️ Gerçek değer göndermeden önce adresleri her zaman kanonik PancakeSwap dağıtım listesine göre **yeniden doğrula**. Yukarıdaki tabloyu bir başlangıç noktası olarak değerlendir.

V3 **havuzu** `(token0, token1, fee)` ile tanımlanır. Ücret kademeleri ve tick aralıkları:

| Ücret | `fee` değeri | Tick aralığı | Tipik kullanım               |
| ----- | ------------ | ------------ | ----------------------------- |
| %0,01 | `100`        | 1            | Stablecoin–stablecoin         |
| %0,05 | `500`        | 10           | İlişkili (örn. ETH/BTC)       |
| %0,25 | `2500`       | 50           | Çoğu çift                     |
| %1,00 | `10000`      | 200          | Egzotik / değişken            |

V3 **pozisyonu**, NonfungiblePositionManager içinde tutulan bir ERC-721 NFT'sidir. `tickLower`, `tickUpper`, `liquidity` ve birikmiş ücretleri depolar. Buna `tokenId` ile başvurulur.

***

### 3. Araçlar

Bu sözleşmelerle ham ABI'ler ve herhangi bir web3 kütüphanesiyle konuşabilirsin, ancak **`@pancakeswap/v3-sdk`** ve **`@pancakeswap/smart-router`** paketleri zor matematiği (tick ↔ fiyat, Kayma-düzeltilmiş minimumlar, calldata kodlaması) senin adına yapar. Aşağıdaki örnekler [viem](https://viem.sh/) ile birlikte bunları kullanır.

```bash
pnpm add @pancakeswap/v3-sdk @pancakeswap/smart-router @pancakeswap/sdk viem
```

```tsx
import { createPublicClient, createWalletClient, http } from 'viem'
import { bsc } from 'viem/chains'
import { privateKeyToAccount } from 'viem/accounts'

const account = privateKeyToAccount(process.env.AGENT_PRIVATE_KEY as `0x${string}`)

const publicClient = createPublicClient({ chain: bsc, transport: http() })
const walletClient = createWalletClient({ chain: bsc, account, transport: http() })
```

Ajanın, bir programa veya tetikleyiciye göre işlem yürüten yalnızca bu cüzdandır. Cüzdan Agent Studio tarafından finanse edilir ve yönetilir — BNB belgelerine bakabilirsin.

***

### 4. Durum okuma (her eylemden önce bunu yap)

Ajan, zinciri okuyarak harekete geçip geçmeyeceğine karar verir. Çoğu stratejiyi yönlendiren üç okuma:

**Havuz fiyatı ve mevcut tick** — zincir üstü `slot0` + `liquidity`'den bir `Pool` varlığı oluştur:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress, fabrika veya computePoolAddress() üzerinden çözümlendi
const [slot0, liquidity] = await Promise.all([
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'slot0' }),
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'liquidity' }),
])

const pool = new Pool(
  token0, token1, FeeAmount.MEDIUM,
  slot0[0],      // sqrtPriceX96
  liquidity,
  slot0[1],      // tick
)

console.log('price token0→token1:', pool.token0Price.toSignificant(6))
console.log('current tick:', pool.tickCurrent)
```

**Sahip olduğun bir pozisyon** — NonfungiblePositionManager'dan `tokenId` ile oku:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**Pozisyon aralık içinde mi?** Bu tek boolean değeri, bir yeniden dengeleyici için tetikleyicidir. Aralık dışına _çıkmadan_ önce hareket etmek için bunu "sınırdan N tick içinde" olarak sıkılaştırabilirsin.

***

### 5. Güvenli işlem dizileri

Tam olarak doğru yapılması gereken kısım budur. Gözetimsiz bir ajanın kötü işlemi yakalayacak insan yoktur; bu nedenle her durum değiştiren çağrının aşağıdaki dört güvenlik önlemiyle korunması gerekir.

#### 5.1 Onaylar

Bir sözleşme tokenlarını taşıyabilmesi için izne ihtiyaç duyar. Doğru mekanizma hangi sözleşmeyi çağırdığına bağlıdır — üçü de izinsizdir:

* **ERC-20 `approve`** — Herhangi bir token ile hem Smart Router hem de NonfungiblePositionManager için çalışır. Token/harcayan başına bir işlem. En basiti, ancak sürekli sınırsız onay süregelen bir risktir.
* **`selfPermit` (EIP-2612)** — **NonfungiblePositionManager** likidite işlemleri için. Token EIP-2612'yi destekliyorsa SDK, ayrı bir onay işlemi olmaksızın `mint`/`increaseLiquidity` ile çok çağrıda imzalı, miktara kapsamlı bir izni paketleyebilir. EIP-2612 içermeyen tokenlar için `approve`'a geri döner.
* **Permit2** — **Smart Router** swap'ları için. Token başına Permit2'yi bir kez onayla, ardından swap başına kısa ömürlü, imzalı, miktara kapsamlı izinler ver.

Otonom bir ajan için: Her izni tam miktara ve kısa bir son kullanma süresine kapsa. **Önemli bakiye tutan bir ajan cüzdanından hiçbir zaman sınırsız onay verme.**

#### 5.2 Kayma — asla `amountMin = 0` gönderme

Her ekleme/çıkarma/swap, kabul edilebilir minimum çıktıyı belirtmelidir. SDK'nın bunu elle hesaplamak yerine bir toleranstan türetmesine izin ver:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // %0,50

// mint / ekleme sırasında:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// çıkarma sırasında:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Swap'lar için Smart Router, `slippageTolerance`'ı uygular ve senin için `amountOutMinimum`'u hesaplar (§6, adım 0). **Sıfır minimum, sandviç botlarına açık bir davettir** — gözetimsiz bir cüzdanda bu tekrarlayan, sessiz kayıplara yol açabilir.

#### 5.3 Son tarihler — her zaman bir tane belirle

Her çağrı bir `deadline` (unix saniyeleri) alır. İşlem o zamana kadar beklemede kalırsa eski bir fiyatta yürütmek yerine geri döner. Bir ajan için bunu kısa tut:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 dakika
```

#### 5.4 Multicall — çok adımlı eylemleri atomik yap

NonfungiblePositionManager ve Smart Router, `multicall`'ı destekler: **tek bir işlemde** paketlenmiş ve hepsi başarılı olan ya da hepsi geri dönen birkaç çağrı. Bu sadece gas tasarrufu değil — bir güvenlik özelliğidir. `decreaseLiquidity` yapıp ardından `collect` yapan bir yeniden dengeleme yarı yürütülmemeli. SDK senin için paketler:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Atomik bir "yeniden dengeleme" işlevi yoktur.** Bir aralığı taşımak _birleşik_ bir dizidir (çıkar → topla → yeni mint). Çıkarma ve yeni mint ayrı işlemlerde gerçekleşir; arada fiyat değişebilir. Çıkarma onaylandıktan sonra mint için durumu yeniden oku ve minimumları yeniden hesapla — çıkarma öncesi sayıları tekrar kullanma.

#### Güvenlik önlemi kontrol listesi (her ajan eylemine uygula)

* \[ ] Token izni miktara (Permit2) kapsamlı, sınırsız değil
* \[ ] `amount*Min` / `amountOutMinimum` açık bir Kayma toleransından türetilmiş, asla `0` değil
* \[ ] Her çağrıda kısa `deadline`
* \[ ] Çok adımlı eylemler `multicall` ile paketlenmiş
* \[ ] Bir dizinin ayrı işlemleri arasında durum yeniden okunmuş
* \[ ] Taşınan değer üzerinde işlem başına sınır ve hareket etmeden önce havuz fiyatının beklenen sınırlar içinde olduğuna dair akıl sağlığı kontrolü (manipüle edilmiş/likidite zayıf havuza karşı ucuz koruma)

***

### 6. Çalışma örneği — otomatik V3 aralık yeniden dengeleyici

Referans ajan. Bir pozisyonu izler; fiyat aralık sınırına yaklaştığında likiditey çeker ve mevcut fiyatın etrafında taze bir aralık yeniden oluşturur. Beş adım.

**Tetikleyici:** `pool.tickCurrent`, `tickLower`/`tickUpper`'ın tampon mesafesi içinde (§4'ten).

#### Adım 0 — (isteğe bağlı) token oranını yeniden dengele

Çıkardıktan sonra eski aralığın ürettiği oranda token0 ve token1 tutarsın. Yeni, yeniden ortalanmış bir aralık genellikle farklı bir oran gerektirir; bu yüzden Smart Router aracılığıyla fazlalığı takas et:

```tsx
import { SmartRouter, SwapRouter } from '@pancakeswap/smart-router'
import { TradeType } from '@pancakeswap/swap-sdk-core' 

const quoteProvider = SmartRouter.createQuoteProvider({ onChainProvider: () => publicClient })                                                                                                     
const trade = await SmartRouter.getBestTrade(amountIn, tokenOut, TradeType.EXACT_INPUT, {
  gasPriceWei: () => publicClient.getGasPrice(),
  maxHops: 2,
  poolProvider: SmartRouter.createStaticPoolProvider(candidatePools),
  quoteProvider,
})

const { calldata, value } = SwapRouter.swapCallParameters(trade, {
  slippageTolerance: new Percent(50, 10_000),
  deadlineOrPreviousBlockhash: deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: SMART_ROUTER_ADDRESS, data: calldata, value: BigInt(value) })
```

#### Adım 1–3 — likiditey kaldır, topla, yak (tek işlem)

`removeCallParameters` tüm paketi oluşturur: likiditey sıfıra `decreaseLiquidity` eder, hem çekilen anaparayı hem de birikmiş ücretleri `collect` eder ve şimdi boş olan NFT'yi `burn` eder — tek atomik bir `multicall` olarak.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // %100 — tam çıkış
  slippageTolerance: new Percent(50, 10_000),     // %0,50 — amount0Min/amount1Min ayarlar
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // bekle — bir sonraki mint bu tokenlarla bağımlı
```

> Pozisyon **MasterChefV3'te stake edilmişse**, NFPM'den kaldırmazsın. Önce unstake etmek için `MasterChefV3.withdraw(tokenId, to)` çağır (bu aynı zamanda bekleyen CAKE'i hasat eder) ve NFT'yi cüzdanına iade eder — ardından yukarıdaki kaldırmayı uygula. Bkz. §7.

#### Adım 4 — yeni aralığı mint et

_Mevcut_ fiyatın etrafında tick'leri yeniden hesapla (havuzu yeniden oku — bkz. §5.4), bunları ücret kademesinin aralığına yaklaştır, artık tuttuğun tokenlardan bir `Position` oluştur ve mint et.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* slot0 + liquidity'yi yeniden oku → yeni Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // strateji tanımlı aralık genişliği

const tickLower = nearestUsableTick(freshPool.tickCurrent - halfWidth, spacing)
const tickUpper = nearestUsableTick(freshPool.tickCurrent + halfWidth, spacing)

const newPosition = Position.fromAmounts({
  pool: freshPool,
  tickLower,
  tickUpper,
  amount0: balance0,
  amount1: balance1,
  useFullPrecision: true,
})

const { calldata, value } = NonfungiblePositionManager.addCallParameters(newPosition, {
  slippageTolerance: new Percent(50, 10_000), // mint için amount0Min/amount1Min ayarlar
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

Ajan artık taze, aralık içi bir NFT tutuyor. Farm'layorsa yeniden stake et (§7). Bir sonraki tick'te §4 okumasına geri dön.

***

### 7. Farm etkileşimleri (MasterChefV3)

MasterChefV3'te bir V3 pozisyon NFT'si stake etmek, Swap ücretlerinin üstünde CAKE kazandırır.

> **Yalnızca aktif Farm'a sahip havuzlardan gelen pozisyonlar CAKE kazanır.** PancakeSwap Yönetişimi, hangi havuzların Farm'lanabilir olduğunu kaydeder (her biri bir `pid` alır). Kaydedilmemiş bir havuzdaki pozisyonu stake etmek `InvalidPid` hatasıyla geri döner. Ajan aktivitesinin PancakeSwap tarafındaki bir listeye bağlı olduğu tek yer burasıdır — ve bu havuz düzeyinde, ajan düzeyinde değildir: herhangi bir cüzdan herhangi bir aktif Farm'a stake edebilir. (NonfungiblePositionManager aracılığıyla bir pozisyon yönetmek — mint/collect/rebalance — Farm gerektirmez ve her havuz için çalışır.)

> **Yalnızca aktif Farm'a sahip havuzlardan gelen pozisyonlar CAKE kazanır.** PancakeSwap Yönetişimi, hangi havuzların Farm'lanabilir olduğunu kaydeder (her biri bir `pid` alır). Kaydedilmemiş bir havuzdaki pozisyonu stake etmek `InvalidPid` hatasıyla geri döner. Ajan aktivitesinin PancakeSwap tarafındaki bir listeye bağlı olduğu _tek_ yer burasıdır — ve bu havuz düzeyinde, ajan düzeyinde değildir: herhangi bir cüzdan herhangi bir _aktif_ Farm'a stake edebilir. Bir Farm stratejisi oluşturmadan önce havuzun canlı bir Farm'a sahip olup olmadığını kontrol et. (NonfungiblePositionManager aracılığıyla bir pozisyon yönetmek — mint/collect/rebalance — Farm gerektirmez ve her havuz için çalışır.)

* **Stake et** — Pozisyon NFT'sini MasterChefV3'e aktar (`safeTransferFrom(owner, masterChefV3, tokenId)`). Farm artık NFT'yi korur.
* **Hasat et** — `harvest(tokenId, to)` unstake etmeden bekleyen CAKE'i talep eder. Birkaç pozisyon genelinde tek bir işlemde talep etmek için `batchHarvest` kullan.
* **Çek / çık** — `withdraw(tokenId, to)` unstake eder, bekleyen CAKE'i hasat eder ve NFT'yi cüzdanına iade eder. `decreaseLiquidity`/`burn` yapabilmeden önce çekmen gerekir (§6'daki NFPM çağrıları yalnızca cüzdanının tuttuğu bir NFT üzerinde çalışır).

Dolayısıyla **stake edilmiş** bir pozisyon için yeniden dengeleyici şu şekilde çalışır: `withdraw` → çıkar/topla/yak → mint → `safeTransferFrom` ile MasterChefV3'e geri stake et.

***

### 8. Güvenlik, sınırlamalar ve yasal uyarılar

Gerçek fonları taşıyan bir ajan dağıtmadan önce bunu oku.

* **Özerklik geri alınamaz.** Dağıtılmış bir ajan işlemleri insan onayı olmadan imzalayıp gönderir. Bir hata, kötü bir tetikleyici veya manipüle edilmiş bir fiyat akışı gerçek sonuçlar doğurur. BSC test ağında test et, ardından ölçeklendirmeden önce ana ağ maruziyetini sınırla (işlem başına ve günlük sınırlar).
* **Kayma ve son tarihler zorunludur**, isteğe bağlı değil (§5). Bunları atlayan bir ajan er ya da geç sandviçlenecektir.
* **Fiyat manipülasyonu savunması.** Harekete geçmeden önce havuz fiyatını bağımsız bir referansla karşılaştır ve farklılık varsa çalıştırmayı atla — manipüle edilmiş veya ince bir havuza karşı işlem yapmaya karşı ucuz bir sigorta.
* **Gas ve finansman.** Ajan cüzdanını gas için BNB ile finanse tutun; yetersiz kalan bir ajan pozisyonu yeniden dengeleme ortasında bırakabilir (çıkarıldı ama yeniden mint edilmedi). Her çalıştırmada durumu yeniden okumak (§4) bir sonraki tick'te kurtarmasını sağlar.
* **Scaled-UI / RWA tokenları.** Bazı BSC tokenları (örn. Binance Hisse Tokenları) zincir üstü UI çarpanları kullanır (ERC-8056). Zincir üstü ham miktarlar görüntülenen miktarlardan farklıdır. Ajanın bunlarla işlem yapması gerekiyorsa tüm sözleşme matematiğini ham birimlerle yap ve çarpanı yalnızca insanlara yönelik görüntülemede uygula.
* **Ajanından sen sorumlusun.** PancakeSwap havuzları izinsiz sözleşmelerdir; karşılarına otonom bir ajan dağıtmak senin kararın ve senin riskindir. Bu rehber teknik bir referanstır, finansal tavsiye değildir; PancakeSwap sonuçlar konusunda herhangi bir garanti vermez.

***

### 9. Referans

* **`@pancakeswap/smart-router`** — yönlendirme + Swap calldata (en iyi repo içi örnekler README'sindedir)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, tick/fiyat matematiği
* **BNB Agent Studio** — ajanı tanımlama, oluşturma ve dağıtma (BNB belgeleri)
* **PancakeSwap dağıtım adresleri** — kanonik sözleşme listesi (kullanmadan önce doğrula)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
