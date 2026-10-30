# CAKE 토크노믹스 v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **발행 속도** <a href="#emission-rate" id="emission-rate"></a>

### **블록당**

| **지표**                                                               | **블록당 발행량 (CAKE)** | **일일 발행량 (CAKE)** |
| -------------------------------------------------------------------- | -----------------: | ----------------: |
| 발행량                                                                  |                 40 |         1,152,000 |
| 주간 소각 [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |             -25.75 |          -787,600 |
| **실질 발행량**                                                           |       **<14.25\*** |     **364,400\*** |

\*실질 발행량은 사실 이 수치보다 약간 낮습니다. 복권에 할당된 금액에서 하루 45,000 CAKE가 추가로 전용되어 소각됩니다(PID 137 - 자세한 내용은 아래 참조).

위 내용에 더해 동적인 양의 CAKE가 9.09%의 비율로 [Dev 주소로 민팅](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns)됩니다. 즉, 100 CAKE가 수확되면 추가로 9.09 CAKE가 민팅되어 Dev 주소로 전송됩니다.

{% hint style="info" %}
Dev 주소로 민팅된 모든 CAKE는 주간 소각에서 소각되며 유통에 진입하지 않습니다.

따라서 위의 발행 속도에는 포함하지 않았습니다.
{% endhint %}

## 분배 <a href="#distribution" id="distribution"></a>

| 분배 대상             | 블록당 보상 (발행량의 %) | 블록당 보상 (총 CAKE) |           일일 보상 |
| ----------------- | --------------: | --------------: | --------------: |
| 파밍 및 복권           |          10.62% |            4.25 |     122,400 (약) |
| 이 중 전용되어 소각됨      |                 |                 |         -46,000 |
| 시럽 풀              |             25% |              10 |     288,000 (약) |
| **일일 총 CAKE 발행량** |                 |                 | **364,400 (약)** |

## **기타 디플레이션 메커니즘** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
소각 과정은 현재 수동으로 진행됩니다. [소각 거래는 여기에서 확인하세요](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

위 방식 외에도 CAKE는 다음과 같은 방식으로 소각됩니다.

* PancakeSwap V2에서 이루어지는 모든 거래의 **0.05%**
* Dev 주소로 전송된 CAKE의 **100%**
* IFO의 CAKE 성과 수수료의 **100%**
* 프로필 생성 및 NFT 민팅에 사용된 CAKE의 **100%**
* 파밍 경매 중 입찰된 CAKE의 **100%**
* 복권 티켓에 사용된 CAKE의 **20%**
* 하루 **45,000** CAKE (과거 복권에 할당됨) (_이를 위한 CAKE는 파밍 - PID 137에서 생성됩니다_)
* 예측 마켓의 모든 라운드에서 \*\*3%\*\*가 CAKE를 구매하여 소각하는 데 사용됩니다.
* Auto CAKE 풀의 모든 수익 수확의 **2%**
* NFT 마켓에서의 모든 NFT 판매의 \*\*2%\*\*가 CAKE를 구매하여 소각하는 데 사용됩니다.

## CAKE 소각이 수동인 이유는 무엇인가요?

빠르게 시작하기 위해 PancakeSwap은 MasterChef 컨트랙트가 블록당 40 CAKE를 발행하는 MVP(최소 기능 제품)로 출시되었습니다. 이러한 이유로 초기 팀은 CAKE 민팅 로직을 사용자 지정하는 기능과 같은 추가 기능을 넣지 않았습니다. 새로운 MasterChef로 마이그레이션하려면 많은 시간과 노력이 필요하므로 팀은 두 개의 풀을 만들어 수동 소각 과정을 통해 CAKE 발행량을 줄이는 방식을 택했습니다.

* 레거시 복권 풀(PID - 137) - 복권의 CAKE를 소각
* 소각 풀(PID - 138) - 블록당 CAKE를 소각

이 풀들은 파밍과 비슷하게 작동하며, 셰프들은 CAKE 발행량 감소 투표 이후마다 블록당 40 CAKE 중 해당 풀에 할당되는 비율을 조정할 수 있습니다.

{% hint style="warning" %}
소각하는 날에는 홈페이지에 표시되는 공급량이 갑자기 수백만 CAKE 늘어날 수 있습니다.

걱정하지 마세요 - **이 CAKE는 실제로 유통에 진입하지 않습니다.**
{% endhint %}

이 겉보기상의 급증은 소각을 위해 할당된 모든 CAKE가 한 주 동안 보관되는 방식 때문일 뿐입니다.

PID-137과 PID-138 두 풀로 전송된 CAKE는 주간 토큰 소각을 완료하기 전에 수확되며, 이로 인해 사이트에 표시되는 총 공급량이 약 600만 개 증가합니다. 이는 대기 중인 CAKE가 소각일에 수확될 때까지 총 공급량에 반영되지 않기 때문입니다. 토큰 소각 거래가 완료되면 약 600만 개는 지금까지 소각량에 표시됩니다.

## CAKE 공급량을 직접 확인하는 방법

PancakeSwap 홈페이지에 표시되는 유통 CAKE 공급량이 정확한지 확인하려면,

1. BscScan에서 CAKE 토큰 컨트랙트로 이동하여 [소각 주소에 보관된 CAKE의 양을 확인](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances)하세요. 이것이 소각된(영원히 유통에서 제거되어 되찾을 수 없는) CAKE의 총량입니다.
2. 그런 다음 BscScan에 표시된 "Total Supply"에서 이 소각량을 빼세요.
3. 그러면 실제 CAKE 공급량을 알 수 있습니다.

#### **CAKE의 디플레이션 메커니즘에 대해서는 다음 페이지에서 자세히 알아보세요.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
