# 🤖 Building Trading Agents on PancakeSwap V3

Trang này chỉ cung cấp tổng quan, vui lòng truy cập [pancakeswap.ai](https://pancakeswap.ai) để biết thêm thông tin

> Hướng dẫn dành cho nhà phát triển xây dựng các agent tự động — bằng [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) hoặc bất kỳ framework nào — tương tác với các nhóm thanh khoản và farm PancakeSwap V3 trên BNB Smart Chain.
>
> Bạn mô tả một chiến lược; agent của bạn thực thi chiến lược đó on-chain, không cần giám sát. Trang này đề cập phần của PancakeSwap: các hợp đồng cần gọi, thứ tự gọi an toàn, và một ví dụ hoàn chỉnh (bot tái cân bằng phạm vi V3 tự động). Về cách mô tả, xây dựng và triển khai chính agent, hãy xem tài liệu BNB Agent Studio.

PancakeSwap **không yêu cầu tích hợp** nào để việc này hoạt động. Các nhóm và farm V3 là các hợp đồng thông minh không cần cấp phép — agent của bạn gọi trực tiếp chúng, giống như cách giao diện PancakeSwap thực hiện. Mọi thứ dưới đây đều là bề mặt công khai trên on-chain.

***

### 1. Agent có thể làm gì với PancakeSwap

Thanh khoản tập trung (V3) mang lại cho LP hiệu quả vốn tốt hơn nhiều so với V2, đổi lại là phải quản lý chủ động: một vị thế chỉ kiếm phí khi giá nằm trong phạm vi tick của nó, và phần thưởng/lợi suất liên tục thay đổi. Gánh nặng vận hành đó chính là thứ agent loại bỏ. Các chiến lược phổ biến:

* **Range rebalancer** — theo dõi một vị thế LP; khi giá dịch chuyển gần mép của phạm vi, rút thanh khoản và mint lại quanh mức giá mới để vị thế tiếp tục kiếm phí. _(Ví dụ hoàn chỉnh ở §6.)_
* **Farm APR router** — theo dõi lợi suất CAKE + phí giữa các nhóm và chuyển thanh khoản sang nơi có tổng lợi suất cao nhất.
* **Swap/quote bots** — định tuyến giao dịch qua Smart Router để có kết quả thực thi tốt nhất trên V2 + V3.

Tất cả những chiến lược này đều là sự kết hợp của cùng một số ít lệnh gọi hợp đồng bên dưới.

***

### 2. Bề mặt hợp đồng (BNB Smart Chain, chainId 56)

| Contract                              | Address                                      | Agent của bạn dùng nó để                                                                         |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Tạo/quản lý vị thế LP — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Thực hiện hoán đổi với định tuyến V2+V3 tốt nhất                                                 |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Stake NFT vị thế để farm CAKE — `harvest`, `withdraw`                                            |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Báo giá một giao dịch hoán đổi trước khi gửi                                                     |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Xác định địa chỉ nhóm từ `(token0, token1, fee)`                                                 |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Phê duyệt token không tốn gas/theo lô cho **hoán đổi qua Smart Router** (xem §5.1)               |

> ⚠️ **Luôn xác nhận lại địa chỉ** với danh sách triển khai chính thức của PancakeSwap trước khi gửi giá trị thực. Hãy coi bảng trên chỉ là điểm xuất phát.

Một **nhóm** V3 được xác định bởi `(token0, token1, fee)`. Các mức phí và tick spacing tương ứng:

| Fee   | Giá trị `fee` | Tick spacing | Trường hợp sử dụng điển hình |
| ----- | ----------- | ------------ | ------------------------- |
| 0.01% | `100`       | 1            | Stable–stable             |
| 0.05% | `500`       | 10           | Tương quan (ví dụ ETH/BTC) |
| 0.25% | `2500`      | 50           | Hầu hết các cặp           |
| 1.00% | `10000`     | 200          | Lạ / biến động mạnh       |

Một **vị thế** V3 là một NFT ERC-721 được giữ trong NonfungiblePositionManager. Nó lưu `tickLower`, `tickUpper`, `liquidity` và phí đã tích lũy. Bạn tham chiếu đến nó bằng `tokenId`.

***

### 3. Công cụ

Bạn có thể giao tiếp với các hợp đồng này bằng ABI thô và bất kỳ thư viện web3 nào, nhưng các gói **`@pancakeswap/v3-sdk`** và **`@pancakeswap/smart-router`** sẽ xử lý các phép toán phức tạp (tick ↔ giá, mức tối thiểu đã điều chỉnh theo trượt giá, mã hóa calldata) cho bạn. Các ví dụ bên dưới dùng chúng cùng với [viem](https://viem.sh/).

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

Agent của bạn chỉ là ví này thực hiện giao dịch theo lịch hoặc theo kích hoạt. Ví được Agent Studio cấp vốn và quản lý — xem tài liệu BNB.

***

### 4. Đọc trạng thái (thực hiện trước mỗi hành động)

Agent quyết định có _nên_ hành động hay không bằng cách đọc chuỗi. Ba lần đọc thúc đẩy hầu hết các chiến lược:

**Giá nhóm và tick hiện tại** — xây dựng một thực thể `Pool` từ `slot0` + `liquidity` on-chain:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress resolved from the factory or computePoolAddress()
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

**Một vị thế bạn sở hữu** — đọc nó từ NonfungiblePositionManager theo `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**Vị thế có nằm trong phạm vi không?** Giá trị boolean duy nhất đó là điều kiện kích hoạt cho bot tái cân bằng. Bạn có thể siết chặt thành "trong vòng N tick tính từ ranh giới" để hành động _trước khi_ vị thế ra khỏi phạm vi.

***

### 5. Chuỗi giao dịch an toàn

Đây là phần cần làm chính xác tuyệt đối. Agent không giám sát không có con người nào để phát hiện một giao dịch xấu, vì vậy mọi lệnh gọi thay đổi trạng thái phải được bảo vệ bằng bốn lớp rào chắn dưới đây.

#### 5.1 Phê duyệt

Trước khi một hợp đồng có thể di chuyển token của bạn, nó cần một hạn mức. Cơ chế phù hợp phụ thuộc vào hợp đồng bạn đang gọi — cả ba cơ chế dưới đây đều không cần cấp phép:

* **ERC-20 `approve`** — hoạt động với cả Smart Router và NonfungiblePositionManager, với mọi token. Một giao dịch cho mỗi token/spender. Đơn giản nhất, nhưng một phê duyệt vô hạn thường trực là một rủi ro thường trực.
* **`selfPermit` (EIP-2612)** — dành cho các thao tác thanh khoản của **NonfungiblePositionManager**. Nếu token hỗ trợ EIP-2612, SDK có thể gói một permit đã ký, giới hạn theo số lượng _trực tiếp_ cùng `mint`/`increaseLiquidity` qua multicall — không cần giao dịch approve riêng. Quay về `approve` với các token không có EIP-2612.
* **Permit2** — dành cho hoán đổi qua **Smart Router**. Phê duyệt Permit2 một lần cho mỗi token, sau đó cấp các hạn mức ngắn hạn, có chữ ký, giới hạn theo số lượng cho từng giao dịch hoán đổi.

Đối với agent tự động: giới hạn mọi permit ở đúng số lượng cần dùng và thời hạn ngắn. **Không bao giờ cấp phê duyệt không giới hạn từ ví agent đang giữ số dư đáng kể.**

#### 5.2 Trượt giá — không bao giờ gửi `amountMin = 0`

Mọi thao tác thêm/rút/hoán đổi phải chỉ định mức đầu ra tối thiểu chấp nhận được. Hãy để SDK tính ra nó từ một mức dung sai thay vì tự làm thủ công:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// when minting / adding:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// when removing:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Với hoán đổi, Smart Router áp dụng `slippageTolerance` và tự tính `amountOutMinimum` cho bạn (§6, bước 0). **Mức tối thiểu bằng 0 là lời mời gọi các bot sandwich** — với ví không giám sát, điều đó có thể gây ra các khoản lỗ lặp đi lặp lại, âm thầm.

#### 5.3 Deadline — luôn đặt một deadline

Mỗi lệnh gọi nhận một `deadline` (giây unix). Nếu giao dịch vẫn đang chờ vào thời điểm đó, nó sẽ revert thay vì thực thi ở mức giá đã cũ. Hãy giữ nó ngắn cho agent:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutes
```

#### 5.4 Multicall — biến các hành động nhiều bước thành nguyên tử

NonfungiblePositionManager và Smart Router hỗ trợ `multicall`: nhiều lệnh gọi được gói vào **một giao dịch**, tất cả cùng thành công hoặc cùng revert. Đây không chỉ là tiết kiệm gas — đó là một đặc tính an toàn. Một lần tái cân bằng thực hiện `decreaseLiquidity` rồi `collect` không bao giờ được phép chỉ thực thi một nửa. SDK sẽ gói giúp bạn:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Không có hàm "rebalance" nguyên tử.** Dịch chuyển phạm vi là một chuỗi _kết hợp_ (remove → collect → mint). Việc rút và mint mới diễn ra trong các giao dịch riêng; giá có thể thay đổi giữa chúng. Hãy đọc lại trạng thái và tính lại mức tối thiểu cho lần mint sau khi việc rút được xác nhận — đừng dùng lại số liệu trước khi rút.

#### Danh sách kiểm tra rào chắn (áp dụng cho mọi hành động của agent)

* \[ ] Hạn mức token được giới hạn theo số lượng (Permit2), không vô hạn
* \[ ] `amount*Min` / `amountOutMinimum` được tính từ mức dung sai trượt giá rõ ràng, không bao giờ là `0`
* \[ ] `deadline` ngắn cho mọi lệnh gọi
* \[ ] Các hành động nhiều bước được gói qua `multicall`
* \[ ] Đọc lại trạng thái giữa các giao dịch riêng biệt trong một chuỗi
* \[ ] Giới hạn giá trị di chuyển cho mỗi lần chạy, và kiểm tra hợp lý rằng giá nhóm nằm trong giới hạn kỳ vọng trước khi hành động (cách phòng vệ rẻ tiền để tránh hành động trong một nhóm bị thao túng/thiếu thanh khoản)

***

### 6. Ví dụ hoàn chỉnh — bot tái cân bằng phạm vi V3 tự động

Agent tham chiếu. Nó theo dõi một vị thế; khi giá tiến gần ranh giới phạm vi, nó rút thanh khoản ra và mint lại một phạm vi mới có tâm tại mức giá hiện tại. Gồm năm bước.

**Kích hoạt:** `pool.tickCurrent` nằm trong vùng đệm so với `tickLower`/`tickUpper` (từ §4).

#### Bước 0 — (tùy chọn) cân bằng lại tỷ lệ token

Sau khi rút, bạn sẽ giữ token0 và token1 theo tỷ lệ mà phạm vi cũ tạo ra. Một phạm vi mới, được căn lại tâm thường cần tỷ lệ khác, vì vậy hãy hoán đổi phần dư qua Smart Router:

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

#### Bước 1–3 — rút thanh khoản, collect, burn (một giao dịch)

`removeCallParameters` dựng toàn bộ gói: nó `decreaseLiquidity` về 0, `collect` cả vốn gốc đã rút lẫn phí đã tích lũy, và `burn` NFT giờ đã trống — tất cả trong một `multicall` nguyên tử.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — full exit
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — sets amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // wait — the next mint depends on these tokens
```

> Nếu vị thế đang được **stake trong MasterChefV3**, bạn không rút từ NFPM. Hãy gọi `MasterChefV3.withdraw(tokenId, to)` trước để unstake (việc này cũng harvest CAKE đang chờ), trả NFT về ví của bạn — sau đó chạy phần rút ở trên. Xem §7.

#### Bước 4 — mint phạm vi mới

Tính lại các tick quanh mức giá _hiện tại_ (đọc lại nhóm — xem §5.4), căn chúng theo tick spacing của mức phí, dựng một `Position` từ các token bạn đang giữ, rồi mint.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* re-read slot0 + liquidity → new Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // strategy-defined range width

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
  slippageTolerance: new Percent(50, 10_000), // sets amount0Min/amount1Min for the mint
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

Agent giờ giữ một NFT mới nằm trong phạm vi. Nếu trước đó nó đang farm, hãy stake lại (§7). Quay lại bước đọc ở §4 ở tick tiếp theo.

***

### 7. Tương tác với farm (MasterChefV3)

Stake NFT vị thế V3 trong MasterChefV3 giúp kiếm CAKE bên cạnh phí hoán đổi.

> **Chỉ các vị thế từ nhóm có farm đang hoạt động mới kiếm được CAKE.** Quản trị PancakeSwap đăng ký những nhóm nào có thể farm (mỗi nhóm có một `pid`). Stake một vị thế mà nhóm của nó chưa được đăng ký sẽ revert với `InvalidPid`. Đây là nơi duy nhất hoạt động của agent phụ thuộc vào một danh sách phía PancakeSwap — và nó ở cấp nhóm, không phải cấp agent: bất kỳ ví nào cũng có thể stake vào bất kỳ farm đang hoạt động nào. (Quản lý vị thế qua NonfungiblePositionManager — mint/collect/rebalance — không cần farm và hoạt động với mọi nhóm.)

> **Chỉ các vị thế từ nhóm có farm đang hoạt động mới kiếm được CAKE.** Quản trị PancakeSwap đăng ký những nhóm nào có thể farm (mỗi nhóm có một `pid`). Stake một vị thế mà nhóm của nó chưa được đăng ký sẽ revert với `InvalidPid`. Đây là _nơi duy nhất_ hoạt động của agent phụ thuộc vào một danh sách phía PancakeSwap — và nó ở cấp nhóm, không phải cấp agent: bất kỳ ví nào cũng có thể stake vào bất kỳ farm _đang hoạt động_ nào. Hãy kiểm tra nhóm có farm đang chạy trước khi xây dựng chiến lược farming xoay quanh nó. (Quản lý vị thế qua NonfungiblePositionManager — mint/collect/rebalance — không cần farm và hoạt động với mọi nhóm.)

* **Stake** — chuyển NFT vị thế đến MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). Farm lúc này giữ NFT.
* **Harvest** — `harvest(tokenId, to)` nhận CAKE đang chờ mà không unstake. Dùng `batchHarvest` để nhận trên nhiều vị thế trong một giao dịch.
* **Withdraw / exit** — `withdraw(tokenId, to)` unstake, harvest CAKE đang chờ, và trả NFT về ví của bạn. Bạn phải withdraw trước khi có thể `decreaseLiquidity`/`burn` (các lệnh gọi NFPM ở §6 chỉ hoạt động trên NFT mà ví của bạn đang giữ).

Do đó, bot tái cân bằng cho một vị thế **đang farm** chạy theo thứ tự: `withdraw` → remove/collect/burn → mint → `safeTransferFrom` trở lại MasterChefV3.

***

### 8. An toàn, giới hạn & tuyên bố miễn trừ

Hãy đọc phần này trước khi triển khai một agent di chuyển tiền thật.

* **Tính tự chủ là không thể đảo ngược.** Một agent đã triển khai ký và gửi giao dịch mà không có con người xác nhận. Một lỗi, một điều kiện kích hoạt sai, hoặc một nguồn giá bị thao túng sẽ được thực thi thật. Hãy kiểm thử trên BSC testnet, sau đó giới hạn mức rủi ro trên mainnet (giới hạn theo giao dịch và theo ngày) trước khi mở rộng quy mô.
* **Trượt giá và deadline là bắt buộc**, không phải tùy chọn (§5). Một agent bỏ qua chúng sớm muộn sẽ bị sandwich.
* **Phòng vệ thao túng giá.** Trước khi hành động, hãy kiểm tra hợp lý giá nhóm với một tham chiếu độc lập và bỏ qua lần chạy nếu chúng chênh lệch — bảo hiểm rẻ tiền chống lại việc giao dịch vào một nhóm bị thao túng hoặc mỏng.
* **Gas và nguồn vốn.** Luôn giữ ví agent có đủ BNB để trả gas; một agent cạn kiệt có thể để vị thế dở dang giữa lúc tái cân bằng (đã rút nhưng chưa mint lại). Đọc lại trạng thái ở mỗi lần chạy (§4) giúp nó phục hồi ở tick tiếp theo.
* **Token Scaled-UI / RWA.** Một số token BSC (ví dụ Binance Stock Tokens) dùng hệ số nhân UI on-chain (ERC-8056). Số lượng thô on-chain khác với số lượng hiển thị. Nếu agent của bạn giao dịch các token này, hãy thực hiện mọi phép toán hợp đồng bằng đơn vị thô và chỉ áp dụng hệ số nhân cho phần hiển thị cho người dùng.
* **Bạn chịu trách nhiệm về agent của mình.** Các nhóm PancakeSwap là hợp đồng không cần cấp phép; triển khai một agent tự động trên chúng là quyết định và rủi ro của bạn. Hướng dẫn này là tài liệu tham khảo kỹ thuật, không phải lời khuyên tài chính, và PancakeSwap không bảo đảm về kết quả.

***

### 9. Tham khảo

* **`@pancakeswap/smart-router`** — định tuyến + calldata hoán đổi (các ví dụ tốt nhất trong repo nằm ở README của nó)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, phép toán tick/giá
* **BNB Agent Studio** — mô tả, xây dựng và triển khai agent (tài liệu BNB)
* **Địa chỉ triển khai PancakeSwap** — danh sách hợp đồng chính thức (xác minh trước khi dùng)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
