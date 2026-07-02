# Principais Recursos

### 1️⃣ Singleton

No PancakeSwap v3, cada Pool de Liquidez tinha seu próprio contrato, o que tornava a criação de pools e o Swap entre múltiplos pools mais caros.

O Infinity resolve isso implementando o modelo Singleton. Agora, todos os pools residem dentro de um único contrato chamado PoolManager. Essa mudança reduz os custos de gas para criação de pools em até 99% e torna os swaps multi-hop (swaps que passam por múltiplos pools) muito mais baratos ao evitar transferências desnecessárias de tokens.

#### ⚙️ **Como funciona:**

* Os dados de cada pool são armazenados em um contrato compartilhado usando um ID de pool único.
* Criar um novo pool agora é apenas uma atualização de estado, não uma implantação completa de contrato.
* Fazer Swap entre pools é mais rápido e usa menos gas.<br>

Essa abordagem Singleton, junto com outras otimizações como Flash Accounting e ERC-6909, ajuda a tornar o PancakeSwap Infinity uma das plataformas DEX mais eficientes em gas disponíveis hoje.

***

### ⚡️ Flash Accounting

O Flash Accounting é uma poderosa otimização no PancakeSwap Infinity que ajuda a reduzir as taxas de gas durante transações complexas como swaps multi-hop e alterações de Liquidez.

Em versões mais antigas (como v3), os tokens eram movimentados dentro e fora de cada pool durante cada etapa de uma transação. Isso levava a altos custos de gas, especialmente para swaps multi-hop.

Com o Flash Accounting, isso não é mais necessário. Em vez de mover tokens após cada etapa, o PancakeSwap Infinity rastreia todas as movimentações de tokens internamente e faz apenas uma transferência final ao término de toda a transação. Isso economiza muito gas.

#### ⚙️ **Como funciona:**

* Quando você interage com o Infinity (por exemplo, fazendo Swap ou adicionando Liquidez), o sistema calcula o saldo líquido de tokens que você deve ou recebe.
* Esses saldos líquidos de tokens são armazenados temporariamente usando Transient Storage, um novo recurso introduzido com a atualização Cancun do Ethereum (EIP-1153).
* O Transient Storage é mais barato do que o armazenamento tradicional porque dura apenas durante a transação — nenhuma gravação ou leitura permanente é necessária.

***

### 🪙 Suporte a Tokens Nativos

Com a introdução da arquitetura Singleton e do Flash Accounting, o PancakeSwap Infinity agora suporta tokens de gas nativos (por exemplo, BNB, ETH) diretamente em pools de Liquidez — sem mais necessidade de embrulhar e desembrulhar.

#### ✅ Destaques Principais

* **Pools de Tokens Nativos Diretos:** Agora você pode criar pools como ETH/USDC, BNB/CAKE sem precisar de WETH ou WBNB.
* **Eficiência de Gas:** Transferências de tokens nativos são \~50% mais baratas do que transferências de tokens ERC-20, resultando em menores custos de gas para Swaps e ações de Liquidez.<br>

**Anteriormente Removido, Agora Reabilitado:** O suporte a tokens nativos estava ausente em versões anteriores devido à complexidade de implementação e à fragmentação de Liquidez.

***

### 📈 Curvas de Precificação Personalizadas

O PancakeSwap Infinity dá aos desenvolvedores o poder de criar modelos de precificação personalizados para pools — indo além do modelo tradicional usado na maioria dos AMMs.

{% hint style="success" %}
**Os desenvolvedores podem construir comportamentos de Swap completamente novos e modelos de Liquidez adaptados a tipos de ativos ou estratégias de negociação específicas.**
{% endhint %}

#### 🔧 O que são Curvas de Precificação Personalizadas?

As curvas de precificação personalizadas permitem que os desenvolvedores:

* Contornem a lógica nativa do gerenciador de pools, criando pools com comportamentos de Swap definidos de forma personalizada.
* Alterem como os valores dos tokens são calculados para Swaps ou modificações de Liquidez.
* Incorporem mecânicas de taxa personalizadas, como:
  * Taxas de retirada de Liquidez
  * Reembolsos ou penalidades baseados em estratégia

Tudo isso é possível por meio de callbacks de hook antes/depois do Swap, que podem interceptar e modificar parâmetros de Swap dinamicamente.

#### 🛠 Exemplos de Casos de Uso

* **Curvas StableSwap:** Projete curvas mais planas em torno de uma proporção de preço 1:1, reduzindo o impacto de preço entre ativos como USDC e USDT.
* **RWAs:** Crie comportamentos personalizados para diferentes tipos de ativos com oferta dinâmica.
* **Taxas no Nível do Hook:** Cobre taxas únicas que diferem das taxas no nível do pool, como taxas de desenvolvedor.
* **Modelos de Risco Personalizados:** Ajuste a precificação para refletir volatilidade, dados de oráculo ou métricas externas.

