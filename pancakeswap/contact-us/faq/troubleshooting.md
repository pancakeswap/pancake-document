---
description: 자주 발생하는 오류 메시지입니다. 사이드바 ➡️를 이용해 발생한 오류로 바로 이동하세요.
---

# 오류 문제 해결

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

명확한 해결책이 없어 보이는 문제에 부딪힐 때가 있습니다. 이 문제 해결 팁이 마주친 문제를 해결하는 데 도움이 될 수 있습니다.

## **익스체인지 관련 문제**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

토큰을 스왑하려고 하지만 슬리피지 허용치가 너무 낮거나 유동성이 너무 낮은 경우입니다.

{% tabs %}
{% tab title="해결 방법" %}
1. 페이지를 새로고침한 후 나중에 다시 시도하세요.
2. 한 번에 더 적은 수량으로 거래해 보세요.
3. 슬리피지 허용치를 높이세요.
   1. 유동성 페이지에서 설정 아이콘을 누릅니다.
   2. 슬리피지 허용치를 조금 높인 후 다시 시도합니다. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(9\)%20\(4\).png)
4. 마지막으로, 소수점 자릿수가 더 적은 수량을 입력해 보세요.
{% endtab %}

{% tab title="원인" %}
**이 오류는 보통 유동성이 낮은 토큰을 거래할 때 발생합니다.**

즉, 스왑하려는 토큰 중 하나가 유동성 풀에 충분히 없다는 뜻입니다. 거래하는 사람이 거의 없는 소형 토큰일 가능성이 높습니다.

다만 매도할 수 없는 사기 토큰을 거래하려는 경우일 수도 있습니다. 이 경우 PancakeSwap은 토큰을 차단하거나 자금을 되돌려 드릴 수 없습니다.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT 또는 INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

유동성 풀(LP)에 유동성을 추가하거나 제거하려고 하지만 페어를 이루는 두 토큰 중 하나가 충분하지 않은 경우입니다.

{% tabs %}
{% tab title="해결 방법" %}
**페이지를 새로고침한 후 다시 시도하거나, 나중에 다시 시도하세요.**

여전히 해결되지 않나요?

1. 유동성 페이지에서 설정 아이콘을 누릅니다.
2. 슬리피지 허용치를 조금 높인 후 다시 시도합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(9\)%20\(4\).png)
{% endtab %}

{% tab title="원인" %}
이 오류는 토큰 A 또는 토큰 B(페어를 이루는 토큰 중 하나)의 수량이 부족한 유동성 풀(LP)에 유동성을 추가하거나 제거하려고 할 때 발생합니다.

가격이 너무 빠르게 업데이트되는데 슬리피지 허용치가 너무 낮은 경우일 수 있습니다.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="고급 사용자를 위한 해결 방법" %}
이 문제를 반드시 해결하고 싶으시군요. 무엇을 하는지 정확히 알지 못한다면 이 방법은 권장하지 않습니다.

현재 PancakeSwap 웹사이트에서 이 문제를 해결하는 간단한 방법은 없으며 컨트랙트와 직접 상호작용해야 합니다. 라우터 컨트랙트를 통해 직접 유동성을 추가하면서 amountAMin을 작은 값으로 설정한 다음, 모든 유동성을 출금할 수 있습니다.

**LP 컨트랙트 승인하기**

승인하려는 LP 토큰의 컨트랙트로 이동합니다.\
예를 들어 ETH/WBNB 페어는 다음과 같습니다. [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. **Write Contract**를 선택한 다음 **Connect to Web3**를 선택하여 지갑을 연결합니다. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. **"1. approve" 섹션**에서 다음을 입력하여 라우터에 대해 LP 토큰을 승인합니다.
   1. spender (address): 상호작용하려는 LP 토큰의 컨트랙트 주소를 입력합니다.
   2. value (uint256): -1

**"balanceOf" 조회하기**

1. **Read Contract**로 전환합니다.
2. **5. balanceOf**에 지갑 주소를 입력하고 **Query**를 누릅니다.
3. 출력된 숫자를 기록해 둡니다. 이 숫자는 uint256 형식으로 표시된 LP 내 잔액이며 다음 단계에서 필요합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(74\).png)

