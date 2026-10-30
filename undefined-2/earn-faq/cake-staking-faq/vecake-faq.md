---
hidden: true
---

# veCAKE 자주 묻는 질문 (FAQ)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(340).png" alt=""><figcaption></figcaption></figure>

#### 락업된 CAKE와 veCAKE의 차이점은 무엇인가요? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE는 고정 기간 CAKE 스테이킹의 새로운 버전으로, 락업된 CAKE 보유자에게 더 많은 혜택과 권한을 제공합니다. 게이지 가중치 투표, 추가 인센티브, 일드 부스팅 등이 포함됩니다.

#### 새로운 veCAKE가 배포되면 CAKE 풀 보상은 어떻게 되나요? <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

CAKE 풀 보상 배출량은 전체 공급량 대비 veCAKE 잔액에 따라 모든 veCAKE 보유자에게 보상하는 방향으로 전환됩니다.

CAKE 보상과 주간 수익 공유 보상은 이제 매주 목요일에 수령할 수 있습니다.

계속해서 보상을 받으려면 사용자가 새로운 veCAKE 스테이킹으로 마이그레이션해야 한다는 점에 유의하세요.

#### CAKE를 최대 얼마 동안 락업할 수 있나요? <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

CAKE를 락업할 수 있는 최대 기간이 이제 4년으로 연장되었습니다.

#### veCAKE는 새로운 토큰인가요? 전송할 수 있나요? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE는 락업된 CAKE의 수량과 남은 락 기간을 기반으로 실시간으로 생성되는 수치입니다. 일반적인 토큰이 아니며 전송할 수 없습니다.

#### veCAKE 잔액이 변경된 이유는 무엇인가요? 잔액은 어떻게 계산하나요? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

veCAKE 잔액은 남은 락 기간에 따라 0까지 선형적으로 감소합니다. 따라서 잠금 해제 시점에 가까워질수록 잔액이 줄어듭니다.

veCAKE 잔액은 다음과 같이 계산할 수 있습니다.

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### veCAKE를 늘리려면 어떻게 해야 하나요? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

활성 veCAKE 포지션이 있다면 CAKE를 더 추가하거나 락 기간을 갱신/연장하여 veCAKE 잔액을 늘릴 수 있습니다.

#### 포지션이 잠금 해제되면 어떻게 되나요? 바로 갱신할 수 있나요? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

veCAKE 스테이킹 포지션이 잠금 해제되면 스테이킹된 모든 CAKE를 출금할 수 있습니다.

포지션을 갱신하려면 모든 CAKE를 출금한 다음, 락업할 수량과 락 기간을 선택하여 새로운 스테이킹 포지션을 설정해야 합니다.

#### 1주일 동안 락업했는데 남은 락 시간이 1주일보다 짧은 이유는 무엇인가요? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

새로운 veCAKE로 락업하면 잠금 해제 시간은 UTC 기준으로 가장 가까운 목요일로 올림 처리됩니다. 예를 들어 화요일에 1주일 동안 락업하면 실제 잠금 해제 시간은 2일 후인 다가오는 목요일이 됩니다.

하단에서 실제 잠금 해제 시간을 미리 확인할 수 있습니다.

#### CAKE 풀에 CAKE를 더 락업할 수 있나요? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

아니요.

veCAKE가 배포되면 CAKE 스테이킹 풀은 폐지되며 더 이상 CAKE 연장이나 예치를 받지 않습니다.

CAKE를 락업하고 혜택을 누리려면 veCAKE 페이지로 이동하세요.

#### 마이그레이션할 수 없는 이유는 무엇인가요? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

CAKE 풀에서 veCAKE로 마이그레이션하려면 활성 포지션이 있어야 합니다. CAKE 풀 스테이킹 포지션이 이미 잠금 해제된 경우, 해당 CAKE를 출금하고 네이티브 veCAKE 스테이킹 포지션을 생성하면 됩니다.

경우에 따라 남은 CAKE 풀 락 시간이 7일 미만일 때는 마이그레이션을 수행할 수 없습니다. 이 경우 잠금 해제를 기다린 후 해당 CAKE를 출금하고 네이티브 veCAKE 스테이킹 포지션을 생성하면 됩니다.

#### 락업된 CAKE를 조기에 출금할 수 있나요? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

아니요.

