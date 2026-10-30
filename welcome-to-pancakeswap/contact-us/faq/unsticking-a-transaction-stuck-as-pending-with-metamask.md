---
description: Как «разблокировать» зависшие pending-транзакции в MetaMask
---

# Исправление зависших pending-транзакций в MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Если твоя транзакция зависла в статусе pending в Metamask, а кнопка “Cancel” не помогает, возможно, тебе понадобится этот способ, чтобы очистить очередь.

Он работает так: зависшая транзакция по сути перезаписывается другой транзакцией с более высоким приоритетом.

### **1. Включи настраиваемый nonce транзакции**

1\. Открой плагин MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Нажми на разноцветный круглый значок в правом верхнем углу и выбери **Settings** в выпадающем меню.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. В меню настроек выбери **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Прокрути вниз до **Advanced gas controls**. Включи этот переключатель (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Оставаясь в расширенных настройках, продолжай прокручивать, пока не увидишь **Customize transaction nonce**. Включи этот переключатель (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Найди свою зависшую транзакцию**

Теперь мы найдём зависшую транзакцию и запишем её “nonce”. Это своего рода идентификатор, который мы используем позже.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Вернись на главную страницу MetaMask. На вкладке “Assets” найди тип токена своей зависшей транзакции (в нашем случае CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. В меню токена найди свою транзакцию со статусом **Pending** в разделе Queue. Нажми на неё, чтобы увидеть подробности.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Найди пункт **Nonce** и запомни это число.

### **3. Перезапиши зависшую транзакцию**

Теперь мы создадим новую транзакцию, которая заменит зависшую. Мы настроим номер Nonce так, чтобы он совпадал с тем, который ты только что записал.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Создай новую транзакцию вместо зависшей. На этот раз увеличь **Transaction Fee**. Здесь мы увеличили её с 9 до 20. Так у твоей транзакции больше шансов попасть в блок.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. На странице подтверждения убедись, что Gas Price теперь равна новой, более высокой сумме.

11\. Найди пункт **CUSTOM NONCE** и измени nonce на число, которое ты записал на шаге 8. Теперь нажми Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Теперь твоя новая транзакция должна попасть в блок. Чтобы проверить, открой MetaMask и перейди на вкладку **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Завершённая транзакция должна отображаться в верхней части списка Activity. Если там всё ещё оранжевый статус “Pending”, подожди ещё немного или повтори процесс с ещё более высокой комиссией транзакции (gas price).

Поскольку ни один кошелёк не может создать две транзакции с одним и тем же nonce, если твоя заменяющая транзакция пройдёт успешно, зависшая транзакция будет отменена.<br>
