# FAQ de Previsão

{% hint style="info" %}
Use a barra lateral para encontrar rapidamente as respostas às suas perguntas!
{% endhint %}

## A) Perguntas Gerais

### **1. Quais são as taxas?**

3% do prêmio total de cada rodada irá para o tesouro, do qual 100% será usado para recompra e queima de CAKE.

### 2. Como o pagamento é calculado?

* Razão de Pagamento para Pool CIMA = Valor Total de Ambos os Pools ÷ Valor do Pool CIMA
* Razão de Pagamento para Pool BAIXO = Valor Total de Ambos os Pools ÷ Valor do Pool BAIXO

**Exemplo - Apostar 2 BNB em "BAIXO", resultado = "BAIXO":**

* Lado BAIXO = 15 BNB, prêmio total = 150 BNB&#x20;
* Razão de pagamento BAIXO = 150 BNB / 15 BNB = 10x
* Valor do Pagamento = Razão de Pagamento × Posição × (1 - Taxa do Tesouro)
  * Se você apostou 2 BNB em BAIXO, pagamento = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Lucro = 19,4 − 2 = 17,4 BNB

### 3. Há um prazo para coletar meus ganhos?

Não, você poderá coletar seus ganhos a qualquer momento no futuro.

### 4. Qual é o endereço do contrato de Previsão da PancakeSwap?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Posições e Resultados

### 1. **Posso alterar ou remover minha posição?**

Não. Uma vez que você registra uma posição, NÃO é possível alterar a direção, adicionar ou remover sua posição. Ela está bloqueada, então certifique-se de estar 100% satisfeito com a direção da sua posição antes de confirmar. &#x20;

### 2. Quando os mercados serão cancelados? O que acontece então?

* **Quando:** Falha do Oracle ou do serviço de backend, ou outras circunstâncias extraordinárias.
* **Resultado:** Os usuários podem reivindicar 100% do valor original de sua aposta (sem taxa).

### 3. O resultado da rodada mudou depois que a rodada terminou! Por quê?

Às vezes, após o encerramento de uma rodada, o resultado final pode ser diferente do último resultado exibido durante a rodada ao vivo. Se você observar uma rodada terminar em "BAIXO", ela pode parecer mudar para "CIMA" alguns segundos depois.

Isso acontece porque usamos o feed de preço do Oracle para determinar o resultado final de uma rodada. O período entre o fim de uma rodada e o início da próxima é de 30 segundos, mas o Oracle é atualizado a cada 20 segundos. É possível que, durante esse curto período, o Oracle envie uma atualização enquanto a transação para iniciar a próxima rodada está sendo processada. Isso pode parecer "inverter" o resultado da rodada anterior.

### 4. O que é Preço Bloqueado e Preço de Fechamento?

* **Preço Bloqueado:** Preço no início da fase AO VIVO.
* **Preço de Fechamento:** Preço ao final da rodada, usado para determinar os vencedores.

**Exemplo – Rodada 400 (Previsão BNB):**

1. **12:00–12:05:** Registrar Aposta → Usuário aposta 0,1 BNB em "CIMA"
2. **12:05–12:10:** Fase de Bloqueio → Preço Bloqueado = $850
3. **12:10:** Fase de Fechamento → Preço de Fechamento = $860
4. **Resultado: aposta "CIMA"** vence

**Observações:**

* O preço do Oracle pode levar até 20 segundos para ser atualizado.
* Vitória da casa: Todas as apostas vão para a Casa

### 5. Quais situações são consideradas VITÓRIA DA CASA?

**Cenários:**

1. Não existem apostas opostas e o usuário perde (ex.: apenas um usuário aposta CIMA e o resultado = BAIXO)
2. Preço Bloqueado = Preço de Fechamento

**O que acontece:**

* A PancakeSwap fica com 100% do pool; todos os fundos são destinados à queima de CAKE.
* Os usuários de ambos os lados perdem o valor inicial da aposta.

**Exemplo - Sem apostas opostas:**

* Usuário A aposta CIMA, sem apostas BAIXO, resultado = BAIXO → Usuário A perde; 100% dos fundos vão para o tesouro.
* Usuário B aposta CIMA, sem apostas BAIXO, resultado = CIMA → Usuário B recupera 97% do depósito.



## C) Pausas de Mercado

### 1. O que significa quando os mercados estão pausados?

Os mercados são pausados quando há condições que afetam a confiabilidade do contrato. Mercados pausados significam que nenhuma aposta será registrada em nenhuma rodada.

### 2. O que causa a pausa do mercado de Previsão da PancakeSwap?

