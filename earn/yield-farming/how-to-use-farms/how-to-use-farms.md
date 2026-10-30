---
description: PancakeSwap에서의 일드 파밍은 쉽습니다!
---

# 파밍 이용 방법 (레거시)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-header.png)

파밍을 통한 일드 파밍은 PancakeSwap에서 CAKE 보상을 얻는 훌륭한 방법입니다.

시럽 풀과 달리 파밍에서는 **두 가지 토큰**을 스테이킹하여 유동성을 공급하고, 유동성 포지션 NFT 또는 LP 토큰을 받은 다음 이를 파밍에 스테이킹하여 보상을 얻습니다. 이를 통해 다른 토큰의 포지션을 유지하면서도 CAKE를 획득할 수 있습니다!

{% hint style="warning" %}
일드 파밍은 시럽 풀보다 더 높은 보상을 제공할 수 있지만, **비영구적 손실(Impermanent Loss)** 위험이 따릅니다. 이름처럼 그렇게 무서운 것은 아니지만, 시작하기 전에 개념을 알아 두는 것이 좋습니다.

자세한 내용은 Binance Academy의 [비영구적 손실에 대한 훌륭한 글](https://academy.binance.com/en/articles/impermanent-loss-explained)을 확인하세요.
{% endhint %}

## 파밍 v3

### **준비하기**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2832%29.png)

파밍에 참여하려면 유동성 포지션이 필요합니다. 파밍은 해당 파밍과 정확히 일치하는 거래 페어 및 수수료 등급의 유동성 포지션만 받을 수 있습니다. 예를 들어 CAKE-BNB 0.25% 파밍은 수수료 등급 0.25%가 선택된 CAKE-BNB 유동성 포지션만 받습니다. 다음은 받지 않습니다.

* CAKE-BUSD와 같은 다른 페어
* 같은 페어이지만 수수료 등급이 다른 경우: 예를 들어 0.05% 수수료율의 CAKE-BNB

정확한 LP 포지션을 만들려면 올바른 수수료율을 선택하여 해당 거래 페어에 유동성을 공급해야 합니다. 따라서 CAKE-BNB 0.25% LP 포지션을 얻으려면 먼저 0.25% 수수료 등급을 선택하여 CAKE-BNB 페어에 유동성을 공급해야 합니다.

어렵게 들릴 수 있지만 그리 복잡하지 않습니다. 단계별로 따라 해 보겠습니다.

### **파밍 찾기**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28239%29.png)

진행하기 전에 나에게 맞는 파밍을 선택하세요. [파밍 페이지를 방문](https://pancakeswap.finance/farms)하여 이용 가능한 파밍 목록을 확인하세요.

APR 기준 등 다른 정렬 옵션을 선택하면 현재 보상률이 가장 높은 파밍을 볼 수 있습니다. APR은 개별 포지션에 대해 전체 기준으로 계산되므로, 가격 범위 설정에 따라 달라질 수 있습니다.

사용하고 싶은 파밍을 찾았다면, 나중에 필요할 경우를 대비해 거래 페어와 수수료율(예: BNB-CAKE, 0.25%)을 메모해 두세요.

### **유동성을 공급하여 포지션 생성하기**

이제 스테이킹할 파밍을 찾았으니 유동성을 공급해야 합니다.

1 - 사용 가능한 포지션이 없다면 "Add Liquidity" 버튼이 표시됩니다. 이 버튼을 클릭하면 파밍 페이지를 벗어나지 않고 "Add Liquidity" 창이 열립니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2840%29.png)

2 - 또는 목록에서 선택한 파밍의 행을 클릭하면 더 자세한 정보가 펼쳐집니다. 카드 보기에서는 "Details"를 클릭하여 자세한 정보를 펼치세요. 상세 섹션에서 "Add XXX-YYY LP" 링크를 클릭하여 유동성을 추가하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28242%29.png)

### **포지션을 파밍에 스테이킹하기**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28124%29.png)

유동성 추가를 마치면 사용하려는 파밍 아래에 내 포지션이 표시됩니다.

포지션이 여러 개인 경우 "View All"을 클릭하여 새 팝업 창에서 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28198%29.png) ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28151%29.png)

목록에 표시된 포지션에서 "Stake"를 클릭하면 지갑이 확인을 요청합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28229%29.png)

잠시 기다리면 창이 닫히고 상세 정보에서 스테이킹된 포지션을 확인할 수 있습니다.

위 단계를 반복하여 서로 다른 가격 범위 설정의 여러 포지션을 빠르게 스테이킹할 수 있습니다. 각 포지션은 CAKE를 획득하며 별도로 수확해야 합니다.

### **파밍 보상 수확하기**

파밍 v3에서는 같은 파밍에 여러 포지션을 스테이킹할 수 있습니다. 스테이킹된 각 포지션은 CAKE를 획득하며 별도로 수확해야 합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

스테이킹한 포지션에서 CAKE 보상을 수확하려면 파밍 페이지로 돌아가 수확하려는 파밍과 포지션을 찾으세요. "Staked Only" 토글을 사용하면 현재 스테이킹 중인 파밍만 빠르게 필터링할 수 있습니다.

