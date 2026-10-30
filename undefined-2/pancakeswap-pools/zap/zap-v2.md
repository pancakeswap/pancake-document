---
description: 단 한 번의 클릭으로 간편하게 유동성 공급
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Zap이란 무엇인가요? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap은 간편한 유동성 공급을 가능하게 합니다. 수동으로 스왑하거나 토큰 비율을 맞추지 않고도 토큰 하나로 한 번의 클릭만으로 유동성을 추가할 수 있습니다.

* 토큰 하나로 유동성 추가: 거래 쌍의 토큰 중 하나만으로 유동성을 추가할 수 있습니다. Zap이 제공한 토큰 하나로 자동으로 스왑을 수행하고, 유동성을 추가하기 전에 거래 쌍을 자동으로 50/50 비율로 맞춥니다.
* 거래 쌍의 토큰 수량이 불균형한 상태로 유동성 추가: 제공하는 토큰 수량이 현재 풀의 비율과 정확히 맞지 않아도 유동성을 추가할 수 있습니다. 예를 들어 기본 풀 비율인 50:50과 다른 30:70이어도 됩니다. Zap이 유동성을 추가하기 전에 토큰을 자동으로 50/50 비율로 재조정합니다.
* 유동성 제거 시 받을 토큰 선택: 유동성을 제거할 때 Zap을 사용하면 거래 쌍의 토큰 중 하나만 받을 수 있습니다. Zap이 토큰을 돌려주기 전에 자동으로 스왑을 수행합니다.

### Zap 활성화 <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

기본적으로 Zap 기능은 모든 사용자에게 켜져 있습니다. 유동성을 추가하거나 제거할 때 새로운 Zap UI가 보이지 않는다면 설정 패널에서 활성화해 주세요. 톱니바퀴 아이콘을 클릭하면 설정 패널을 열 수 있습니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
참고: 현재 Zap 기능은 베타 단계입니다. 전송 시 수수료가 부과되는 토큰 등 일부 토큰은 지원되지 않습니다. 유동성을 추가하거나 제거하는 중에 문제가 발생하면 설정 패널에서 Zap을 비활성화해 주세요.
{% endhint %}

### Zap In (유동성 추가) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

[유동성 페이지](https://pancakeswap.finance/liquidity)로 이동해 "Add Liquidity"를 선택합니다.

두 입력 토큰을 선택해 유동성을 공급할 거래 쌍을 고릅니다. 자세한 내용은 [유동성 가이드](https://docs.pancakeswap.finance/earn/pancakeswap-pools/liquidity-guide)를 확인하세요.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

"Add Liquidity" 버튼을 클릭해 계속 진행합니다.

유동성을 추가하는 거래 쌍의 토큰이 지갑에 잔액이 있다면 해당 토큰의 체크박스가 자동으로 선택됩니다. 두 토큰 모두 지갑에 잔액이 있다면 두 체크박스가 모두 선택됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### 토큰 하나로 Zap하기 <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

거래 쌍의 토큰 중 하나만으로 유동성을 추가할 수 있습니다. 사용하려는 토큰의 체크박스 하나만 선택하세요. Zap이 유동성을 추가하기 전에 선택한 토큰의 절반을 거래 쌍의 다른 토큰으로 자동 스왑합니다. 어떤 토큰이 전환되는지 알려주는 경고 메시지가 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
가격 영향이 너무 크면 Zap이 슬리피지 설정으로 사용자를 보호합니다. "Reduce TOKEN"을 클릭해 원하는 한도로 줄이세요.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### 불균형한 수량의 토큰 두 개로 Zap하기 <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

두 토큰이 모두 선택되었는데 입력한 토큰 수량이 50/50 비율과 맞지 않으면 Zap 밸런싱이 적용됩니다. "Some of your Token A will be converted to Token B"라는 메시지가 표시됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
유동성을 추가하기 전에 Zap이 토큰 수량을 맞추는 것을 원하지 않는다면 "Don’t Convert"를 클릭하세요. 이 경우 Zap은 스왑하여 재조정하는 대신 입력 토큰 수량을 50/50 비율에 맞게 조정합니다.
{% endhint %}

### Zap 진행하기 <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

"Supply"를 클릭하면 Zap의 세부 정보가 표시되며 확인을 기다립니다.

다음 내용을 확인할 수 있습니다.

1. 받게 될 LP 토큰의 수량
2. 입력 토큰의 종류와 투입하는 토큰 수량
3. 50/50 비율에 맞추기 위해 입력 토큰이 어떻게 거래되는지
4. 적용 중인 슬리피지 허용치

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap Out (유동성 제거) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap을 사용하면 유동성을 제거할 때 거래 쌍의 토큰 중 하나만 받을 수도 있습니다.

1. [유동성 페이지](https://pancakeswap.finance/swap#/pool)로 이동합니다.
2. "Your Liquidity" 아래에서 유동성을 제거할 쌍을 클릭합니다.
3. "Remove"를 클릭합니다. 새 팝업이 나타납니다.

"You Will Receive" 섹션에서 받고 싶지 않은 토큰의 체크를 해제할 수 있습니다. 유동성을 제거할 때 Zap이 자동으로 스왑하여 반환금의 100%를 체크된 토큰으로 전환합니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
