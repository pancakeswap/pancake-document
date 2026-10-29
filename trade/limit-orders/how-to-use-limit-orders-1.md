# 지정가 주문 사용 방법

PancakeSwap의 수수료 수익형 지정가 주문은 기존의 지정가 주문과 다르게 작동합니다. 사용자가 지정가 주문을 넣으면 사실상 PancakeSwap Infinity 풀에 **단방향 유동성**을 제공하는 것입니다.

시장 가격이 움직이면 풀의 스왑이 사용자의 유동성을 사용할 수 있습니다. 이 경우 예치한 토큰이 출력 토큰으로 전량 전환되며, 사용자는 다음을 받습니다.

* 출력 토큰, 그리고
* 자신의 유동성을 상대로 실행된 스왑에서 발생한 거래 수수료.

***

**예시: BNB를 USDT로 매도하기**

* **BNB/USDT 풀의 현재 가격:** BNB당 600 USDT
* **사용자의 목표 / 지정가:** BNB당 700 USDT

진행 과정:

1. 사용자가 700 USDT에 BNB를 매도하는 지정가 주문을 설정합니다.
2. 사용자의 BNB는 풀에서 BNB당 700 USDT 가격에 가장 가까운 틱에 예치됩니다.
3. 외부 시장 가격이 700 USDT에 도달하면 (차익거래 기회 / 더 나은 가격 때문에) 풀 가격이 이에 맞게 조정됩니다.
4. 그 시점에 사용자의 BNB가 USDT로 스왑됩니다.
5. 이 과정에서 사용자는 자신의 유동성을 소비하는 각 스왑에서 수수료를 얻습니다.
6. 유동성이 전량 소비되면 전환된 USDT(및 수수료)가 자동으로 인출되어 사용자의 지갑으로 전송됩니다.

***

### 단계별 가이드

매도 / 매수하려는 토큰 페어(예: BNB/CAKE)와 수량을 선택합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

목표 가격 / 지정가를 설정합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

지정가 주문을 넣고 "Confirm"을 누릅니다. 유동성은 지정가와 가장 가까운 틱에 사용자를 대신하여 배치됩니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

풀 가격이 목표에 도달하면 주문이 실행됩니다. 원하는 출력 토큰과 수수료가 자동으로 인출되어 지갑으로 전송됩니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### 주문 상태

여기를 클릭하여 주문 상태를 확인할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**주문은 다음 상태 중 하나일 수 있습니다.**

| 상태               | 설명                                                                  |
| ---------------- | ------------------------------------------------------------------- |
| Pending(대기 중)     | 가격이 목표에 도달하기를 기다리는 중                                                |
| Filled(체결 완료)    | 주문이 실행되고 자금이 지갑으로 전송됨                                               |
| Partially Filled(부분 체결) | 주문의 일부만 실행됨. 두 토큰을 모두 보유하게 됩니다(예: 일부는 BNB, 일부는 USDT) |
| Cancelled(취소됨)   | 사용자가 주문을 취소함. 모든 자금이 사용자에게 반환됨                                      |

### 자주 묻는 질문 (FAQ)

**Q: 지정가 주문을 넣을 때 수수료를 내야 하나요?**

A: 아니요. 오히려 주문이 실행되면 거래 수수료로 0.1%를 받습니다.

**Q: 모든 페어에 대해 주문할 수 있나요?**

A: 출시 시점에는 선별된 페어만 지원됩니다. 더 많은 페어가 추후 추가될 예정입니다.

**Q: 최소 주문 규모는 얼마인가요?**

A: $50입니다. 이는 과도한 가스비를 유발할 수 있는 소액 주문을 방지하기 위한 것입니다.&#x20;

**Q: 주문의 일부만 체결되면 어떻게 되나요?**

A: 두 토큰을 모두 보유하게 됩니다. 언제든지 주문을 취소하고 두 토큰과 발생한 수수료를 인출할 수 있습니다.

**Q: 주문이 체결되었는데 아직 지갑에 자금이 들어오지 않았어요.**

A: 매우 드물게 이런 일이 발생할 수 있지만 자금은 항상 안전합니다. 주문 세부 정보 UI의 "Withdraw" 버튼을 사용하여 직접 자금을 수령하세요.
