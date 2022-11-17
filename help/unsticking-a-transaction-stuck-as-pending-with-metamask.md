---
description: >-
  Como "desprender" quaisquer transações pendentes que estão presas na sua
  MetaMask
---

# Corrigindo transações presas na MetaMask

![](../.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Se sua transação estiver pendente na Metamask e o botão "Cancelar" não estiver ajudando, talvez seja necessário usar esse método para limpar seu backlog.&#x20;

Esse método funciona essencialmente substituindo a transação travada por outra transação de prioridade mais alta.

### **1. Permita Customizar o Nonce da Transação**

1\. Abra seu plugin da MetaMask.

![](../.gitbook/assets/1-1-MetaMask\_plugin.png)

2\. Clique no ícone circular colorido no canto superior direito e clique em **Configurações/Settings** do menu suspenso que abrir.

![](<../.gitbook/assets/1-2-MetaMask\_settings (1).png>)

3\. No menu de configurações, selecione **Avançado/Advanced**.

![](../.gitbook/assets/1-3-MetaMask\_advanced.png)

4\. Role para baixo até ver **Controle de gás avançado/Advanced gas controls**. Alterne isso para Ligado/ON.

![](../.gitbook/assets/1-4-MetaMask\_gas\_control\_on.png)

5\. Ainda na configurações avançadas, role até ver **Customize o Nonce da Transação/Customize transaction nonce**. Ligue isso para Ligado/ON.

![](<../.gitbook/assets/1-4-MetaMask\_gas\_control\_on (1).png>)

### **2. Encontre sua Transação Presa**&#x20;

Agora vamos encontrar a transação que está travada e anotar o “nonce”. Esse é um tipo de identificador, que vamos reutilizar mais tarde.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg\_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Volte para a página inicial da MetaMask. Na página “Ativos”, encontre o tipo de token da sua transação travada (neste caso, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. No menu do token, encontre sua transação **Pendente** na área Fila. Clique na sua transação para mais detalhes.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z\_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm\_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO\_CN-k)

7\. Procure a entrada do **Nonce**, e anote este número.

### **3. Substituir  a transação presa**

Agora vamos fazer uma nova transação para substituir a travada. Vamos personalizar o número do Nonce, para que seja igual ao que você acabou de anotar.

![](<../.gitbook/assets/image (9) (1) (1).png>)

8\. Crie uma nova transação para substituir sua transação travada. Desta vez, aumente a **Taxa da Transação**. Aqui, aumentamos de 9 para 20. Isso aumentará a probabilidade de sua transação ser adicionada a um bloco.

![](<../.gitbook/assets/image (10) (1) (1).png>)

9\. Na página de confirmação, certifique-se de que o preço do gás está agora no valor novo e mais alto.&#x20;

10\. Encontre a entrada **CUSTOM NONCE** e altere o nonce para o número que você anotou na etapa 7. Agora clique em Confirmar.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v\_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Sua nova transação agora deve ser aceita em um bloco. Para verificar, abra a MetaMask e clique na guia **AtividadeActivity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC\_9j3\_LfU3o1-\_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU\_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Sua transação concluída deve aparecer no topo da sua lista de atividades. Se ainda disser "Pendente" em laranja, você precisará esperar um pouco mais ou tentar o processo novamente com uma taxa de transação ainda maior (preço do gás).&#x20;

Como nenhuma carteira pode criar duas transações do mesmo nonce, se a transação de substituição que você fizer for bem-sucedida, sua transação travada será cancelada.
