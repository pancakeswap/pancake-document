---
description: Ethereum, BNB Chain, Aptos 등 다양한 체인 간에 CAKE를 브릿지하세요
---

# 🌉 브릿징

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
EVM 간 브릿지(새 사이트): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Aptos 간 브릿지(V1 브릿지): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## 암호화폐에서 브릿징이란 무엇인가요?

* 암호화폐에서 브릿징이란 서로 다른 블록체인 네트워크 간에 자산을 전송하는 과정을 말합니다.
* 상호 운용성을 높여 다양한 네트워크 간에 데이터와 자산을 이동할 수 있게 합니다.

\
다음과 같은 이유로 브릿지가 필요할 수 있습니다.

* 다양한 암호화폐 토큰 구매
* 특정 네트워크에서만 이용 가능한 NFT 민팅
* 더 저렴한 트랜잭션으로 비용 절감
* 다른 네트워크에서만 이용 가능한 dApp 사용

***

## CAKE, 멀티체인 토큰

멀티체인 확장과 배포를 통해 CAKE는 BNB Chain 네이티브 토큰이면서 Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB, Monad, Aptos에서도 이용할 수 있는 멀티체인 토큰이 되었습니다.

다른 체인의 CAKE는 BNB Smart Chain의 CAKE와 동일한 가치를 가집니다. 이 체인들 사이에서 CAKE는 언제나 1:1 비율로, CAKE 수수료 없이 브릿지할 수 있습니다.

**CAKE는 단 하나뿐이라는 점에 유의하세요.** 체인마다 다른 버전의 CAKE가 존재하지 않습니다. 모든 블록체인에 걸친 CAKE의 총 공급량은 이 [투표 제안](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5)에 명시된 대로 4억 개로 제한됩니다.

***

## PancakeSwap 브릿지란 무엇인가요?

PancakeSwap 브릿지는 PancakeSwap 인터페이스에서 바로 서로 다른 블록체인 간에 자산을 이동할 수 있게 해주는 편리한 앱 내 도구입니다. 외부 브릿지 사이트를 방문할 필요 없이 BNB Chain, Ethereum, Base, Arbitrum 등의 체인 간에 지원되는 토큰을 한곳에서 브릿지할 수 있습니다.

PancakeSwap 브릿지는 신뢰할 수 있는 서드파티 제공업체를 기반으로 하며, 가격, 속도, 안정성을 기준으로 최적의 경로를 선택하는 **애그리게이터**로 작동합니다.

CAKE를 브릿지하는 방법은 다음 섹션의 튜토리얼과 자주 묻는 질문 (FAQ)을 참고하세요.

***

## 🔗 작동 방식

### 애그리게이터를 통한 브릿징

PancakeSwap 브릿지는 신뢰할 수 있는 서드파티 브릿지 프로토콜 위에서 작동하는 스마트 레이어입니다. 브릿지 전송을 시작하면 PancakeSwap은 다음과 같이 처리합니다.

* 연동된 여러 브릿지를 확인해 최적의 경로를 찾습니다
* 선택된 제공업체로 트랜잭션을 전송합니다

브릿징은 논커스터디 방식으로, 자산이 PancakeSwap의 보관 상태가 되지 않습니다. 전송은 브릿지 제공업체가 직접 처리합니다.

### 지원되는 브릿지 제공업체

현재 다음 제공업체와 연동되어 있습니다.

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson
* Mayan

> 참고: 제공업체마다 브릿징 방식, 지원 체인, 수수료, 한도가 다릅니다.

***

### 지원되는 체인 및 토큰

#### 현재 지원되는 체인

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Monad
* Robinhood
* Solana
* Aptos (V1 사이트)

#### 브릿지 가능한 토큰

사용 가능한 토큰은 체인과 경로에 따라 다릅니다. 일반적으로 지원되는 토큰은 다음과 같습니다(이에 국한되지 않습니다).

* CAKE
* USDT
* USDC
* ETH

***

#### 제한 사항 및 제외 대상

일부 토큰은 브릿지 제한이나 유동성 제약으로 인해 지원되지 않을 수 있습니다. 이러한 토큰은 최상의 사용자 경험을 위해 제외되었습니다. 예를 들면 다음과 같습니다.

**cBridge의 경우:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**deBridge의 경우:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_위 목록은 예시입니다. 체인별로 실제 이용 가능한 토큰은 브릿지 UI에 직접 표시됩니다._

***

### 💸 수수료 및 비용

#### 브릿지 수수료

* 기반이 되는 브릿지 제공업체가 부과합니다
* 일반적으로 전송당 소액의 수수료가 포함됩니다
* 브릿지를 확정하기 전에 명확하게 표시됩니다

***

#### 가스 비용

* 트랜잭션을 시작하려면 **출발 체인**에서 가스비를 지불해야 합니다
* 일부 제공업체는 **도착 체인**의 가스도 요구할 수 있습니다
* **팁:** 브릿지 양쪽 체인 모두에 네이티브 토큰(예: ETH, BNB)을 항상 보유하세요

***

#### 최소 수량 및 제한 사항

일부 브릿지 경로에는 다음과 같은 제한이 적용됩니다.

* **최소/최대 브릿지 수량** (예: 최소 10 USDC)
* **지원되는 토큰 소수점 자릿수 또는 형식** (예: ERC-20 토큰만 가능)

UI가 유효하지 않은 전송을 자동으로 감지하여 표시합니다.

***

### ⏳ 트랜잭션 소요 시간 및 추적

#### 브릿징에는 얼마나 걸리나요?

브릿지 전송은 일반적으로 몇 **분** 안에 완료되며, 다음 요인에 따라 달라집니다.

* 출발 체인과 도착 체인
* 네트워크 혼잡도
* 브릿지 제공업체의 처리 효율

#### 전송 추적하기

전송을 제출한 후에는 제공업체별 탐색기에서 트랜잭션 상태를 확인할 수 있습니다.

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

트랜잭션이 오랫동안 멈춰 있다면 해당 탐색기를 확인하거나 [소셜 채널](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)을 통해 운영진에게 [도움](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help)을 요청하세요.

***

### 🧠 브릿지 전 유의 사항

* **양쪽 체인 모두에 가스 토큰을 보유하세요** (예: ETH + BNB)
* 처음 브릿지한다면 **소액으로 시작하세요**
* 체인 활동이 많은 시간대에는 브릿지를 피하세요(가스비가 높아질 수 있습니다)
* 양쪽 체인에서 토큰 호환 여부를 확인하세요
* 출발 네트워크와 도착 네트워크를 항상 다시 확인하세요

***

### 추가 정보: CAKE Omni-chain Fungible Token (OFT) 주소

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([링크](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([링크](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([링크](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([링크](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([링크](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([링크](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([링크](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([링크](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([링크](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
9. **Monad**
   * `cakeOFT`: `0xF59D81cd43f620E722E07f9Cb3f6E41B031017a3`
10. **Solana**
    * `cakeOFT`: `4qQeZ5LwSz6HuupUu8jCtgXyW1mYQcNbFAW1sWZp89HL`
