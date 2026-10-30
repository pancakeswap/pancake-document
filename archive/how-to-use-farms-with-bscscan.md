# BscScan으로 파밍 사용하는 방법

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

여러 단계가 필요하기 때문에 PancakeSwap에서 파밍을 사용하는 것은 처음에는 부담스럽게 느껴질 수 있습니다. 이 가이드는 BscScan을 통해 파밍 컨트랙트를 직접 사용하는 방법을 안내합니다.

{% hint style="warning" %}
BscScan을 사용해 컨트랙트와 상호작용하는 것은 초보자에게 권장되지 않습니다. 확신이 없다면 대신 [파밍 사용 방법 가이드](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms)를 이용하시기 바랍니다.
{% endhint %}

## 파밍 프로세스 식별자 찾기

파밍 스마트 컨트랙트와 올바르게 상호작용하려면 LP 페어에 해당하는 프로세스 식별자(PID)가 필요합니다. 현재로서는 GitHub에서 확인하는 것이 가장 쉬운 방법입니다.

1\. [GitHub의 PancakeSwap 웹사이트 파밍 코드](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts)를 엽니다.

2\. **Control**/**command** + **F**를 누르고 (프로젝트 이름이 아닌) 티커로 페어를 검색합니다. 예: 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. PID 번호(이 경우 389)를 쉽게 접근할 수 있는 곳에 적어 두거나 복사해 둡니다. 나중에 필요합니다.

## BscScan으로 LP 토큰 예치하기

BscScan을 사용하여 LP 토큰을 예치하는 데는 몇 가지 과정이 필요합니다. 따라 하기 쉽도록 단계별로 나누었습니다.

### 메인 스테이킹 컨트랙트 주소 확인하기

메인 스테이킹 컨트랙트의 주소는 **0x73feaa1eE314F8c655E354234017bE2193C9E24E**입니다.

확인하고 싶다면 [PancakeSwap: Main Staking Contract BscScan 페이지](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)를 방문하세요. 왼쪽 상단에 주소가 표시됩니다. **페이지 아이콘**을 클릭하여 클립보드에 복사하세요. 곧 필요합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### LP 토큰 컨트랙트 열기

파밍에 예치하려는 LP 토큰을 사용하려면 먼저 해당 LP 토큰의 스마트 컨트랙트를 승인해야 합니다.

### 소스 코드에서 찾기

1\. 먼저 [GitHub의 farms.ts](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts)를 엽니다.

2\. **Control**/**command** + **F**를 누르고 (프로젝트 이름이 아닌) 티커로 페어를 검색합니다. 예: 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. 찾으려는 LP 페어의 코드가 표시되면 "56:" 뒤의 주소를 찾습니다. 이것이 컨트랙트 주소입니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### UI에서 찾기