락업된 CAKE는 잠금 해제 시간까지 veCAKE 컨트랙트에 스테이킹됩니다.

#### CAKE를 부분적으로 마이그레이션할 수 있나요? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

아니요.

CAKE 풀 포지션 전체를 한 번에만 마이그레이션할 수 있습니다.

#### iCAKE, bCAKE, vCAKE, rCAKE는 어떻게 되나요? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**iCAKE의 경우:**

IFO iCAKE는 이제 veCAKE를 지원하도록 업그레이드되었습니다. 다음을 확인하세요.

{% content-ref url="../../../pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**bCAKE의 경우:**

파밍 부스팅 bCAKE는 이제 veCAKE를 지원하도록 업그레이드되었습니다. 다음을 확인하세요.

{% content-ref url="../../../pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**vCAKE의 경우:**

투표용 vCAKE는 이제 veCAKE를 지원하도록 업그레이드되었습니다. 다음을 확인하세요.

{% content-ref url="../../../undefined-5/voting/voting-guide/" %}
[voting-guide](../../../undefined-5/voting/voting-guide/)
{% endcontent-ref %}

**rCAKE의 경우:**

모든 veCAKE 보유자(네이티브 또는 마이그레이션)는 새로운 수익 공유 풀에 자동으로 등록됩니다. 수익 분배는 기존 일정에 따라 이루어집니다. 기존 수익 공유 풀은 종료되며, 사용자는 혜택 카드에서 대기 중인 보상을 수령할 수 있습니다. 다음을 확인하세요.

{% content-ref url="revenue-sharing-faq.md" %}
[revenue-sharing-faq.md](revenue-sharing-faq.md)
{% endcontent-ref %}

#### 멀티시그 지갑으로 veCAKE와 상호작용할 수 있나요?

네

다만 veCAKE 스테이킹 컨트랙트에는 화이트리스트에 등록되지 않은 주소에 대해 `noContract` 모디파이어가 구현되어 있습니다. 고정 기간 CAKE 스테이킹 풀에서 스테이킹하거나 마이그레이션하려면, 모든 컨트랙트 기반 멀티시그 지갑은 일회성 자체 화이트리스트 등록 작업을 수행해야 합니다.

화이트리스트에 등록하려면 다음 페이지 중 하나를 방문하세요.

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

프롬프트가 나타납니다. "Whitelist"를 클릭하고 멀티시그 지갑에서 트랜잭션을 진행하세요.

veCAKE의 소유자에게 트랜잭션이 전송되며, 이는 모든 컨트랙트가 자체 화이트리스트 등록을 수행할 수 있도록 권한 없이 사용할 수 있는 쓰기 함수를 가진 컨트랙트입니다.

프롬프트가 나타나지 않으면 다음 안내에 따라 [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11)에서 트랜잭션을 실행하세요.

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### APR이 여러 개인 이유는 무엇인가요?

CAKE를 락업하여 veCAKE를 얻으면 PancakeSwap이 구축한 다양한 제품군에서 여러 가지 훌륭한 혜택을 얻을 수 있습니다. 혜택과 인센티브는 다양한 형태로, 다양한 출처에서 제공됩니다. 따라서 APR이 여러 개 있습니다.

이 모든 것을 동시에 획득할 수 있으므로 합산 APR은 모든 APR의 합계가 됩니다.

[파밍 일드 부스터 bCAKE](../../../pancakeswap/vecake-sunset/bcake/)나 [IFO iCAKE](../../../pancakeswap/vecake-sunset/icake.md)와 같이 veCAKE의 다른 많은 혜택은 APR 형태로 수치화할 수 없다는 점에 유의하세요. 이것들도 꼭 확인해 보세요.

#### veCAKE 풀 APR이란 무엇인가요?

CAKE 배출에서 나오는 인센티브로, 그 비율은 veCAKE 풀 투표 게이지에 의해 조절됩니다.

이 게이지에 대한 배출을 늘리려면 [게이지 투표](../../../pancakeswap/vecake-sunset/gauges-voting/)를 확인하세요.

#### 수익 공유 APR이란 무엇인가요?

DEX 제품에서 징수한 스왑 수수료에서 발생하는 프로토콜 수익 공유로부터 나오는 인센티브입니다.

자세한 내용은 [수익 공유](revenue-sharing-faq.md)를 확인하세요.
