---
hidden: true
---

# 마켓 메이커 통합

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Ethereum의 마켓 메이커 통합

PancakeSwap은 Ethereum과 Binance Smart Chain에서 마켓 메이커와 통합되어 트레이더가 더 낮은 비용으로 거래를 체결할 수 있도록 돕습니다.

이제 PancakeSwap의 거래는 AMM 외에도, 지정된 화이트리스트 마켓 메이커가 AMM의 현재 가격보다 더 좋은 체결을 제공하는 경우 해당 마켓 메이커로 라우팅될 수 있습니다. 이 라우팅은 [Smart Router](smart-router-v2/)가 자동으로 처리하며, 마켓 메이커가 더 좋은 가격을 적극적으로 제시할 때에만 거래가 마켓 메이커로 라우팅됩니다. AMM이 더 경쟁력 있는 경우에는 AMM으로 라우팅되어 체결됩니다.

PancakeSwap에서 마켓 메이커가 운영되는 시나리오는 두 가지입니다.

**시나리오 1: 기존 AMM 유동성 풀이 있는 경우**

특정 토큰(예: WETH/USDC)에 대한 유동성이 이미 PancakeSwap AMM에 있다면, PancakeSwap은 동일한 거래에 대해 마켓 메이커에게 견적을 요청합니다. 그러면 PancakeSwap의 Smart Router가 그 시점에 가장 좋은 가격을 제공하는 유동성 소스에 따라 거래 요청을 AMM 또는 마켓 메이커로 라우팅합니다.

**시나리오 2: 기존 AMM 유동성 풀이 없는 경우**

이 경우 Smart Router가 거래를 마켓 메이커로 자동 라우팅합니다. 다만 프로젝트가 이후에 AMM 유동성 풀을 만들고 저희와 협력하여 탈중앙화 DEX 유동성을 유지하는 것을 막지는 않습니다.

### 수수료

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap은 마켓 메이커가 체결하는 거래에 대해 트레이더에게 어떠한 수수료도 부과하지 않습니다. 대신 PancakeSwap은 화이트리스트 마켓 메이커가 체결한 거래량에 대해 마켓 메이커로부터 **0.05%**의 **거래 수수료**를 받습니다. 스테이블코인 페어 간 거래의 경우에는 낮아진 **0.01%**의 **거래 수수료**를 받습니다. 아래 수수료 내역을 참고하세요.<br>

<table><thead><tr><th width="178">거래</th><th width="138">거래 수수료</th><th width="182">MM으로부터의 PCS 수수료</th><th width="147">CAKE 소각</th><th align="center">PancakeSwap 트레저리</th></tr></thead><tbody><tr><td>다른 네트워크에서 브릿지된 코인</td><td>해당 없음</td><td>0.25%</td><td>0.083%</td><td align="center">0.167%</td></tr><tr><td>Ethereum의 비스테이블코인 (예: ETH/USDC)</td><td>해당 없음</td><td>0.05%</td><td>0.017%</td><td align="center">0.033%</td></tr><tr><td>BSC의 비스테이블코인 (예: BNB/USDT)</td><td>해당 없음</td><td>0.05%</td><td>0.017% </td><td align="center">0.033%</td></tr><tr><td>Ethereum의 스테이블코인 간 거래</td><td>해당 없음</td><td>0.01%</td><td>0.003%</td><td align="center">0.007%</td></tr></tbody></table>

#### 현재 지원되는 자산

현재 다음 자산이 지원되며, 마켓 메이커에 따라 늘어나거나 줄어들 수 있습니다.

**Ethereum**

* **메이저 자산:** WETH, WBTC
* **스테이블코인:** USDT, USDC, DAI, BUSD
* **기타 인기 ERC-20 자산:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Binance Smart Chain**

* **메이저 자산:** BNB, ETH, BTCB
* BNB 네이티브가 아닌 토큰: ARB, OP

AMM과 달리 마켓 메이커는 모든 수량을 거래할 수 있는 것은 아니며, 체결 가능한 수량은 각 마켓 메이커의 유동성에 따라 달라진다는 점에 유의하세요. 매우 큰 주문은 전량 체결되지 않는 경우도 드물지 않습니다. 각 거래가 원하는 가격과 수량을 반영하는지 견적을 꼼꼼히 확인하시기 바랍니다.

**마켓 메이커 중단 시간**

마켓 메이커가 24시간 내내 견적을 제시하는 것은 아닙니다. 주요 경제 이벤트나 시스템 업그레이드 등으로 마켓 메이커가 일시적으로 견적을 제공하지 못하는 경우가 있습니다. 이 기간에는 해당 토큰을 거래할 수 없으며, 마켓 메이커가 다시 온라인 상태가 될 때까지 잠시 기다려 주시기 바랍니다.

#### 자주 묻는 질문 (FAQ)

**Q.** 마켓 메이커가 Aptos에도 통합되나요?

**답변:** 가능성은 있습니다. 더 나은 사용자 경험을 위한 유동성 확대를 위해 현재는 Ethereum과 Binance Smart Chain에만 마켓 메이커 통합을 출시하며, 다른 체인도 계속 살펴보겠습니다.

**Q.** 사용자에게 수수료를 부과하지 않는다면 PancakeSwap은 어떻게 수익을 얻나요?

**답변:** PancakeSwap은 사용자에게 어떠한 수수료도 부과하지 않지만, 마켓 메이커로부터 소정의 수수료를 받아 CAKE 바이백 및 소각에 사용합니다.

**Q.** 유동성 공급자는 계속 LP 수수료를 받나요?

**답변:** 네, 유동성 공급자는 앞으로도 0.17%의 거래 수수료 보상(LP 수수료)과 CAKE 파밍 수익을 계속 받게 됩니다.

**Q.** 마켓 메이커가 AMM에 유동성을 공급하나요? 그러면 APR이 낮아지나요?

**답변:** 마켓 메이커는 별도의 자체 유동성을 운용하므로 AMM 거래로부터 APR을 얻지 않습니다. AMM 풀에 유동성을 공급하는 LP만 수수료와 APR을 받습니다.

**Q.** Ethereum PancakeSwap에서 유동성을 공급하고 있습니다. 따로 해야 할 일이 있나요?

**답변:** 아니요, 아무것도 하실 필요가 없습니다. AMM을 통해 체결된 거래에 대한 LP 수수료를 계속 받으시고, CAKE 수익도 계속 얻으실 수 있습니다.

**Q.** 마켓 메이커가 되려면 어떻게 해야 하나요?

**답변:** 저희는 마켓 메이커를 개별적으로 심사하고 협력합니다. 협력에 관심이 있으시면 저희 또는 운영진을 통해 직접 문의해 주세요.
