# 수수료 및 경로

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(61).png" alt=""><figcaption></figcaption></figure>

Exchange V3에서는 기본적으로 PancakeSwap Smart Router가 V3, V2, StableSwap(BNB 체인), AMM, 그리고 마켓 메이커(BNB 체인 및 Ethereum)의 유동성을 활용하여 거래를 체결하고 트레이더에게 최적의 가격을 찾아 줍니다.

다만 사용자는 언제든지 라우터가 사용할 유동성 소스를 직접 선택하고, 멀티홉과 분할 라우팅을 켜거나 끄는 방식으로 거래를 커스터마이징할 수 있습니다.

### **현재 적용되는 수수료율과 수수료 금액 확인하기**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(182\).png)

현재 스왑에 부과되는 거래 수수료를 확인하려면 스왑 상세 정보 영역의 "Fee" 섹션을 확인하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(296\).png)

거래가 현재 어떤 종류의 풀과 수수료 등급을 통해 라우팅되는지 확인하려면 "Route" 섹션을 확인하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(265\).png)

더 자세히 알아보려면 돋보기 아이콘을 클릭하여 전체 거래 경로를 표시하세요.

### **유동성 소스 커스터마이징**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(289\).png)

"Customize Routing" 화면 상단에서 거래를 라우팅할 때 사용할 유동성 소스를 선택할 수 있습니다. 이 화면을 열려면 다음 중 하나를 하세요.

* 거래 경로 화면 하단의 "Customize Routing"을 클릭합니다.
* 스왑 화면의 톱니바퀴 아이콘을 클릭한 뒤, 하단의 "Customize Routing"을 클릭합니다.

기본적으로 모든 유동성 소스가 활성화되어 있으며, Smart Router는 PancakeSwap 내에서 사용 가능한 모든 유동성을 최대한 활용합니다.

라우터는 AMM 유동성 풀과 MM 마켓 메이커 사이에서 거래를 라우팅하지 않는다는 점에 유의하세요. 거래가 MM 마켓 메이커를 통해 체결되는 경우, 어떤 AMM 유동성 풀도 거치지 않습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(199\).png)

오른쪽 상단의 "Reset" 버튼을 클릭하면 설정을 기본값으로 초기화할 수 있습니다.

### **라우팅 환경설정 커스터마이징**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(129\).png)

"Customize Routing" 화면 하단에서 멀티홉과 분할 라우팅을 켜거나 끄는 방식으로 라우팅 환경설정을 조정할 수 있습니다.

멀티홉은 여러 유동성 풀을 여러 단계에 걸쳐 거쳐 가며 토큰을 스왑하여 최적의 조건을 얻는 기능입니다. 이를 끄면 거래가 직접 스왑으로 제한되어 슬리피지가 커지거나 자금 손실이 발생할 수도 있습니다.

분할 라우팅은 토큰 스왑을 여러 경로로 나누어 최적의 조건을 얻는 기능입니다. 이를 끄면 거래가 단일 경로로만 체결되어 효율이 낮아지거나 슬리피지가 커질 수 있습니다.

{% hint style="warning" %}
커스터마이징한 거래 설정 때문에 거래를 체결할 수 없는 경우 경고가 표시됩니다. "Check your settings"를 클릭하면 "Customize Routing" 화면을 빠르게 열 수 있고, "Reset to default"를 선택하면 설정을 기본값으로 빠르게 되돌릴 수 있습니다.
{% endhint %}
