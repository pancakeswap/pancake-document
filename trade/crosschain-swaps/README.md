# 🔀 Swaps Cross-chain

Os Swaps Cross-chain permitem que os usuários façam swap de tokens entre blockchains de forma fluida — tudo em uma única transação simplificada.

Os swaps cross-chain são suportados entre:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**As transações são extremamente rápidas — geralmente concluídas em segundos a menos de um minuto.**
{% endhint %}

***

### 🔍 Como Funciona

1. O usuário seleciona as blockchains De / Para e os tokens De / Para
2. O roteador da PancakeSwap calcula a rota mais eficiente
3. Os swaps são executados usando os pools de liquidez da PancakeSwap (v2, v3, Infinity, StableSwaps) nas blockchains de origem e destino
4. O Bridging é feito pelos nossos protocolos parceiros: [Across](https://across.to/) (para EVM <> EVM), [Relay](https://relay.link/bridge) (para SOL <> EVM)

{% hint style="success" %}
**Os swaps cross-chain estão disponíveis para qualquer token com liquidez adequada nas blockchains de origem e destino.**
{% endhint %}

***

### 💸 Taxas

* **A PancakeSwap não cobra nenhuma taxa por transações Cross-chain.**
* As taxas são compostas por:
  1. **Taxa de Negociação:** Cobrada por swaps dentro dos pools de liquidez nas blockchains de origem e destino
  2. **Taxa de Bridge:** Paga aos relayers pelo bridging dos ativos

***

### 🎯 O Que São Intents?

Intents permitem que os usuários definam o resultado desejado sem se preocupar com como ele é alcançado.

Exemplos de Intents:

* "Fazer swap de 1 ETH na Base por pelo menos 3000 USDC no Arbitrum"

Sem intents, o usuário precisaria manualmente:

* Fazer bridge de ETH para o Arbitrum
* Encontrar uma DEX com o melhor preço ETH → USDC

{% hint style="success" %}
**Com intents — o sistema cuida de tudo automaticamente.**
{% endhint %}

**Benefícios do design baseado em intents:**

* UX fluida
* Tempos de transação mais rápidos
* Transações únicas com um clique

***

### 🔐 Auditorias

Realizamos múltiplas rodadas de auditoria com nomes respeitados no espaço de segurança cross-chain:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
