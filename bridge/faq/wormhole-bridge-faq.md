---
hidden: true
---

# FAQ по Wormhole Bridge

### В: Как проверить мою транзакцию? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole Explorer

На странице статуса моста ты увидишь ссылку, которая перенаправит тебя к твоей транзакции в Wormhole Explorer. Когда транзакция в исходной сети завершена, но ещё не верифицирована Wormhole, статус транзакции будет выглядеть так:

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

Функция «find redeem» — это альтернативный способ завершить транзакцию в целевой сети. Ты можешь воспользоваться им в случае, если Wormhole Bridge завис или не обновляет статус твоей транзакции. Чтобы получить свои средства, сначала нажми кнопку «redeem»:

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

После этого отобразится опция возобновления транзакции. Нажми на неё, чтобы перейти на форум (ссылка в следующем вопросе), где ты сможешь завершить транзакцию получения средств. <br>

### В: Я отправил токены в \<chain> — они не пришли в целевой кошелёк, но ушли из исходного. Что делать?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

Тебе нужно либо a) получить токены, либо, если получение уже было успешным, b) добавить их в свой кошелёк:

**a) Получение токенов:**

* Перейди на [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)
* Тебе нужно указать исходную сеть и соответствующий ID транзакции (его можно найти в кошельке или по своему адресу в обозревателе блокчейна)

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Нажми «Recover»
* Нажми «Redeem» и подтверди действие в кошельке

**b) Добавление токенов в кошелёк:**

**Metamask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* На вкладке активов в Metamask нажми «Import tokens»
* Адрес контракта можно найти в соответствующей транзакции в обозревателе блоков, нажав на название токена. При нажатии откроется новое окно, и адрес контракта будет указан справа в сводке профиля.
* Тебе также понадобится символ — это может быть любое название, по которому ты будешь узнавать токен.
* Нажми «Add custom token»

Смотри видеоурок — Как добавить токен в кошелёк Metamask [здесь.](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### Я перевёл через мост токен X, но теперь не могу его обменять. Ни один DEX не имеет ликвидных рынков,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

Ты перевёл токен, у которого нет ликвидности в целевой сети. Тебе нужно воспользоваться Portal Bridge для обратного бриджинга. Для этого вставь адрес контракта токена (который можно найти в кошельке или по своему адресу в обозревателе блокчейна) в поле поиска «select a token» в Portal.

Полный обзор ликвидных рынков можно найти [здесь](https://portalbridge.com/docs/faqs/liquid-markets).

#### Как получить токены в целевой сети?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

Если ты случайно обновил страницу во время процесса перевода или не получил свои токены, следуй руководству [здесь](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow).
