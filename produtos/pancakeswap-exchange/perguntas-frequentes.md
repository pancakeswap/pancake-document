# Perguntas Frequentes

## Swap

### O que há de novo na Exchange V3? <a href="#whats-new-in-exchange-v3" id="whats-new-in-exchange-v3"></a>

* Liquidez concentrada - a liquidez estará concentrada na faixa(range) de preço mais ativamente negociada, o que significa:
  * Menor derrapagem de negociação para traders
  * Potencialmente mais recompensas de taxa de LP para fornecedores de liquidez
* Uma estrutura flexível de taxas de negociação - Os provedores de liquidez podem escolher entre vários níveis de taxas de negociação ao criar pares de liquidez ou fornecer liquidez&#x20;
* Faixa de preço personalizável - Os provedores de liquidez também podem escolher em quais faixas de preço desejam fornecer liquidez&#x20;
* Posições de liquidez não-fungíveis - Cada posição de liquidez terá seu próprio ID exclusivo correspondente às suas configurações (como faixa de preço). Portanto, você poderá criar e manter várias posições com o mesmo par de negociação, mas com diferentes configurações e quantidade de liquidez&#x20;
* Compatível com versões anteriores - aExchange v3 também utilizará os pares de liquidez de swap legados v2 e stable swap para sempre fornecer a melhor rota de negociação&#x20;
* Ordem-limite integrada - Os usuários profissionais podem utilizar a nova faixa de preço personalizável no provisionamento de liquidez para criar efetivamente uma ordem de limite que converterá todos os tokens para o desejado quando o preço atingir a meta

### Posso adicinar meu próprio token na Exchange V3? <a href="#can-i-add-my-own-tokens-to-exchange-v3" id="can-i-add-my-own-tokens-to-exchange-v3"></a>

Todos podem criar pools de liquidez depositando liquidez na V3. No entanto, os seguintes tokens **NÃO** são suportados no momento:&#x20;

* Tokens com taxa na transferência&#x20;
* Tokens com rebase&#x20;

Para esses tokens, **NÃO** adicione liquidez na Exchange V3. Seus ativos podem ficar presos na posição de liquidez.

### Por que minha transação não vai?  <a href="#how-come-my-transaction-wont-go-through" id="how-come-my-transaction-wont-go-through"></a>

A PancakeSwap é um aplicativo DeFi que interage com a carteira para concluir transações on-chain de swap, criação de LPs, stake em farms e pools, etc.&#x20;

**Taxas de gás**&#x20;

Se sua ação de swap ainda não for concluída e estiver exibindo um erro para você revisar o deslizamento (slippage) - verifique se os tokens que você está tentando trocar **têm alguma taxa embutida e restrições nas transações.**&#x20;

Não é incomum que os tokens da BNB Smart Chain incluam uma taxa de transação em seus contratos, geralmente essas taxas poderiam ser usadas para queimar, financiar um tesouro de um projeto de lançamento justo - por exemplo, [o token APX tem uma taxa de 1%](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) sobre cada transação para enviar para um endereço de queima, de modo que mais transações significassem mais queima, agregando valor aos holders de token APX.&#x20;

Com a taxa de transação, seja ela inclusiva (uma parte do valor do swap é enviada para outro lugar além do seu endereço, de modo que a saída seja menor do que o esperado para a entrada estimada) ou exclusiva (exigindo uma transferência adicional do seu endereço para enviar tokens extras para que a entrada seja maior do que o esperado para a saída estimada), isso afeta o valor de entrada e saída que você concorda para assinar a transação. Em muitos casos, a transação não consegue cumprir os requisitos de entrada e saída por causa da taxa.

**Fazendo Swap com Taxas de Transação**

Antes de fazer swaap de quaisquer tokens, certifique-se de ter visitado o site deles para entender se eles têm um mecanismo de taxa de transação (ou _imposto_ como muitos projetos o chamam). Se houver, certifique-se de definir uma derrapagem(slippage) suficiente para acomodar a taxa de transação - por exemplo, se houver uma taxa de transação de 5%, sua derrapagem terá que ser definida em pelo menos 5% mais a derrapagem normal de negociação, dependendo do valor da negociação e da liquidez do token, digamos 5,5%-6%.&#x20;

Em alguns casos extremos, incluindo alguns golpes, alguns tokens ainda bloqueiam a maioria ou todas as transferências onchain, ou permitem apenas a venda de determinados endereços; nesse caso, é impossível fazer swap do token com sucesso. Aprenda sobre o token que você está tentando trocar e esteja ciente de quaisquer taxas e restrições!

### A nova interface de Swap usa a liquidez da v2 ou  do StableSwap? <a href="#does-the-new-swap-interface-use-v2-or-stable-swap-liquidity" id="does-the-new-swap-interface-use-v2-or-stable-swap-liquidity"></a>

