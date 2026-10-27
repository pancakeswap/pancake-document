# 유동성 추가/제거 방법 (EVM)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-add-remove-liquidity-header.png)

"유동성"은 PancakeSwap 거래소가 작동하는 핵심 요소입니다. 유동성 페이지에서 두 토큰을 모두 스테이킹하여 어떤 토큰 쌍에도 유동성을 추가할 수 있습니다.

유동성을 추가하면 해당 쌍의 거래 수수료를 받고, NFT 또는 LP 토큰을 받게 되며 이를 [파밍](https://pancakeswap.finance/farms)에 스테이킹해 CAKE 보상을 얻을 수 있습니다!

## Exchange V3

유동성을 공급하려면 원하는 토큰 쌍을 일정 수량 투입해야 합니다. 두 토큰 중 (USD 기준) 가치가 더 낮은 쪽이 공급할 수 있는 유동성의 한도가 됩니다.

필요한 토큰은 쉽게 거래해서 구할 수 있습니다. 필요하다면 [PancakeSwap에서 거래하는 방법](https://docs.pancakeswap.finance/trade/pancakeswap-exchange/trade-guide) 가이드를 참고하세요.

이 예시에서는 ETH와 USDC로 V3 유동성을 추가해 보겠습니다.



1 - [유동성](https://pancakeswap.finance/liquidity) 페이지로 이동합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28243%29.png" alt=""><figcaption></figcaption></figure>

2 - "Add Liquidity" 버튼을 클릭합니다.



3 - 왼쪽 상단 입력란에서 유동성을 추가할 거래 쌍의 두 토큰을 선택합니다. 여기서는 ETH와 USDC를 예로 들겠습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28126%29.png)



4 - 인터페이스가 가장 인기 있는 거래 수수료 등급을 자동으로 선택하고 가격 범위를 설정해 줍니다.



5 - "V3 LP - x% fee tier" 표시를 확인하여 공급하려는 유동성 풀의 버전과 수수료 등급을 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2843%29.png)

* 수수료 등급을 직접 설정하려면 "More"를 클릭하고 원하는 수수료 등급을 선택하세요.
* 가장 인기 있는 수수료 등급에 유동성을 공급하는 것을 항상 권장합니다.



6 - 오른쪽 화면에서 가격 범위를 검토하고 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2822%29.png)

* 차트는 모든 가격 범위에 걸친 유동성 수준을 보여줍니다. 돋보기 버튼으로 확대/축소할 수 있습니다. 하단 x축을 드래그해 차트를 이동하고 탐색할 수 있습니다.
* 가격 범위를 직접 설정하려면 핸들을 드래그하거나, 두 가격의 + 및 - 버튼을 클릭하거나, 두 가격 숫자를 클릭해 직접 입력하세요.
* 권장하지는 않지만 "Full Range" 버튼을 클릭해 전체 가격 범위에 유동성을 공급할 수도 있습니다.



7 - "Deposit Amount"에서 토큰 중 하나의 수량을 입력합니다. 나머지 토큰은 자동으로 계산되어 채워집니다. 토큰 중 하나의 잔액이 부족하면 오류가 표시되고 버튼이 회색으로 비활성화됩니다. 더 적은 수량을 입력하거나 "MAX" 버튼을 사용해 사용 가능한 최대 수량을 입력하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2847%29.png)



8 - "Enable USDC" 버튼을 클릭합니다. ETH 이외의 토큰과 쌍으로 유동성을 추가하는 경우 쌍의 각 토큰마다 두 번씩 Enable을 클릭해야 할 수 있습니다. 지갑에서 해당 작업을 확인하라는 요청이 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2898%29.png)



9 - 그러면 "Add" 버튼이 활성화됩니다. 클릭해 진행합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2826%29.png)



10 - 유동성 포지션을 미리 보여주는 새 팝업 창이 나타납니다. 모든 내용이 문제없다면 "Add"를 다시 클릭해 진행합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2838%29.png)



11 - 지갑에서 확인을 요청합니다. 지갑에서 트랜잭션을 확인하세요.



12 - 잠시 후 "My Liquidity" 페이지에서 새로운 유동성 포지션을 확인할 수 있습니다. 포지션을 클릭하면 상세 내용을 확인할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28211%29.png" alt=""><figcaption></figcaption></figure>

### **유동성 제거**

유동성을 제거하려면 다음과 같이 하세요.

1 - [유동성](https://pancakeswap.finance/liquidity) 페이지로 이동합니다**.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28191%29.png" alt=""><figcaption></figcaption></figure>



2 - "Your Liquidity" 아래에서 유동성을 제거할 포지션을 클릭합니다. 필터를 사용하면 모든 V3 유동성 포지션을 빠르게 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28251%29.png)



