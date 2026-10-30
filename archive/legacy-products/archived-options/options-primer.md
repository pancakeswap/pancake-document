# Introdução às Opções



{% hint style="danger" %}
\[ARQUIVADO] Opções – A partir de 11 de março de 2025\
Se você ainda tem liquidez para sacar, faça isso imediatamente acessando https://www.stryke.xyz/en/trade.
{% endhint %}



## O que são Opções?

Opções são contratos de derivativos que dão ao comprador o direito, mas não a obrigação, de comprar (opção de compra, ou call) ou vender (opção de venda, ou put) um ativo subjacente a um preço predeterminado (strike price) dentro de um período especificado (data de vencimento).

## Tipos de Opções

### Opções de Compra (Call)

Uma opção de compra dá ao titular o direito de comprar o ativo subjacente ao strike price acordado na data de vencimento ou antes dela. Os traders compram opções de compra quando esperam que o preço do ativo subjacente suba. Isso permite se beneficiar de uma possível valorização sem precisar possuir o ativo subjacente diretamente.

> Um trader compra uma opção de compra de Bitcoin com strike price de $50.000 vencendo em um mês. Se o preço do Bitcoin subir acima de $50.000 nesse mês, o investidor pode exercer a opção para comprar Bitcoin a $50.000, potencialmente lucrando com a diferença de preço.

### Opções de Venda (Put)

Uma opção de venda dá ao titular o direito de vender o ativo subjacente ao strike price acordado na data de vencimento ou antes dela. Os traders compram opções de venda quando esperam que o preço do ativo subjacente caia. Isso permite lucrar com possíveis quedas de preço sem precisar fazer uma venda a descoberto do ativo subjacente. Normalmente, as opções de venda também são usadas para proteção (hedge) contra riscos de queda nas carteiras de investimento.

> Um trader compra uma opção de venda de Ethereum com strike price de $3.000 vencendo em duas semanas. Se o preço do Ethereum cair abaixo de $3.000 nesse período, o trader pode exercer a opção para vender Ethereum a $3.000, mitigando assim possíveis perdas.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Posições em Opções

Para cada tipo de opção, existem duas posições possíveis:

### **Long Option (Comprador da Opção)**&#x20;

Esta posição envolve pagar um prêmio antecipado para adquirir a opção. Se a opção terminar com lucro, o titular recebe uma liquidação.

### **Short Option (Lançador/Vendedor da Opção)**

Nesta posição, o vendedor recebe um prêmio antecipado por emitir a opção. No entanto, se a opção terminar com lucro (para o comprador; com base no preço do ativo subjacente, no strike price e no tipo da opção), o vendedor é obrigado a pagar uma liquidação.

## Opções Americanas vs. Europeias

* **Opções Americanas:** Podem ser exercidas a qualquer momento antes da data de vencimento. Essa flexibilidade as torna mais valiosas do que as opções europeias.
* **Opções Europeias:** Só podem ser exercidas na data de vencimento. Geralmente são mais baratas do que as opções americanas por causa da falta de flexibilidade.

## Quando usar Opções?

Aqui estão alguns exemplos de casos de uso:

1. **Especulação:** Um investidor acredita que o preço do Bitcoin vai subir no próximo mês. Ele compra opções de compra de Bitcoin para lucrar com a alta esperada.
2. **Hedge:** Um validador de criptomoedas quer se proteger contra possíveis quedas no preço do Ethereum. Ele compra opções de venda de Ethereum para se proteger contra perdas se o preço cair abaixo de um determinado nível.
3. **Geração de Renda:** Um investidor de cripto que possui uma grande quantidade de Ether decide lançar opções de compra sobre suas posições, ganhando prêmios e ainda participando de possíveis altas de preço.

## Precificação de Opções

A precificação de opções é complexa e envolve vários fatores, sendo o modelo Black-Scholes o mais usado.&#x20;

Os principais fatores que influenciam a precificação de opções incluem:

* **Preço do Ativo Subjacente:** O preço atual de mercado do ativo subjacente.
* **Strike Price:** O preço pelo qual o titular da opção pode comprar ou vender o ativo subjacente.
* **Volatilidade:** O grau de flutuação de preço do ativo subjacente.&#x20;
* **Tempo até o Vencimento:** O tempo restante até a opção vencer.
* **Taxas de Juros:** A taxa de retorno livre de risco.

