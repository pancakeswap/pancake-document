# 🤖 PancakeSwap V3에서 트레이딩 에이전트 구축하기

이 페이지는 개요를 제공합니다. 자세한 내용은 [pancakeswap.ai](https://pancakeswap.ai)를 방문하세요.

> [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) 또는 다른 프레임워크로 BNB Smart Chain의 PancakeSwap V3 유동성 풀 및 파밍과 상호작용하는 자율 에이전트를 구축하는 개발자를 위한 가이드입니다.
>
> 전략을 설명하면 에이전트가 사람의 개입 없이 온체인에서 이를 실행합니다. 이 페이지는 PancakeSwap 측 내용을 다룹니다. 호출할 컨트랙트, 안전한 호출 순서, 그리고 완전한 실제 예시(자동화된 V3 범위 리밸런서)입니다. 에이전트 자체를 설명하고 구축하고 배포하는 방법은 BNB Agent Studio 문서를 참조하세요.

이 작업에는 PancakeSwap과의 **별도 통합이 필요하지 않습니다**. V3 풀과 파밍은 허가가 필요 없는 스마트 컨트랙트이며, 에이전트는 PancakeSwap 프론트엔드와 동일한 방식으로 이를 직접 호출합니다. 아래의 모든 내용은 공개된 온체인 인터페이스입니다.

***

### 1. 에이전트가 PancakeSwap으로 할 수 있는 일

집중 유동성(V3)은 LP에게 V2보다 훨씬 높은 자본 효율성을 제공하지만 그 대가로 적극적인 관리가 필요합니다. 포지션은 가격이 틱 범위 안에 있을 때만 수수료를 얻으며, 보상과 수익률은 끊임없이 변합니다. 이러한 운영 부담을 덜어 주는 것이 바로 에이전트입니다. 일반적인 전략은 다음과 같습니다.

* **범위 리밸런서** — LP 포지션을 감시하다가 가격이 범위의 경계로 다가가면 유동성을 출금하고 새로운 가격 주변으로 다시 민팅하여 포지션이 계속 수수료를 얻도록 합니다. _(실제 예시는 §6 참조.)_
* **파밍 APR 라우터** — 여러 풀에서 CAKE + 수수료 수익률을 추적하여 유동성을 총수익률이 가장 높은 곳으로 이동합니다.
* **스왑/견적 봇** — V2 + V3 전반에서 최적 체결을 위해 Smart Router를 통해 거래를 라우팅합니다.

이 모든 전략은 아래의 몇 가지 동일한 컨트랙트 호출을 조합한 것입니다.

***

### 2. 컨트랙트 인터페이스 (BNB Smart Chain, chainId 56)

| 컨트랙트                                  | 주소                                           | 에이전트의 사용 목적                                                                        |
| ------------------------------------- | -------------------------------------------- | ---------------------------------------------------------------------------------- |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | LP 포지션 생성/관리 — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | V2+V3 최적 라우팅으로 스왑 실행                                                               |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | 포지션 NFT를 스테이킹하여 CAKE 파밍 — `harvest`, `withdraw`                                    |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | 스왑을 보내기 전에 견적 조회                                                                   |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | `(token0, token1, fee)`로부터 풀 주소 확인                                                 |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | **Smart Router 스왑**을 위한 가스 없는/일괄 토큰 승인 (§5.1 참조)                                   |

> ⚠️ 실제 자산을 보내기 전에 공식 PancakeSwap 배포 목록과 대조하여 **항상 주소를 다시 확인하세요**. 위 표는 출발점으로만 활용하세요.

V3 **풀**은 `(token0, token1, fee)`로 식별됩니다. 수수료 등급과 틱 간격은 다음과 같습니다.

| 수수료   | `fee` 값 | 틱 간격 | 일반적인 용도                |
| ----- | ------- | ---- | ---------------------- |
| 0.01% | `100`   | 1    | 스테이블–스테이블              |
| 0.05% | `500`   | 10   | 상관성 높은 자산 (예: ETH/BTC) |
| 0.25% | `2500`  | 50   | 대부분의 페어                |
| 1.00% | `10000` | 200  | 비주류 / 변동성 높은 자산        |

V3 **포지션**은 NonfungiblePositionManager에 보관되는 ERC-721 NFT입니다. `tickLower`, `tickUpper`, `liquidity` 및 누적 수수료를 저장하며 `tokenId`로 참조합니다.

***

### 3. 도구

원시 ABI와 아무 web3 라이브러리로도 이 컨트랙트와 통신할 수 있지만, **`@pancakeswap/v3-sdk`** 및 **`@pancakeswap/smart-router`** 패키지가 까다로운 계산(틱 ↔ 가격, 슬리피지가 반영된 최솟값, calldata 인코딩)을 대신 처리해 줍니다. 아래 예시는 [viem](https://viem.sh/)과 함께 이 패키지들을 사용합니다.

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

에이전트는 일정이나 트리거에 따라 거래를 실행하는 이 지갑일 뿐입니다. 지갑은 Agent Studio가 자금을 충전하고 관리합니다. BNB 문서를 참조하세요.

***

### 4. 상태 읽기 (모든 작업 전에 수행)

에이전트는 체인을 읽어서 작업을 \_할지 여부\_를 결정합니다. 대부분의 전략을 움직이는 세 가지 읽기 작업은 다음과 같습니다.

**풀 가격과 현재 틱** — 온체인 `slot0` + `liquidity`로 `Pool` 엔티티를 생성합니다.

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

**보유한 포지션** — `tokenId`로 NonfungiblePositionManager에서 읽어옵니다.

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**포지션이 범위 안에 있는가?** 이 단일 불리언 값이 리밸런서의 트리거입니다. "경계로부터 N틱 이내"로 조건을 더 엄격하게 설정하면 범위를 벗어나기 _전에_ 조치할 수 있습니다.

***

### 5. 안전한 트랜잭션 순서

이 부분은 정확하게 구현해야 합니다. 사람이 없는 에이전트는 잘못된 트랜잭션을 잡아 줄 사람이 없으므로, 상태를 변경하는 모든 호출은 아래 네 가지 가드레일로 보호되어야 합니다.

#### 5.1 승인

컨트랙트가 토큰을 이동시키려면 허용량(allowance)이 필요합니다. 적합한 방식은 호출하는 컨트랙트에 따라 다르며, 아래 세 가지 모두 허가가 필요 없습니다.

* **ERC-20 `approve`** — Smart Router와 NonfungiblePositionManager 모두에서 모든 토큰에 사용할 수 있습니다. 토큰/스펜더당 하나의 트랜잭션이 필요합니다. 가장 간단하지만 상시 무한 승인은 상시 위험이 됩니다.
* **`selfPermit` (EIP-2612)** — **NonfungiblePositionManager** 유동성 작업용입니다. 토큰이 EIP-2612를 지원하면 SDK가 multicall을 통해 서명된 금액 한정 permit을 `mint`/`increaseLiquidity`와 _함께_ 묶을 수 있어 별도의 approve 트랜잭션이 필요 없습니다. EIP-2612를 지원하지 않는 토큰은 `approve`로 대체됩니다.
* **Permit2** — **Smart Router** 스왑용입니다. 토큰당 한 번 Permit2를 승인한 후, 스왑마다 단기간 유효한 서명된 금액 한정 허용량을 부여합니다.

자율 에이전트의 경우 모든 permit을 정확한 금액과 짧은 만료 시간으로 한정하세요. **상당한 잔액을 보유한 에이전트 지갑에서 무제한 승인을 절대 부여하지 마세요.**

#### 5.2 슬리피지 — `amountMin = 0`을 절대 보내지 마세요

모든 추가/제거/스왑에는 허용 가능한 최소 출력을 지정해야 합니다. 직접 계산하지 말고 SDK가 허용치로부터 도출하도록 하세요.

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

스왑의 경우 Smart Router가 `slippageTolerance`를 적용하여 `amountOutMinimum`을 대신 계산합니다(§6, 0단계). **최솟값이 0이면 샌드위치 봇에게 문을 열어주는 것과 같으며**, 사람이 없는 지갑에서는 조용히 반복되는 손실로 이어질 수 있습니다.

#### 5.3 마감 시간 — 항상 설정하세요

모든 호출은 `deadline`(유닉스 초)을 받습니다. 해당 시간에 트랜잭션이 아직 대기 중이면 오래된 가격으로 실행되는 대신 되돌려집니다. 에이전트에서는 짧게 유지하세요.

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutes
```

#### 5.4 Multicall — 여러 단계의 작업을 원자적으로 만들기

NonfungiblePositionManager와 Smart Router는 `multicall`을 지원합니다. 여러 호출을 **하나의 트랜잭션**으로 묶어 모두 성공하거나 모두 되돌려지게 합니다. 이는 단순한 가스 절약이 아니라 안전 속성입니다. `decreaseLiquidity` 후 `collect`를 수행하는 리밸런싱은 절반만 실행되어서는 안 됩니다. SDK가 대신 묶어 줍니다.

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **원자적인 "리밸런스" 함수는 없습니다.** 범위를 이동하는 것은 _조합된_ 순서(제거 → 수령 → 민팅)입니다. 제거와 새로운 민팅은 별도의 트랜잭션에서 이루어지며 그 사이에 가격이 움직일 수 있습니다. 제거가 확인된 후 상태를 다시 읽고 민팅의 최솟값을 다시 계산하세요. 제거 이전의 수치를 재사용하지 마세요.

#### 가드레일 체크리스트 (모든 에이전트 작업에 적용)

* \[ ] 토큰 허용량은 무한이 아닌 금액으로 한정(Permit2)
* \[ ] `amount*Min` / `amountOutMinimum`은 명시적인 슬리피지 허용치로부터 도출하며 절대 `0`이 아님
* \[ ] 모든 호출에 짧은 `deadline` 설정
* \[ ] 여러 단계의 작업은 `multicall`로 묶음
* \[ ] 순서 내 별도 트랜잭션 사이에 상태를 다시 읽음
* \[ ] 실행당 이동 가치의 상한을 두고, 작업 전에 풀 가격이 예상 범위 내에 있는지 확인(조작되었거나 유동성이 낮은 풀에서 작업하는 것에 대한 저렴한 방어)

***

### 6. 실제 예시 — 자동화된 V3 범위 리밸런서

레퍼런스 에이전트입니다. 하나의 포지션을 감시하다가 가격이 범위 경계에 가까워지면 유동성을 빼내어 현재 가격을 중심으로 새로운 범위를 다시 민팅합니다. 총 다섯 단계입니다.

**트리거:** `pool.tickCurrent`가 `tickLower`/`tickUpper`의 버퍼 이내에 있음(§4 기준).

#### 0단계 — (선택 사항) 토큰 비율 재조정

출금 후에는 이전 범위에서 생성된 비율대로 token0과 token1을 보유하게 됩니다. 새로 중심을 맞춘 범위는 보통 다른 비율이 필요하므로 Smart Router를 통해 초과분을 스왑합니다.

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

#### 1\~3단계 — 유동성 제거, 수령, 소각 (하나의 트랜잭션)

`removeCallParameters`가 전체 번들을 구성합니다. `decreaseLiquidity`로 유동성을 0으로 줄이고, 출금된 원금과 누적 수수료를 모두 `collect`하고, 이제 비어 있는 NFT를 `burn`합니다. 이 모든 과정이 하나의 원자적 `multicall`로 처리됩니다.

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

> 포지션이 **MasterChefV3에 스테이킹되어 있다면** NFPM에서 제거할 수 없습니다. 먼저 `MasterChefV3.withdraw(tokenId, to)`를 호출하여 언스테이킹하고(대기 중인 CAKE도 함께 수확됩니다) NFT를 지갑으로 되돌려 받은 후 위의 제거 작업을 실행하세요. §7을 참조하세요.

#### 4단계 — 새로운 범위 민팅

_현재_ 가격을 중심으로 틱을 다시 계산하고(풀을 다시 읽으세요 — §5.4 참조), 수수료 등급의 간격에 맞춰 조정한 다음, 현재 보유한 토큰으로 `Position`을 구성하여 민팅합니다.

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

이제 에이전트는 범위 안에 있는 새로운 NFT를 보유합니다. 파밍 중이었다면 다시 스테이킹하세요(§7). 다음 틱에서 §4의 읽기 작업으로 돌아가 반복합니다.

***

### 7. 파밍 상호작용 (MasterChefV3)

V3 포지션 NFT를 MasterChefV3에 스테이킹하면 스왑 수수료에 더해 CAKE를 얻습니다.

> **활성 파밍이 있는 풀의 포지션만 CAKE를 얻습니다.** PancakeSwap 거버넌스가 파밍 가능한 풀을 등록합니다(각 풀은 `pid`를 부여받습니다). 풀이 등록되지 않은 포지션을 스테이킹하면 `InvalidPid`로 되돌려집니다. 에이전트 활동이 PancakeSwap 측 목록에 의존하는 유일한 부분이며, 이는 에이전트 단위가 아닌 풀 단위입니다. 어떤 지갑이든 활성 파밍에 스테이킹할 수 있습니다. (NonfungiblePositionManager를 통한 포지션 관리 — 민팅/수령/리밸런스 — 는 파밍이 필요 없으며 모든 풀에서 작동합니다.)

> **활성 파밍이 있는 풀의 포지션만 CAKE를 얻습니다.** PancakeSwap 거버넌스가 파밍 가능한 풀을 등록합니다(각 풀은 `pid`를 부여받습니다). 풀이 등록되지 않은 포지션을 스테이킹하면 `InvalidPid`로 되돌려집니다. 에이전트 활동이 PancakeSwap 측 목록에 의존하는 _유일한_ 부분이며, 이는 에이전트 단위가 아닌 풀 단위입니다. 어떤 지갑이든 _활성_ 파밍에 스테이킹할 수 있습니다. 파밍 전략을 구축하기 전에 해당 풀에 운영 중인 파밍이 있는지 확인하세요. (NonfungiblePositionManager를 통한 포지션 관리 — 민팅/수령/리밸런스 — 는 파밍이 필요 없으며 모든 풀에서 작동합니다.)

* **스테이킹** — 포지션 NFT를 MasterChefV3로 전송합니다(`safeTransferFrom(owner, masterChefV3, tokenId)`). 이제 파밍이 NFT를 보관합니다.
* **수확** — `harvest(tokenId, to)`는 언스테이킹 없이 대기 중인 CAKE를 수령합니다. `batchHarvest`를 사용하면 여러 포지션을 하나의 트랜잭션으로 수령할 수 있습니다.
* **출금 / 종료** — `withdraw(tokenId, to)`는 언스테이킹하고, 대기 중인 CAKE를 수확하며, NFT를 지갑으로 반환합니다. `decreaseLiquidity`/`burn`을 하려면 먼저 출금해야 합니다(§6의 NFPM 호출은 지갑이 보유한 NFT에서만 작동합니다).

따라서 **파밍 중인** 포지션의 리밸런서는 `withdraw` → 제거/수령/소각 → 민팅 → MasterChefV3로 `safeTransferFrom` 순서로 실행됩니다.

***

### 8. 안전, 한계 및 면책 조항

실제 자금을 이동시키는 에이전트를 배포하기 전에 이 내용을 읽어 보세요.

* **자율성은 되돌릴 수 없습니다.** 배포된 에이전트는 사람의 확인 없이 트랜잭션에 서명하고 전송합니다. 버그, 잘못된 트리거 또는 조작된 가격 피드가 실제로 실행됩니다. BSC 테스트넷에서 테스트한 후 확장하기 전에 메인넷 노출 한도(거래당 및 일일 한도)를 설정하세요.
* **슬리피지와 마감 시간은 선택이 아닌 필수입니다**(§5). 이를 생략한 에이전트는 결국 샌드위치 공격을 당합니다.
* **가격 조작 방어.** 작업 전에 풀 가격을 독립적인 기준과 비교하여 검증하고, 차이가 크면 해당 실행을 건너뛰세요. 조작되었거나 유동성이 얕은 풀에서 거래하는 것에 대한 저렴한 보험입니다.
* **가스 및 자금.** 에이전트 지갑에 가스비용 BNB를 충분히 유지하세요. 자금이 고갈된 에이전트는 리밸런싱 도중(제거되었지만 다시 민팅되지 않은 상태)에 멈출 수 있습니다. 매 실행마다 상태를 다시 읽으면(§4) 다음 틱에서 복구할 수 있습니다.
* **스케일드 UI / RWA 토큰.** 일부 BSC 토큰(예: Binance Stock Tokens)은 온체인 UI 승수(ERC-8056)를 사용합니다. 온체인 원시 금액은 표시되는 금액과 다릅니다. 에이전트가 이러한 토큰을 거래한다면 모든 컨트랙트 계산을 원시 단위로 수행하고 사람에게 보여주는 표시에만 승수를 적용하세요.
* **에이전트에 대한 책임은 본인에게 있습니다.** PancakeSwap 풀은 허가가 필요 없는 컨트랙트이며, 이를 대상으로 자율 에이전트를 배포하는 것은 본인의 결정이자 본인의 위험입니다. 이 가이드는 기술 참고 자료이며 재무 조언이 아니고, PancakeSwap은 결과에 대해 어떠한 보증도 하지 않습니다.

***

### 9. 참고 자료

* **`@pancakeswap/smart-router`** — 라우팅 + 스왑 calldata (저장소 내 가장 좋은 예시는 해당 README에 있음)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, 틱/가격 계산
* **BNB Agent Studio** — 에이전트 설명, 구축, 배포 (BNB 문서)
* **PancakeSwap 배포 주소** — 공식 컨트랙트 목록 (사용 전 확인)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
