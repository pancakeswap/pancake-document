# 🤖 BNB AI Agent Studio

> Panduan bagi pengembang yang membangun agen otonom — dengan [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) atau kerangka kerja apa pun — yang berinteraksi dengan pool Likuiditas dan farm PancakeSwap V3 di BNB Smart Chain.
>
> Anda mendeskripsikan strategi; agen Anda mengeksekusinya di jaringan tanpa pengawasan. Halaman ini mencakup bagian PancakeSwap: kontrak yang perlu dipanggil, urutan aman untuk memanggilnya, dan contoh lengkap yang telah dikerjakan (rebalancer rentang V3 otomatis). Untuk cara mendeskripsikan, membangun, dan menerapkan agen itu sendiri, lihat dokumentasi BNB Agent Studio.

PancakeSwap **tidak memerlukan integrasi** agar ini berfungsi. Pool dan farm V3 adalah smart contract yang tidak memerlukan izin — agen Anda memanggilnya secara langsung, sama seperti yang dilakukan frontend PancakeSwap. Semua yang ada di bawah ini adalah permukaan publik di jaringan.

***

### 1. Apa yang dapat dilakukan agen terhadap PancakeSwap

Likuiditas terkonsentrasi (V3) memberikan efisiensi modal yang jauh lebih baik bagi LP dibandingkan V2, dengan biaya manajemen aktif: posisi hanya mendapatkan biaya selama harga berada dalam rentang tick-nya, dan hadiah/imbal hasil terus bergeser. Overhead operasional itulah yang dihilangkan oleh agen. Strategi umum:

* **Rebalancer rentang** — pantau posisi LP; ketika harga bergerak ke tepi rentang, tarik dan mint ulang di sekitar harga baru agar posisi terus mendapatkan biaya. _(Contoh dalam §6.)_
* **Router APR Farm** — pantau imbal hasil CAKE + biaya di seluruh pool dan pindahkan Likuiditas ke imbal hasil total tertinggi.
* **Bot Swap/kuotasi** — arahkan perdagangan melalui Smart Router untuk eksekusi terbaik di V2 + V3.

Semua ini adalah komposisi dari segelintir panggilan kontrak yang sama di bawah ini.

***

### 2. Permukaan kontrak (BNB Smart Chain, chainId 56)

| Kontrak                               | Alamat                                       | Agen Anda menggunakannya untuk                                                                                   |
| ------------------------------------- | -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Membuat/mengelola posisi LP — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Mengeksekusi swap dengan routing V2+V3 terbaik                                                                   |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Stake NFT posisi untuk farm CAKE — `harvest`, `withdraw`                                                         |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Kuotasi swap sebelum mengirimkannya                                                                               |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Mendapatkan alamat pool dari `(token0, token1, fee)`                                                             |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Persetujuan token tanpa gas/berkelompok untuk **swap Smart Router** (lihat §5.1)                                 |

> ⚠️ **Selalu konfirmasi ulang alamat** terhadap daftar deployment PancakeSwap kanonik sebelum mengirimkan nilai nyata. Anggap tabel di atas sebagai titik awal.

Pool V3 **diidentifikasi** oleh `(token0, token1, fee)`. Tingkatan biaya dan jarak tick-nya:

| Biaya  | Nilai `fee` | Jarak tick | Penggunaan umum          |
| ------ | ----------- | ---------- | ------------------------ |
| 0,01%  | `100`       | 1          | Stabil–stabil            |
| 0,05%  | `500`       | 10         | Berkorelasi (mis. ETH/BTC) |
| 0,25%  | `2500`      | 50         | Kebanyakan pasangan      |
| 1,00%  | `10000`     | 200        | Eksotis / volatil        |

**Posisi** V3 adalah NFT ERC-721 yang disimpan dalam NonfungiblePositionManager. Menyimpan `tickLower`, `tickUpper`, `liquidity`, dan biaya yang terkumpul. Anda mereferensikannya dengan `tokenId`.

***

### 3. Perkakas

