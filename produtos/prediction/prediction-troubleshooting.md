# Soluções de Problemas na Previsão

{% hint style="info" %}
Use a barra lateral para encontrar rapidamente as respostas para suas perguntas!
{% endhint %}

### Por que não consigo ver meus ganhos em minha carteira?

Quando você coleta ganhos, eles podem não aparecer nos registros de transações da sua carteira como de costume. Isso ocorre porque eles usam um tipo diferente de transação: transações internas. Digite o endereço da sua carteira no BscScan e verifique a guia "Internal Txns" para confirmar que eles chegaram.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP\_uWeFDYsa0\_nxN3sKUiIwFdACy\_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### Por que os resultados da minha rodada não estão aparecendo?&#x20;

Há um buffer de 15 blocos em cada rodada, o que pode causar atrasos de até 45 segundos após o final de uma rodada. Esse buffer é para acomodar o fato de que podemos não ser capazes de buscar um preço de forma confiável e terminar uma rodada imediatamente: vários fatores da blockchain afetam a velocidade na qual as transações são confirmadas na rede.&#x20;

### Não consigo coletar meus ganhos!&#x20;

Certifique-se de ter BNB suficiente em sua carteira para pagar as taxas de gás. Você precisará de um pouco de BNB para acionar o contrato inteligente.&#x20;

### Não posso reivindicar ganhos de uma rodada de previsão no site.&#x20;

Você pode reivindicar seus ganhos diretamente do contrato. Siga as etapas nas 3 guias abaixo.

{% tabs %}
{% tab title="Verifique as rodadas jogadas" %}
Como verificar o histórico de rodadas que você jogou&#x20;

1. Vá para a página BscScan do contrato de previsão.&#x20;
2. Role para baixo até “8. getUserRounds”.&#x20;
3. Digite o endereço da sua carteira em "user(address)".&#x20;
4. Defina "cursor(uint256)" como 0 e "size(uint256)" como 1000.&#x20;
5. Toque em “Query”&#x20;
6. As rodadas que você inseriu serão exibidas abaixo na primeira linha. (após “uint256\[]:”)
{% endtab %}

{% tab title="Verifique se você pode reivindicar" %}
Primeiro, verifique se você realmente pode reivindicar a rodada que jogou.

1. [Vá para página da BscScan do contrato do Prediction](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#readContract), e vá para a aba Write
2. Role para baixo até “4. claimable”.
3. Digite o ID da rodada que você deseja verificar "epoch(uint256)”.
4. Digite o endereço da sua carteira em “user(address)”.
5. Tecle em “Query”
6. Se uma rodada for reivindicada, ela mostrará “true”.
7. Se o resultado é "false". Por favor, repita os passos acima e tente com "19. refundable".
8. Observe: ⬆️ Se você vir uma rodada retornando "false" em ambos "4. claimable" e "19. refundable", mas aparece no site, provavelmente já foi reivindicado e o site está atrasado.
{% endtab %}

{% tab title="Reivindicar uma rodada" %}
Como reivindicar

1. [Vá para a página da BscScan do contrato do Prediction](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#writeContract), e vá para a aba Write
2. Tecle em  “🔴 Connect to Web3”
3. Use MetaMask ou WalletConnect para conectar.
4. Role para baixo até “3. claim”
5.  Digite o número redondo que deseja reivindicar neste formato, incluindo o \[] brackets: `[12345]`

    Se você quiser reivindicar várias rodadas juntas, separe as rodadas com uma vírgula como esta: `[12345,12346,12347]`
6. Tecle em “Write”
7. Confirme na carteira
{% endtab %}
{% endtabs %}