3 - "Remove"를 클릭합니다. 새 창이 나타납니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28286%29.png)



4 - 버튼이나 슬라이더를 사용해 제거할 유동성의 양을 선택합니다. 이 쌍의 유동성을 모두 제거하려면 "MAX"를 선택하세요.

5 - "Remove"를 클릭해 진행합니다.

6 - 받게 될 토큰 수량을 보여주는 창이 나타납니다. "Remove"를 다시 클릭합니다. 지갑에서 해당 작업을 확인하라는 요청이 표시됩니다.

7 - 트랜잭션이 확정되면 쌍의 두 토큰을 받게 됩니다. 유동성을 모두 제거하지 않았다면 남은 유동성 가치가 유동성 페이지에 업데이트됩니다.



## Exchange V2

### 유동성 추가

이 예시에서는 BNB와 CAKE로 V2 유동성을 추가해 보겠습니다.

{% hint style="warning" %}
이 예시는 설명을 위한 것일 뿐이며, CAKE/BNB 거래 쌍은 V3로 마이그레이션되었습니다. 기초 토큰 중 하나가 Exchange V3를 지원하지 않거나 해당 토큰 쌍의 유동성 대부분이 아직 마이그레이션되지 않은 경우가 아니라면 항상 V3 유동성을 공급하세요.
{% endhint %}

1. [유동성](https://pancakeswap.finance/liquidity) 페이지로 이동합니다.
2. "Add Liquidity" 버튼을 클릭합니다.
3. 왼쪽 상단 입력란에서 유동성을 추가할 거래 쌍의 두 토큰을 선택합니다. 여기서는 BNB와 CAKE를 예로 들겠습니다.
4. 인터페이스는 몇 가지 예외를 제외하고 기본적으로 V3 유동성 추가로 설정됩니다.
   1. 거래 쌍에 활성 PancakeSwap V2 파밍이 있다면 기본적으로 V2 유동성 추가로 설정됩니다.
   2. 거래 쌍에 기존 V2 유동성 풀이 있다면 "Add V2 Liquidity" 링크가 표시됩니다. 클릭하면 V2 유동성 추가로 전환됩니다.
5. "V2 LP - 0.25 fee tier" 표시를 확인하여 V2 유동성을 추가하고 있는지 확인합니다.
6. "Deposit Amount"에서 토큰 중 하나의 수량을 입력합니다. 나머지 토큰은 자동으로 계산되어 채워집니다. 토큰 중 하나의 잔액이 부족하면 오류가 표시되고 버튼이 회색으로 비활성화됩니다. 더 적은 수량을 입력하거나 "MAX" 버튼을 사용해 사용 가능한 최대 수량을 입력하세요.
7. "Enable CAKE" 버튼을 클릭합니다. BNB 이외의 토큰과 쌍으로 유동성을 추가하는 경우 쌍의 각 토큰마다 두 번씩 Enable을 클릭해야 할 수 있습니다. 지갑에서 해당 작업을 확인하라는 요청이 표시됩니다.
8. 그러면 "Add" 버튼이 활성화됩니다. 클릭해 진행합니다.
9. 지갑에서 확인을 요청합니다. 지갑에서 트랜잭션을 확인하세요.
10. 잠시 후 유동성 페이지에서 V3 및 StableSwap의 다른 유동성 포지션과 함께 LP 토큰 잔액을 확인할 수 있습니다.

### **유동성 제거**

유동성을 제거하려면 다음과 같이 하세요.

1\. [유동성 페이지](https://exchange.pancakeswap.finance/#/pool)로 이동합니다**.**

2\. "Your Liquidity" 아래에서 유동성을 제거할 쌍을 클릭합니다. 필터를 사용하면 모든 V2 유동성 포지션을 빠르게 확인할 수 있습니다.

3\. "Remove"를 클릭합니다. 새 창이 나타납니다.

4\. 버튼이나 슬라이더를 사용해 제거할 유동성의 양을 선택합니다. 이 쌍의 유동성을 모두 제거하려면 "MAX"를 선택하세요.

5\. "Enable"을 클릭합니다. 지갑에서 해당 작업에 서명하라는 요청이 표시됩니다**.**

6\. "Remove" 버튼이 활성화됩니다. 클릭해 진행합니다.

7\. 받게 될 토큰 수량을 보여주는 창이 나타납니다. "Confirm"을 클릭합니다. 지갑에서 해당 작업을 확인하라는 요청이 표시됩니다.

8\. 트랜잭션이 확정되면 쌍의 두 토큰을 받게 됩니다. 유동성을 모두 제거하지 않았다면 남은 유동성 가치가 유동성 페이지에 업데이트됩니다.<br>
