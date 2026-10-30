# veCAKE 브릿지

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

다른 체인에서 bCAKE(파밍 수익 부스트), iCAKE(IFO 공개 판매 할당)와 같은 veCAKE 혜택을 누리려면, BNB 체인에서 간단한 브릿지 요청을 수행하여 veCAKE 잔액과 PancakeProfile을 다른 체인에 동기화해야 합니다.

## 브릿지는 어떻게 하나요? <a href="#id-734b8113-0e00-40ff-bccb-9c129460e2e2" id="id-734b8113-0e00-40ff-bccb-9c129460e2e2"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29.png" alt=""><figcaption></figcaption></figure>

[CAKE Staking](https://pancakeswap.finance/cake-staking) 페이지로 이동하여 veCAKE 혜택 아래의 veCAKE Sync 카드를 찾으세요. "View Details"를 클릭하여 동기화 창을 여세요.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

창에서 BNB 체인에 보유한 veCAKE 수량과 대상 체인 목록을 확인할 수 있습니다. veCAKE와 Pancake Profile을 브릿지하여 각 체인의 veCAKE 및 Pancake Profile 상태에 반영할 수 있습니다.

동기화하려면 체인을 선택하고 "Sync"를 클릭한 다음 지갑 팝업에서 확인하세요.

브릿지를 완료하는 데 최대 20분이 걸릴 수 있습니다. 동기화 창에서 브릿지 진행 상황을 확인할 수 있습니다.&#x20;

참고:

* 한 번에 하나의 체인만 브릿지할 수 있습니다. 여러 체인에 veCAKE를 동기화하려면 위 과정을 반복하세요.
* 브릿지 요청 시 대상 체인의 가스 비용을 충당하기 위해 BNB가 차감됩니다. BNB 금액은 대상 체인에 따라 다릅니다. Ethereum 메인넷과 같은 체인은 가스 비용이 높아 동기화 비용이 훨씬 비쌉니다.
* 불필요한 가스 비용을 피하려면 혜택을 누리고자 하는 체인에만 veCAKE를 동기화하세요.
* CAKE를 추가하거나 veCAKE 스테이킹 포지션을 연장한 후에는 위 과정을 반복하여 대상 체인의 veCAKE 잔액을 업데이트하고 혜택이 최신 상태로 유지되도록 하세요.

## 자주 묻는 질문 (FAQ) <a href="#id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad" id="id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad"></a>

**Q: veCAKE와 Pancake Profile은 얼마나 자주 동기화해야 하나요?**

A: veCAKE의 경우 CAKE를 추가하거나, 락업 기간을 연장하거나, 재락업을 수행할 때만 동기화하면 됩니다. 대상 체인의 veCAKE 잔액은 BNB 체인의 잔액과 함께 선형적으로 감소합니다.

Pancake Profile과 해당 NFT의 경우, 프라이빗 세일에 참여하려면 두 번의 동기화가 필요합니다. 첫 번째는 IFO가 게시되어 UI에 표시될 때 수행해야 합니다. 두 번째는 수령을 활성화하기 위해 IFO 판매가 종료된 후에 수행해야 합니다.

**Q: 브릿지에는 얼마나 걸리나요?**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

대상 체인에 따라 다르지만, 브릿지와 전체 동기화에는 보통 2~5분 정도 걸립니다. 속도가 느린 일부 체인은 최대 30분까지 걸릴 수 있습니다. 브릿지 요청을 추적하려면 동기화 창에서 LayerZero 탐색기 링크를 확인하거나, [https://layerzeroscan.com/](https://layerzeroscan.com/)에 접속하여 BNB 체인 트랜잭션 ID로 검색하세요.

**Q: BNB 체인에서 브릿지 트랜잭션이 실패하는 이유는 무엇인가요?**

A:

* 대상 체인의 가스 추정치가 오래되었기 때문일 수 있습니다. 페이지를 새로고침한 후 다시 시도해 주세요.
* 또한 대상 체인에서 필요한 가스 비용을 지불할 수 있도록 지갑에 BNB가 충분한지 확인해 주세요.

**Q: veCAKE 또는 Pancake Profile이 브릿지되지 않는 이유는 무엇인가요?**

A:

* 남은 락업 기간이 1일 미만인 veCAKE 포지션은 브릿지되지 않습니다. 먼저 락업을 연장한 후 동기화를 다시 시도해 주세요.
* 동기화를 완료하는 데 최대 30분이 걸릴 수 있습니다. https://layerzeroscan.com/ 에 접속하여 BNB 체인 트랜잭션 ID로 검색하고 브릿지 상태가 "Delivered"인지 확인해 주세요.
* 브릿지 상태가 "Failed" 또는 "Blocked"인 경우, 공개 채널을 통해 앰배서더에게 문의하여 자세한 내용을 확인해 주세요.
