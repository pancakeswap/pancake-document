---
hidden: true
---

# Руководство по Wormhole Bridge

### Отказ от ответственности

Перед началом использования Wormhole Bridge необходимо прочитать это руководство. В нём пошагово объясняется, как пользоваться мостом, а также демонстрируются некоторые полезные функции, которые он поддерживает из коробки, такие как поиск по транзакциям и возобновление транзакций. Руководство также содержит действия по устранению неполадок.

### Выполнение бриджинга

<figure><img src="https://lh7-us.googleusercontent.com/ZnR2zSNBpjyrzAs_JVlYdKCMDVYmOw4AVdJj_VIk0dmkvqTNxAC1ror2bEQlmSLeVGNV-PwhQSZdyquv-nCBPsHLjACy6LQsyM7M98dFrT9xKnZqC0aWYgUj0fjwC5pbZ9g1UwLalAU6DV-ORgPs-UY" alt=""><figcaption></figcaption></figure>

1. **Перейди на PancakeSwap Wormhole Bridge -** [**https://bridge.pancakeswap.finance/wormhole**](https://bridge.pancakeswap.finance/wormhole)
2. **Подключи кошелёк исходной сети** — первый шаг — подключить кошелёк. При использовании виджета не обязательно заранее устанавливать кошелёк на ту сеть, из которой ты хочешь выполнить бриджинг. Wormhole автоматически установит правильную сеть на основе той, которую ты выбрал. Для EVM-сетей поддерживается только Metamask.
3. **Выбери сеть исходной цепочки** — PancakeSwap в настоящее время поддерживает 4 сети через Wormhole Bridge (Ethereum, Binance Smart Chain, Arbitrum и Base)
4. **Выбери актив исходной цепочки** — выбери токен, который хочешь перевести через мост.
5. **Для шагов 4, 5 и 6** — повтори шаги 1, 2 и 3 для целевой сети
6. Введи сумму бриджинга — введи сумму и подтверди транзакцию. Маршрут и мост будут отображены примерно так:

<figure><img src="https://lh7-us.googleusercontent.com/k6VhFctTcH__ojn3fMScEUUONGP_uPHk-s8OvVonboim7Cm37xCQhNiReTpUuo90_c81jg51pHVKsxhok50I6dwHWjBGZgB-yaIksikYP0aQB7uUaI1Wm6wK9uoYdZdygkViWnXWZcGnsBrPnivbij0" alt="" width="563"><figcaption></figcaption></figure>

7. После подтверждения и отправки транзакции появится страница со статусом транзакции:

<figure><img src="https://lh7-us.googleusercontent.com/RpERMKVOpXOJn56_-awggVO63Pl_KkkvQBzrwlD3jdEssKk7H6gznb7Np8ampHm3quG3doPGReqKFMyU1Fa4b0nlxjmSiZgSlY1WfEEAzbM_PcpZVRtESmXWol50wku4SE5oT8MgjfIwdoj8-rf-IBE" alt="" width="563"><figcaption></figcaption></figure>

Процесс бриджинга состоит из трёх шагов. Эти шаги могут занять некоторое время и, как правило, требуют определённого количества подтверждений блоков в транзакции исходной сети. Как только этот порог подтверждений будет достигнут, Wormhole сгенерирует доказательство, подтверждающее успешность транзакции. Это доказательство необходимо для того, чтобы получить переведённый актив в целевой сети.

8. После завершения верификации ты сможешь получить переведённые активы, нажав показанную кнопку получения:

<figure><img src="https://lh7-us.googleusercontent.com/1OQVN7yTv2LcyZVpuwdZx4xxHsWFkGoSmfNSDDwJDSib47EVxmY-c_mD5EcfVGyb72KNdtZ-BC3CH_cWZtXNXVflFV8PP_577nIb4dG_Z1_O3rdoXETRWORZmgn4eUKyGAdmavmdzzA6YRA3aVA8_R8" alt="" width="563"><figcaption></figcaption></figure>
