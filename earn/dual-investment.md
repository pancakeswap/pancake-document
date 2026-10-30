# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

O Dual Investment permite que você comprometa fundos a um preço-alvo e ganhe uma recompensa fixa, independentemente de como o mercado se comporte. Escolha um ativo, decida se quer **Buy Low** ou **Sell High** e selecione um preço-alvo e uma data de liquidação. Na liquidação, você recebe seu principal mais a recompensa, seja no ativo que depositou ou convertido ao seu preço-alvo.

O Dual Investment está disponível na BNB Chain com **BTCB** e **BNB**, pareados com **USDT**.

{% hint style="info" %}
O Dual Investment não é um produto de poupança. Dependendo do preço de liquidação, seus fundos podem ser convertidos em outro ativo ao seu preço-alvo, e esse ativo pode valer menos do que o que você depositou.
{% endhint %}

***

## O que é o Dual Investment?

#### **Dois resultados, uma recompensa fixa**

Cada produto Dual Investment tem um preço-alvo e uma data de liquidação. Ao se inscrever, sua recompensa fica travada no APR exibido. Na liquidação, o preço de mercado decide qual dos dois resultados você recebe:

* **O preço não atinge o seu alvo.** Você recebe de volta seu ativo original mais a recompensa.
* **O preço atinge o seu alvo.** Seu principal e sua recompensa são convertidos no outro ativo ao seu preço-alvo.

Você ganha a recompensa nos dois casos. A única coisa que muda é qual ativo você recebe.

#### **Buy Low**

Use Buy Low quando você ficaria feliz em comprar BTCB ou BNB abaixo do preço de hoje. Você deposita **USDT** e escolhe um preço-alvo abaixo do preço atual.

| Preço de liquidação        | Você recebe                                                     |
| ----------------------- | --------------------------------------------------------------- |
| Igual ou acima do seu alvo | USDT (principal + recompensa)                                |
| Abaixo do seu alvo       | BTCB ou BNB, comprado ao seu preço-alvo junto com sua recompensa |

#### **Sell High**

Use Sell High quando você ficaria feliz em vender BTCB ou BNB acima do preço de hoje. Você deposita **BTCB ou BNB** e escolhe um preço-alvo acima do preço atual.

| Preço de liquidação        | Você recebe                                            |
| ----------------------- | ------------------------------------------------------ |
| Igual ou abaixo do seu alvo | BTCB ou BNB (principal + recompensa)               |
| Acima do seu alvo       | USDT, vendido ao seu preço-alvo junto com sua recompensa |

#### **Como funciona o APR**

O APR depende de quão perto o preço-alvo está do preço atual e de quanto tempo o produto dura. Alvos mais próximos do preço atual pagam um APR maior, porque é mais provável que sejam convertidos. Alvos mais distantes pagam menos, mas têm mais chance de devolver seu ativo original.

Sua recompensa é calculada assim:

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Exemplo: Buy Low**

O BTCB está sendo negociado a US$ 83.467. Você se inscreve com 1.000 USDT em um produto Buy Low de 1 dia, com alvo de US$ 82.000 e APR de 14,68%. Sua recompensa é de cerca de 0,40 USDT.

| Preço de liquidação | Você recebe                           |
| ---------------- | ------------------------------------- |
| US$ 82.000 ou mais | 1.000,40 USDT                       |
| Abaixo de US$ 82.000    | 0,0122 BTCB (1.000,40 USDT ÷ US$ 82.000) |

Se o BTCB for liquidado a US$ 78.000, você ainda compra a US$ 82.000. Você teria 0,0122 BTCB, que valem cerca de 951,60 USDT, menos do que você depositou.

#### **Exemplo: Sell High**

O BTCB está sendo negociado a US$ 83.467. Você se inscreve com 0,01 BTCB em um produto Sell High de 1 dia, com alvo de US$ 84.500 e APR de 89,28%. Sua recompensa é de cerca de 0,0000245 BTCB.

| Preço de liquidação | Você recebe                            |
| ---------------- | -------------------------------------- |
| US$ 84.500 ou menos | 0,0100245 BTCB                      |
| Acima de US$ 84.500    | 847,07 USDT (0,0100245 BTCB × US$ 84.500) |

Se o BTCB for liquidado a US$ 88.000, você ainda vende a US$ 84.500. Você receberia 847,07 USDT por um BTCB que valeria cerca de 882 USDT.

#### **Quem está do outro lado?**

