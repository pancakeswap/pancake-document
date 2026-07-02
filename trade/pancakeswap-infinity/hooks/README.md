# Hooks

{% hint style="info" %}
Se você é um desenvolvedor ou está procurando documentação técnica detalhada sobre como desenvolver um hook, visite [aqui](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Os hooks são complementos poderosos que permitem que os desenvolvedores estendam e personalizem o comportamento dos pools de Liquidez no PancakeSwap Infinity. Pense neles como "plugins" ou "widgets" que adicionam novos recursos aos pools de Liquidez.

#### 🔍 O que são Hooks?

* Hooks são contratos inteligentes externos criados por qualquer pessoa — desenvolvedores, protocolos ou membros da comunidade — e anexados a pools de Liquidez para melhorar ou modificar seu comportamento.
* Cada pool pode ter apenas um hook anexado, mas um único hook pode atender a muitos pools.
* Os hooks podem executar código personalizado antes ou depois de ações-chave como:
  * Inicialização de um pool
  * Swap
  * Adição/remoção de Liquidez
  * Doação<br>

**⛓️ Como os Hooks funcionam:**

* Um hook é selecionado durante a criação do pool e não pode ser alterado posteriormente.
* Um contrato de hook é acionado em ações específicas (Swap, adição de Liquidez, etc.) e executa lógica antes ou depois dessas ações conforme definido no contrato.
* Por exemplo, um hook poderia:
  * Oferecer descontos de taxa de Swap para detentores de CAKE
  * Cobrar taxas personalizadas e distribuir recompensas
  * Habilitar nova lógica de Swap como StableSwaps ou ordens no estilo TWAMM<br>

#### ⚙️ Callbacks de Hook

Os hooks podem ser acionados durante dez momentos específicos. Os desenvolvedores podem escolher quais deles desejam implementar:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Isso permite implementar comportamento altamente personalizável e modular por meio de hooks.

#### 🔧 Dois Tipos de Hooks

**Tipo 1: Sem Autorização Necessária**

Esses hooks são executados automaticamente e não requerem permissão do usuário. Eles são acionados por ações como Swaps ou alterações de Liquidez.



Exemplos:

* Taxas Dinâmicas: Ajustam as taxas de Swap com base na volatilidade do mercado
* Reembolsos de Taxa: Concedem descontos aos usuários que detêm CAKE ou negociam grandes volumes



Exemplo de Fluxo (Desconto de Taxa com CAKE):

1. Um usuário inicia um Swap.
2. O hook verifica seu saldo de CAKE via callback `beforeSwap`.
3. Se o usuário detiver CAKE suficiente conforme os limites definidos, ele recebe um desconto de 50% nas taxas do pool.
4. O restante da transação prossegue normalmente.<br>

{% hint style="success" %}
Esses hooks não precisam de uma interface especial ou interação adicional. Os benefícios são aplicados automaticamente.
{% endhint %}

**Tipo 2: Autorização do Usuário Necessária**

Esses hooks precisam que os usuários interajam diretamente com eles, forneçam autorização e podem exigir a transferência de fundos, frequentemente para criar ou gerenciar posições.



Exemplos:

* Ordens Limitadas: Executam um Swap somente quando o preço alvo é atingido.
* TWAMM: Divide grandes ordens em partes menores para melhor execução.
* Gerenciamento Ativo de Liquidez: Gerencia automaticamente posições LP para retornos ideais.



Exemplo de Fluxo (Hook de Ordem Limitada):

1. O usuário interage diretamente com o contrato de hook (não com a interface de Swap usual).
2. Ele insere detalhes como preço limite, par de tokens e valor.
3. O hook emite um token de recibo representando a ordem.
4. Mais tarde, quando o preço do pool atinge o alvo, o hook executa a ordem usando afterSwap.
5. O usuário pode devolver o token de recibo para resgatar os ativos trocados.

{% hint style="info" %}
Esses hooks frequentemente precisam de uma interface personalizada e os usuários devem confiar e aprovar o contrato de hook para manter seus fundos.
{% endhint %}

#### 🚀 Casos de Uso e Inovação

Os hooks desbloqueiam possibilidades ilimitadas, incluindo:

* AMMs personalizados (por exemplo, curvas de stablecoin)
* Recompensas de mineração de Liquidez
* Estratégias de negociação automatizadas, gerenciamento de Liquidez
* Ordens limitadas on-chain, outros tipos de ordens
* Ajustes dinâmicos de precificação e taxas
* Estratégias LP de aumento de rendimento<br>

Com hooks, os desenvolvedores podem construir uma experiência DeFi completamente nova usando a infraestrutura existente do PancakeSwap Infinity — acelerando o desenvolvimento e reduzindo custos.
