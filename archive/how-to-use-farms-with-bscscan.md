# Как использовать Farms через BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Использование Farms на PancakeSwap поначалу может показаться сложным, ведь нужно выполнить несколько шагов. Это руководство покажет, как работать с контрактом Farms напрямую через BscScan.

{% hint style="warning" %}
Учти, что взаимодействие с контрактами через BscScan не рекомендуется новичкам. Если ты не уверен в себе, лучше воспользуйся [руководством по использованию Farms](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms).
{% endhint %}

## Поиск идентификатора процесса Farm

Чтобы правильно взаимодействовать со смарт-контрактом фарминга, тебе понадобится идентификатор процесса (PID) для твоей LP-пары. Пока что проще всего найти его на GitHub.

1\. Открой [код Farms сайта PancakeSwap на GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Нажми **Control**/**command** + **F** и найди свою пару по тикеру (не по названию проекта). Например, 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Запиши или скопируй номер PID (в этом примере 389) туда, где он будет у тебя под рукой. Он понадобится позже.

## Внесение LP-токенов через BscScan

Внесение LP-токенов через BscScan состоит из нескольких действий. Мы разбили его на шаги, чтобы было проще следовать инструкции.

### Получение адреса Main Staking Contract

Адрес основного контракта стейкинга: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Если хочешь убедиться в этом, открой [страницу PancakeSwap: Main Staking Contract на BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Адрес указан в левом верхнем углу. Нажми **значок страниц**, чтобы скопировать его в буфер обмена. Он скоро понадобится.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Открой контракт своего LP-токена

Прежде чем потратить LP-токен, который ты хочешь отправить в фарм, нужно дать смарт-контракту разрешение на его использование.

### Из исходного кода

1\. Сначала открой [farms.ts на GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Нажми **Control**/**command** + **F** и найди свою пару по тикеру (не по названию проекта). Например, 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Когда найдёшь код нужной LP-пары, найди адрес после "56:". Это адрес твоего контракта.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Через интерфейс

1\. Сначала открой [страницу Farms на PancakeSwap](https://pancakeswap.finance/farms) и найди нужную пару через поле "SEARCH" в правом верхнем углу. В этом примере мы используем CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Нажми **Details**, чтобы раскрыть строку и увидеть больше информации.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Нажми **View Contract**, чтобы открыть смарт-контракт на BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Выдача разрешения контракту LP-токена

Теперь, когда контракт твоего LP-токена открыт на BscScan, нужно разрешить трату LP-токенов в Farm.

1\. На странице контракта LP-токена перейди в **Contract**, а затем в **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Нажми **Connect to Web3**, чтобы подключить MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Подтверди подключение.

3\. В функции 1, “approve”, ты увидишь поле “spender:address”. Вставь туда адрес Main Staking Contract, который ты скопировал ранее.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Также нужно указать, сколько LP-токенов контракт может потратить. В поле value введи сумму в Wei. Для удобного перевода суммы в Wei можно использовать [BscScan Unit Converter](https://www.bscscan.com/unitconverter). Здесь мы используем 5 LP-токенов CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Также в качестве значения можно указать `-1`, чтобы выдать неограниченное разрешение на трату. Это не значит, что по умолчанию будет потрачено всё: это лишь означает, что твой кошелёк разрешит транзакцию любого размера, использующую этот контракт.
{% endhint %}

6\. Нажми **Write** и подтверди действие в кошельке MetaMask. Теперь ты можешь вносить LP-токены в Farm в пределах одобренной суммы.

### Внесение LP-токенов через смарт-контракт Main Staking Contract

Теперь, когда Main Staking Contract получил разрешение тратить твои LP-токены, пора сделать депозит.

1\. Вернись на [страницу PancakeSwap: Main Staking Contract на BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), перейди в **Contract**, а затем в **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Нажми **Connect to Web3**, чтобы подключить MetaMask.

3\. Прокрути до функции 2, "deposit", и введи свой PID в поле "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Если ты не записал свой PID ранее, узнать его можно в разделе **Поиск идентификатора процесса Farm** выше на этой странице.

4\. Под \_pid ты увидишь "\_amount". Введи количество LP, которое контракт может потратить и которое ты одобрил ранее.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Проверь данные и нажми **Write**. Подтверди действие в MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Убедиться, что депозит прошёл, можно, нажав **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Вывод из пула

Вывод LP-токенов из пула очень похож на внесение депозита. Разница лишь в том, с какой функцией ты работаешь.

1\. Вернись на [страницу PancakeSwap: Main Staking Contract на BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), перейди в **Contract**, а затем в **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Нажми **Connect to Web3**, чтобы подключить MetaMask.

3\. Прокрути в самый низ до функции 15, "withdraw", и введи свой PID в поле "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Если ты не записал свой PID ранее, узнать его можно в разделе **Поиск идентификатора процесса Farm** выше на этой странице.

4\. Под \_pid ты увидишь "\_amount". Введи количество LP, которое хочешь вывести из пула.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Проверь данные и нажми **Write**. Подтверди действие в MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Убедиться, что вывод прошёл, можно, нажав **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Экстренный вывод**

‌Функция экстренного вывода позволяет забрать все твои средства из пула, когда другие способы не работают.

{% hint style="danger" %}
**При использовании функции экстренного вывода ты потеряешь свои награды в CAKE!**

Команда PancakeSwap настоятельно рекомендует не использовать эту функцию, если только команда PancakeSwap не посоветовала этого официально или если ты очень уверенно работаешь со смарт-контрактами и понимаешь лежащий в их основе код.
{% endhint %}

‌1. На [странице PancakeSwap: Main Staking Contract на BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) перейди в **Contract**, а затем в **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Нажми **Connect to Web3**, чтобы подключить MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Прокрути вниз до функции 4, "emergencyWithdraw", и введи свой PID в поле "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Если ты не записал свой PID ранее, узнать его можно в разделе **Поиск идентификатора процесса Farm** выше на этой странице.

5\. Проверь данные и нажми **Write**. Подтверди действие в MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Убедиться, что вывод прошёл, можно, нажав **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
