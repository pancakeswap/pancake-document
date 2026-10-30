---
description: EVM 체인과 Aptos 간에 CAKE 브릿지
---

# 브릿지 방법 - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(113).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
다음 가이드는 EVM 체인의 예시로 BNB Chain을 사용합니다. Aptos **로** 브릿지할 때는 Ethereum에도 동일한 과정을 적용할 수 있습니다. Aptos **에서** 브릿지할 때는 현재 BNB Smart Chain만 도착 체인으로 지원됩니다.
{% endhint %}

## BNB Smart Chain에서 Aptos로 CAKE 브릿지하기

1 - 지갑이 BNB Smart Chain과 Aptos 메인넷을 모두 지원하는지 확인하세요. 또는 두 지갑이 모두 브라우저에 설치되어 있어야 합니다.

그런 다음 [PancakeSwap CAKE 브릿지](https://bridge.pancakeswap.finance/)를 엽니다.

2 - 먼저 BNB Smart Chain 지갑을 연결합니다.

"Connect"를 클릭하고 "EVM" 섹션에서 원하는 지갑을 선택합니다. 그런 다음 지갑 팝업에서 확인하고 승인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - 다음으로 Aptos 지갑을 연결합니다.

지갑 연결 창의 "Aptos" 섹션에서 원하는 지갑을 선택합니다. 그런 다음 지갑 팝업에서 확인하고 승인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - 위쪽 토큰 선택 필드의 "v"를 클릭하고 "CAKE"를 선택합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Aptos로 브릿지할 CAKE 수량을 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Aptos 지갑을 새로 만들어 APT(Aptos Coin) 잔액이 없다면 "gas on destination" 옵션을 기본값으로 두는 것을 권장합니다. 브릿지가 소량의 APT를 지갑에 입금해 주며, 이는 Aptos에서의 시작을 돕는 것뿐만 아니라 브릿지된 CAKE를 등록(register)하고 수령(claim)하는 데 가스로 APT가 필요하기 때문이기도 합니다.

이 옵션을 변경하면 브릿징이 실패할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - "Transfer"를 클릭해 브릿징 트랜잭션을 시작하고 지갑 확인 팝업에서 확인합니다.

BNB Smart Chain 지갑과 Aptos 지갑의 상태에 따라 지갑 확인을 **여러 번** 승인해야 할 수 있습니다. 예를 들어 CAKE를 Aptos로 처음 브릿지하는 경우 다음을 수행해야 합니다.

* 브릿지 컨트랙트에 대한 CAKE 사용 승인 (BNB Smart Chain 지갑에서 진행)
* CAKE 등록 (Aptos 지갑에서 진행)

자세한 내용은 [이 설명](aptos.md#bridging-cake-to-aptos-for-the-first-time)을 확인하세요.

8 - 편안하게 기다리세요. 몇 분이면 충분합니다. 브릿징이 완료되면 CAKE가 Aptos 지갑에 입금됩니다. 진행 표시줄로 진행 상황을 추적할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## CAKE를 Aptos로 처음 브릿지하기

CAKE를 Aptos 지갑으로 브릿지하려면 등록 및 수령 트랜잭션이 필요합니다. 이는 사용자 보안을 강화하기 위한 것이며 Aptos에만 있는 방식입니다.

### **지갑에 이미 APT(Aptos Coin)가 있는 경우:**

Aptos 지갑에 CAKE가 아직 등록되지 않았다면 CAKE 등록을 요청받습니다. 이 경우 별도의 수령 트랜잭션은 필요하지 않습니다.

### **지갑에 APT(Aptos Coin)가 없는 경우:**

브릿지 트랜잭션이 완료된 후 CAKE를 직접 수령해야 합니다. 수령에 필요한 가스비를 충당하기 위해 출발 지갑에서 Aptos 지갑으로 APT 토큰이 전송됩니다.

이러한 등록 및 수령 단계는 Aptos에서 해당 토큰을 처음 이용할 때에만 적용됩니다. 이후 동일한 토큰을 전송할 때는 이 과정이 필요하지 않습니다.

CAKE를 Aptos로 처음 브릿지하기 전에 Aptos 주소에 가스비를 충당할 충분한 APT가 있는지 확인하세요. 자세한 내용은 Aptos의 설명을 참고하세요: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Aptos에서 BNB Smart Chain으로 CAKE 브릿지하기

1 - 지갑이 BNB Smart Chain과 Aptos 메인넷을 모두 지원하는지 확인하세요. 또는 두 지갑이 모두 브라우저에 설치되어 있어야 합니다.

그런 다음 [PancakeSwap CAKE 브릿지](https://bridge.pancakeswap.finance/)를 엽니다.

2 - 먼저 BNB Smart Chain 지갑을 연결합니다.

"Connect"를 클릭하고 "EVM" 섹션에서 원하는 지갑을 선택합니다. 그런 다음 지갑 팝업에서 확인하고 승인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - 다음으로 Aptos 지갑을 연결합니다.

지갑 연결 창의 "Aptos" 섹션에서 원하는 지갑을 선택합니다. 그런 다음 지갑 팝업에서 확인하고 승인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - 위쪽 토큰 선택 필드의 "v"를 클릭하고 "CAKE"를 선택합니다. 그런 다음 페이지 중앙의 양방향 화살표 버튼을 클릭해 브릿징 방향을 바꿉니다.

위쪽 필드에 "Aptos" 네트워크가 있는지 확인하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - BNB Smart Chain으로 브릿지할 CAKE 수량을 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - BNB Smart Chain 지갑을 새로 만들어 BNB(가스 토큰) 잔액이 없다면 "gas on destination" 옵션을 기본값으로 두는 것을 권장합니다. 브릿지가 소량의 BNB를 지갑에 입금해 줍니다. 이는 BNB Smart Chain에서의 시작을 돕고 다채로운 PancakeSwap 생태계를 탐험하는 데 도움이 됩니다.

7 - "Transfer"를 클릭하고 지갑 팝업에서 트랜잭션을 승인합니다.

8 - 편안하게 기다리세요. 몇 분이면 충분합니다. 브릿징이 완료되면 CAKE가 BNB Smart Chain 지갑에 입금됩니다. 진행 표시줄로 진행 상황을 추적할 수 있습니다.
