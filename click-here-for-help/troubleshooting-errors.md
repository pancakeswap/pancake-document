---
description: >-
  Распространенные сообщения об ошибках. Используйте боковую панель, чтобы
  перейти к ошибке, которую вы увидели.
---

# Устранение неисправностей и Ошибки

## Сложности при обмене

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.

Вы пытаетесь обменять токен, но выставили слишком низкий коэфициент проскальзивания. Сделка также может не пройти из-за низкой ликвидности..

{% tabs %}
{% tab title="Решение" %}
1. Обновите страницу и попробуйте снова.
2. Попробуйте обменять меньшую сумму за раз.
3. Увеличьте проскальзывание:
   1. Нажмите значок настроек на странице ликвидности.
   2. Увеличьте проскальзывание в большую сторону и повторите попытку. ![](../.gitbook/assets/image%20%289%29%20%284%29%20%284%29.png)
4. Напоследок попробуйте ввести сумму с меньшим количеством знаков после запятой.
{% endtab %}

{% tab title="Причина" %}
**Обычно это происходит при торговле токенами с низкой ликвидностью.**

Это означает, что не хватает одного из токенов, которые вы пытаетесь обменять в Пуле Ликвидности: это, вероятно токен которым мало кто торгует.

Тем не менее, есть также шанс, что вы пытаетесь торговать мошенническим токеном, который не может быть продан. В этом случае PancakeSwap не может заблокировать токен или вернуть средства.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'  
> or  
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Вы пытаетесь добавить/убрать ликвидность из пула ликвидности \(LP\), но вам не хватает одного из двух токенов в паре.

{% tabs %}
{% tab title="Решение" %}
**Обновите страницу и попробуйте снова**

До сих пор не работает?

1. Нажмите значок настроек на странице ликвидности.
2. Увеличьте проскальзывание в большую сторону и повторите попытку.

![](../.gitbook/assets/image%20%289%29%20%284%29%20%284%29.png)
{% endtab %}

{% tab title="Причина" %}
Причиной ошибки является попытка добавить/убрать ликвидность из пула ликвидности \(LP\), но не хватает одного из двух токенов в паре token A или token B

Возможно, что цены изменяются слишком быстро, а допуск на проскальзывание слишком мал.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)