1\. 먼저 [PancakeSwap 파밍 페이지](https://pancakeswap.finance/farms)를 방문하여 오른쪽 상단의 "SEARCH" 필드로 원하는 페어를 검색합니다. 이 예시에서는 CAKE-BUSD를 사용합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. **Details**를 클릭하여 행을 펼쳐 더 많은 정보를 표시합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. **View Contract**를 클릭하여 BscScan에서 스마트 컨트랙트를 엽니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### LP 토큰 컨트랙트에 권한 부여하기

이제 BscScan에서 LP 토큰의 컨트랙트가 열려 있으므로, LP 토큰을 파밍에 사용할 수 있도록 승인합니다.

1\. LP 토큰의 컨트랙트 페이지에서 **Contract**, 그리고 **Write Contract**로 이동합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**를 클릭하여 MetaMask를 연결합니다.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

연결을 확인합니다.

3\. 함수 1번 "approve"에 "spender:address"가 표시됩니다. 앞서 클립보드에 복사한 메인 스테이킹 컨트랙트의 컨트랙트 주소를 붙여 넣습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. 컨트랙트가 사용할 수 있는 LP 토큰의 양도 승인해야 합니다. 값 필드에 Wei 단위로 금액을 입력해야 합니다. [BscScan 단위 변환기](https://www.bscscan.com/unitconverter)를 사용하면 금액을 쉽게 Wei로 변환할 수 있습니다. 여기서는 5 CAKE-BUSD LP 토큰을 사용하겠습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
값으로 `-1`을 사용하여 무제한 사용 승인을 부여할 수도 있습니다. 이것은 기본적으로 모든 것을 사용한다는 의미가 아니라, 이 컨트랙트를 사용하는 어떤 규모의 거래든 지갑에서 허용된다는 의미일 뿐입니다.
{% endhint %}

6\. **Write**를 클릭하고 MetaMask 지갑에서 작업을 수락합니다. 이제 승인한 금액까지 LP 토큰을 파밍에 예치할 수 있습니다.

### 메인 스테이킹 컨트랙트 스마트 컨트랙트로 LP 토큰 예치하기

메인 스테이킹 컨트랙트가 LP 토큰을 사용할 수 있도록 승인되었으므로 이제 예치할 차례입니다.

1\. [PancakeSwap: Main Staking Contract BscScan 페이지](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)로 돌아가서 **Contract**, 그리고 **Write Contract**로 이동합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**를 클릭하여 MetaMask를 연결합니다.

3\. 함수 2번 "deposit"까지 스크롤하여 "\_pid" 필드에 PID를 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

앞서 PID를 복사해 두지 않았다면 이 페이지 위쪽의 **파밍 프로세스 식별자 찾기** 섹션에서 얻는 방법을 확인할 수 있습니다.

4\. \_pid 아래에 "\_amount"가 있습니다. 앞서 승인한 범위 내에서 LP 컨트랙트가 사용할 금액을 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. 정보를 확인하고 **Write**를 클릭합니다. MetaMask에서 작업을 확인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **View your transaction**을 클릭하여 예치가 정상적으로 처리되었는지 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## 풀에서 출금하기

풀에서 LP 토큰을 출금하는 것은 예치하는 것과 매우 비슷합니다. 차이점은 상호작용하는 함수입니다.

1\. [PancakeSwap: Main Staking Contract BscScan 페이지](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)로 돌아가서 **Contract**, 그리고 **Write Contract**로 이동합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**를 클릭하여 MetaMask를 연결합니다.

3\. 함수 15번 "withdraw"까지 맨 아래로 스크롤하여 "\_pid" 필드에 PID를 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

앞서 PID를 복사해 두지 않았다면 이 페이지 위쪽의 **파밍 프로세스 식별자 찾기** 섹션에서 얻는 방법을 확인할 수 있습니다.

4\. \_pid 아래에 "\_amount"가 있습니다. 풀에서 출금하려는 LP 금액을 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. 정보를 확인하고 **Write**를 클릭합니다. MetaMask에서 작업을 확인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **View your transaction**을 클릭하여 출금이 정상적으로 처리되었는지 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **긴급 출금하기**

‌긴급 출금 기능을 사용하면 다른 방법이 모두 작동하지 않을 때 풀에서 모든 자금을 인출할 수 있습니다.

{% hint style="danger" %}
**긴급 출금 기능을 사용하면 CAKE 보상을 포기하게 됩니다!**

PancakeSwap 팀은 PancakeSwap 팀의 공식 안내가 있거나, 스마트 컨트랙트와 상호작용하는 데 매우 익숙하고 기반 코드를 이해하고 있는 경우가 아니라면 이 기능을 사용하지 않을 것을 강력히 권장합니다.
{% endhint %}

‌1. [PancakeSwap: Main Staking Contract BscScan 페이지](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract)에서 **Contract**, 그리고 **Write Contract**로 이동합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. **Connect to Web3**를 클릭하여 MetaMask를 연결합니다.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. 함수 4번 "emergencyWithdraw"까지 아래로 스크롤하여 "\_pid" 필드에 PID를 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

앞서 PID를 복사해 두지 않았다면 이 페이지 위쪽의 **파밍 프로세스 식별자 찾기** 섹션에서 얻는 방법을 확인할 수 있습니다.

5\. 정보를 확인하고 **Write**를 클릭합니다. MetaMask에서 작업을 확인합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **View your transaction**을 클릭하여 출금이 정상적으로 처리되었는지 확인할 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