A precificação de opções determina o prêmio/taxa que um lançador recebe quando um trader de opções compra a sua opção. Os lançadores de opções estão expostos ao risco de pagar a liquidação se suas opções vencerem In-The-Money ou ITM (com lucro para o comprador). Por isso, os prêmios que eles ganham dos compradores devem refletir de forma justa a probabilidade de um evento ITM.

Os prêmios das opções CLAMM da PancakeSwap são derivados do modelo Black-Scholes com as seguintes premissas:

* A taxa livre de risco é assumida como zero.
* A volatilidade é baseada na volatilidade histórica de 30 dias do ativo subjacente \[usada como proxy da volatilidade implícita (IV)].

Algumas exceções incluem:

* A IV de $ETH e $BTC é obtida diretamente da Deribit se os strike prices coincidirem. Se não coincidirem, os strikes superior e inferior mais próximos da Deribit são ponderados com base no grau de deslocamento para definir a IV.
* $ARB usa volatilidade histórica de 30 dias baseada em beta, calculando o strike price efetivo do ativo base em relação ao $ETH para extrapolar a IV, que é multiplicada pelo beta do ativo base em relação ao $ETH

Ativos com alta volatilidade têm um prêmio mais caro do que ativos com menos volatilidade, pois há um risco maior para os lançadores de a opção vencer ITM.

## Liquidação de Opções

### Condições de Liquidação

* A liquidação é determinada com base no moneyness da opção no vencimento.
* A liquidação é calculada apenas se a opção estiver In-The-Money (ITM) no momento do exercício.

### Condições de ITM

* **Opção de Compra (Call):** Se o Preço à Vista na Liquidação > Strike Price
* **Opção de Venda (Put):** Se o Preço à Vista na Liquidação < Strike Price

### Cálculo da Liquidação

* **Opção de Compra (Call):** #Opções \* (Preço à Vista na Liquidação - Strike Price)
* **Opção de Venda (Put):** #Opções \* (Strike Price - Preço à Vista na Liquidação)

### Moneyness

Moneyness refere-se ao valor intrínseco de uma opção, determinado pela comparação entre seu strike price e seu preço à vista no momento da execução.

### Classificação

1. Out-of-The-Money (OTM):
   1. Uma opção é OTM se o preço à vista na liquidação for diferente do strike price e nenhum valor for trocado caso a liquidação ocorra imediatamente.
   2. Condições:
      1. Opção de Compra (Call): Preço à Vista < Strike Price
      2. Opção de Venda (Put): Preço à Vista > Strike Price

{% hint style="info" %}
Uma opção de compra de $ETH com strike price de $2.000 seria OTM se o preço à vista for $1.800 ($1.800 < $2.000, ou seja, OTM).
{% endhint %}

2. At-The-Money (ATM):
   1. Uma opção é ATM se o preço à vista na liquidação for igual ao strike price e nenhum valor for trocado caso a liquidação ocorra imediatamente.
   2. Condições: Tanto Opções de Compra quanto de Venda: Preço à Vista = Strike Price

{% hint style="info" %}
Tanto uma opção de compra quanto uma de venda de $ETH com strike price de $1.800 seriam ATM se o preço à vista também for $1.800 ($1.800 = $1.800, ou seja, ATM).
{% endhint %}

3. In-The-Money (ITM):
   1. Uma opção é ITM se o preço à vista na liquidação for diferente do strike price e houver valor a ser trocado caso a liquidação ocorresse imediatamente.
   2. Condições:
      1. Opção de Compra (Call): Preço à Vista > Strike Price
      2. Opção de Venda (Put): Preço à Vista < Strike Price

{% hint style="info" %}
Uma opção de compra de $ETH com strike price de $1.600 seria ITM se o preço à vista for $1.800 ($1.800 > $1.600, ou seja, ITM).
{% endhint %}

A liquidação recebida pelo comprador da opção é igual ao colateral perdido pelo lançador da opção. A liquidação não inclui o prêmio das opções pago, que é considerado no cálculo de lucros ou perdas dos compradores e lançadores de opções.