Sim. O novo Swap v3 usa a liquidez da PancakeSwap v3, v2 e StableSwap para obter a melhor rota de negociação.

#### O que é divisão de roteamento?

No Swap v3, sua negociação pode ser dividida em várias rotas para executar sua negociação com a melhor taxa.&#x20;

Para ver mais detalhes de como sua negociação é roteada, toque no botão “v” na seção “Rota” para expandir e visualizar os detalhes. Saiba mais [aqui](taxas-e-roteamento.md).

#### Como personalizar ou desabilitar certas fontes de liquidez? <a href="#how-to-customise-or-disable-certain-liquidity-sources" id="how-to-customise-or-disable-certain-liquidity-sources"></a>

O novo Swap v3 usa a liquidez da PancakeSwap v3, v2 e StableSwap para obter a melhor rota de negociação. No entanto, você pode personalizar ou desabilitar certas fontes de liquidez se não quiser que sua negociação passe por elas.&#x20;

Ao visualizar uma rota de trade, clique no botão “Personalizar roteamento”. Ou clique no botão de engrenagem ⚙️ no canto superior direito da interface do Swap e escolha “Personalizar roteamento”.&#x20;

No pop-up “Personalizar roteamento”, você pode escolher qual fonte de liquidez deseja utilizar. Ou desabilite completamente o multihops.&#x20;

Observe: desabilitar o multihops pode levar a um aumento da derrapagem ou a uma taxa de negociação pior em pares de negociação específicos. Prossiga com cuidado.

Saiba mais [aqui](taxas-e-roteamento.md).

## Liquidez

### O que são níveis de taxas e como escolher o correto? <a href="#what-are-fee-tiers-and-how-to-pick-the-correct-one" id="what-are-fee-tiers-and-how-to-pick-the-correct-one"></a>

No Exchange v3, ao fornecer liquidez, você pode escolher entre várias taxas de negociação diferentes (0,01%, 0,05%, 0,25% e 0,1%) para o mesmo par de tokens.&#x20;

Por exemplo, para CAKE-BNB, pode haver um par de 0,25%, o que significa que uma taxa de negociação de 0,25% está em vigor para cada negociação. No entanto, alguns provedores de liquidez podem optar por fornecer liquidez a um par de negociação CAKE-BNB com uma taxa de taxa de 0,05%, oferece uma cotação melhor e atrai mais volume de negociação.&#x20;

Não há uma resposta “correta” para qual configuração de taxa de negociação escolher. Depende dos tokens dentro do par de negociação. Normalmente, os tokens voláteis devem ter uma taxa de negociação mais alta para compensar melhor a perda impermanente trazida pela volatilidade. Por outro lado, tokens como moedas estáveis têm movimentos de preços menores e perdas impermanentes menores, portanto, sua taxa de negociação deve ser menor.&#x20;

Ao selecionar um par de tokens, a interface “Adicionar liquidez” escolherá automaticamente o nível de taxa mais popular para você.

### Por que dois dos meus tokens de depósito não são iguais em valor em USD? <a href="#why-two-of-my-deposit-tokens-are-not-equal-in-usd-value" id="why-two-of-my-deposit-tokens-are-not-equal-in-usd-value"></a>

Na Exchange V3, os ativos subjacentes em uma posição de liquidez nem sempre terão um valor igual em USD. Isso dependerá das configurações de faixa(range) de preço de uma posição e do preço atual do par.&#x20;

Na verdade. Se sua posição sair do intervalo, todos os tokens serão convertidos em um único ativo. Além disso, você pode fornecer liquidez a uma faixa de preço que não cobre o preço atual e depositar apenas um único ativo. Continue lendo para saber mais ⬇️

### O que acontece se minha posição de liquidez sair da faixa(range)? <a href="#what-happens-if-my-liquidity-position-goes-out-of-range" id="what-happens-if-my-liquidity-position-goes-out-of-range"></a>

Você não ganhará nenhuma recompensa de taxa de negociação se o preço atual sair da faixa de preço definida em sua posição.

Além disso, todos os tokens serão convertidos em um único ativo, dependendo da direção da condição do preço.&#x20;

Por exemplo, se uma posição de CAKE/BUSD for configurada com uma faixa de preço de 3 BUSD por CAKE a 5 BUSD por CAKE. Todos os ativos na posição serão convertidos para BUSD se o preço do CAKE for maior ou igual a 5 BUSD por CAKE, e vice-versa.&#x20;

Observe que, se o preço voltar ao intervalo, você começará a receber recompensas de taxas de negociação novamente. Nenhuma ação adicional é necessária.

