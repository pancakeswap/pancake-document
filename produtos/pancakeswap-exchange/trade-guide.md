# Como Fazer Trade

![](../../.gitbook/assets/how-to-trade-on-pancakeswap-header.png)

Fazer trade na PancakeSwap é muito fácil em comparação com a maioria das corretoras. Você não ficará sobrecarregado com gráficos ou jargões, e os cálculos são todos feitos para você.

### Preparando-se para negociar

Antes de poder negociar, você precisará de uma carteira compatível com a BNB Smart Chain. Você pode aprender como obter um [aqui](https://docs.pancakeswap.finance/v/portuguese-brazilian/get-started/wallet-guide). Você também precisará ter alguns tokens BEP20 para negociar. Você pode aprender como obter alguns [aqui](https://docs.pancakeswap.finance/v/portuguese-brazilian/get-started/bep20-guide).

### Fazendo trade na PancakeSwap

1\. Vá para a página da exchange [aqui](https://exchange.pancakeswap.finance/#/swap).

2\. Desbloqueie sua carteira compatível com BNB Smart Chain clicando em **Desbloquear carteira** (você também pode conectar no canto superior direito). Se você ainda não conectou sua carteira à PancakeSwap, você pode ver o tutorial [aqui](https://docs.pancakeswap.finance/get-started/connection-guide).

![](<../../.gitbook/assets/image (12) (2).png>)

3\. Escolha o token que você deseja negociar no menu suspenso na seção "De/From". A configuração padrão é BNB.

![](<../../.gitbook/assets/image (13) (1).png>)

Seja qual for o token que você escolher, você precisará se certificar de ter algum token para negociar. Seu saldo é mostrado acima do menu suspenso do token.&#x20;

4\. Escolha o token com o qual deseja negociar na seção "To/Para" como está na imagem. Em seguida, digite um valor da moeda que quer receber em "To/Para" clicando dentro da caixa.

![](<../../.gitbook/assets/image (14) (1).png>)

O valor da moeda em "From/De" será estimado automaticamente. Você também pode digitar o valor em "From/De" e ter a estimativa do valor em "To/Para" automaticamente, se desejar.&#x20;

5\. Verifique os detalhes e clique no botão **Swap**.

![](<../../.gitbook/assets/image (15).png>)

6\. Aparecerá uma janela com mais detalhes. Verifique se os detalhes estão corretos.

![](<../../.gitbook/assets/image (16) (2).png>)

Quando estiver pronto, clique no botão **Confirm Swap**. Sua carteira pedirá que você confirme a ação.&#x20;

7\. Pronto! Você pode clicar em **Exibir no BscScan** para ver os detalhes da transação no explorer da blockchain.

![](<../../.gitbook/assets/image (17) (1).png>)

## Como é que a minha transação não vai passar?

A PancakeSwap é um aplicativo DeFi que interage com a carteira para concluir transações on-chain para swap, criação de LPs, staking em farms e pools, etc.&#x20;

### Taxas de gás&#x20;

Para isso, a primeira coisa é **garantir que você tenha BNB suficiente para pagar a taxa de gás** das transações on-chain. Normalmente, a taxa de gás flutua dependendo do número de transações na fila, se houver mais transações, uma taxa de gás mais alta pode ser necessária para realizar a transação. Na BNB Smart Chain, a taxa de gás normalmente varia de centavos a um dólar em BNB. Saiba mais sobre a taxa de gás [aqui](https://academy.binance.com/en/glossary/gas).&#x20;

### Taxas de transação&#x20;

Se seu swap ainda não for concluído e estiver exibindo um erro para você revisar a slippage - você pode verificar se os tokens que você está tentando negociar têm **alguma** **taxa e/ou restrições nas transações.**&#x20;

Não é incomum que alguns tokens da BNB Smart Chain incluam uma **taxa de transação** em seus contratos, geralmente essas taxas podem ser usadas para queimar, financiar um tesouro de um projeto de lançamento justo - por exemplo, este token **APX tem uma taxa de 1% sobre cada transação** que vai para um endereço de queima, de modo que mais transações significaria mais queima, acumulando valor para os holders do token APX.&#x20;

Com a taxa de transação, seja ela inclusiva (uma parte do valor do swap é enviada para outro lugar que não o seu endereço, de modo que a saída seja menor do que o esperado para a entrada estimada) ou exclusiva (exigindo uma transferência adicional do seu endereço para enviar tokens extras para que o entrada seja mais do que o esperado para a saída estimada), isso afeta o valor de entrada e saída que você concorda para assinar a transação. Em muitos casos, a transação não pode atender aos requisitos de entrada e saída por causa da taxa.&#x20;

### Troca com taxas de transação&#x20;

Antes de fazer swap de qualquer token, certifique-se de ter visitado o site do projeto para entender se eles têm um mecanismo de taxa de transação (ou taxas, como muitos projetos colocam). Se houver, certifique-se de definir um slippage (derrapagem) que seja suficiente para acomodar a taxa de transação - por exemplo, se houver uma taxa de transação de 5%, sua derrapagem terá que ser definida em pelo menos 5% mais a derrapagem de negociação normal, dependendo do valor da sua negociação e da liquidez do token, digamos 5,5%-6%.&#x20;

Em alguns casos extremos, incluindo alguns golpes, alguns tokens até têm um bloqueio na maioria ou em todas as transferências on-chain, ou permitindo apenas a venda de determinados endereços, nesse caso é impossível trocar o token com sucesso. Aprenda sobre o token que você está tentando negociar e esteja ciente de quaisquer taxas e restrições!

