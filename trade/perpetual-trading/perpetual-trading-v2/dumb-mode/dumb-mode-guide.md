# Руководство по Dumb Mode

### Как размещать ордера в Dumb Mode

Чтобы разместить ордер в Dumb Mode на PancakeSwap, выполни следующие шаги:

1. Выбери рынок: перейди на [**PancakeSwap Perpetuals**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) на BSC. Выбери один из доступных рынков: BTCUSD, ETHUSD и т.д.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Module_Order.png" alt="" width="338"><figcaption></figcaption></figure>

2. Нажми на **иконку Dumb (Beta).** Интерфейс позиций изменится на режим Dumb.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Module_Order%20%281%29.png" alt="" width="338"><figcaption></figcaption></figure>

2. Выбери позицию: выбери лонг или шорт по базовому активу\*
   1. Для лонг-позиций: если цена истечения выше цены открытия, пользователь выигрывает сделку и получает прибыль.&#x20;
   2. Для шорт-позиций: если цена истечения ниже цены открытия, пользователь выигрывает сделку и получает прибыль.
   3. В противном случае пользователь теряет весь залог.
   4. Подробнее о позиции см. в примечаниях.
3.  Задай маржу и сумму: выбери маржинальный актив (USDC, USDT, CAKE и т.д.) и укажи сумму залога.

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%2048097008.jpg" alt=""><figcaption></figcaption></figure>
4. Выбери продолжительность: реши, каков срок истечения твоей сделки — 60 с, 5 мин или 10 мин.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Info.png" alt=""><figcaption></figcaption></figure>

5. Разместите ордер: проверь ROI, подтверди детали и разместите сделку, нажав **Open Position**\*

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Info.jpg" alt=""><figcaption></figcaption></figure>

5. Отслеживай сделку: после размещения сделки следи за её ходом до завершения через вкладку «Position». **Пользователи не могут закрыть сделки до истечения срока.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Module_Bottom.png" alt=""><figcaption></figcaption></figure>

7. Расчёт: по завершении сделки, если она успешна, твой ROI будет зачислен за вычетом комиссии 6%. При неудачной сделке убыток составит 100%.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Module_Bottom%20%281%29.png" alt=""><figcaption></figcaption></figure>

### Дополнительное примечание о позиции

* Обрати внимание, что таймер истечения не запускается при нажатии кнопки «OpenPosition»; вместо этого обратный отсчёт на 60 секунд / выбранную продолжительность начинается с момента подтверждения транзакции в блокчейне.
* Отображаемая цена служит только ориентиром. Окончательная цена входа определяется ценой в момент подтверждения транзакции в блокчейне. Она будет обновлена на вкладке «position».

### Советы по использованию Dumb Mode

* Понимай риски: помни о высоких рисках, особенно с ROI -100% при убытке.
* Управляй залогом: инвестируй только то, что можешь позволить себе потерять.
* Будь в курсе событий: следи за рыночными тенденциями для активов, которыми торгуешь.
