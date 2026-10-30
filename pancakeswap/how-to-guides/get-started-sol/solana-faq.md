# Solana 자주 묻는 질문 (FAQ)

### V3 풀 – 자주 묻는 질문 (FAQ)

#### 1. 어떤 수수료 등급을 사용할 수 있나요?

**지원되는 수수료 등급:**\
V3(집중 유동성) 풀에서는 다음 수수료 등급을 사용할 수 있습니다.

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**수수료 분배 (모든 수수료 등급에 적용):**

* 84%는 유동성 공급자(LP)에게 지급
* 16%는 프로토콜에 귀속
  * 8%는 소각
  * 8%는 프로토콜 트레저리로 이동

#### 2. 누구나 풀을 만들 수 있나요?

네. 풀 생성은 허가가 필요 없으며(permissionless), 몇 가지 예외가 있습니다.

* **토큰 페어 + 수수료 등급** 조합마다 하나의 풀만 존재할 수 있습니다 (예: SOL<> USDC 0.1% 풀은 동시에 하나만 존재할 수 있습니다)
* 현재는 **SPL 토큰**과 일부 선별된 **Token-2022** 토큰만 지원됩니다.

#### 3. 새로 만든 풀이 나타나기까지 얼마나 걸리나요?

* 풀은 보통 생성 후 약 **5분** 뒤에 풀 목록에 나타납니다.
* 나타나지 않는 경우:
  * **검색창**을 사용해 직접 찾아보세요.
  * **낮은 TVL** 때문에 목록에서 필터링되었을 수 있습니다.

#### 4. 풀의 APR 또는 TVL이 계속 0으로 표시되는 이유는 무엇인가요?

새 풀을 만든 직후에는 정상적인 현상입니다.

* APR과 TVL 데이터는 풀에서 **최소 한 번의 스왑**이 발생한 후에야 채워집니다.
* 스왑 이후 약 **15분** 이내에 해당 지표가 표시되기 시작합니다.

#### 5. 풀을 만들기 위해 커스텀 토큰은 어떻게 추가하나요?

새 토큰을 추가하는 방법입니다.

* 풀 생성 화면에서 토큰 선택기를 엽니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(410).png" alt="" width="248"><figcaption></figcaption></figure>

* 검색창에 토큰 주소를 붙여넣습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(411).png" alt="" width="247"><figcaption></figcaption></figure>

* \*\*"Add Token"\*\*을 클릭합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(414).png" alt="" width="251"><figcaption></figcaption></figure>

* 이제 목록에서 해당 토큰을 검색할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(412).png" alt="" width="249"><figcaption></figcaption></figure>

* 토큰을 관리하려면:
  * \*\*"View Token List"\*\*를 클릭합니다.
  *   수동으로 추가한 토큰이 포함된 **User Added Token List**를 비롯한 여러 목록을 켜거나 끌 수 있습니다.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(413).png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Solana에서 첫 번째 트랜잭션이 더 비싸게 느껴지는 이유는 무엇인가요?

Solana는 **Associated Token Account(ATA)** 를 사용해 각 지갑의 토큰 잔액을 관리합니다. 토큰을 처음 사용할 때 지갑에서 ATA를 생성해야 하며, 이때 최초 1회 비용(SOL로 지불)이 발생합니다.

* 이 ATA 생성 수수료는 Solana 프로토콜에서 요구하는 것이며 PancakeSwap에만 해당되는 것이 아닙니다.
* 이후 ATA를 닫으면 **처음에 사용한 SOL을 지갑으로 환불받을 수 있습니다.**
