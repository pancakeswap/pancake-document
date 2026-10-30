# 무기한 선물 V1 용어집

**선물 거래와 관련된 모든 용어의 정의를 확인할 수 있습니다**

### **무기한 선물 거래**

&#x20;무기한 선물(Perpetuals), 무기한 스왑(perpetual swaps), 또는 퍼프(perps)는 만기일이 없는 특별한 유형의 선물 계약입니다.



### **레버리지**

레버리지는 거래 메커니즘입니다. 트레이더는 투자 금액 전체를 내지 않고도 시장에 대한 노출을 늘릴 수 있습니다. 쉽게 말해, 돈을 빌려 투자 규모를 키우는 것입니다.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **마진**

레버리지 포지션을 위해 걸어 두는 보증금입니다. 사용 모드는 두 가지입니다.

* 교차 마진 모드(Cross Margin Mode): 동일한 마진 자산을 사용하는 모든 교차 포지션이 해당 자산의 교차 마진 잔액을 공유합니다. 청산이 발생하면 해당 자산의 전체 마진 잔액과 그 자산으로 보유한 나머지 미결제 포지션이 모두 소실될 수 있습니다.
* 격리 마진 모드(Isolated Margin Mode): 각 포지션에 배정된 마진 금액을 제한하여 개별 포지션의 위험을 관리합니다. 포지션의 마진 비율이 100%에 도달하면 해당 포지션이 청산됩니다. 이 모드에서는 포지션에 마진을 추가하거나 제거할 수 있습니다.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**마진 비율(Margin Ratio)**: 마진 비율 = 유지 마진 / 마진 잔액. 마진 비율이 100%에 도달하면 포지션이 청산됩니다.

**유지 비율(Maintenance Ratio)**: 미결제 포지션을 유지하는 데 필요한 최소 마진 잔액입니다.

**마진 잔액(Margin Balance)** = 지갑 잔액 + 미실현 손익. 마진 잔액이 유지 마진 이하가 되면 포지션이 청산됩니다.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### 자산:

**입금(Deposit)**: 선물 계정에 자금을 입금합니다.

**출금(Withdraw)**: 선물 계정의 자금을 지갑으로 출금합니다.

**잔액(Balance)**: 지갑 잔액 = 총 순이체 + 총 실현 수익 + 총 순 펀딩 수수료 - 총 수수료.

**미실현 손익(Unrealized PNL)**: 마크 가격을 기준으로 계산한 해당 포지션의 미실현 손익과 자기자본 수익률(%)입니다.

**모드:**&#x20;

* 단일 자산 모드(Single Asset Mode): 해당 심볼의 단일 마진 자산만 사용하여 USDⓈ-M 선물 거래를 지원합니다. 동일한 마진 자산 포지션끼리 손익을 상계할 수 있습니다. 교차 마진 모드와 격리 마진 모드를 모두 지원합니다.
* 다중 자산 모드(Multi-Assets Mode): 여러 마진 자산에 걸쳐 USDⓈ-M 선물 거래를 할 수 있습니다. 서로 다른 마진 자산 포지션 간에 손익을 상계할 수 있습니다. 교차 마진 모드만 지원합니다.

{% hint style="info" %}
참고: USDⓈ-M 선물에 미결제 포지션이나 미체결 주문이 있으면 다중 자산 모드를 활성화할 수 없습니다. 다중 자산 모드는 USDⓈ-M 선물에만 적용됩니다. 다중 자산 모드를 활성화하기 전에 가이드를 자세히 읽고, 해당 모드를 사용할 때 USDⓈ-M 선물 계정의 위험을 적절히 관리하시기 바랍니다.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### 주문

**매수/롱(Buy/Long):** 롱 주문을 개시합니다. 이 주문에서는 자산을 매수한 뒤 가격이 오르면 매도하기를 기다립니다. "매수"와 "롱"은 같은 의미로 사용됩니다.

**매도/숏(Sell/Short):** 숏 주문을 개시합니다. 이 주문에서는 자산을 빌려서 매도한 뒤, 가격이 내려가면 다시 매수하기를 기대합니다. "매도"와 "숏"은 같은 의미로 사용됩니다.

**지정가 주문(Limit Order):** 지정가 주문은 특정 가격 또는 그보다 유리한 가격으로 매수 또는 매도하는 주문입니다. 지정가 주문은 체결이 보장되지 않습니다.

**시장가 주문(Market Order):** 시장가 주문은 현재 가장 유리한 가격으로 매수 또는 매도하는 주문입니다. 오더북에 먼저 등록되어 있던 지정가 주문과 체결됩니다. 시장가 주문을 넣으면 마켓 테이커로서 수수료를 지불하게 됩니다.

**스톱 리밋 주문(Stop Limit Order):** 스톱 리밋 주문은 스톱 가격과 지정가로 나누어 보면 이해하기 쉽습니다. 스톱 가격은 지정가 주문을 발동시키는 가격이고, 지정가는 발동된 지정가 주문의 가격입니다. 즉, 스톱 가격에 도달하면 지정가 주문이 즉시 오더북에 등록됩니다.

**스톱 마켓 주문(Stop Market Order):** 스톱 리밋 주문과 비슷하게 스톱 마켓 주문도 스톱 가격을 발동 조건으로 사용합니다. 다만 스톱 가격에 도달하면 지정가 주문 대신 시장가 주문이 발동됩니다.

**트레일링 스톱(Trailing Stop):** 트레일링 스톱은 거래가 유리하게 진행될 때 수익을 확정하거나 손실을 제한하도록 설계된 주문 유형입니다. 트레일링 스톱은 가격이 유리한 방향으로 움직일 때만 이동합니다. 수익을 확정하거나 손실을 줄이는 방향으로 한 번 이동하면 반대 방향으로는 되돌아가지 않습니다.

**포스트 온리(Post Only):** 포스트 온리 모드에서는 오더북에 메이커 주문으로 등록되는 경우에만 주문할 수 있습니다. 테이커 주문으로 등록될 주문은 거부됩니다. 시장가 주문은 넣을 수 없고 체결되는 주문도 없습니다. 포스트 온리 모드에서도 대기 중인 주문은 취소할 수 있습니다.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**감소 전용(Reduce Only):** 감소 전용 주문은 포지션을 줄이기만 하며 늘리지는 않습니다.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF 지시**를 사용하면 주문이 체결되거나 만료되기 전까지 유효하게 유지되는 시간을 지정할 수 있습니다. TIF 지시에는 다음 옵션 중 하나를 선택할 수 있습니다.

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel): 주문이 체결되거나 취소될 때까지 유효하게 유지됩니다.&#x20;
* **IOC** (Immediate Or Cancel): 주문이 즉시 (전량 또는 일부) 체결됩니다. 일부만 체결된 경우 나머지 미체결 수량은 취소됩니다.&#x20;
* **FOK** (Fill Or Kill): 주문이 즉시 전량 체결되어야 합니다. 그렇지 않으면 전혀 체결되지 않습니다.