스테이킹한 포지션이 여러 개인 경우 "View All"을 클릭하여 새 팝업 창에서 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28241%29.png)

포지션에서 "Harvest"를 클릭하면 지갑이 확인을 요청합니다. 잠시 기다리면 CAKE 보상이 지갑으로 전송됩니다.

### **파밍에 스테이킹한 상태에서 유동성 추가 또는 제거**

파밍에 스테이킹한 상태에서도 파밍에서 언스테이킹하지 않고 유동성을 추가하거나 제거할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

이렇게 하려면 파밍 페이지로 돌아가 조정하려는 파밍과 포지션을 찾으세요. "Staked Only" 토글을 사용하면 현재 스테이킹 중인 파밍만 빠르게 필터링할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28267%29.png)

토큰 페어, 수수료율, 포지션 ID와 "&gt;" 화살표가 표시된 포지션 제목을 클릭하면 포지션 상세 페이지로 이동합니다.

"Add" 또는 "Remove" 버튼을 사용하여 스테이킹한 포지션의 유동성을 조정하면 됩니다.

포지션을 조정하는 동안 아직 수령하지 않은 모든 CAKE 보상이 수확되어 지갑으로 전송된다는 점에 유의하세요.

### **파밍에서 포지션 언스테이킹하기**

포지션은 언제든지 언스테이킹할 수 있습니다.

언스테이킹하려면 파밍 페이지로 돌아가 언스테이킹하려는 파밍과 포지션을 찾으세요. "Staked Only" 토글을 사용하면 현재 스테이킹 중인 파밍만 빠르게 필터링할 수 있습니다.

스테이킹한 포지션이 여러 개인 경우 "View All"을 클릭하여 새 팝업 창에서 확인할 수 있습니다.

포지션에서 "Unstake"를 클릭하면 지갑이 확인을 요청합니다. 잠시 기다리면 포지션 NFT가 대기 중인 모든 CAKE 보상과 함께 지갑으로 반환됩니다.

## 파밍 v2

### 준비하기

일드 파밍을 시작하려면 약간의 설정이 필요합니다.

파밍에 참여하려면 "LP 토큰"이 필요합니다. 파밍은 해당 파밍과 정확히 일치하는 LP 토큰만 받을 수 있습니다. 예를 들어 CAKE-BNB 파밍은 CAKE-BNB LP 토큰만 받습니다.

정확한 LP 토큰을 얻으려면 해당 거래 페어에 유동성을 공급해야 합니다. 따라서 CAKE-BNB LP 토큰을 얻으려면 먼저 CAKE-BNB 페어에 유동성을 공급해야 합니다.

어렵게 들릴 수 있지만 그리 복잡하지 않습니다. 단계별로 따라 해 보겠습니다.

### 파밍 찾기

진행하기 전에 나에게 맞는 파밍을 선택하세요. [파밍 페이지를 방문](https://pancakeswap.finance/farms)하면 이용 가능한 파밍 목록이 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2862%29.png)

원한다면 현재 보상률이 가장 높은 파밍을 보기 위해 **APR** 기준 등 다른 정렬 옵션을 선택할 수 있습니다.

사용하고 싶은 파밍을 찾았다면, 나중에 필요할 경우를 대비해 거래 페어(예: BNB-CAKE)를 메모해 두세요.

### 유동성을 공급하여 LP 토큰 받기

이제 스테이킹할 파밍을 찾았으니, 유동성을 추가하여 LP 토큰을 받아야 합니다.

1. 목록에서 선택한 파밍의 행을 클릭하면 더 자세한 정보가 펼쳐집니다.
2. 왼쪽에 몇 가지 링크가 표시됩니다. **Get (your pair) LP** 링크를 클릭하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28131%29.png)

### LP 토큰을 파밍에 넣기

이제 LP 토큰이 생겼으니 파밍에 스테이킹하고 보상을 획득할 준비가 되었습니다!

1 - [파밍 페이지](https://pancakeswap.finance/farms)로 돌아가 내 파밍을 찾으세요. 페어가 표시된 행의 아무 곳이나 클릭하면 더 자세한 정보가 펼쳐집니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28244%29.png)

준비가 되면 **Enable** 버튼을 클릭하고 지갑에서 작업을 확인하세요.

2 - 잠시 기다리면 Enable 버튼이 **Stake LP**로 바뀝니다. 클릭하면 새 창이 나타납니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28171%29.png)

3 - 파밍에 사용할 LP 토큰의 수량을 입력란에 입력하거나, **Max**를 클릭하여 보유한 모든 LP 토큰을 사용하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28109%29.png)

4 - 수량을 입력하면 **Confirm** 버튼이 활성화됩니다. 클릭하세요. 지갑이 작업 확인을 요청합니다.

5 - 잠시 기다리면 창이 닫히고 상세 정보에서 새로 스테이킹된 LP 토큰 잔액을 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28261%29.png)

