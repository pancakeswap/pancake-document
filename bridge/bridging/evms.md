---
description: Ethereum, BNB Chain 등 EVM 간 브릿지
---

# 브릿지 방법 – EVM 간

{% hint style="success" %}
**EVM:** EVM 체인은 이더리움 가상 머신(Ethereum Virtual Machine)을 사용해 Ethereum 호환 스마트 컨트랙트와 dApp을 실행하는 블록체인입니다. 예로는 Ethereum, BNB Smart Chain 등이 있습니다.
{% endhint %}

1. [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)로 이동합니다.
2. 지갑이 연결되어 있는지 확인합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%283%29.png" alt=""><figcaption></figcaption></figure>

3. 네트워크 선택기에서 **출발** 체인과 **도착** 체인을 선택합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%283%29.png" alt="" width="375"><figcaption></figcaption></figure>

4. 보낼 수량을 입력하고 드롭다운에서 토큰을 선택합니다.

* **팁:** 전송하기 전에 항상 토큰 컨트랙트 주소를 다시 한 번 확인하세요!

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%283%29.png" alt="" width="374"><figcaption></figcaption></figure>

5. **받을 토큰**을 선택합니다. USDC / USDT처럼 토큰 심볼이 동일한 경우에는 여러 변형 토큰이 표시되어 선택할 수 있습니다.

* **팁:** 토큰 위에 마우스를 올리거나 링크를 클릭해 토큰 이름과 주소를 확인하세요.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%282%29.png" alt="" width="375"><figcaption><p>USDC</p></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29%20%282%29.png" alt="" width="375"><figcaption><p>USDC (Wormhole)</p></figcaption></figure>

6. "수령 예정 수량(You Receive)" 섹션을 검토하여 모든 내용이 올바른지 확인합니다.

* PancakeSwap은 출발 체인과 도착 체인에 따라 여러 브릿지 제공업체 중에서 선택합니다.
* 제공업체마다 수수료, 처리 시간, 제한 사항이 다르며 이 정보는 명확하게 표시됩니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28385%29.png" alt=""><figcaption></figcaption></figure>

* 태그를 통해 경로를 비교할 수 있습니다.
  * **Best Return** = 수령 수량이 가장 많은 경로
  * **Fastest** = 전송 시간이 가장 짧은 경로

이 태그를 활용해 필요에 맞게 속도와 가치의 균형을 맞추세요.

{% hint style="warning" %}
브릿지 제공업체와의 **첫 번째 트랜잭션**에서는 토큰 전송 승인을 요청받습니다(1회만 필요한 절차입니다).

* **두 번째 트랜잭션**부터는 "Send"를 클릭하기만 하면 브릿지 전송이 시작됩니다.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

7. 편안하게 기다리세요! 대부분의 브릿지 전송은 몇 분 안에 완료됩니다. 완료되면 토큰이 Ethereum 주소에 표시됩니다.
