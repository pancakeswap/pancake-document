---
description: ApolloX가 V2에서 트레이딩 리워드 프로그램을 시작합니다
hidden: true
---

# 트레이딩 리워드 프로그램

### 리워드 프로그램 개요

세부 내용은 다음과 같습니다.

활동 기간: 주기와 체인에 따라 날짜가 다릅니다

리워드 지급 시간: 각 주기는 매일 00:00 (UTC)부터 23:59 (UTC)까지입니다. 리워드는 다음 날 03:00 (UTC) 무렵에 지급됩니다. 사용자는 리워드가 지급된 후 30일 이내에 리워드를 수령해야 합니다. 수령하지 않으면 플랫폼이 리워드를 회수합니다.

리워드 금액: 하루 최대 $15,000 USD 상당의 APX

활동 규칙: V2에서 거래하는 사용자는 리워드 상금 풀에서 보상을 받습니다. DAO에 APX를 스테이킹하여 veNFT를 획득한 사용자는 veNFT로 산출된 Power 값에 따른 부스팅 배수를 적용받습니다.

| Power 값                   | 부스팅 배수 |
| ------------------------- | ------ |
| 50,000 < Power =<100,000  | 1.5    |
| 100,000 < Power =<300,000 | 2      |
| Power > 300,000           | 2.5    |

트레이딩 리워드 계산 공식:

각 트레이딩 리워드 주기가 끝나면 해당 주기에서 사용자의 유효 거래 수수료와 스테이킹 수량을 계산하여 APX 리워드의 가중치와 수량을 결정합니다. 공식은 다음과 같습니다.

r = R\*W / sum(Wi)

매개변수:

| r       | 이번 주기의 사용자 APX 리워드                                                                                                                                       |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | 전일 사용자의 V2 거래 수수료 기여도와 최신 APX 토큰 가격으로 결정됩니다                                                                                                              |
| W       | <p>개인 총 가중치 점수 W=f*w, 여기서;</p><p>f는 이번 주기에 사용자가 기여한 유효 거래 수수료로, USD로 환산됩니다.</p><p>w는 이번 주기에 사용자가 DAO에 APX를 스테이킹하여 얻은 부스팅 배수입니다. (자세한 내용은 위 표를 참고하세요)</p> |
| sum(Wi) | 모든 사용자의 총점입니다. Wi는 개별 사용자의 점수를, sum(Wi)는 모든 사용자 점수의 합계를 나타냅니다                                                                                            |

R의 계산 공식은 다음과 같습니다.

R=Min(Dollar value multiplier \* Trading Fee, Dollar value Cap)/ Max(APX Last Price,APX Price Floor)

* Dollar value multiplier(달러 가치 배수): 이번 에포크 0.70
* Trading Fee(거래 수수료): 전일 V2 수수료 수입을 USD로 환산한 가치
* Dollar value Cap(달러 가치 상한): 시스템 설정 기준 15,000
* APX Last Price(APX 최근 가격): 최신 APX 토큰 가격 기준
* APX Price Floor(APX 가격 하한): 이번 에포크 0.04

이용 약관

* 각 주기가 끝난 후 ApolloX는 사용자 피드백과 시장 상황에 따라 프로그램 규칙을 조정할 수 있습니다. 리워드는 비선형적으로 지급됩니다.
* 활동 기간 동안 플랫폼은 ALP 풀에 투입되는 V2 거래 수수료 수입의 비율을 50%에서 20%로 줄입니다. 나머지 30%는 APX를 재매입하는 데 사용됩니다.
* V2의 거래 페어마다 거래 수수료가 다르기 때문에, 유효 거래량이 같더라도 사용자가 받는 리워드는 달라질 수 있습니다.
* 각 주기에 분배될 리워드는 다음 컨트랙트 주소에 보관됩니다: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX는 이 활동에 대한 최종 해석 권한을 보유합니다.

위험 경고: 암호화폐 선물 거래는 상당한 위험을 수반합니다. 모든 거래 활동은 사용자의 재량과 책임하에 이루어집니다. 여기에 있는 정보는 ApolloX의 재무 또는 투자 조언으로 간주되어서는 안 됩니다. ApolloX는 사용자가 ApolloX를 이용함으로써 발생할 수 있는 어떠한 손실에 대해서도 책임지지 않습니다.

### 리워드 수령하기

트레이딩 리워드 프로그램은 파트너인 ApolloX가 운영하므로, 리워드를 수령하려면 다음 단계를 진행하세요.\
\
1단계: [PancakeSwap 무기한 선물 페이지](https://perp.pancakeswap.finance/en/futures/v2/)로 이동합니다.

2단계: 페이지 상단의 Trading Reward (V2) 탭을 클릭합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

3단계: ApolloX 리워드 수령 페이지로 이동하여 현재 리워드 상태를 확인할 수 있습니다. 활동 기간 중에 "Claim"을 클릭하여 리워드를 수령하세요.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
