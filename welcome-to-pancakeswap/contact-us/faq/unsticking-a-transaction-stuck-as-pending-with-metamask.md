---
description: Как «разблокировать» ожидающие транзакции, зависшие в MetaMask
---

# Исправление зависших ожидающих транзакций в MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Если твоя транзакция зависла в режиме ожидания в Metamask, а кнопка «Cancel» не помогает, возможно, тебе нужно воспользоваться этим методом для очистки очереди.

Этот метод работает путём замены зависшей транзакции другой транзакцией с более высоким приоритетом.

### **1. Включи настраиваемый Nonce транзакции**

1\. Открой плагин MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Нажми на цветной значок круга в правом верхнем углу и выбери **Settings** в выпадающем меню.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. В меню Settings выбери **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Прокрути вниз до **Advanced gas controls**. Переключи в положение ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Оставаясь в настройках Advanced, продолжай прокручивать вниз до **Customize transaction nonce**. Переключи в положение ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Найди зависшую транзакцию**

Теперь мы найдём зависшую транзакцию и запишем её «nonce». Это своеобразный идентификатор, который мы используем повторно позже.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Вернись на главную страницу MetaMask. На вкладке «Assets» найди тип токена зависшей транзакции (в данном случае CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. В меню токена найди свою **ожидающую** транзакцию в разделе Queue. Нажми на транзакцию для получения подробностей.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Найди запись **Nonce** и запомни это число.

### **3. Перезапиши зависшую транзакцию**

Теперь мы создадим новую транзакцию для замены зависшей. Настроим число Nonce так, чтобы оно совпадало с тем, которое ты только что записал.

![](<../../../.gitbook/assets/image (176).png>)

8\. Создай новую транзакцию для замены зависшей. На этот раз увеличь **Transaction Fee**. Здесь мы увеличили его с 9 до 20. Это повысит вероятность включения твоей транзакции в блок.

![](<../../../.gitbook/assets/image (34).png>)

9\. На странице подтверждения убедись, что Gas Price теперь соответствует новому более высокому значению.

10\. Найди запись **CUSTOM NONCE** и измени nonce на число, которое ты записал на шаге 7. Теперь нажми Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Твоя новая транзакция должна быть теперь принята в блок. Для проверки открой MetaMask и нажми на вкладку **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUJTTWaQPzXHAWClpsb4)

12\. Завершённая транзакция должна отображаться вверху списка Activity. Если она всё ещё отображается как «Pending» оранжевым цветом, тебе нужно немного подождать или повторить процесс с ещё более высокой комиссией за транзакцию (ценой газа).

Поскольку ни один кошелёк не может создать две транзакции с одинаковым nonce, если замещающая транзакция выполнена успешно, зависшая транзакция будет отменена.<br>
