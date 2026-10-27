# 🚜 일드 파밍

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

파밍(Farm)에서는 LP 토큰을 스테이킹하여 PancakeSwap을 지원하면서 CAKE를 획득할 수 있습니다.

파밍을 시작하려면 [파밍 이용 방법 가이드](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms)를 확인하세요.

[파밍 스마트 컨트랙트를 찾는 방법](../../archive/how-to-use-farms-with-bscscan.md)을 알아보세요.

{% hint style="warning" %}
일드 파밍은 시럽 풀보다 더 높은 보상을 제공할 수 있지만, **비영구적 손실(Impermanent Loss)** 위험이 따릅니다. 이름처럼 그렇게 무서운 것은 아니지만, 시작하기 전에 개념을 알아 두는 것이 좋습니다.

자세한 내용은 Binance Academy의 [비영구적 손실에 대한 훌륭한 글](https://academy.binance.com/en/articles/impermanent-loss-explained)을 확인하세요.
{% endhint %}

## 보상 계산

파밍 APR 계산에는 다음 두 가지가 모두 포함됩니다.

* 유동성을 공급하여 얻는 **LP 보상 APR**
* 파밍에 LP 토큰을 스테이킹하여 얻는 **파밍 기본 보상 APR**

이유는 간단합니다. CAKE를 얻기 위해 LP 토큰을 파밍에 스테이킹하더라도 여전히 유동성 풀에 유동성을 공급하고 있는 것이므로 LP 보상도 함께 받기 때문입니다!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

그렇다면 이 수치들은 어떻게 계산할까요?

### 파밍 기본 보상 APR 계산

**파밍 기본 APR**은 파밍 배수와 파밍에 예치된 총 유동성에 따라 계산되며, 이는 해당 파밍에 분배되는 CAKE의 양을 의미합니다.

### LP 보상 APR 계산

이에 더해, 파머는 유동성을 공급한 대가로 **LP 보상**을 받습니다. 다음은 **LP 보상**을 계산하는 예시입니다.

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

위의 WBNB/BUSD 페어에서 다음과 같은 값을 확인할 수 있습니다.

**유동성:** $387.42M\
**24시간 거래량:** $96.97M\
**7일 거래량:** 709.73M

* 연간 수수료 계산
  * 24시간 거래량을 사용하여 풀에서 유동성 공급자(LP)의 **수수료 몫**을 계산합니다(0.17% 거래 수수료 구조 기준):\
    $96,970,000\*0.17/100 = **$164,849**
  * 다음으로, 이 **수수료 몫**을 사용하여 풀이 얻을 것으로 예상되는 **연간 수수료**를 추정합니다(현재 24시간 거래량 기준):\
    $164,849\*365 = **$60,169,885**
* 이제 연간 수수료를 사용하여 **LP 보상 APR**을 계산할 수 있습니다. **연간 수수료**를 **유동성**으로 나누면 됩니다:\
  ($60,169,885/$387,420,000)\*100 = **15.53% LP 보상 APR**
