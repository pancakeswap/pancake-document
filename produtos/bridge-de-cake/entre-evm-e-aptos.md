---
description: Bridge de CAKE entre Aptos e chains EVM
---

# Entre EVM e Aptos



![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FhbVsTxyjJyeQ4nitrT2R%2Fimage.png?alt=media\&token=87135c3d-49f3-451b-9916-b3e75b175285)

{% hint style="info" %}
O guia a seguir usa o BNB Chain como um exemplo de uma chain EVM. O mesmo processo pode ser aplicado na Ethereum.
{% endhint %}

## Bridge do CAKE de BNB Smart Chain para Aptos&#x20;

1 - Certifique-se de que sua carteira suporta tanto a BNB Smart Chain quanto a Aptos Mainnet. Ou você tem ambas as carteiras instaladas em seu navegador.&#x20;

Em seguida, abra a[ bridge de Aptos da PancakeSwap](https://bridge.pancakeswap.finance/aptos)

2 - Primeiro, precisamos conectar nossa carteira BNB Smart Chain.

Clique em "Conectar" e escolha a carteira de sua preferência na seção "EVM". Em seguida, confirme e aprove no pop-up da sua carteira. (Até o momento, apenas a MetaMask é suportada. O suporte para mais carteiras estará disponível em breve)

![](<../../.gitbook/assets/image (7) (1) (1).png>)

3 - Então, precisamos conectar nossa carteira Aptos.&#x20;

No modal wallet connect, escolha a carteira de sua preferência na seção "Aptos". Em seguida, confirme e aprove no pop-up da sua carteira.

![](<../../.gitbook/assets/image (8) (1).png>)

4 - Clique no "v" no campo de seleção de token e escolha "CAKE".

![](<../../.gitbook/assets/image (10).png>)

5 - Informe o número de CAKE que deseja fazer a ponte para Aptos.

![](<../../.gitbook/assets/image (9) (4).png>)

6 - Se sua carteira Aptos foi criada recentemente e não possui saldo em APT (Aptos Coin), recomendamos manter a opção "gás no destino" como padrão. A ponte depositará uma pequena quantia de APT em sua carteira, não apenas para ajudá-lo a iniciar sua jornada no Aptos, mas você também precisará de APT para abastecer para se registrar e reivindicar seu CAKE na bridge.&#x20;

A alteração dessa opção pode causar falha na ponte.

![](<../../.gitbook/assets/image (6) (5).png>)

7 - Clique em "Transferir" e aprove as transações no pop-up da sua carteira.&#x20;

Observe que, dependendo da condição de sua carteira BNB Smart Chain e carteira Aptos. Pode ser necessário aprovar várias confirmações de carteira. Por exemplo, se você estiver conectando CAKE a Aptos pela primeira vez, precisará:&#x20;

* Aprovar os gastos do CAKE no contrato da bridge (vindo de sua carteira BNB Smart Chain)&#x20;
* Registrar o CAKE (vindo de sua carteira Aptos)&#x20;

Para mais detalhes, por favor, confira [esta parte](entre-evm-e-aptos.md#bridging-cake-to-aptos-for-the-first-time).



8 - Sente-se e relaxe. Deve levar apenas alguns minutos. Assim que a ponte estiver concluída, o CAKE será depositado em sua carteira Aptos. Você pode acompanhar o progresso pela barra de progresso.

![](<../../.gitbook/assets/image (5) (3).png>)

## Fazendo bridge de CAKE para Aptos pela primeira vez <a href="#bridging-cake-to-aptos-for-the-first-time" id="bridging-cake-to-aptos-for-the-first-time"></a>

Fazer a ponte entre as carteiras CAKE e Aptos requer transações de registro e reivindicação. Isso é feito para aumentar a segurança do usuário e é exclusivo da Aptos.&#x20;

### Se você já possui APT (Aptos Coin) em sua carteira.&#x20;

Nesse cenário, você será solicitado a registrar o CAKE em sua carteira Aptos, caso ainda não tenha sido registrado. Você não será obrigado a enviar uma transação de reivindicação adicional neste cenário.&#x20;

### Se você não tiver APT (Aptos Coin) em sua carteira.&#x20;

Você só terá que reivindicar seu CAKE quando a transação for concluída. Você receberá tokens APT (para taxas de gás) na carteira de destino para pagar o custo de reivindicar seus ativos. Este APT é pago pela sua carteira de origem e é transferido para o destino.&#x20;

Lembre-se de que esses requisitos de registro e reivindicação só se aplicam quando você interage com um token pela primeira vez. As transferências subsequentes do mesmo token não exigirão essas transações.&#x20;

## Ponte de CAKE da Aptos para BNB Smart Chain&#x20;

1 - Certifique-se de que sua carteira suporta tanto o BNB Smart Chain quanto o Aptos Mainnet. Ou você tem ambas as carteiras instaladas em seu navegador.&#x20;

Então abra a página da [PancakeSwap Aptos Bridge](https://bridge.pancakeswap.finance/aptos)

2 - Primeiro, precisamos conectar nossa carteira BNB Smart Chain.

Clique em "Conectar" e escolha a carteira de sua preferência na seção "EVM". Em seguida, confirme e aprove no pop-up da sua carteira. (Até o momento, apenas a MetaMask é suportada. O suporte para mais carteiras estará disponível em breve)

![](<../../.gitbook/assets/image (11) (4).png>)

3 - Então, precisamos conectar nossa carteira Aptos.&#x20;

No modal da conexão da carteira, escolha a carteira de sua preferência na seção "Aptos". Em seguida, confirme e aprove no pop-up da sua carteira.

![](<../../.gitbook/assets/image (1) (5).png>)

4 -Clique no "v" no campo de seleção de token e escolha "CAKE". Em seguida, clique no botão de seta dupla no meio da página para inverter a direção da ponte.&#x20;

Verifique se a rede "Aptos" está no campo superior.

![](<../../.gitbook/assets/image (11) (1).png>)

5 - Insira o número de CAKE que você deseja conectar à BNB Smart Chain.

![](<../../.gitbook/assets/image (2) (1) (2).png>)

6 - Se sua carteira BNB Smart Chain foi criada recentemente e não possui saldo de BNB (gas token). Recomendamos manter a opção "gás no destino" como padrão. A ponte depositará uma pequena quantia de BNB em sua carteira. Isso ajudará você a iniciar sua jornada na BNB Smart Chain e explorar o vívido ecossistema PancakeSwap.

7 - Clique em "Transferir" e aprove as transações no pop-up da sua carteira.

8 - Sente-se e relaxe. Deve levar apenas alguns minutos. Assim que a ponte estiver concluída, o CAKE será depositado em sua carteira BNB Smart Chain. Você pode acompanhar o progresso pela barra de progresso.

