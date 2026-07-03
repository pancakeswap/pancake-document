---
description: Faça Bridge de CAKE entre chains EVM e Aptos
---

# Como Fazer Bridge - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
O guia a seguir usa a BNB Chain como exemplo de uma chain EVM. O mesmo processo pode ser aplicado ao Ethereum.
{% endhint %}

## Fazer Bridge de CAKE da BNB Smart Chain para Aptos

1 - Certifique-se de que sua Carteira suporta tanto a BNB Smart Chain quanto a Aptos Mainnet. Ou que você tenha ambas as carteiras instaladas no seu navegador.

Em seguida, abra o [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Primeiro, precisamos conectar nossa Carteira da BNB Smart Chain.

Clique em "Conectar" e escolha a Carteira de sua preferência na seção "EVM". Em seguida, confirme e aprove no pop-up da sua Carteira.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Em seguida, precisamos conectar nossa Carteira Aptos.

No modal de conexão de Carteira, escolha a Carteira de sua preferência na seção "Aptos". Em seguida, confirme e aprove no pop-up da sua Carteira.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Clique no "v" no campo de seleção de token superior e escolha "CAKE".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Insira a quantidade de CAKE que deseja fazer bridge para Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Se sua Carteira Aptos foi criada recentemente e não tem nenhum saldo de APT (Aptos Coin). Recomendamos manter a opção "gas no destino" no seu padrão. O bridge depositará uma pequena quantidade de APT na sua Carteira, não apenas para ajudá-lo a iniciar sua jornada em Aptos, mas você também precisará de APT para gas ao registrar e reivindicar seu CAKE com bridge.

Alterar essa opção pode causar falha no bridging.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Clique em "Transferir" para iniciar a transação de bridging e confirme pelo pop-up de confirmação da Carteira.

Por favor, note que dependendo da condição da sua Carteira BNB Smart Chain e Carteira Aptos, você pode precisar aprovar **múltiplas** confirmações de Carteira. Por exemplo, se você estiver fazendo bridge de CAKE para Aptos pela primeira vez, você precisará:

* Aprovar o gasto de CAKE no contrato de bridging (vindo da sua Carteira BNB Smart Chain)
* Registrar CAKE (vindo da sua Carteira Aptos)

Para mais detalhes, confira [este detalhamento](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 - Relaxe. Deve levar apenas alguns minutos. Após a conclusão do bridging, o CAKE será depositado na sua Carteira Aptos. Você pode acompanhar o progresso pela barra de progresso.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Fazendo Bridge de CAKE para Aptos pela Primeira Vez

Fazer bridge de CAKE para carteiras Aptos requer transações de registro e reivindicação. Isso é feito para aumentar a segurança do usuário e é exclusivo do Aptos.

### **Se você já tem APT (Aptos Coin) na sua Carteira:**

Você será solicitado a registrar CAKE na sua Carteira Aptos se ainda não estiver registrado. Nenhuma transação adicional de reivindicação é necessária neste caso.

### **Se você não tem APT (Aptos Coin) na sua Carteira:**

Após a conclusão da transação de bridge, você precisará reivindicar manualmente seu CAKE. Para cobrir as taxas de gas da reivindicação, tokens APT serão enviados para sua Carteira Aptos a partir da sua Carteira de origem.

Essas etapas de registro e reivindicação se aplicam apenas na primeira vez que você interage com um token no Aptos. Transferências subsequentes do mesmo token não exigirão essas ações.

Antes de fazer bridge de CAKE para Aptos pela primeira vez, certifique-se de que seu endereço Aptos tenha APT suficiente para taxas de gas. Para mais detalhes, confira a explicação da Aptos aqui: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Fazer Bridge de CAKE de Aptos para BNB Smart Chain

1 - Certifique-se de que sua Carteira suporta tanto a BNB Smart Chain quanto a Aptos Mainnet. Ou que você tenha ambas as carteiras instaladas no seu navegador.

Em seguida, abra o [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Primeiro, precisamos conectar nossa Carteira da BNB Smart Chain.

Clique em "Conectar" e escolha a Carteira de sua preferência na seção "EVM". Em seguida, confirme e aprove no pop-up da sua Carteira.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Em seguida, precisamos conectar nossa Carteira Aptos.

No modal de conexão de Carteira, escolha a Carteira de sua preferência na seção "Aptos". Em seguida, confirme e aprove no pop-up da sua Carteira.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Clique no "v" no campo de seleção de token superior e escolha "CAKE". Em seguida, clique no botão de seta dupla no meio da página para inverter a direção do bridging.

Por favor, certifique-se de que a rede "Aptos" está no campo superior.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - Insira a quantidade de CAKE que deseja fazer bridge para BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - Se sua Carteira BNB Smart Chain foi criada recentemente e não tem nenhum saldo de BNB (token de gas). Recomendamos manter a opção "gas no destino" no seu padrão. O bridge depositará uma pequena quantidade de BNB na sua Carteira. Isso ajudará a iniciar sua jornada na BNB Smart Chain e explorar o vibrante ecossistema do PancakeSwap.

7 - Clique em "Transferir" e aprove as transações no pop-up da sua Carteira.

8 - Relaxe. Deve levar apenas alguns minutos. Após a conclusão do bridging, o CAKE será depositado na sua Carteira BNB Smart Chain. Você pode acompanhar o progresso pela barra de progresso.
