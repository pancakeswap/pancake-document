# 📔 거버넌스

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
[Tokenomics 3.0 업그레이드](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3)의 일환으로 이 페이지는 2025년 5월 15일에 업데이트되었습니다
{% endhint %}

투표는 PancakeSwap 커뮤니티에 목소리를 부여하여 PancakeSwap이 앞으로 어떻게 발전할지에 대해 커뮤니티가 의견을 낼 수 있게 합니다.

[PancakeSwap 자체 투표 포털](https://pancakeswap.finance/voting)과 [포럼](https://forum.pancakeswap.finance/) 페이지를 확인해 보세요.

## 투표 메커니즘

:notebook\_with\_decorative\_cover:요약 - 변경 사항 ([Tokenomics 3.0 업데이트](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) 이후)

<table><thead><tr><th width="200.6015625">거버넌스 구성 요소</th><th width="218.01953125">Tokenomics 3.0 이전</th><th width="205.1796875">Tokenomics 3.0 이후</th><th>상태<select><option value="q1dVFsCri7zA" label="✅ 변경됨" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 변경 없음" color="blue"></option></select></th></tr></thead><tbody><tr><td>투표권</td><td>1 veCAKE = 1 투표권</td><td>1 CAKE = 1 투표권</td><td><span data-option="q1dVFsCri7zA">✅ 변경됨</span></td></tr><tr><td>위임</td><td>허용(veCAKE 메커니즘을 통해)</td><td>위임은 허용되지 않음</td><td><span data-option="q1dVFsCri7zA">✅ 변경됨</span></td></tr><tr><td>제안 제출 기준</td><td>Snapshot 100K veCAKE 필요</td><td>Snapshot 100K CAKE 필요</td><td><span data-option="q1dVFsCri7zA">✅ 변경됨</span></td></tr><tr><td>코어 제안 vs 커뮤니티 제안</td><td>각 제안 유형별로 역할과 목적이 정의됨</td><td>변경 없음</td><td><span data-option="4AGl26rwjYcI">🔁 변경 없음</span></td></tr><tr><td>투표 기간</td><td>커뮤니티: 고정<br>코어: 가변</td><td>변경 없음</td><td><span data-option="4AGl26rwjYcI">🔁 변경 없음</span></td></tr><tr><td>스냅샷 시점</td><td>제안이 게시된 블록 기준</td><td>변경 없음</td><td><span data-option="4AGl26rwjYcI">🔁 변경 없음</span></td></tr><tr><td>정족수</td><td>최소 정족수 없음</td><td>변경 없음</td><td><span data-option="4AGl26rwjYcI">🔁 변경 없음</span></td></tr></tbody></table>

### 1. **투표권 (변경됨)**

* **모든 CAKE 보유자는 직접 투표권을 가집니다.**
* **투표권은 스냅샷 시점에 지갑 주소에 보유한 CAKE 수량과 직접 대응합니다**
  * **1 CAKE = 1 투표권**
  * **시럽 풀에 스테이킹된 CAKE는 투표권에 포함되지 않습니다**. 스냅샷 시점에 지갑 잔액의 일부가 아니기 때문입니다.
  * 스냅샷 잔액 = 제안이 게시된 동일한 블록
* **위임은 더 이상 지원되지 않습니다.** 모든 CAKE 보유자는 개별적으로 투표해야 합니다.

### 2. **제안 제출 (변경 없음)**

* **제안 제출 방법**
  * [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)에서 제출합니다.
  * 다음 항목을 포함해야 합니다.
    * 제목
    * 내용
    * 설명
    * 온체인 작업(필요한 경우)
    * 투표 기간
* 제안 유형
  1.  코어 제안

      * **PancakeSwap 코어 팀**만 제안할 수 있습니다.
      * CAKE 보유자의 투표가 필요합니다.
      * 통과되면 PancakeSwap 팀이 구현합니다.

      예시

      1. 프로토콜 조정(제품 변경, 수수료 변경)
      2. 이전 제안에서 다루지 않은 생태계 성장 자금의 중요한 사용
  2. 커뮤니티 제안
     * **커뮤니티** 제안은 PancakeSwap 커뮤니티가 게시합니다. 아이디어를 제안하고 커뮤니티의 관점을 표현하는 데 사용됩니다. 이는 커뮤니티의 **구속력 없는 제안**입니다.
     * **100,000 CAKE(스냅샷 잔액)**를 보유한 사람이면 누구나 제출할 수 있습니다.
     * PancakeSwap 팀은 우수한 제안을 향후 코어 제안에 채택할 수 있습니다.
     * 커뮤니티 구성원은 [포럼](https://forum.pancakeswap.finance/)을 활용하여 프로토콜에 대한 피드백과 제안을 할 수도 있습니다.

### **3. 투표 기간 (변경 없음)**

* 모든 CAKE 보유자는 각 제안의 **투표 기간 중에** 투표할 수 있습니다.
  * 커뮤니티 제안: 3일로 고정
  * 코어 제안: 가변, PancakeSwap이 설정
* 투표권은 **제안이 게시된 블록에서의 CAKE 잔액 스냅샷**으로 결정됩니다.
* **제안이 게시된 후 CAKE를 더 추가해도** 해당 투표의 **투표권은 늘어나지 않습니다**.

자세한 내용은 [투표 가이드](https://docs.pancakeswap.finance/protocol/voting/voting-guide)를 참조하세요.

### **4. 투표 결과 (변경 없음)**

* 결과는 **총 투표 수**(투표에 사용된 총 CAKE)를 기준으로 합니다.
* 제안이 통과되기 위한 **최소 정족수는 현재 없습니다**.

## 참고: 거부권

프로토콜을 보호하기 위해 **PancakeSwap 코어 팀은 보안 위협이나 플랫폼의 안정적인 운영에 영향을 미치는 문제와 같은 중대한 상황에서 개입할 권리를 보유합니다**. 이 경우 **커뮤니티 투표나 Snapshot 투표는 필요하지 않습니다**.

거부권 행사 조치가 취해지는 경우 코어 팀은 해당 결정에 대한 **명확한 설명을 공개적으로 공유**합니다.

**가능한 거부권 행사 조치는 다음과 같습니다.**

1. 긴급 버그나 취약점을 수정하기 위해 **스마트 컨트랙트를 일시적으로 중지**.
