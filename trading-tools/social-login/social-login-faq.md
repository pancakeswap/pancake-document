# Social Login 자주 묻는 질문 (FAQ)

{% hint style="info" %}
자세한 내용은 다음을 참조하세요: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 일반 개요

**1. PancakeSwap의 소셜 로그인이란 무엇이며 왜 사용해야 하나요?**

소셜 로그인을 사용하면 **Google**, **X (Twitter)**, **Discord** 또는 **Telegram** 계정으로 PancakeSwap에 접속할 수 있습니다. 지갑 확장 프로그램이나 시드 구문이 필요 없습니다. 백그라운드에서 자기 수탁형 지갑이 생성되므로 소액으로도 즉시 DeFi를 체험할 수 있습니다. 이를 통해 진입 장벽이 낮아지며, 특히 시간이 촉박한 순간에 유용합니다.

**2. 소셜 로그인은 어떤 체인을 지원하나요?**

소셜 로그인 지갑은 현재 PancakeSwap이 지원하는 모든 체인에서 작동합니다.

* **BNB 체인**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

모든 지갑은 **EVM 호환**이며 PancakeSwap을 통해 이러한 네트워크에서 기본적으로 사용할 수 있습니다. 다른 체인(non-EVM 포함)에 대한 지원을 원하시면 알려 주세요!

**3. 소셜 로그인 지갑은 어디에서 사용할 수 있나요?**

데스크톱 또는 모바일 **브라우저**에서 PancakeSwap 웹 앱을 통해 바로 사용할 수 있습니다. 외부 지갑 앱이나 dApp 브라우저와는 **호환되지 않습니다**.



### 🛠️ 지갑 설정 및 사용

**4. 지갑은 어떻게 생성되고 보호되나요?**

지갑은 로그인 시 자동으로 생성되며 **2-of-2 키 셰어 시스템**으로 보호됩니다. 키를 재구성하고 서명을 생성하려면 두 셰어가 모두 필요합니다.

셰어 암호화에 대한 자세한 내용은 다음을 참조하세요.

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. 지갑을 몇 개까지 만들 수 있나요?**

dApp별로 소셜 계정당 **지갑 1개**를 사용할 수 있습니다. 예를 들어 Privy를 사용하는 다른 앱에서 동일한 Google 로그인을 사용하면 별도의 지갑이 생성됩니다.



### 🔐 보안 및 개인정보

**6. 누군가 내 기기를 훔치면 내 지갑에 접근할 수 있나요?**

아니요. 누군가 기기에 접근하더라도 **소셜 로그인**과 (설정한 경우) **복구 비밀번호**가 모두 필요합니다.

**7. PancakeSwap 또는 Privy는 어떤 데이터를 저장하나요?**

* PancakeSwap은 지갑과 관련된 키 셰어를 **저장하지 않습니다**.
* Privy는 **암호화된 인증 셰어와 복구 셰어(복구 흐름을 설정하지 않은 경우)**를 저장합니다.

> 복구 설정을 완료하지 않았다면 복구 셰어는 기본적으로 Privy에 저장된 상태로 유지됩니다. 자세한 내용은 다음을 참조하세요: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 복구 및 세션 관리

**8. 다른 기기나 브라우저에서 같은 지갑을 사용할 수 있나요?**

네! 같은 소셜 계정으로 로그인하기만 하면 됩니다. 새 기기라면 (설정한 경우) 복구 비밀번호를 사용한 복구 과정을 거치게 됩니다.

**9. 기기를 변경하면 어떻게 되나요?**

소셜 계정으로 다시 로그인하고 복구 흐름(비밀번호 설정)을 거치라는 안내가 표시됩니다. 복구 비밀번호를 설정하지 않았다면 소셜 계정 로그인만으로 충분합니다.

**10. 소셜 로그인과 복구 수단에 모두 접근할 수 없게 되면 어떻게 하나요?**

소셜 계정과 복구 수단에 모두 접근할 수 없게 되면 **지갑을 복구할 수 없습니다**. 시드 구문을 통한 대체 수단이 없으며 개인 키 내보내기는 현재 지원되지 않습니다.

> ⚠️ 기억하세요: 향후 활성화되더라도 개인 키를 내보내면 해당 키를 가진 누구에게나 지갑의 모든 권한이 주어지므로 극도로 주의해서 다루세요.

**11. 활성 세션은 얼마나 지속되나요?**

세션은 30**일** 동안 지속됩니다. 이후에는 **다시 로그인**하고 (필요한 경우) 복구 자격 증명을 다시 입력하라는 안내가 표시됩니다. 활성 세션 중에는 각 작업을 수동으로 승인하지 않고도 거래할 수 있습니다.



### ⚙️ 호환성 및 제한 사항

**12. 지갑을 내보내거나 가져올 수 있나요?**

* **내보내기**: 보안상의 이유로 기본적으로 지원되지 않습니다. 향후 업데이트에서 변경될 수 있습니다.
* **가져오기**: 지원되지 않습니다. MetaMask나 Phantom과 같은 외부 지갑은 가져올 수 없습니다.

**13. WalletConnect를 사용해 이 지갑을 다른 dApp에 연결할 수 있나요?**

현재는 불가능합니다. 임베디드 지갑은 **PancakeSwap에서만 사용할 수 있습니다**. 더 폭넓게 사용하고 싶으시다면 알려 주세요. 향후 확대될 가능성이 있습니다.



### 🚀 고급 기능

**14. 소셜 로그인 지갑은 계정 추상화(Account Abstraction)를 지원하나요?**

네. Biconomy 등과의 통합을 통해 거래 일괄 처리 및 **가스비 대납**과 같은 **계정 추상화 기능**을 지원합니다.

**15. 서명 없는 거래는 어떻게 가능한가요?**

* 로그인 후 세션은 최대 30**일** 동안 활성 상태로 유지됩니다. 이 기간 동안 PancakeSwap은 세션 자격 증명을 사용하여 Privy에 사용자를 대신해 거래에 서명하도록 요청할 수 있습니다.&#x20;
* 각 작업마다 지갑 팝업이 표시되지 않으며 모든 것이 백그라운드에서 처리됩니다. 30일이 지나면 이 서명 없는 경험을 계속 사용하려면 다시 로그인해야 합니다.