**유동성 추가 또는 제거하기**

라우터 컨트랙트로 이동합니다. [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. 위와 같이 **Write Contract**를 선택하고 **Connect to Web3**를 선택합니다.
2. 수행하려는 작업에 따라 **addLiquidity** 또는 **removeLiquidity**를 찾습니다.
3. LP를 구성하는 두 토큰의 토큰 주소를 입력합니다.
4. \*\*liquidity (uint256)\*\*에 위의 "balanceOf"에서 얻은 uint256 숫자를 입력합니다.
5. **amountAMin** 또는 **amountBMin**을 낮게 설정합니다. 둘 다 1로 시도해 보세요.
6. \*\*to (address)\*\*에 지갑 주소를 입력합니다.
7. Deadline은 트랜잭션이 실행되는 시각보다 큰 에포크 시간이어야 합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(136\).png)

{% hint style="warning" %}
이 방법은 슬리피지가 매우 높아질 수 있으며, 프론트러닝을 당하면 일부 자금을 잃을 수 있습니다.
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

트랜잭션을 생성한 즉시 확인(서명 및 브로드캐스트)하여 다시 시도하세요.

트랜잭션을 만들기 시작했지만 마감 시간이 지난 후에 서명하고 브로드캐스트했기 때문에 발생한 오류입니다. 즉, "확인"을 충분히 빨리 누르지 않았다는 뜻입니다.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

"받는 토큰(To)" 필드의 수량을 수정해 보세요. 그러면 "보내는 토큰(From)"에 "(estimated)" 표시가 나타납니다. 그런 다음 바로 스왑을 진행하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20\(2\).png)

이 오류는 보통 자체 수수료가 있는 토큰을 스왑하려고 할 때 발생합니다.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

지갑에 거래하려는 수량보다 30% 더 많은 토큰이 있는지 확인하거나, 더 적은 수량을 거래해 보세요. 가능한 최대 수량을 매도하려면 100% 대신 70% 또는 69%로 시도해 보세요.\
tDoge나 tBTC 같은 복원형 리베이스(Restorative Rebase) 토큰의 설계 때문에 발생합니다.\
[복원형 리베이스 토큰의 작동 방식 이해하기](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

또 다른 원인으로는 악의적인 토큰 발행자가 해당 토큰의 거래를 중단했거나, 특정 지갑 주소에서만 매도할 수 있도록 설정했을 수 있습니다. 잠재적인 사기를 피하기 위해 항상 직접 조사해 보세요. 이 오류 코드로 스왑에 실패한 토큰이 에어드롭으로 받은 것이라면 사기일 가능성이 매우 높습니다. 토큰 승인을 하거나 링크를 따라가지 마세요. 그렇게 하면 자금이 위험해질 수 있습니다.

### Transaction cannot succeed

더 적은 수량을 거래하거나, 설정 아이콘에서 슬리피지 허용치를 높인 후 다시 시도하세요. 이는 낮은 유동성 때문에 발생합니다.

### **Price Impact too High**

더 적은 수량을 거래하거나, 설정 아이콘에서 슬리피지 허용치를 높인 후 다시 시도하세요. 이는 낮은 유동성 때문에 발생합니다.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="해결 방법" %}
**BNB 페어에서 유동성을 제거하다가 이 오류가 발생한 경우:**

"Receive WBNB"를 선택하고 다시 시도하세요.

**스왑하려다가 이 오류가 발생한 경우:**

스왑하려는 토큰의 프로젝트 팀에 문의하세요. \*\*\*\* 이 문제는 프로젝트 팀이 해결해야 합니다.
{% endtab %}

{% tab title="원인" %}
**(스왑 중 발생하는) 이 문제는 컨트랙트에 V1 PancakeSwap 라우터를 하드코딩한 토큰 때문에 발생합니다.**

이러한 방식은 바람직하지 않지만, 해당 프로젝트들이 이렇게 한 이유는 토크노믹스 때문으로 보입니다. 구매가 일어날 때마다 일정 비율의 토큰이 LP로 전송되는 구조입니다.