### É melhor sempre fornecer liquidez em um faixa menor? <a href="#is-it-better-to-always-provide-liquidity-with-a-smaller-range" id="is-it-better-to-always-provide-liquidity-with-a-smaller-range"></a>

Fornecer liquidez em uma faixa de preço menor ajudará a concentrar sua liquidez em uma faixa de preço específica, aumentando suas ações relativas novamente a liquidez total dentro da faixa de preço, potencialmente ganhando mais recompensas de taxa de negociação.&#x20;

No entanto, tenha em mente que apenas posições de liquidez ativas ganharão recompensas de taxas de negociação dos trades. Isso significa que você só ganhará recompensas quando o preço de negociação atual estiver dentro da faixa de preço definida na posição de liquidez.

#### Existem maneiras de ajustar automaticamente minha posição para que ela esteja sempre dentro da faixa e ganhando recompensas de taxas? <a href="#are-there-any-ways-to-automatically-adjust-my-position-so-it-is-always-in-range-and-earning-fee-rewa" id="are-there-any-ways-to-automatically-adjust-my-position-so-it-is-always-in-range-and-earning-fee-rewa"></a>

O recurso de gerenciamento automático de posição está chegando em breve à PancakeSwap v3 com depósito de liquidez com um clique (Zap!). Fique ligado para mais detalhes.

### Qual é distribuição detalhada da taxa de negociação na Exchange v3? <a href="#what-will-be-the-trading-fee-breakdown-for-v3-exchange" id="what-will-be-the-trading-fee-breakdown-for-v3-exchange"></a>

| Text                   | 0,01% | 0,05% | 0,25% | 1%  |
| ---------------------- | ----- | ----- | ----- | --- |
| Fornecedor de Liquidez | 67%   | 66%   | 68%   | 68% |
| Queima de CAKE         | 10%   | 10%   | 23%   | 23% |
| Tesouro                | 23%   | 24%   | 9%    | 9%  |

### As recompensas de taxa de LP são reinvestidas automaticamente como na Exchange v2? <a href="#are-lp-fee-rewards-automatically-compounded-like-exchange-v2" id="are-lp-fee-rewards-automatically-compounded-like-exchange-v2"></a>

Não

Na Exchange v3, você precisará reivindicar as recompensas de taxas de negociação manualmente. Você pode fazer isso na página de detalhes da posição. Você pode encontrar todas as suas posições de liquidez v3 na página de liquidez.

### O que afeta o APR do LP?

Na Exchange v3, o APR de recompensa de taxa de LP pode variar entre as posições de liquidez. É baseado nos seguintes fatores:

* Volume de Trade\
  \-mais volume gera mais recompensas de taxas&#x20;
* Nível de taxa de par de liquidez\
  \-nível de taxa mais alto gera mais recompensas de taxas de negociações individuais&#x20;
* O número de tokens depositados\
  \-mais token na posição se traduz em uma participação relativa maior em relação à liquidez ativa total, que obtém mais recompensas de taxas de negociação dos trades&#x20;
* A faixa de preço selecionada\
  \-uma faixa de preço menor permite uma concentração maior para a mesma quantidade de token depositado, o que se traduz em uma participação relativa maior em relação à liquidez ativa total e obtém mais recompensas de taxas de negociação dos trades&#x20;
* A quantidade de liquidez atualmente ativa\
  \-se houver mais usuários que depositam e concentram sua liquidez com o mesmo intervalo que você, você ganhará menos taxa de negociação devido a uma participação relativa menor em relação ao total&#x20;
* Se a posição de liquidez está ativa\
  \-apenas posições de liquidez ativas ganharão recompensas de taxas de negociação

### Posso fornecer liquidez v2? <a href="#can-i-provide-v2-liquidity" id="can-i-provide-v2-liquidity"></a>

Fornecer liquidez v2 não é mais aconselhável. Recomendamos usar a liquidez v3 para aproveitar os novos recursos para melhorar a eficiência.&#x20;

Se você deseja prosseguir com a adição de liquidez v2:&#x20;

* Se o par de tokens não tiver uma pool v3 ou tiver mais liquidez na v2 do que a maior pool na v3. Um “Adicionar Liquidez V2” aparecerá. Basta clicar para alternar para a adição de liquidez v2&#x20;
* Como alternativa, use `/v2` no URL para sempre usar o fornecimento de liquidez v2

### Como gerenciar LP de stable e LP v2 legado? <a href="#how-to-manage-stable-lp-and-legacy-v2-lp" id="how-to-manage-stable-lp-and-legacy-v2-lp"></a>

Você pode gerenciá-los normalmente acessando a p\[agina de [Liquidez](https://pancakeswap.finance/liquidity).