O mercado de previsão será pausado nas seguintes condições:

1. O contrato de previsão não conseguiu obter o preço do Oracle ChainLink porque o Oracle não publicou o preço no momento em que a rodada terminou.
2. O contrato de previsão não conseguiu executar uma ação (encerrar uma rodada ou obter um preço do Oracle) porque a transação ficou presa no mempool por mais de 15 blocos.
3. A PancakeSwap decidiu descontinuar a previsão para aquele mercado / ativo.

### 3. O que acontece com minha posição se o mercado pausar?

Se os mercados pausarem enquanto você tiver uma posição ao vivo, seus fundos estarão disponíveis para resgate, da mesma forma que você normalmente resgataria seus ganhos.

Para resgatar os fundos, você precisará pagar algumas taxas de gas. Não podemos compensá-lo pelas taxas de gas, então tenha esse pequeno risco em mente antes de participar.

### 4. Quando os mercados serão retomados após serem pausados?

Os mercados serão retomados quando um administrador (um dos chefs) retomar o mercado manualmente.



## D) Solução de Problemas e Resgates

### 1. Como faço para resgatar ganhos antigos do mercado CAKEUSD na BNB Chain?&#x20;

* Acesse [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Verifique a aba de histórico para ganhos de rodadas anteriores

### 2. Por que não consigo ver meus ganhos na minha carteira?

Quando você coleta ganhos, eles podem não aparecer nos registros de transações da sua carteira como de costume.\
Isso porque eles usam um tipo diferente de transação: Transações internas.\
Insira o endereço da sua carteira no BscScan e verifique a aba "Internal Txns" para confirmar que chegaram.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Por que os resultados da minha rodada não estão aparecendo?

Há um buffer de 15 blocos em cada rodada, o que pode causar atrasos de até 45 segundos após o término de uma rodada.\
Esse buffer existe para acomodar o fato de que pode não ser possível obter um preço de forma confiável e encerrar uma rodada imediatamente: vários fatores da blockchain afetam a velocidade com que as transações são confirmadas na rede.

### 4. Não consigo coletar meus ganhos, o que devo fazer?

Certifique-se de ter BNB suficiente em sua carteira para pagar as taxas de gas. Você precisará de um pouco de BNB para acionar o contrato inteligente.

### **5. E se eu não conseguir resgatar os ganhos pelo site?**

Você pode conseguir resgatar seus ganhos diretamente do contrato. Siga os passos nas 3 abas abaixo.

{% tabs %}
{% tab title="Verificar rodadas que você jogou" %}
Como verificar o histórico das rodadas em que você jogou

1. Acesse a página BscScan do [contrato de Previsão](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ex.: BNBUSD).
2. Role para baixo até "8. getUserRounds".
3. Digite o endereço da sua carteira em "user(address)".
4. Defina "cursor(uint256)" como 0 e "size(uint256)" como 1000.
5. Clique em "Query"
6. As rodadas em que você participou serão exibidas abaixo na primeira linha. (após "uint256\[]:")
{% endtab %}

{% tab title="Verificar se você pode resgatar" %}
Primeiro, verifique se você realmente deve poder resgatar da rodada em que jogou.

1. Acesse a página BscScan do [contrato de Previsão](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ex.: BNBUSD) e vá para a aba Read
2. Role para baixo até "4. claimable".
3. Digite o id da rodada que deseja verificar em "epoch(uint256)".
4. Digite o endereço da sua carteira em "user(address)".
5. Clique em "Query"
6. Se uma rodada for resgatável, exibirá "true".
7. Se o resultado for "false", repita os passos acima e tente com "19. refundable".&#x20;
8. Observação: ⬆️ Se uma rodada retornar "false" tanto em "4. claimable" quanto em "19. refundable", mas aparecer no site, provavelmente já foi resgatada e o site está desatualizado.
{% endtab %}

{% tab title="Resgatar de uma rodada" %}
Como resgatar

1. Acesse a página BscScan do [contrato de Previsão](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ex.: BNBUSD) e vá para a aba Write
2. Clique em "🔴 Conectar ao Web3"
3. Use MetaMask ou WalletConnect para conectar.
4. Role para baixo até "3. claim"
5.  Digite o número da rodada que deseja resgatar neste formato, incluindo os colchetes \[]: `[12345]`&#x20;

    Se quiser resgatar de várias rodadas ao mesmo tempo, separe as rodadas com vírgula assim: `[12345,12346,12347]`
6. Clique em "Write"
7. Confirme na carteira&#x20;
{% endtab %}
{% endtabs %}
