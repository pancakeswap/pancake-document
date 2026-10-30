---
description: Como "destravar" transações pendentes que estão travadas na sua MetaMask
---

# Corrigindo Transações Pendentes Travadas na MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Se sua transação está travada como pendente na Metamask e o botão “Cancel” não está ajudando, talvez você precise usar este método para limpar sua fila.

Esse método funciona basicamente sobrescrevendo a transação travada por outra, de prioridade mais alta.

### **1. Ative o Nonce de Transação Personalizado**

1\. Abra a extensão da MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Clique no ícone de círculo colorido no canto superior direito e clique em **Settings** no menu suspenso.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. No menu Settings, selecione **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Role para baixo até ver **Advanced gas controls**. Ative essa opção (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Ainda nas configurações Advanced, continue rolando até ver **Customize transaction nonce**. Ative essa opção (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Encontre Sua Transação Travada**

Agora vamos encontrar a transação que está travada e anotar o “nonce”. Ele é uma espécie de identificador, que vamos reutilizar mais adiante.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Volte à página inicial da MetaMask. Na aba “Assets”, encontre o tipo de token da sua transação travada (neste caso, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. No menu do token, encontre sua transação **Pending** na área Queue. Clique na transação para ver mais detalhes.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Procure o campo **Nonce** e anote esse número.

### **3. Sobrescreva a Transação Travada**

Agora vamos criar uma nova transação para substituir a travada. Vamos personalizar o número do Nonce para que seja igual ao que você acabou de anotar.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Crie uma nova transação para substituir a travada. Desta vez, aumente a **Transaction Fee**. Aqui aumentamos de 9 para 20. Isso torna mais provável que sua transação seja incluída em um bloco.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Na página de confirmação, confirme que seu Gas Price agora está no novo valor, mais alto.

11\. Encontre o campo **CUSTOM NONCE** e altere o nonce para o número que você anotou no passo 8. Agora clique em Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Sua nova transação deve ser aceita em um bloco. Para conferir, abra a MetaMask e clique na aba **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Sua transação concluída deve aparecer no topo da lista de Activity. Se ainda estiver como “Pending” em laranja, você precisará esperar um pouco mais ou tentar o processo novamente com uma taxa de transação (gas price) ainda mais alta.

Como nenhuma carteira pode criar duas transações com o mesmo nonce, se a transação de substituição for bem-sucedida, sua transação travada será cancelada.<br>
