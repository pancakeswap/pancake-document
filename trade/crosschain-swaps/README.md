# 🔀 크로스체인 스왑

크로스체인 스왑을 사용하면 하나의 간소화된 트랜잭션으로 체인 간 토큰을 매끄럽게 스왑할 수 있습니다.

다음 체인 간 크로스체인 스왑이 지원됩니다.

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**트랜잭션이 매우 빠르며, 보통 몇 초에서 1분 이내에 완료됩니다.**
{% endhint %}

***

### 🔍 작동 방식

1. 사용자가 출발/도착 체인과 출발/도착 토큰을 선택합니다.
2. PancakeSwap 라우터가 가장 효율적인 경로를 계산합니다.
3. 출발 체인과 도착 체인에서 PancakeSwap의 유동성 풀(v2, v3, Infinity, StableSwaps)을 사용해 스왑이 실행됩니다.
4. 브릿징은 파트너 프로토콜을 통해 처리됩니다. EVM <> EVM은 [Across](https://across.to/), SOL <> EVM은 [Relay](https://relay.link/bridge)를 사용합니다.

{% hint style="success" %}
**출발 체인과 도착 체인 모두에 충분한 유동성이 있는 토큰이라면 어떤 토큰이든 크로스체인 스왑이 가능합니다.**
{% endhint %}

***

### 💸 수수료

* **PancakeSwap은 크로스체인 트랜잭션에 어떠한 수수료도 부과하지 않습니다.**
* 수수료는 다음으로 구성됩니다.
  1. **거래 수수료:** 출발 체인과 도착 체인의 유동성 풀에서 스왑할 때 발생합니다.
  2. **브릿지 수수료:** 자산을 브릿징하기 위해 릴레이어에게 지급됩니다.

***

### 🎯 인텐트(Intent)란 무엇인가요?

인텐트를 사용하면 결과를 어떻게 달성할지 신경 쓰지 않고 원하는 결과만 정의할 수 있습니다.

인텐트 예시:

* "Base의 1 ETH를 Arbitrum의 최소 3000 USDC로 스왑"

인텐트가 없다면 사용자는 직접 다음을 해야 합니다.

* ETH를 Arbitrum으로 브릿징
* ETH → USDC 가격이 가장 좋은 DEX 찾기

{% hint style="success" %}
**인텐트를 사용하면 시스템이 이 모든 것을 자동으로 처리합니다.**
{% endhint %}

**인텐트 기반 설계의 장점:**

* 매끄러운 사용자 경험
* 더 빠른 트랜잭션 처리 시간
* 클릭 한 번으로 끝나는 단일 트랜잭션

***

### 🔐 감사

크로스체인 보안 분야에서 인정받는 팀들과 여러 차례 감사를 진행했습니다.

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