영향을 받는 프로젝트는 V2 라우터와 작동하지 않을 가능성이 높습니다. 새 라우터 주소를 가리키는 새 버전의 토큰을 만들고, 기존 토큰 보유자를 새 토큰으로 마이그레이션해야 할 것입니다.

이러한 토큰을 만든 프로젝트는 사용자가 해당 토큰을 V2 LP에 추가하지 않도록 막는 노력도 해야 한다고 권장합니다.

최신 라우터 주소는 [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)입니다.
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

토큰을 스왑하려고 하면 트랜잭션이 실패하고 이 오류 메시지가 표시됩니다. 이 오류는 Trust Wallet을 사용하는 모바일 기기에서 보고되었습니다.

{% tabs %}
{% tab title="해결 방법" %}
1. 슬리피지 허용치를 높여 트랜잭션을 다시 시도하세요.
2. 1번으로 해결되지 않으면 SafePal 같은 다른 지갑으로 트랜잭션을 진행해 보세요.
{% endtab %}

{% tab title="원인" %}
**이 오류는 보통 Trust Wallet에서 슬리피지 허용치가 부족한 상태로 토큰을 거래할 때 발생합니다.**

정확한 문제 내용은 아직 조사 중입니다.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

토큰을 스왑하려고 하면 트랜잭션이 실패하고 이 오류 메시지가 표시됩니다. 이 오류는 여러 플랫폼에서 보고되었습니다.

{% tabs %}
{% tab title="해결 방법" %}
1. 사용 가능한 자금이 충분한지 확인하세요.
2. 거래하려는 금액을 사용할 수 있도록 컨트랙트에 허용량(allowance)을 부여했는지 확인하세요.
{% endtab %}

{% tab title="원인" %}
이 오류는 허용량이 부족한 상태로 토큰을 거래하거나 지갑의 자금이 부족할 때 발생합니다.\
tDoge나 tBTC 같은 tau 자산처럼 복원형 리베이스 토큰을 거래하는 경우, 먼저 이 [리베이스 토큰 가이드](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)로 작동 방식을 이해하고 있는지 확인하세요.
{% endtab %}
{% endtabs %}

## **파밍 관련 문제**

### Fail with error 'ds-math-sub-underflow'

MasterChef 컨트랙트에 대한 LP 토큰 허용량이 모두 소진된 경우입니다.

**unrekt나 BscScan 같은 토큰 승인 관리 도구를 사용하여**

## **시럽 풀 관련 문제**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

CAKE-CAKE 풀에서 언스테이킹하기에 지갑에 SYRUP이 충분하지 않은 경우입니다.

**언스테이킹하려는 CAKE 수량 이상의 SYRUP을 확보하세요.**

1. 익스체인지에서 SYRUP을 구매합니다. 100 CAKE를 언스테이킹하려면 최소 100 SYRUP이 필요합니다.
2. 다시 언스테이킹을 시도합니다.

그래도 실패한다면 컨트랙트에서 직접 "emergencyWithdraw"를 실행하여 스테이킹한 토큰을 언스테이킹할 수 있습니다.

1. 다음으로 이동합니다. [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. \*\*"Connect to Web3"\*\*를 클릭하여 지갑을 연결합니다. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. **"4. emergencyWithdraw"** 섹션에 "0"을 입력하고 "Write"를 클릭합니다.

이렇게 하면 스테이킹한 토큰이 언스테이킹되며 아직 수령하지 않은 CAKE 수익은 잃게 됩니다.

{% hint style="warning" %}
**아직 수확하지 않은 수익은 모두 잃게 됩니다.**
{% endhint %}

이 문제가 다시 발생하지 않도록 **SYRUP을 판매하지 마세요.** "Stake CAKE Earn CAKE" 풀에서 언스테이킹하려면 여전히 SYRUP이 필요합니다.

이 오류는 SYRUP 토큰을 판매했거나 전송했기 때문에 발생했습니다. CAKE-CAKE 시럽 풀에 스테이킹하면 CAKE와 1:1 비율로 SYRUP이 발행됩니다. leaveStaking을 호출하여 풀에서 CAKE를 언스테이킹할 때는 SYRUP을 CAKE와 1:1 비율로 소각해야 하므로, SYRUP이 부족하면 풀에서 언스테이킹할 수 없습니다.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]