![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Решение для ботанов" %}
Хорошо, значит, ты действительно полон решимости что-то исправить. Мы не советуем делать это, если ты не знаешь, что делаешь.

В настоящее время нет простого способа решить этот вопрос с сайта PancakeSwap: вам нужно будет напрямую взаимодействовать с контрактом. Вы можете добавлять ликвидность непосредственно через контракт Рутера, устанавливая при этом сумму в размере небольшого объема, а затем снимать всю ликвидность.

### Одобрить **LP контракт**

Отправляйтесь к контракту с токеном LP, который вы пытаетесь одобрить..   
Например, вот ETH/WBNB пара: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Нажмите **Write Contract**, потом **Connect to Web3** и подключите кошелек. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. В **секции "1. approve",** подтвердите LP токен рутеру вводя следующее
   1. spender \(address\): введите адрес контракта LP токена с которым вы пытаетесь взаимодействовать
   2. value \(uint256\): -1

### Запрос "balanceOf"

1. Выберите пункт **Read Contract.**
2. строка **5. balanceOf**, введите адрес своего кошелька и нажмите **Query**.
3. Запомните число, которое экспортируется. Оно показывает ваш баланс в пределах LP в формате uint256, которое понадобится в следующем шаге.

![](../.gitbook/assets/image%20%2832%29.png)

### Добавить или извлечь Ликвидность

Перейдите к контракту на роутер: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f\#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Выберите **Write Contract** и **Connect to Web3** как было описано выше.
2. Найдите **addLiquidity** или **removeLiquidity** \(что бы вы ни пытались сделать\)
3. Введите адреса обоих токенов LP.
4. В **liquidity \(uint256\),** введите uint256 который вы получили в "balanceOf" ранее.
5. Установите **amountAMin** или **amountBMin**: "1" должно получится.
6. Добавьте адрес вашего кошелька в **to \(address\)**.
7. Крайний срок \(deadline\) должен быть epoch \(Unix-время\) больше чем время исполнении транзакции.

![](../.gitbook/assets/image%20%2819%29.png)

{% hint style="warning" %}
Это может привести к очень высокому проскальзыванию, и может привести к потере пользователем средств, в случае фронтрана ботом.
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Попробуйте еще раз, но при этом подтвердите \(подпишите и отправьте в сеть\) транзакцию как только её сгенерируете. 

Подобное может случиться, если вы начали сделку, но не закончили её вовремя. Постарайтесь сразу нажать кнопку "Confirm".

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Обновите страницу и попробуйте снова. Увеличьте коэфициент проскальзывания.

 Вероятнее всего, в момент сделки слишком быстро изменилась цена токена. Подобное происходит в периоды сильной волотильности и ажиотажа на рынке. Сайт может отображать устаревшую информацию из смартконтракта \(цена/кол-во токенов к покупке\). По этой причине сделка может не состояться.



## Сложности с **Syrup Пулом**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

Вам не хватает токенов SYRUP для снятия CAKE из пула.

{% tabs %}
{% tab title="Решение 1" %}
**Количество токенов SYRUP на вашем балансе должно соответствовать количеству CAKE в пуле.**

1. Купить SYRUP на бирже. Если вы хотите снять 100 CAKE, вам необходимо 100 SYRUP.
2. Попробуйте снова.
{% endtab %}

{% tab title="Решение 2" %}
Если первый пункт не получился, вы можете выполнить “emergencyWithdraw” напрямую с контрактом чтоб получить токены что были использованы.

1. Откройте: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E\#writeContract ](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20)
2. Нажмите **“Connect to Web3”** и подключите кошелёк. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Секция **“4. emergencyWithdraw”**, введите "0" нажмите “Write”.

Это снимет ваши токены и вы потеряете не собранные CAKE.

{% hint style="warning" %}
**Это потеряет любой доход, который вы еще не собрали.**
{% endhint %}
{% endtab %}

{% tab title="Причина" %}
Чтобы это больше не повторилось, **не продавай свои SYRUP.**  Тебе он нужен чтобы снять саке из “Stake CAKE Earn CAKE” пула.

Эта ошибка произошла из-за того, что вы продали или отправили токены SYRUP. SYRUP печатается в соотношении 1:1 к CAKE, когда вы делаете вклад в пул CAKE-CAKE. SYRUP должен быть сожжен в соотношении 1:1 к CAKE при запросе функции leaveStaking \(снятие из пула CAKE\), так что если тебе не хватает, ты не можешь выйти из пула.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}



![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endtab %}
{% endtabs %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas\]

Вы установили слишкий низкий лимит газа для проведения сделки.

{% tabs %}
{% tab title="Решение" %}
Попробуйте вручную увеличить **gas limit** \(не трогайте gas price \(gwei\)!\) в вашем кошельке перед тем, как подписать транзакцию. 

Лимита в 200000 почти всегда достаточно.

![](../.gitbook/assets/image%20%28169%29.png)

Пример выше из Metamask; Если вы не уверены, как настроить лимит газа, то проверьте документацию кошелька, которым вы пользуетесь.
{% endtab %}

{% tab title="Причина" %}
Все просто, твой кошелек \(Metamask, Trust Wallet и т.д.\) не может завершить то, что он пытается сделать.

Ваш кошелек расчитал не правильно, лимит газа слишком мал- поэтому вызов функции обрывается до завершения вызываемой функции.  
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Вы пытаетесь выйти из SYRUP пула с низким вознаграждением \(не хватает наград\).

{% tabs %}
{% tab title="Решение" %}
Чтобы получить свои токены, выполните “emergencyWithdraw” напрямую с адресом контракта.

1. Найдите адрес контракта пула, от которого вы пытаетесь выйти. Вы можете найти его в журнале транзакций вашего кошелька..
2. Откройте [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20) и в поиске введите адрес контракта.
3. Выберите **Write Contract.**
4. Нажмите **“Connect to Web3”** и подключите кошелек.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Открыв секцию **“4. emergencyWithdraw”,** введите "0" и нажмите “Write”.

Это действие снимет токен САКЕ, но не соберет награду.

{% hint style="warning" %}
**Это потеряет любой доход, который вы еще не собрали.**
{% endhint %}
{% endtab %}

{% tab title="Причина" %}
Эта ошибка имеет тенденцию появляться, когда вы пытаетесь выйти из старого Syrup пула, но не хватает наград в резерве, чтобы собрать их при выходе из него. Это приводит к провалу сделки.
{% endtab %}
{% endtabs %}

## \*\*\*\*

