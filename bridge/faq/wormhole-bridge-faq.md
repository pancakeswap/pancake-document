---
hidden: true
---

# Wormhole 브릿지 자주 묻는 질문 (FAQ)

### Q: 내 트랜잭션은 어떻게 확인하나요? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole 탐색기

브릿지 상태 페이지에서 Wormhole 탐색기의 내 트랜잭션으로 연결되는 링크를 확인할 수 있습니다. 출발 체인 트랜잭션은 완료되었지만 아직 Wormhole의 검증을 받지 못한 경우 트랜잭션 상태는 다음과 같이 표시됩니다.

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

redeem 찾기 옵션은 도착 체인 트랜잭션을 완료할 수 있는 대체 방법입니다. Wormhole 브릿지가 멈추거나 브릿지 트랜잭션 상태를 업데이트하지 못하는 경우에 이 방법을 사용할 수 있습니다. 트랜잭션을 redeem하려면 먼저 redeem 버튼을 클릭하세요.

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

그러면 트랜잭션을 재개하는 옵션이 표시됩니다. 이를 클릭하면 redeem 트랜잭션을 완료할 수 있는 포럼(링크는 다음 질문에 있습니다)으로 이동합니다. <br>

### Q: \<chain>으로 토큰을 보냈는데 대상 지갑에 도착하지 않고 출발 지갑에서만 빠져나갔습니다. 어떻게 해야 하나요?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

a) redeem을 해야 하거나, redeem이 이미 성공했다면 b) 지갑에 토큰을 추가해야 합니다.

**a) Redeem:**

* [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)으로 이동합니다.
* 출발 체인과 해당 트랜잭션 ID를 입력해야 합니다(지갑에서 찾거나, 블록체인 탐색기에서 내 주소로 검색해 찾을 수 있습니다).

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Recover를 클릭합니다.
* Redeem을 클릭하고 지갑 승인을 수락합니다.

**b) 지갑에 토큰 추가:**

**MetaMask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* MetaMask의 자산 탭에서 토큰 가져오기(import tokens)를 클릭합니다.
* 컨트랙트 주소는 해당 블록 탐색기의 트랜잭션에서 토큰 이름을 클릭하면 찾을 수 있습니다. 토큰 이름을 클릭하면 새 창이 열리고, 컨트랙트 주소는 프로필 요약의 오른쪽에 있습니다.
* 심볼도 필요합니다. 토큰을 알아볼 수 있는 이름이라면 무엇이든 괜찮습니다.
* 사용자 지정 토큰 추가(add custom token)를 클릭합니다.

MetaMask 지갑에 토큰을 추가하는 방법의 동영상 튜토리얼은 [여기](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)에서 확인하세요.

### X 토큰을 브릿지했는데 스왑할 수 없습니다. 유동성 있는 시장이 있는 DEX가 없습니다.[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

도착 체인에 유동성이 없는 토큰을 브릿지하신 경우입니다. 이 토큰은 Portal 브릿지를 사용해 다시 브릿지해야 합니다. 토큰 컨트랙트 주소(지갑에서 찾거나 블록체인 탐색기에서 내 주소로 검색해 찾을 수 있습니다)를 Portal의 "select a token" 검색 필드에 붙여넣으면 됩니다.

유동성이 있는 시장의 전체 목록은 [여기](https://portalbridge.com/docs/faqs/liquid-markets)에서 확인할 수 있습니다.

#### 도착 체인에서 토큰을 redeem하려면 어떻게 하나요?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

전송 과정에서 실수로 페이지를 새로고침했거나 토큰을 redeem하지 않았다면 [여기](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow)의 튜토리얼을 따라 해보세요.