Anda dapat berbicara dengan kontrak-kontrak ini dengan ABI mentah dan pustaka web3 apa pun, tetapi paket **`@pancakeswap/v3-sdk`** dan **`@pancakeswap/smart-router`** melakukan matematika sulit (tick ↔ harga, minimum yang disesuaikan dengan Slippage, pengkodean calldata) untuk Anda. Contoh-contoh di bawah menggunakannya dengan [viem](https://viem.sh/).

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

Agen Anda hanyalah dompet ini yang mengeksekusi transaksi berdasarkan jadwal atau pemicu. Dompet didanai dan dikelola oleh Agent Studio — lihat dokumentasi BNB.

***

### 4. Membaca state (lakukan ini sebelum setiap tindakan)

Agen memutuskan _apakah_ akan bertindak dengan membaca rantai. Tiga bacaan yang mendorong sebagian besar strategi:

**Harga pool dan tick saat ini** — bangun entitas `Pool` dari `slot0` + `liquidity` di jaringan:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress diselesaikan dari factory atau computePoolAddress()
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

**Posisi yang Anda miliki** — baca dari NonfungiblePositionManager dengan `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**Apakah posisi dalam rentang?** Boolean tunggal itulah pemicu untuk rebalancer. Anda dapat mempersempitnya menjadi "dalam N tick dari batas" untuk bertindak _sebelum_ keluar dari rentang.

***

### 5. Urutan transaksi yang aman

Inilah bagian yang harus dilakukan dengan tepat. Agen tanpa pengawasan tidak memiliki manusia untuk menangkap transaksi yang buruk, sehingga setiap panggilan yang mengubah state harus dilindungi dengan empat penjaga di bawah ini.

#### 5.1 Persetujuan

Sebelum kontrak dapat memindahkan token Anda, kontrak memerlukan tunjangan. Mekanisme yang tepat bergantung pada kontrak yang Anda panggil — ketiganya di bawah ini tidak memerlukan izin:

* **ERC-20 `approve`** — berfungsi untuk Smart Router dan NonfungiblePositionManager, dengan token apa pun. Satu tx per token/pengeluaran. Paling sederhana, tetapi persetujuan tak terbatas yang berdiri adalah risiko yang berdiri.
* **`selfPermit` (EIP-2612)** — untuk operasi Likuiditas **NonfungiblePositionManager**. Jika token mendukung EIP-2612, SDK dapat menggabungkan permit bertanda tangan dengan cakupan jumlah secara _inline_ dengan `mint`/`increaseLiquidity` melalui multicall — tanpa tx approve terpisah. Kembali ke `approve` untuk token tanpa EIP-2612.
* **Permit2** — untuk swap **Smart Router**. Setujui Permit2 sekali per token, kemudian berikan tunjangan bertanda tangan jangka pendek per swap.

Untuk agen otonom: lingkupkan setiap permit ke jumlah yang tepat dan kedaluwarsa pendek. **Jangan pernah memberikan persetujuan tak terbatas dari dompet agen yang menyimpan saldo bermakna.**

#### 5.2 Slippage — jangan pernah kirim `amountMin = 0`

Setiap tambah/hapus/swap harus menentukan output minimum yang dapat diterima. Biarkan SDK menurunkannya dari toleransi daripada menghitungnya sendiri:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// saat minting / menambahkan:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// saat menghapus:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Untuk swap, Smart Router menerapkan `slippageTolerance` dan menghitung `amountOutMinimum` untuk Anda (§6, langkah 0). **Minimum nol adalah undangan terbuka untuk bot sandwich** — pada dompet tanpa pengawasan itu bisa berarti kerugian berulang yang diam-diam.

#### 5.3 Deadline — selalu tetapkan

Setiap panggilan mengambil `deadline` (detik unix). Jika tx masih tertunda pada waktu tersebut, transaksi dibatalkan alih-alih dieksekusi pada harga yang basi. Tetap pendek untuk agen:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 menit
```

#### 5.4 Multicall — buat tindakan multi-langkah menjadi atomik

NonfungiblePositionManager dan Smart Router mendukung `multicall`: beberapa panggilan digabungkan menjadi **satu transaksi** yang semuanya berhasil atau semuanya dibatalkan. Ini bukan hanya penghematan gas — ini adalah properti keamanan. Rebalance yang melakukan `decreaseLiquidity` kemudian `collect` tidak boleh pernah setengah dieksekusi. SDK menggabungkan untuk Anda:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Tidak ada fungsi "rebalance" yang atomik.** Memindahkan rentang adalah _urutan_ yang disusun (hapus → kumpulkan → mint). Penghapusan dan mint baru terjadi dalam transaksi terpisah; harga dapat bergerak di antara keduanya. Baca ulang state dan hitung ulang minimum untuk mint setelah penghapusan dikonfirmasi — jangan gunakan kembali angka sebelum penghapusan.

#### Daftar periksa penjaga (terapkan pada setiap tindakan agen)

* \[ ] Tunjangan token dicakupkan ke jumlah (Permit2), bukan tak terbatas
* \[ ] `amount*Min` / `amountOutMinimum` diturunkan dari toleransi Slippage yang eksplisit, tidak pernah `0`
* \[ ] `deadline` pendek pada setiap panggilan
* \[ ] Tindakan multi-langkah digabungkan melalui `multicall`
* \[ ] State dibaca ulang di antara transaksi terpisah dari suatu urutan
* \[ ] Batas per-jalankan pada nilai yang dipindahkan, dan pemeriksaan kewarasan bahwa harga pool berada dalam batas yang diharapkan sebelum bertindak (pertahanan murah terhadap bertindak ke pool yang dimanipulasi/tidak likuid)

***

### 6. Contoh yang dikerjakan — rebalancer rentang V3 otomatis

Agen referensi. Memantau satu posisi; ketika harga mendekati batas rentang, menarik Likuiditas dan mint ulang rentang segar yang berpusat pada harga saat ini. Lima langkah.

**Pemicu:** `pool.tickCurrent` berada dalam buffer dari `tickLower`/`tickUpper` (dari §4).

#### Langkah 0 — (opsional) seimbangkan ulang rasio token

Setelah Anda menarik, Anda akan menyimpan token0 dan token1 dalam rasio apa pun yang dihasilkan rentang lama. Rentang baru yang dicentrkan ulang biasanya memerlukan rasio yang berbeda, jadi tukar kelebihan melalui Smart Router:

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

#### Langkah 1–3 — hapus Likuiditas, kumpulkan, bakar (satu transaksi)

`removeCallParameters` membangun seluruh paket: ini `decreaseLiquidity` ke nol, mengumpulkan (`collect`) principal yang ditarik dan biaya yang terkumpul, dan membakar (`burn`) NFT yang sekarang kosong — sebagai satu `multicall` atomik.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — keluar penuh
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — menetapkan amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // tunggu — mint berikutnya bergantung pada token-token ini
```

> Jika posisi **di-stake di MasterChefV3**, Anda tidak menghapus dari NFPM. Panggil `MasterChefV3.withdraw(tokenId, to)` terlebih dahulu untuk unstake (ini juga memanen CAKE yang tertunda), yang mengembalikan NFT ke dompet Anda — kemudian jalankan penghapusan di atas. Lihat §7.

#### Langkah 4 — mint rentang baru

Hitung ulang tick di sekitar harga _saat ini_ (baca ulang pool — lihat §5.4), snap ke jarak tick tingkatan biaya, bangun `Position` dari token yang Anda miliki sekarang, dan mint.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* baca ulang slot0 + liquidity → Pool baru (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // lebar rentang yang ditentukan strategi

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
  slippageTolerance: new Percent(50, 10_000), // menetapkan amount0Min/amount1Min untuk mint
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

Agen sekarang menyimpan NFT dalam rentang segar. Jika sedang farming, stake kembali (§7). Kembali ke bacaan §4 pada tick berikutnya.

***

### 7. Interaksi Farm (MasterChefV3)

Staking NFT posisi V3 di MasterChefV3 mendapatkan CAKE di atas biaya swap.

> **Hanya posisi dari pool dengan farm aktif yang mendapatkan CAKE.** Tata Kelola PancakeSwap mendaftarkan pool mana yang dapat di-farm (masing-masing mendapatkan `pid`). Staking posisi yang pool-nya tidak terdaftar akan dibatalkan dengan `InvalidPid`. Ini adalah satu tempat aktivitas agen bergantung pada daftar sisi PancakeSwap — dan itu pada tingkat pool, bukan tingkat agen: dompet mana pun dapat stake ke farm aktif mana pun. (Mengelola posisi melalui NonfungiblePositionManager — mint/collect/rebalance — tidak memerlukan farm dan berfungsi untuk setiap pool.)

> **Hanya posisi dari pool dengan farm aktif yang mendapatkan CAKE.** Tata Kelola PancakeSwap mendaftarkan pool mana yang dapat di-farm (masing-masing mendapatkan `pid`). Staking posisi yang pool-nya tidak terdaftar akan dibatalkan dengan `InvalidPid`. Ini adalah _satu_ tempat aktivitas agen bergantung pada daftar sisi PancakeSwap — dan itu pada tingkat pool, bukan tingkat agen: dompet mana pun dapat stake ke farm _aktif_ mana pun. Periksa pool memiliki farm yang aktif sebelum membangun strategi farming di sekitarnya. (Mengelola posisi melalui NonfungiblePositionManager — mint/collect/rebalance — tidak memerlukan farm dan berfungsi untuk setiap pool.)

* **Stake** — transfer NFT posisi ke MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). Farm sekarang menjadi kustodian NFT.
* **Harvest** — `harvest(tokenId, to)` mengklaim CAKE yang tertunda tanpa unstaking. Gunakan `batchHarvest` untuk mengklaim di beberapa posisi dalam satu tx.
* **Withdraw / keluar** — `withdraw(tokenId, to)` unstakes, memanen CAKE yang tertunda, dan mengembalikan NFT ke dompet Anda. Anda harus withdraw sebelum dapat `decreaseLiquidity`/`burn` (panggilan NFPM di §6 hanya berfungsi pada NFT yang dipegang dompet Anda).

Rebalancer untuk posisi yang **di-farm** oleh karena itu menjalankan: `withdraw` → hapus/kumpulkan/bakar → mint → `safeTransferFrom` kembali ke MasterChefV3.

***

### 8. Keamanan, batas & penafian

Baca ini sebelum menerapkan agen yang memindahkan dana nyata.

* **Otonomi tidak dapat dibalik.** Agen yang diterapkan menandatangani dan mengirimkan transaksi tanpa konfirmasi manusia. Bug, pemicu yang buruk, atau feed harga yang dimanipulasi dieksekusi secara nyata. Uji di testnet BSC, kemudian batasi paparan mainnet (batas per-perdagangan dan per-hari) sebelum skala.
* **Slippage dan deadline adalah wajib**, bukan opsional (§5). Agen yang menghilangkannya pada akhirnya akan di-sandwich.
* **Pertahanan manipulasi harga.** Sebelum bertindak, periksa kewarasan harga pool terhadap referensi independen dan lewati jalankan jika berbeda — asuransi murah terhadap perdagangan ke pool yang dimanipulasi atau tipis.
* **Gas dan pendanaan.** Jaga dompet agen tetap terdanai dengan BNB untuk gas; agen yang kehabisan dapat meninggalkan posisi di tengah rebalance (dihapus tetapi belum dimint ulang). Membaca ulang state pada setiap jalankan (§4) memungkinkannya pulih pada tick berikutnya.
* **Token Scaled-UI / RWA.** Beberapa token BSC (mis. Binance Stock Tokens) menggunakan pengganda UI di jaringan (ERC-8056). Jumlah mentah di jaringan berbeda dari jumlah yang ditampilkan. Jika agen Anda memperdagangkan token-token ini, lakukan semua matematika kontrak dalam unit mentah dan hanya terapkan pengganda untuk tampilan yang menghadap manusia.
* **Anda bertanggung jawab atas agen Anda.** Pool PancakeSwap adalah kontrak yang tidak memerlukan izin; menerapkan agen otonom terhadap kontrak tersebut adalah keputusan dan risiko Anda. Panduan ini adalah referensi teknis, bukan saran keuangan, dan PancakeSwap tidak memberikan jaminan apa pun terhadap hasil.

***

### 9. Referensi

* **`@pancakeswap/smart-router`** — routing + calldata swap (contoh terbaik di repo ada di README-nya)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, matematika tick/harga
* **BNB Agent Studio** — mendeskripsikan, membangun, dan menerapkan agen (dokumentasi BNB)
* **Alamat deployment PancakeSwap** — daftar kontrak kanonik (verifikasi sebelum digunakan)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
