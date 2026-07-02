---
description: Бриджинг CAKE между EVM-сетями и Aptos
---

# Как осуществить бриджинг — EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
В следующем руководстве в качестве примера EVM-сети используется BNB Chain. Тот же процесс применим к Ethereum.
{% endhint %}

## Бриджинг CAKE из BNB Smart Chain в Aptos

1 — Убедись, что твой кошелёк поддерживает как BNB Smart Chain, так и Aptos Mainnet. Либо у тебя установлены оба кошелька в браузере.

Затем открой [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 — Сначала нам нужно подключить кошелёк BNB Smart Chain.

Нажми «Connect» и выбери предпочтительный кошелёк в разделе «EVM». Затем подтверди и одобри действие во всплывающем окне кошелька.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 — Затем нам нужно подключить кошелёк Aptos.

В модальном окне подключения кошелька выбери предпочтительный кошелёк в разделе «Aptos». Затем подтверди и одобри действие во всплывающем окне кошелька.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 — Нажми «v» в верхнем поле выбора токена и выбери «CAKE».

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 — Введи количество CAKE, которое ты хочешь перевести в Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 — Если твой кошелёк Aptos только что создан и на нём нет баланса APT (Aptos Coin), рекомендуем оставить опцию «gas on destination» в значении по умолчанию. Мост зачислит небольшое количество APT на твой кошелёк — это не только поможет тебе начать работу в сети Aptos, но и APT понадобится тебе для оплаты газа при регистрации и получении переведённого CAKE.

Изменение этой опции может привести к сбою бриджинга.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 — Нажми «Transfer», чтобы инициировать транзакцию бриджинга, и подтверди её во всплывающем окне кошелька.

Обрати внимание, что в зависимости от состояния твоего кошелька BNB Smart Chain и кошелька Aptos тебе может потребоваться подтвердить **несколько** операций в кошельке. Например, если ты впервые переводишь CAKE в Aptos, тебе нужно будет:

* Одобрить расходование CAKE в контракте моста (из кошелька BNB Smart Chain)
* Зарегистрировать CAKE (из кошелька Aptos)

Подробнее об этом читай в [разделе ниже](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 — Откинься на спинку кресла и расслабься. Это займёт всего несколько минут. После завершения бриджинга CAKE будет зачислен на твой кошелёк Aptos. Ты можешь отслеживать прогресс с помощью индикатора выполнения.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Бриджинг CAKE в Aptos в первый раз

Для бриджинга CAKE в кошельки Aptos требуются транзакции регистрации и получения средств. Это сделано для повышения безопасности пользователей и является особенностью Aptos.

### **Если у тебя уже есть APT (Aptos Coin) в кошельке:**

Тебе будет предложено зарегистрировать CAKE в кошельке Aptos, если он ещё не зарегистрирован. В этом случае дополнительная транзакция получения средств не требуется.

### **Если у тебя нет APT (Aptos Coin) в кошельке:**

После завершения транзакции бриджинга тебе нужно будет вручную получить свои CAKE. Для покрытия комиссий за газ при получении токены APT будут отправлены на твой кошелёк Aptos из исходного кошелька.

Эти шаги регистрации и получения применяются только при первом взаимодействии с токеном в Aptos. При последующих переводах того же токена эти действия не потребуются.

Прежде чем впервые переводить CAKE в Aptos, убедись, что на твоём адресе Aptos достаточно APT для оплаты газа. Подробнее читай в объяснении Aptos здесь: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Бриджинг CAKE из Aptos в BNB Smart Chain

1 — Убедись, что твой кошелёк поддерживает как BNB Smart Chain, так и Aptos Mainnet. Либо у тебя установлены оба кошелька в браузере.

Затем открой [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 — Сначала нам нужно подключить кошелёк BNB Smart Chain.

Нажми «Connect» и выбери предпочтительный кошелёк в разделе «EVM». Затем подтверди и одобри действие во всплывающем окне кошелька.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 — Затем нам нужно подключить кошелёк Aptos.

В модальном окне подключения кошелька выбери предпочтительный кошелёк в разделе «Aptos». Затем подтверди и одобри действие во всплывающем окне кошелька.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 — Нажми «v» в верхнем поле выбора токена и выбери «CAKE». Затем нажми кнопку с двойной стрелкой в центре страницы, чтобы изменить направление бриджинга.

Убедись, что сеть «Aptos» находится в верхнем поле.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 — Введи количество CAKE, которое ты хочешь перевести в BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 — Если твой кошелёк BNB Smart Chain только что создан и на нём нет баланса BNB (газового токена), рекомендуем оставить опцию «gas on destination» в значении по умолчанию. Мост зачислит небольшое количество BNB на твой кошелёк. Это поможет тебе начать работу в BNB Smart Chain и изучить яркую экосистему PancakeSwap.

7 — Нажми «Transfer» и подтверди транзакции во всплывающем окне кошелька.

8 — Откинься на спинку кресла и расслабься. Это займёт всего несколько минут. После завершения бриджинга CAKE будет зачислен на твой кошелёк BNB Smart Chain. Ты можешь отслеживать прогресс с помощью индикатора выполнения.