{% hint style="info" %}
BNB 체인이 아닌 다른 EVM 블록체인에서 크로스체인 파밍을 진행하는 경우, 크로스체인 트랜잭션이 확인될 때까지 약 30분 정도 기다려야 합니다.

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/crosschain-farm-wait.png" alt="" data-size="original">

크로스체인 파밍 트랜잭션의 진행 상황을 확인하려면 스테이킹된 잔액 옆의 원형 아이콘을 클릭하거나, 오른쪽 상단의 "Recent Transaction" 섹션을 확인하세요.
{% endhint %}

{% hint style="warning" %}
BNB 체인이 아닌 다른 EVM 블록체인에서 처음으로 크로스체인 파밍을 진행하는 경우, 최초 설정을 위해 소량의 네이티브 토큰(예: Ethereum의 경우 ETH)이 필요합니다. 따라서 첫 번째 트랜잭션은 비용이 약간 더 듭니다.
{% endhint %}

### 파밍에서 LP 토큰 추가 또는 제거하기

나중에 파밍에 LP 토큰을 더 추가하거나 일부를 꺼내고 싶을 수 있습니다. 언제든지 매우 쉽게 할 수 있습니다.

1. [일드 파밍 페이지](https://pancakeswap.finance/farms)로 돌아갑니다. 페이지 상단에 **Staked only** 토글이 있습니다. 토글을 클릭하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28240%29.png)

이제 LP 토큰을 보유한 페어만 목록에 표시되어 내 파밍을 더 쉽게 찾을 수 있습니다.

1. LP 토큰을 보유한 파밍을 찾아 행을 클릭하여 상세 정보를 확인하세요. 오른쪽에 **-** 및 **+** 버튼이 표시됩니다. LP 토큰을 제거하려면 **-**를, 더 추가하려면 **+**를 클릭하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28102%29.png)

1. 처음 LP 토큰을 스테이킹할 때 사용했던 것과 비슷한 창이 열립니다. 이전과 마찬가지로 언스테이킹/스테이킹할 수량을 입력하거나, **Max**를 클릭하여 사용 가능한 모든 LP 토큰을 제거/추가하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2879%29.png)

1. 정보가 올바른지 확인하세요. 준비가 되면 **Confirm** 버튼을 클릭하고 지갑에서 작업을 확인하세요.
2. 잠시 기다리면 LP 토큰 페어의 상세 정보 섹션에 새 잔액이 표시됩니다. LP 토큰을 언스테이킹한 경우, 수확하지 않은 보상은 자동으로 수령됩니다.

### 파밍 보상 수령하기

파밍을 하면 시간이 지남에 따라 CAKE 보상을 받게 됩니다. 이 보상을 수령하여 더 많은 LP 토큰을 얻거나, 시럽 풀에 스테이킹하거나, 복권에 참여하는 등 원하는 대로 사용할 수 있습니다.

### 파밍으로 돌아가 수확하기

홈 페이지에서 파밍과 시럽 풀 보상을 함께 수확할 수 있습니다. 파밍 보상만 수령하려면 아래 안내를 따르세요.

보상을 수령하려면 선택한 파밍을 방문하여 대기 중인 CAKE를 수령해야 합니다.

1 - [여기](https://pancakeswap.finance/farms)에서 파밍 페이지로 돌아갑니다.

2 - LP 토큰을 스테이킹한 파밍을 찾아 행을 클릭하여 상세 정보를 확인하세요. "CAKE earned" 아래에 예상 보상이 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28181%29.png)

3 - **Harvest** 버튼을 클릭하고 지갑에서 작업을 확인하세요. 잠시 기다리면 CAKE가 지갑으로 수령되어 원하는 대로 사용할 수 있습니다.

{% hint style="info" %}
BNB 체인이 아닌 다른 EVM 블록체인에서 크로스체인 파밍을 진행하는 경우, 파밍 보상을 수확하려면 항상 BNB Smart Chain으로 전환해야 합니다.

지갑이 체인 전환을 지원하지 않는 경우, LP 토큰을 스테이킹하거나 언스테이킹할 때마다 CAKE가 수확됩니다. 수확된 CAKE는 BNB Smart Chain으로 분배된다는 점에 유의하세요.

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28164%29.png" alt="" data-size="original">
{% endhint %}

## 보상은 얼마나 자주 수확해야 하나요?

보상을 얼마나 자주 수확할지는 본인의 선택이지만, 수확 시 소액의 수수료가 발생한다는 점을 기억해 두면 도움이 됩니다.

**Harvest**를 클릭한 후 확인 단계에서 지갑에 이 수수료가 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28281%29.png)

이 이미지는 MetaMask 지갑에 표시되는 수확 수수료를 보여줍니다. 지갑마다 정보가 약간 다르게 표시될 수 있습니다. 보상을 한동안 쌓아 두었다가 수확하면 수수료를 덜 자주 지불할 수 있습니다.

이게 전부입니다! [PancakeSwap 시럽 풀 이용 방법](https://docs.pancakeswap.finance/earn/cake-staking/syrup-pool/syrup-pool-guide)을 살펴보고 보상을 얻어 보는 것도 좋습니다.

즐거운 파밍 되세요!
