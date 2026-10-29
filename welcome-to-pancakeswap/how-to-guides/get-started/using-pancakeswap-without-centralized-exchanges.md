---
description: >-
  PancakeSwap을 시작하기 위해 Binance, Coinbase, Kraken, Huobi, OKEx 등 어떤
  중앙화 거래소 계정도 필요하지 않습니다!
hidden: true
---

# 중앙화 거래소 없이 PancakeSwap 이용하기

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-pancakeswap-without-cex-header.png)

PancakeSwap은 탈중앙화 애플리케이션입니다. 따라서 Binance 같은 중앙화 플랫폼과 달리 계정을 등록할 필요 없이 암호화폐 지갑만 있으면 됩니다. 그렇다면 중앙화 거래소를 이용하지 않고 어떻게 PancakeSwap으로 암호화폐를 가져올 수 있을까요?

이 튜토리얼에서는 "크로스체인 브릿지"를 이용해 자산을 BNB Smart Chain 지갑으로 옮기고 PancakeSwap을 시작하는 과정을 안내합니다.

### **다른 블록체인에서 BNB Smart Chain으로 자산 옮기기**

다양한 크로스체인 브릿지를 사용해 Ethereum 또는 다른 네트워크의 토큰을 BNB Smart Chain으로 옮길 수 있습니다.

다음 튜토리얼에서는 세 가지 크로스체인 브릿지를 사용하여 여러 블록체인의 USDT를 BNB Smart Chain으로 옮기는 방법을 보여 드립니다.

{% tabs %}
{% tab title="🥞🌉 팬케이크 브릿지 (추천)" %}
![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28168%29.png)

[**PancakeSwap 브릿지**](http://bridge.pancakeswap.finance) — Stargate 기반의 네이티브 자산 크로스체인 브릿지입니다.

이 브릿지를 통해 스테이블코인을 BNB 체인으로 손쉽게 옮기고, 활발한 PancakeSwap 커뮤니티와 더 넓은 BNB 생태계에 참여할 수 있습니다!

📖 [사용 방법 알아보기](https://medium.com/pancakeswap/launching-pancakeswap-bridge-a-partnership-with-stargate-21c1c9f491a8)
{% endtab %}

{% tab title="AnySwap" %}
AnySwap을 사용해 Polygon(MATIC) 블록체인의 USDT를 BSC로 옮겨 보겠습니다.

1. Polygon(MATIC) 지갑에 USDT와 가스비로 사용할 MATIC을 준비합니다.
2. AnySwap은 MetaMask, OKEx Wallet, Coin98 Wallet만 지원합니다. 다른 지갑 앱을 사용 중이라면 MetaMask로 지갑을 가져오기(import)하는 것을 권장합니다.
3. [https://anyswap.exchange/#/router](https://anyswap.exchange/#/router)로 이동합니다.
4. 지갑을 연결하고 네트워크를 Polygon(MATIC) 메인넷으로 전환합니다.
5.  "From"에서 MATIC 메인넷의 USDT를, "To"에서 BSC 메인넷의 USDT를 선택합니다. 그런 다음 옮기려는 USDT 수량을 입력합니다.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-055554AM-Google%20Chrome_AnySwap%20-%20Cross%20Chain%20Protocol.png" alt="" data-size="original">
6. "Approve USDT"를 클릭하여 USDT를 승인합니다.
7. AnySwap이 USDT를 다른 BSC 주소로 입금하도록 하려면 "+ Send To" 버튼을 사용하세요.
8. "Swap"을 클릭하여 크로스체인 트랜잭션을 완료합니다.
9. 전체 과정은 네트워크 혼잡도에 따라 약 10~30분이 소요됩니다.
10. 완료되면 BSC 지갑에서 자금을 받게 됩니다. 이제 PancakeSwap에서 BNB Smart Chain의 토큰을 스왑해 보세요!
{% endtab %}

{% tab title="O3 Hub" %}
⚠️ **O3 Swap은 베타 버전입니다. 본인의 책임하에 거래하세요.**

O3 Hub를 사용해 ERC-20 블록체인의 USDT를 BNB Smart Chain으로 옮겨 보겠습니다.

1. ERC-20(Ethereum 메인넷) 지갑에 USDT와 가스비로 사용할 ETH를 준비합니다.
2. O3 Hub는 MetaMask와 O3 Wallet만 지원합니다. 다른 지갑 앱을 사용 중이라면 MetaMask로 지갑을 가져오기(import)하는 것을 권장합니다.
3. [https://o3swap.com/hub](https://o3swap.com/hub)로 이동합니다.
4.  ETH와 BSC 모두에 대해 MetaMask 또는 O3 지갑을 연결합니다. 그리고 MetaMask의 네트워크를 Ethereum 메인넷으로 전환합니다.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054852AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
5.  "You pay"에서 ERC-20 USDT를, "You will receive"에서 BEP-20 USDT를 선택합니다. 그런 다음 옮기려는 USDT 수량을 입력합니다.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053358AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
6.  "To" 필드에 연결한 올바른 BNB Smart Chain 지갑 주소가 표시되는지 다시 한 번 확인합니다.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053441AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
7. 모든 내용이 올바른지 확인한 후 "Swap"을 클릭합니다.
8. 화면의 안내에 따라 USDT를 승인하고 최종 크로스체인 트랜잭션을 완료합니다.
9.  전체 과정은 네트워크 혼잡도에 따라 약 10~30분이 소요됩니다. 기록(history) 탭에서 진행 상황을 확인할 수 있습니다.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054520AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
10. 완료되면 BSC 지갑에서 자금을 받게 됩니다. 이제 PancakeSwap에서 BNB Smart Chain의 토큰을 스왑해 보세요!

또한 O3 Swap의 [사용자 가이드](https://docs.o3swap.com/o3-swap-user-guide/hub#2.-hub-swap)도 확인해 보세요.
{% endtab %}
{% endtabs %}