{% hint style="info" %}
Em versões anteriores de AMM (por exemplo, PancakeSwap v2/v3), a lógica de precificação era codificada e rígida. A arquitetura do PancakeSwap Infinity desbloqueia a capacidade de construir pools mais eficientes em capital e mais personalizados.
{% endhint %}

#### 🔍 Flexibilidade para Desenvolvedores

* Os desenvolvedores podem implantar contratos de hook personalizados para substituir a lógica de precificação.
* Callbacks de hook como beforeSwap e afterSwap permitem controle total sobre como os deltas de tokens são calculados e aplicados.

***

### 🧮 ERC-6909: Contabilidade Eficiente de Múltiplos Tokens

O PancakeSwap Infinity adota o [ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), um padrão de token leve e eficiente em gas projetado para contabilidade interna de múltiplos tokens dentro de um único contrato. Ele substitui muitas operações tradicionais ERC-20 com primitivas de mint e burn — levando a significativas economias de gas e fluxos de transação simplificados.

#### ⚙️ Como funciona

Em vez de mover tokens para dentro e fora do protocolo a cada interação, os tokens ERC-6909 representam saldos internos:

* Mint: Quando os usuários depositam tokens ou realizam uma negociação, eles podem escolher receber tokens ERC-6909 como créditos.
* Burn: Posteriormente, em vez de transferir tokens ERC-20 novamente, os usuários podem simplesmente queimar esses tokens ERC-6909 para liquidar saldos ou financiar novas operações.

Esse modelo reduz drasticamente a necessidade de transferências externas de tokens, que normalmente incorrem em custos de gas mais altos e interagem com lógica de terceiros (por exemplo, verificações de lista negra da USDC).

#### 🪙 Benefícios do ERC-6909

<table><thead><tr><th width="262.9921875">Recurso</th><th width="497.7421875">Benefício</th></tr></thead><tbody><tr><td>✅ Créditos de Saldo Interno</td><td>Sem necessidade de transferir tokens repetidamente entre usuário e contrato</td></tr><tr><td>✅ Mint/Burn Eficiente em Gas</td><td>Sobrecarga constante independente do token, sem chamadas de contrato externo</td></tr><tr><td>✅ Mais Simples que ERC-1155</td><td>Código menor, sem callbacks, sem requisitos de transferência em lote</td></tr><tr><td>✅ Suporte a Múltiplos Tokens</td><td>Um único contrato pode rastrear múltiplos tipos de tokens com saldos isolados</td></tr><tr><td>✅ Integração Perfeita com PoolManager</td><td>Elimina aprovações e transferências redundantes de ERC-20</td></tr></tbody></table>

#### 🚀 Casos de Uso

* **Traders de alta frequência:** Evite transferências com alto custo de gas e interaja diretamente usando saldos internos.
* **Gerentes de Liquidez:** Abra e feche posições com mais eficiência sem movimentações excessivas de tokens.

#### 💡 Notas Importantes

* Os usuários optam pelo fluxo ERC-6909 quando não precisam liquidar imediatamente as transferências de tokens.
* Os saldos internos podem ser consolidados e liquidados de forma líquida posteriormente, dando aos usuários avançados maior controle e flexibilidade.

***

### 💸 Método Donate

O método `donate()` permite que os usuários incentivem diretamente os provedores de Liquidez dentro do intervalo em um pool doando tokens. Este método depende do sistema de contabilidade de taxas do pool para facilitar os pagamentos, garantindo que apenas os tokens do pool sejam suportados.

#### 🔹 Principais Recursos:

* **Pagamentos Diretos para LPs:** As doações são feitas diretamente aos provedores de Liquidez, recompensando aqueles que mantêm Liquidez dentro do intervalo ativo do pool.
* **Suporta Apenas Tokens do Pool:** O método `donate()` suporta apenas doações nos tokens do pool, pois aproveita o sistema de contabilidade de taxas para garantir a distribuição adequada.
* **Aberto a Todos os Usuários:** Qualquer usuário pode chamar o método `donate()`, permitindo que qualquer pessoa incentive a provisão ativa de Liquidez.

Embora o método `donate()` seja uma ferramenta poderosa para incentivar os LPs, os doadores devem estar cientes de que suas doações podem sofrer frontrunning por outros usuários. Isso pode ocorrer quando um usuário adiciona Liquidez rapidamente ao pool logo antes de uma doação ser feita, recebendo uma parte dos fundos doados.

Para evitar o frontrunning, os doadores podem precisar considerar estratégias adicionais ao projetar seus mecanismos de doação, como:

* Garantir que as doações ocorram de uma forma que minimize a capacidade de frontrunning oportunista.
* Adicionar atrasos de tempo ou condições específicas (usando callbacks de hook antes/depois de donate) que garantam que as doações não sejam exploradas dessa forma.
