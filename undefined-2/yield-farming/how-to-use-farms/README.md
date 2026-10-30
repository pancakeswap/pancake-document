---
description: 찾기, LP 공급, 파밍
---

# 파밍 사용 방법 (EVM)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-header.png)

파밍을 통한 일드 파밍은 PancakeSwap에서 CAKE 보상을 얻는 훌륭한 방법입니다.

파밍에서는 **두 가지 토큰**을 스테이킹하여 유동성을 공급하고, 유동성 포지션 NFT 또는 LP 토큰을 받은 다음 이를 파밍에 스테이킹하여 보상을 얻습니다. 이를 통해 다른 토큰의 포지션을 유지하면서도 CAKE를 획득할 수 있습니다!

{% hint style="warning" %}
일드 파밍은 시럽 풀이나 단일 토큰 스테이킹보다 더 높은 보상을 제공할 수 있지만, **비영구적 손실(Impermanent Loss)** 위험이 따릅니다. 이름처럼 그렇게 무서운 것은 아니지만, 시작하기 전에 개념을 알아 두는 것이 좋습니다.

자세한 내용은 Binance Academy의 [비영구적 손실에 대한 훌륭한 글](https://academy.binance.com/en/articles/impermanent-loss-explained)을 확인하세요.
{% endhint %}

## 유동성을 공급할 페어 찾기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(360).png" alt=""><figcaption></figcaption></figure>

이제 유니버설 파밍 페이지에서 지갑의 네트워크를 전환하지 않고도 PancakeSwap이 지원하는 모든 네트워크에 걸쳐 토큰별로 유동성 페어를 찾고, 수수료, 거래량, APR을 확인할 수 있습니다.

시작하려면 다음 주소로 이동하세요: [https://pancakeswap.finance/liquidity/pools](https://pancakeswap.finance/liquidity/pools)

#### 기능 상세 설명

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(361).png" alt=""><figcaption></figcaption></figure>

1. 인기 있거나 PancakeSwap 파밍이 연결된 모든 유동성 풀/페어입니다.
2. 내가 보유한 모든 유동성 포지션입니다.
3. 모든 레거시 파밍입니다. 이전에 스테이킹한 파밍이 "전체 풀"에서 보이지 않으면 여기에서 검색해 보세요.
4. 기본적으로 이 페이지는 지원되는 모든 체인의 파밍과 토큰을 보여줍니다. 이 드롭다운을 사용하여 네트워크/체인별로 풀을 필터링하세요.
5. 이 드롭다운을 사용하여 토큰별로 풀을 필터링하세요.
6. 이 탭을 사용하여 DEX 유형별로 풀을 필터링하세요.
7. APR, TVL 또는 24시간 거래량의 화살표 버튼을 클릭하면 선택한 지표 기준으로 풀을 정렬할 수 있습니다.
8. 파밍 수익 부스터인 bCAKE 섹션입니다. [자세히 알아보기](../../../pancakeswap/vecake-sunset/bcake/)
9. 새 버전에서 문제가 발생하면 이 링크를 사용하여 레거시 파밍 페이지로 돌아갈 수 있습니다.

## LP 공급

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(362).png" alt=""><figcaption></figcaption></figure>

유동성을 공급할 페어를 찾았다면, 클릭하여 상세 페이지로 이동해 다음과 같은 정보를 확인하세요.

* TVL
* 거래량
* 수수료
* APR
* 내 기존 포지션

LP를 생성하려면 "Add Liquidity +"를 클릭하고 다음 가이드의 안내를 따르세요.

{% content-ref url="../../pancakeswap-pools/liquidity-guide.md" %}
[liquidity-guide.md](../../pancakeswap-pools/liquidity-guide.md)
{% endcontent-ref %}

## 포지션을 스테이킹하여 보상 받기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(363).png" alt=""><figcaption></figcaption></figure>

유동성을 추가하면 오른쪽 상단의 표 또는 "My Position" 탭에 표시됩니다.

* v3의 경우 "Stake"를 클릭하여 포지션을 스테이킹하고 CAKE 획득을 시작하세요. v3에서는 여러 개의 포지션을 만들 수 있으므로, 위 단계를 반복하여 서로 다른 가격 범위의 여러 포지션을 스테이킹할 수 있습니다.
* v2와 StableSwap의 경우 "Stake"를 클릭한 후 스테이킹할 LP 토큰의 수량을 지정해야 합니다. 대부분의 경우 수익을 극대화하려면 LP 토큰의 100%를 스테이킹하는 것이 좋습니다.

## 파밍 보상 수확하기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(364).png" alt=""><figcaption></figcaption></figure>

새로운 유니버설 파밍 페이지에서는 모든 파밍 포지션을 그 어느 때보다 쉽게 찾을 수 있습니다. "My Positions"로 이동하여 오른쪽 상단의 "Farms only"를 클릭하세요. 어떤 네트워크를 선택했는지와 관계없이 모든 파밍 포지션이 필터링됩니다.

풀/페어 목록과 마찬가지로, 도구 모음을 사용하여 네트워크/체인, 토큰, DEX 유형별로 포지션을 필터링할 수 있습니다.

스테이킹한 포지션에서 CAKE 보상을 수확하려면 "Harvest"를 클릭하고 지갑 팝업에서 확인하세요.

스테이킹한 포지션이 여러 개인 경우 각각 별도로 수확해야 합니다.

## **파밍에 스테이킹한 상태에서 유동성 추가 또는 제거**

v3에서는 파밍에 스테이킹한 상태에서도 언스테이킹하지 않고 유동성을 추가하거나 제거할 수 있습니다.

이렇게 하려면 "My Positions" 페이지로 돌아가 조정하려는 포지션을 선택하세요.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(365).png" alt="" width="280"><figcaption></figcaption></figure>

토큰 페어와 포지션 ID가 표시된 포지션 제목을 클릭하여 포지션 상세 페이지를 여세요.

"Add" 또는 "Remove" 버튼을 사용하여 스테이킹한 포지션의 유동성을 조정하면 됩니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(366).png" alt=""><figcaption></figcaption></figure>

포지션을 조정하는 동안 아직 수령하지 않은 모든 CAKE 보상이 수확되어 지갑으로 전송된다는 점에 유의하세요.

## **언스테이킹**

포지션은 언제든지 언스테이킹할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(367).png" alt=""><figcaption></figcaption></figure>

언스테이킹하려면 "My Positions"로 돌아가 포지션을 찾은 다음 다음을 클릭하세요.

* "Unstake" (v3 포지션의 경우)
* "-" (v2, StableSwap LP의 경우)를 클릭한 후 언스테이킹할 수량 선택

그런 다음 지갑 팝업에서 확인하세요. 잠시 기다리면 포지션 NFT 또는 LP 토큰이 대기 중인 모든 CAKE 보상과 함께 지갑으로 반환됩니다.

## 보상은 얼마나 자주 수확해야 하나요?

보상을 얼마나 자주 수확할지는 본인의 선택이지만, 수확 시 소액의 수수료가 발생한다는 점을 기억해 두면 도움이 됩니다.

**Harvest**를 클릭한 후 확인 단계에서 지갑에 이 수수료가 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(281\).png)

이 이미지는 MetaMask 지갑에 표시되는 수확 수수료를 보여줍니다. 지갑마다 정보가 약간 다르게 표시될 수 있습니다. 보상을 한동안 쌓아 두었다가 수확하면 수수료를 덜 자주 지불할 수 있습니다.

**즐거운 파밍 되세요!**
