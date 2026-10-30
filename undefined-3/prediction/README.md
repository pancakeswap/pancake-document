# 🔮 예측

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap 예측은 재미있고 간단한 탈중앙화 예측 시장입니다.

> **BNB, BTC 또는 ETH 가격이 오를지 내릴지 예측하세요. 정확히 맞히면 보상을 받습니다!**

### 플랫폼

다음 환경에서 PancakeSwap 예측을 플레이할 수 있습니다.

* **데스크톱/dApp**: [PancakeSwap 예측 가이드](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram 미니 앱 (BNBUSD 전용)**: [예측 봇](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### 요약: 작동 방식

1. **베팅할 자산 선택**: 현재 **BNB 체인**에서 이용할 수 있으며, **zkSync Era**와 **Arbitrum One**의 마켓은 일시 중단되었습니다.
2. **상승(UP) 또는 하락(DOWN) 선택**: "LIVE" 단계가 끝날 때 자산 가격이 더 높을지 낮을지 예측합니다(각 라운드 = 5분).
3. 베팅 금액 입력: 원하는 BNB 금액
4. **포지션 확정**: 한 번 베팅하면 변경할 수 없습니다.
5. **승리 또는 패배**:
   * **UP**을 선택했다면 라운드 종료 시 _종가_ > _잠금 가격_ 일 때 승리합니다.
   * **DOWN**을 선택했다면 라운드 종료 시 _종가_ < _잠금 가격_ 일 때 승리합니다.

### 메커니즘 및 수수료

* **지원 체인: BNB 체인(운영 중), zkSync Era, Arbitrum One(일시 중단)**
* **라운드 주기**: **5분**마다(연속 라운드).
* **참여 수수료**: 각 라운드 전체 상금 풀의 \*\*3%\*\*이며, 그 일부는 **CAKE 바이백**에 사용됩니다.
* **상금**: 결과가 확정된 후 언제든지 수령할 수 있습니다.
* **지급금**은 각 풀의 베팅 비율에 따라 결정됩니다.
  * 지급 비율(UP 풀) = _(두 풀의 총 가치 ÷ UP 풀의 가치)_
  * 지급 비율(DOWN 풀) = _(두 풀의 총 가치 ÷ DOWN 풀의 가치)_
  * 계산 예시는 [FAQ](prediction-faq.md)를 참조하세요.

### 결과

* **승리:** 다른 승자들과 전체 상금을 나누어 받습니다(3% 수수료 제외).
* **패배:** 베팅한 금액 전액을 잃습니다.

**특수한 경우**:

* **무승부**(잠금 가격 = 종가): 모든 베팅금은 하우스가 가져갑니다.
* 반대편 베팅이 없는 경우:
  * 승리하면: 최초 베팅금의 97%를 되찾습니다(3% 수수료 적용).
  * 패배하면: 베팅금 전액을 하우스에 몰수당합니다.
* **취소:** 예를 들어 오라클 장애가 발생하면 사용자는 최초 베팅 금액을 환불받습니다.

### 가격 피드(오라클)

| 체인     | 마켓                                      | 용도                                         | 오라클                      |
| ------ | --------------------------------------- | ------------------------------------------ | ------------------------ |
| BNB 체인 | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (일시 중단) | \_잠금 가격\_과 \_종가\_를 설정합니다(최대 약 20초마다 업데이트). | **Chainlink**            |
| BNB 체인 | 전체                                      | UI의 실시간 차트에 사용됩니다(참고용).                    | Binance / TradingView 피드 |

#### **ChainLink 오라클**

* 각 예측 시장 라운드의 잠금 가격과 종료 가격에 사용됩니다. 최대 20초 간격으로 업데이트됩니다.
* 예측 컨트랙트는 BNB 체인의 ChainLink 오라클 가격 피드를 사용하여 사용자의 승패를 결정하는 가격을 설정합니다.
* 인터페이스의 "Chainlink" 차트에 사용됩니다.

#### **Binance**

* PancakeSwap 예측 시장 인터페이스의 실시간 가격 업데이트에 사용됩니다.
* 인터페이스의 "TradingView" 차트에 사용됩니다.

두 가지 다른 가격 피드를 사용하기 때문에 Binance의 실시간 가격 업데이트와 ChainLink 오라클 가격은 약간 다를 수 있습니다. 그러나 크게 차이 나지는 않습니다.

### 컨트랙트 주소

BNB 체인:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
