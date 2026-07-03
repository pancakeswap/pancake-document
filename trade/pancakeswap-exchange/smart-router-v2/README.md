---
hidden: true
---

# Smart Router (V2)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

O Smart Router do PancakeSwap é um algoritmo de roteamento que conecta o AMM e o StableSwap (BNB Chain), e o AMM e os formadores de mercado (Ethereum), para fornecer melhor Liquidez e preços. Ele usa um algoritmo de roteamento inteligente de ordens que executa negociações em múltiplos pools para encontrar o melhor preço para os traders. Para mais informações sobre StableSwap, [clique aqui](/broken/pages/nNPogTZMxocdyFIBYbkE) e para a integração com formadores de mercado, [clique aqui](../market-maker-integration.md).

A equipe irá gradualmente lançar pares StableSwap para testar e melhorar ainda mais o produto.

## Por que devo usar o Smart Router para meus Swaps AMM?&#x20;

* Troque suas stablecoins ou outros pares com preços de ativos semelhantes de forma mais eficiente com os mesmos passos de negociação.
* Faça Swap com formadores de mercado, que podem oferecer melhor execução nas negociações do que o AMM normal do PancakeSwap.
* Com a função StableSwap, o Slippage de negociação é menor do que no AMM normal.
* As taxas de negociação do StableSwap são menores em comparação com o AMM normal.

## Em Desenvolvimento&#x20;

* Interface aprimorada para saídas.
* Rotas divididas para negociações mais eficientes. Por exemplo, o roteador envia 50% do par para uma rota diferente para economizar taxas dependendo do tamanho da negociação e da Liquidez.&#x20;
