# ❓ 브릿징 자주 묻는 질문 (FAQ)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## 브릿징 전

1.  **CAKE를 브릿지할 때 모바일 지갑이나 MetaMask 외의 지갑을 사용할 수 있나요?**

    현재 PancakeSwap CAKE 브릿징은 Coinbase Wallet, MetaMask 및 MetaMask 호환 지갑을 지원합니다. 더 많은 지갑이 곧 지원될 예정입니다.

    _팁:_ 개인 키나 시드 구문을 복사해 붙여넣는 위험한 행동을 피하려면, 브릿징용으로 데스크톱 지갑 확장 프로그램을 통해 새 지갑을 만드는 것을 권장합니다.
2.  **경로나 토큰이 표시되지 않는 이유는 무엇인가요?**

    일부 경로는 브릿지 용량, 토큰 지원 여부 또는 유동성에 따라 달라집니다. 나중에 다시 확인하거나 다른 제공업체를 사용해 보세요. 체인별로 이용 가능한 토큰은 브릿지 UI에 직접 표시됩니다.
3.  **브릿징 트랜잭션을 제출할 때 오류가 발생합니다.**

    "MAX" 버튼을 사용하는 대신 수량을 직접 입력해 보세요. 필요하다면 수량에서 소수점 자릿수를 줄여 보세요.
4.  **브릿징 견적에 "Insufficient X to cover native fee"가 표시되는 이유는 무엇인가요?**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    브릿징에는 출발 체인의 네이티브 토큰으로 지불하는 가스비가 필요합니다. 예를 들면 다음과 같습니다.

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    트랜잭션을 완료할 수 있도록 출발 지갑에 수수료를 충당할 충분한 네이티브 토큰이 있는지 확인하세요.
5.  **버튼에 "X CAKE Exceeded"가 표시되는 이유는 무엇인가요?**

    안전을 위해 BSC와 Aptos 간 CAKE 브릿징에는 일일 용량 한도가 있습니다. 더 적은 수량으로 시도하거나 잠시 후 다시 시도하세요. 한도는 수요에 따라 Chef들이 동적으로 조정합니다.
6.  **특정 토큰을 찾을 수 없는 이유는 무엇인가요?**

    선택한 경로에서 해당 토큰이 지원되지 않거나 유동성이 부족할 수 있습니다. 다른 체인이나 다른 수량으로 시도해 보세요.
7.  **BNB Chain에서 Ethereum으로 브릿지할 때 다른 주소로 보낼 수 있나요?**

    아니요, 안전상의 이유로 브릿징은 EVM 체인 간에 동일한 주소끼리만 가능합니다.
8.  **0.00000001 CAKE보다 적은 수량은 브릿지할 수 없는 이유는 무엇인가요?**

    Aptos 토큰(Aptos의 CAKE 포함)은 소수점 이하 최대 8자리까지 지원합니다. 0.00000001 미만의 트랜잭션은 거부되거나 내림 처리됩니다. 이는 Ethereum 브릿징에도 동일하게 적용됩니다. 남은 수량은 출발 지갑에 그대로 남습니다.

***

## 브릿징 후

1.  **확정한 후에 브릿지 전송을 취소할 수 있나요?**

    아니요, 한 번 시작되면 브릿지 트랜잭션은 제공업체가 처리하며 취소할 수 없습니다. 되돌리려면 새 트랜잭션으로 자산을 다시 브릿지해야 합니다.
2.  **트랜잭션이 "pending" 상태에서 멈춰 있다면 어떻게 하나요?**

    브릿징에는 최대 30분이 걸릴 수 있습니다. 해당 브릿지 제공업체의 탐색기에서 트랜잭션 해시를 검색해 상태를 확인하세요.

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    60분이 지나도 pending 상태라면 [소셜 채널](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)을 통해 운영진에게 문의하세요.
3. **CAKE를 받지 못했습니다. 어떻게 해야 하나요?**
   * CAKE를 Aptos로 처음 브릿지하는 경우 CAKE를 **직접 수령**해야 할 수 있습니다. Aptos 지갑에 가스비를 충당할 충분한 APT가 있는지 확인하세요. [Aptos 브릿징 가이드](https://docs.pancakeswap.finance/bridge/bridging/aptos)와 [Aptos 설명](https://theaptosbridge.com/faq#registering-claiming-assets)을 참고하세요.
   * BNB Chain이나 Ethereum으로 브릿지할 때 일부 지갑에서는 잔액을 확인하려면 CAKE 토큰 주소를 직접 추가해야 합니다. 예를 들어 이 [MetaMask 가이드](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/)를 따라 해보세요. 다른 지갑도 비슷한 방식으로 가능합니다.
   * 60분이 지나도 CAKE가 보이지 않는다면 [소셜 채널](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)을 통해 운영진에게 문의하세요.
