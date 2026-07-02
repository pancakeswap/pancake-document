---
description: Como "destravar" qualquer transação pendente que esteja travada no seu MetaMask
---

# Corrigindo Transações Pendentes Travadas no MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Se sua transação estiver travada como pendente no Metamask e o botão "Cancelar" não estiver ajudando, talvez seja necessário usar este método para limpar seu backlog.

Este método funciona essencialmente sobrescrevendo a transação travada com outra de maior prioridade.

### **1. Ativar Nonce de Transação Personalizado**

1\. Abra o plugin do MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Clique no ícone colorido no canto superior direito e clique em **Configurações** no menu suspenso.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. No menu de Configurações, selecione **Avançado**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Role para baixo até ver **Controles avançados de gas**. Ative isso para LIGADO.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Ainda nas configurações Avançadas, continue rolando até ver **Personalizar nonce de transação**. Ative isso para LIGADO.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Encontre Sua Transação Travada**

Agora vamos encontrar a transação que está travada e anotar o "nonce". Isso é um tipo de identificador, que reutilizaremos mais tarde.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Volte para a página inicial do MetaMask. Na aba "Assets", encontre o tipo de token da sua transação travada (neste caso, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. No menu do token, encontre sua transação **Pendente** na área Queue. Clique na sua transação para mais detalhes.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Procure o campo **Nonce** e anote este número.

### **3. Sobrescreva a Transação Travada**

Agora vamos fazer uma nova transação para substituir a travada. Vamos personalizar o número do Nonce, para que seja igual ao que você acabou de anotar.

![](<../../../.gitbook/assets/image (176).png>)

8\. Crie uma nova transação para substituir sua transação travada. Desta vez, aumente a **Taxa de Transação**. Aqui aumentamos de 9 para 20. Isso tornará mais provável que sua transação seja adicionada a um bloco.

![](<../../../.gitbook/assets/image (34).png>)

9\. Na página de confirmação, certifique-se de que seu Preço de Gas está agora no novo valor mais alto.

10\. Encontre o campo **CUSTOM NONCE** e mude o nonce para o número que você anotou no passo 7. Agora clique em Confirmar.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Sua nova transação agora deve ser aceita em um bloco. Para verificar, abra o MetaMask e clique na aba **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUJUhc2iO_CN-k)

12\. Sua transação concluída deve aparecer no topo da sua lista de Activity. Se ainda mostrar "Pending" em laranja, você precisará esperar um pouco mais ou tentar o processo novamente com uma taxa de transação ainda maior (preço de gas).

Como nenhuma carteira pode criar duas transações com o mesmo nonce, se a transação de substituição que você fizer for bem-sucedida, sua transação travada será cancelada.<br>
