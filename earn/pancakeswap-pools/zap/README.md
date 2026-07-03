---
description: Adicionando liquidez com um clique
---

# Zap

### O que é o Zap <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

O Zap é um recurso que permite adicionar liquidez com facilidade. Com o Zap, você pode fornecer liquidez com qualquer token que tenha saldo, independentemente dos tokens exigidos no pool. Basta definir a faixa de preço, escolher o valor a fornecer e executar. Seus tokens serão automaticamente balanceados para formar a posição de liquidez, sendo negociados da forma mais eficiente, com o menor impacto de preço e Slippage.

### Redes Suportadas

* v3 - Todos os pools na BNB Chain, pools selecionados nas redes Ethereum e Arbitrum
* Infinity - Todos os pools CLAMM (sem Hooks) na BNB Chain

### Como Usar <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Por enquanto, o Zap suporta:

* 🆕 Qualquer token!
* Usando token único
* 🆕 Usando dois tokens
* 🆕 Ou... usando múltiplos tokens (sim, pode ser usado como coletor de dust)

#### Iniciar <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Para usar o Zap, basta ir para a página Adicionar Liquidez, selecionar o par de negociação para o qual deseja fornecer liquidez, o nível de taxa e a faixa de preço.

Em seguida, selecione a quantidade de tokens que deseja fornecer como liquidez.

A opção de Zap aparecerá automaticamente quando um ou mais tokens tiverem saldo insuficiente.

Clique no link para abrir o modal do Zap.

#### Iniciar Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

No novo modal "Zap in", você pode encontrar os seguintes campos:

1. O par de negociação para o qual você está fazendo Zap (fornecendo liquidez).
2. O(s) token(s) de depósito e o(s) valor(es) a depositar. Você pode adicionar ou remover tokens livremente para o Zap.
3. A faixa de preço da nova posição. Você também pode clicar nas setas para alternar entre diferentes exibições de preço.
4. Um detalhamento de como o recurso Zap tratará seus tokens de depósito.
5. Um resumo das estatísticas incluindo:
   1. Valor estimado em USD para a nova posição de liquidez.
   2. Quantidade estimada de tokens na nova posição de liquidez.
   3. Fundos sobrando estimados em USD após o Zap. Na maioria dos casos, deve ser 0. Se o pool de liquidez ou os tokens tiverem muito pouca liquidez, esse valor pode aumentar.
   4. O impacto de preço para os swaps e rebalanceamentos de tokens durante o Zap.
   5. O impacto de preço para a adição de liquidez e construção de posição.
   6. Taxa do Zap. Dependendo do par de liquidez, a taxa pode variar.

{% hint style="warning" %}
Observe que pode ser necessário reconfigurar o valor do Zap com base no saldo disponível. Se você não tiver saldo em um dos tokens, remova-os.
{% endhint %}

{% hint style="info" %}
Você pode notar que as configurações de "Add V3 Liquidity" são automaticamente transferidas para o modal do Zap, incluindo o valor do depósito e as configurações de faixa de preço.
{% endhint %}

#### Iniciando o Zap <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Por fim, clique em "Approve" e confirme no pop-up da carteira para a permissão de token.

Em seguida, clique em "Preview" para abrir o modal de confirmação final. Antes de prosseguir, revise todas as estatísticas e estimativas mostradas no modal de confirmação final. Especialmente os valores de impacto e Slippage máximo.

Por fim, clique em "Add Liquidity" e confirme no pop-up da sua carteira.

Após a transação ser confirmada, você verá sua nova posição na página "My Position".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Mais Configurações <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Se quiser personalizar ainda mais sua experiência de Zap, basta clicar no ícone de engrenagem no canto superior direito. Nas configurações, você pode configurar:

* O Slippage máximo durante o Zap.
* O prazo da transação.
* Se deseja usar a liquidez agregada do KyberSwap para realizar o rebalanceamento de tokens. Desative isso se quiser negociar apenas nos Pools PancakeSwap.
* O modo Degen pode ser usado para realizar Zaps com Slippage muito alto. Não recomendado para uso normal; use por sua conta e risco.

{% hint style="warning" %}
Observe que as configurações de Slippage e Prazo são independentes da página de Swap e Liquidez.
{% endhint %}

#### Zap com dois tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Agora você pode fazer Zap com dois tokens. Isso é útil quando seu saldo disponível não corresponde às configurações de preço e à quantidade e proporção de tokens exigida. Basta usar o Zap e a proporção será automaticamente rebalanceada.

#### Zap com muitos tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Sim, funciona como um coletor de tokens dust. É adequado para limpar pequenos saldos na sua carteira e colocá-los em uma posição para começar a ganhar com taxas de negociação.&#x20;