트랜잭션을 실행할 때 가스 한도를 낮게 설정한 경우입니다.

{% tabs %}
{% tab title="해결 방법" %}
트랜잭션에 서명하기 전에 지갑에서 **가스 한도**(가스 가격이 아닙니다!)를 직접 높여 보세요.

보통 200000이면 충분합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(21\).png)

위 예시는 Metamask 화면입니다. 가스 한도를 조정하는 방법이 확실하지 않다면 사용 중인 지갑의 문서를 확인하세요.
{% endtab %}

{% tab title="원인" %}
기본적으로 지갑(Metamask, Trust Wallet 등)이 하려는 작업을 끝내지 못하는 경우입니다.

지갑이 추정한 가스 한도가 너무 낮아서 함수 호출이 완료되기 전에 가스가 소진됩니다.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="해결 방법" %}
1. Unrekt.net을 사용하여 상호작용하려는 스마트 컨트랙트에 대한 승인을 취소합니다.
2. 사용 허용량에 한도를 두지 않고 컨트랙트를 다시 승인합니다.
3. 컨트랙트와 다시 상호작용해 봅니다.
{% endtab %}

{% tab title="원인" %}
컨트랙트를 처음 승인할 때 사용 허용량에 한도를 설정했는데, 그 한도보다 많은 수량을 스왑하려고 할 때 발생합니다.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

보상이 적게 남은 시럽 풀에서 언스테이킹하려는 경우일 가능성이 높습니다. 해결 방법은 아래에 있습니다.

그렇지 않다면 지갑에 없는 토큰을 전송하려는 경우일 수 있습니다(예를 들어 이미 대기 중인 트랜잭션에 할당된 토큰을 전송하려는 경우). 이 경우 사용하려는 토큰을 실제로 보유하고 있는지 확인하세요.

{% tabs %}
{% tab title="해결 방법" %}
먼저 [팀에 알려](../social-accounts.md) 어느 풀에서 언스테이킹하려는지 전달하면 보상을 보충할 수 있습니다. 급하게 언스테이킹해야 하고 대기 중인 수익을 잃어도 괜찮다면 emergencyWithdraw를 시도해 보세요.

컨트랙트에서 직접 "emergencyWithdraw"를 실행하여 스테이킹한 토큰을 언스테이킹할 수 있습니다.

