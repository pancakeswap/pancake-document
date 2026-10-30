---
description: MetaMask에서 멈춰 있는 대기 중 트랜잭션을 "해제"하는 방법
---

# MetaMask에서 멈춘 대기 중 트랜잭션 해결하기

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

MetaMask에서 트랜잭션이 대기 중 상태로 멈춰 있고 "취소" 버튼으로도 해결되지 않는다면, 이 방법으로 밀려 있는 트랜잭션을 정리해야 할 수 있습니다.

이 방법은 멈춘 트랜잭션을 더 높은 우선순위의 다른 트랜잭션으로 덮어쓰는 방식으로 작동합니다.

### **1. 사용자 지정 트랜잭션 논스 활성화하기**

1\. MetaMask 플러그인을 엽니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. 오른쪽 상단의 알록달록한 원 아이콘을 클릭한 다음 드롭다운 메뉴에서 **설정(Settings)**을 클릭합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. 설정 메뉴에서 **고급(Advanced)**을 선택합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. **고급 가스 제어(Advanced gas controls)**가 보일 때까지 아래로 스크롤한 후 이 옵션을 켭니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. 고급 설정에서 계속 스크롤하여 **트랜잭션 논스 사용자 지정(Customize transaction nonce)**이 보이면 이 옵션을 켭니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. 멈춘 트랜잭션 찾기**

이제 멈춘 트랜잭션을 찾아 "논스(nonce)"를 메모해 둡니다. 논스는 일종의 식별자로, 나중에 다시 사용합니다.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMask 첫 화면으로 돌아갑니다. "자산(Assets)" 탭에서 멈춘 트랜잭션의 토큰 종류를 찾습니다(여기서는 CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. 토큰 메뉴의 대기열(Queue) 영역에서 **대기 중(Pending)** 트랜잭션을 찾습니다. 트랜잭션을 클릭하면 자세한 정보를 볼 수 있습니다.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. **논스(Nonce)** 항목을 찾아 이 숫자를 메모해 둡니다.

### **3. 멈춘 트랜잭션 덮어쓰기**

이제 멈춘 트랜잭션을 대체할 새 트랜잭션을 만듭니다. 방금 적어 둔 숫자와 같은 논스 번호를 사용자 지정하여 입력합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. 멈춘 트랜잭션을 대체할 새 트랜잭션을 만듭니다. 이번에는 **트랜잭션 수수료**를 높입니다. 여기서는 9에서 20으로 높였습니다. 이렇게 하면 트랜잭션이 블록에 포함될 가능성이 더 높아집니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. 확인 페이지에서 가스 가격이 새로 설정한 더 높은 금액으로 되어 있는지 확인합니다.

11\. **사용자 지정 논스(CUSTOM NONCE)** 항목을 찾아 8단계에서 적어 둔 숫자로 논스를 변경합니다. 그런 다음 확인을 클릭합니다.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. 이제 새 트랜잭션이 블록에 포함될 것입니다. 확인하려면 MetaMask를 열고 **활동(Activity)** 탭을 클릭합니다.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. 완료된 트랜잭션이 활동 목록 맨 위에 표시됩니다. 여전히 주황색 "대기 중(Pending)"으로 표시된다면 조금 더 기다리거나, 트랜잭션 수수료(가스 가격)를 더 높여 이 과정을 다시 시도해야 합니다.

하나의 지갑은 같은 논스를 가진 두 개의 트랜잭션을 만들 수 없으므로, 대체 트랜잭션이 성공하면 멈춰 있던 트랜잭션은 취소됩니다.<br>