Cada produto é cotado por um market maker, que assume o outro lado da sua posição. Os market makers depositam uma garantia que assegura o seu pagamento. Se um market maker entrar em default, sua reivindicação é coberta pela garantia dele.

***

## Como usar o Dual Investment

#### **Acesse a página do Dual Investment**

Vá para [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) ou clique em **Dual Investment** na barra de navegação principal da PancakeSwap.

#### **1. Escolha um ativo-alvo**

Selecione **BTCB** ou **BNB**. Cada card mostra o preço atual e a faixa de APR disponível em todos os produtos daquele ativo.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. Escolha uma direção**

Selecione **Buy Low** para depositar USDT e comprar o ativo a um preço menor, ou **Sell High** para depositar o ativo e vendê-lo a um preço maior.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. Escolha uma data de liquidação e um preço-alvo**

Use os filtros de duração (**1 Day**, **< 3 Days**, **< 7 Days** e períodos mais longos) para refinar a lista. Os produtos são agrupados por data de liquidação. Cada linha mostra o preço-alvo, sua distância do preço atual e o APR.

A contagem regressiva ao lado de cada data de liquidação mostra quanto tempo você ainda tem para se inscrever. As inscrições são encerradas antes da liquidação.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. Informe o valor da inscrição**

Clique em **Subscribe** no alvo que você quer, depois informe um valor ou toque em **MAX**. Cada produto tem um mínimo e um máximo por inscrição, e uma capacidade total fixa. Quando um alvo é totalmente subscrito, ele não pode ser reaberto, então você precisará escolher outro preço-alvo.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. Revise e confirme**

Revise a direção, o preço-alvo, a data de liquidação e os dois resultados possíveis.&#x20;

A taxa é mantida por um curto período enquanto você confirma. Se ela expirar ou mudar, a página busca uma nova taxa e pede que você a aceite antes de continuar.

#### **6. Resgate seu pagamento**

Após a liquidação, clique em **Claim** em uma posição, ou em **Claim all** para resgatar todas as posições liquidadas de uma só vez. Seu pagamento é enviado para a sua carteira no ativo determinado pelo resultado da liquidação.

***

## FAQ do Dual Investment

#### **O que é o Dual Investment?**

O Dual Investment é um produto que permite comprometer fundos a um preço-alvo e ganhar uma recompensa fixa. Na liquidação, você recebe seu principal mais a recompensa, seja no ativo original ou convertido no outro ativo ao seu preço-alvo.

#### **Quais ativos são compatíveis?**

BTCB e BNB, pareados com USDT, na BNB Chain.

#### **Qual é a diferença entre Buy Low e Sell High?**

O Buy Low permite depositar USDT e comprar BTCB ou BNB a um preço-alvo abaixo do preço atual. O Sell High permite depositar BTCB ou BNB e vendê-lo a um preço-alvo acima do preço atual.

#### **Eu ganho a recompensa nos dois resultados?**

Sim. A recompensa é fixada quando você se inscreve e é paga nos dois resultados. Ela é paga junto com seu principal, em qualquer que seja o ativo que você receber na liquidação.

#### **Posso sacar antes da data de liquidação?**

Não. Depois de se inscrever, seus fundos ficam bloqueados até a liquidação e a inscrição não pode ser cancelada.

#### **Por que os APRs são diferentes entre os produtos?**

Alvos mais próximos do preço atual e datas de liquidação mais curtas geralmente pagam APRs maiores, porque têm maior chance de conversão. As taxas são cotadas em tempo real e podem mudar entre o momento em que você abre um produto e o momento em que confirma.

#### **Por que a taxa mudou enquanto eu me inscrevia?**

As taxas são cotadas em tempo real pelos market makers e só são mantidas por um curto período. Se a taxa expirar, mudar, ou se outro usuário preencher aquele preço primeiro, a página busca uma nova taxa e pede que você a aceite antes de continuar.

#### **Preciso resgatar meu pagamento?**

Sim. Após a liquidação, resgate seu pagamento em **Your Holdings**. Você pode resgatar as posições uma a uma ou usar **Claim all**.

#### **Quem assume o outro lado da minha posição?**

Os market makers cotam cada produto e assumem o outro lado da sua posição. Eles depositam uma garantia que assegura o seu pagamento e, se um market maker entrar em default, sua reivindicação é coberta por essa garantia.

#### **Quais taxas são cobradas?**

É gratuito.