1. 언스테이킹하려는 시럽 풀의 컨트랙트 주소를 찾습니다. 지갑의 트랜잭션 내역에서 확인할 수 있습니다.
2. [https://bscscan.com/](https://bscscan.com/)으로 이동하여 검색창에 컨트랙트 주소를 입력합니다.
3. **Write Contract**를 선택합니다.
4. \*\*"Connect to Web3"\*\*를 클릭하여 지갑을 연결합니다.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. **"3. emergencyWithdraw"** 섹션에서 "Write"를 클릭합니다.

이렇게 하면 스테이킹한 토큰이 언스테이킹되며 아직 수령하지 않은 수익은 잃게 됩니다.

{% hint style="warning" %}
**아직 수확하지 않은 수익은 모두 잃게 됩니다.**
{% endhint %}
{% endtab %}

{% tab title="원인" %}
이 오류는 오래된 시럽 풀에서 언스테이킹하려고 하는데, 출금 시 수확할 수 있는 보상이 풀에 충분히 남아 있지 않을 때 나타나는 경향이 있습니다. 이로 인해 트랜잭션이 실패합니다.
{% endtab %}
{% endtabs %}

## **예측 관련 문제**

[prediction-faq.md](../../../undefined-3/prediction/prediction-faq.md "mention")를 확인하세요.

## **기타 문제**

### Provider Error

> Provider Error\
> No provider was found

MetaMask나 Binance Chain Wallet 같은 브라우저 확장 프로그램으로 연결하려고 하는데 확장 프로그램이 설치되어 있지 않을 때 발생합니다.

{% tabs %}
{% tab title="해결 방법" %}
공식 브라우저 확장 프로그램을 설치하여 연결하거나, [PancakeSwap에 지갑을 연결하는 방법](https://docs.pancakeswap.finance/get-started/connection-guide) 가이드를 읽어 보세요.
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

체인을 BNB 스마트 체인으로 전환하세요. 도움이 필요하면 사용 중인 지갑의 문서에서 가이드를 확인하세요.

### Already processing eth\_requestAccounts. Please wait.

지갑 앱에 로그인되어 있고 BNB 스마트 체인에 연결되어 있는지 확인하세요.

### SAFEMOON 및 유사 토큰 구매 관련 문제

SAFEMOON을 거래하려면 설정 아이콘을 클릭하고 **슬리피지 허용치를 12% 이상으로 설정**해야 합니다.\
**SafeMoon은 모든 트랜잭션에 10%의 수수료를 부과하기** 때문입니다.

* 수수료 5% = 기존 보유자 전체에게 재분배
* 수수료 5% = 유동성 추가에 사용

구매할 때 예상보다 적은 토큰을 받게 되는 것도 이 때문입니다.\
자세한 내용은 [SafeMoon 구매 방법](https://community.trustwallet.com/t/how-to-buy-safemoon/155742)을 참고하세요.

### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Metamask를 통해 일부 토큰의 유동성을 제거하려고 할 때 발생합니다. 근본 원인은 아직 알려지지 않았습니다. 다른 지갑을 사용해 보세요.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

트랜잭션 수수료를 지불할 BNB가 충분하지 않습니다. 지갑에 BEP-20 네트워크 BNB가 더 필요합니다.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

지갑에서 트랜잭션의 가스 한도를 높이세요. 가스 한도를 높이는 방법은 사용 중인 지갑의 문서를 확인하세요.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

원인이 명확하지 않습니다. 다시 시도하기 전에 다음 단계를 먼저 해 보세요.

1. 가스 한도를 높입니다.
2. 슬리피지를 높입니다.
3. 캐시를 삭제합니다.

## **프로필 관련 문제**

### Oops! We couldn't find any Pancake Collectibles in your wallet.

이 문제의 원인을 조사하고 있습니다. 그동안 다음 임시 해결 방법을 시도해 보세요.

{% tabs %}
{% tab title="임시 해결 방법 1" %}
1. "Collectible" 페이지로 이동했다가 프로필 페이지로 돌아옵니다.\
   링크를 찾을 수 없다면 [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles)로 바로 이동하세요.
2. 프로필 생성을 다시 시도합니다.
{% endtab %}

{% tab title="임시 해결 방법 2" %}
환경을 바꿔 보세요.

* 캐시를 삭제한 후 다시 시도합니다.
* 다른 브라우저에서 다시 시도합니다.
* 다른 지갑 앱에서 다시 시도합니다.
* 다른 네트워크에서 다시 시도합니다(Wi-Fi와 셀룰러 간 전환).
{% endtab %}
{% endtabs %}

### 사용자 이름 확인이 계속 로딩됩니다

가능한 원인은 두 가지입니다.

1. 브라우저에 여러 개의 지갑이 설치되어 있습니다.
2. 네트워크 문제입니다.

{% tabs %}
{% tab title="해결 방법 1" %}
근본 원인: 브라우저에 여러 개의 지갑이 설치되어 있습니다.\
\
지갑 간에 충돌이 발생할 수 있습니다. 이는 PancakeSwap이 제어할 수 없는 부분으로 저희가 할 수 있는 것이 없습니다.

1. 브라우저에 지갑을 하나만 설치하고 나머지는 제거합니다.
2. 지갑을 다시 연결하고 사용자 이름 설정을 다시 시도합니다.
{% endtab %}

{% tab title="해결 방법 2" %}
근본 원인: 네트워크가 불안정합니다.

다시 시도해야 합니다.

1. 텍스트 입력란에 입력된 내용을 모두 삭제합니다.
2. 사용자 이름을 다시 입력한 후 몇 초간 기다립니다.
3. 작동하지 않으면 페이지를 새로고침한 후 다시 시도합니다.
{% endtab %}
{% endtabs %}
