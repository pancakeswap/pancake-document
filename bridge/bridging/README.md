---
description: Faça Bridge de CAKE entre Ethereum, BNB Chain, Aptos e muito mais
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging de/para EVMs (Novo site): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging de/para Aptos (Bridge V1): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## O que é bridging em cripto?

* Bridging em cripto refere-se ao processo de transferir ativos entre diferentes redes blockchain.
* Ele melhora a interoperabilidade, permitindo a transferência de dados e ativos entre diversas redes.

\
Aqui estão alguns motivos pelos quais você pode querer fazer bridge:

* Comprar diferentes tokens de criptomoeda
* Mintar um NFT disponível apenas em uma rede específica
* Economizar dinheiro com transações mais baratas
* Usar um dapp disponível apenas em outra rede

***

## CAKE, um token multichain

Com nossa expansão e implantação multichain, o CAKE agora é um token multichain nativo da BNB Chain, mas também disponível em Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB e Aptos.

O CAKE em qualquer uma das outras chains é igual ao CAKE na BNB Smart Chain. Ele sempre pode ser transferido entre essas chains em uma proporção de 1:1 e sem nenhuma taxa em CAKE.

**Por favor, note que existe apenas um CAKE.** Não há versões diferentes de CAKE em diferentes chains. O fornecimento total de CAKE em todas as blockchains é limitado a 400M, conforme descrito nesta [proposta de votação](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5).

***

## O que é o PancakeSwap Bridge?

O PancakeSwap Bridge é uma ferramenta conveniente dentro do aplicativo que permite mover ativos entre diferentes blockchains diretamente pela interface do PancakeSwap. Em vez de visitar sites externos de bridge, você pode fazer bridge de tokens suportados entre chains como BNB Chain, Ethereum, Base, Arbitrum e mais — tudo em um só lugar.

O PancakeSwap Bridge é desenvolvido por provedores terceirizados confiáveis e funciona como um **agregador** — selecionando a melhor rota com base em preço, velocidade e confiabilidade.

Para aprender como fazer bridge de CAKE, confira os tutoriais e o FAQ nas seções a seguir.

***

## 🔗 Como Funciona

### Bridging via Agregadores

O PancakeSwap Bridge atua como uma camada inteligente sobre protocolos de bridge terceirizados confiáveis. Quando você inicia uma transferência de bridge, o PancakeSwap:

* Verifica múltiplos bridges integrados para rotas otimizadas
* Envia sua transação para o provedor selecionado

O bridging é não custodial — seus ativos não passam pela custódia do PancakeSwap. As transferências são realizadas diretamente pelos provedores de bridge.

### Provedores de Bridge Suportados

Atualmente integramos com:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Nota: Cada provedor tem mecânicas de bridging, chains suportadas, taxas e limites diferentes.

***

### Chains e Tokens Suportados

#### Chains Atualmente Suportadas

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (site V1)

#### Tokens Disponíveis para Bridging

Os tokens disponíveis variam por chain e rota. Tokens comuns suportados incluem (mas não estão limitados a):

* CAKE
* USDT
* USDC
* ETH

***

#### Limitações e Exclusões

Alguns tokens podem não ser suportados devido a limitações do bridge ou restrições de Liquidez. Estes foram filtrados para a melhor experiência do usuário. Por exemplo:

**Para cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Para deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Os itens acima são exemplos. Os tokens realmente disponíveis por chain são mostrados diretamente na interface do Bridge._

***

### 💸 Taxas e Custos

#### Taxas de Bridge

* Cobradas pelo provedor de bridge subjacente
* Normalmente inclui uma pequena taxa por transferência
* Claramente exibidas antes de você confirmar seu bridge

***

#### Custos de Gas

* Você paga as taxas de gas na **chain de origem** para iniciar a transação
* Alguns provedores também podem exigir gas na **chain de destino**
* **Dica:** Sempre mantenha tokens nativos (ex.: ETH, BNB) em ambos os lados do bridge

***

#### Quantias Mínimas e Restrições

Algumas rotas de bridge impõem:

* **Quantias mínimas/máximas de bridge** (ex.: mínimo de 10 USDC)
* **Decimais ou formatos de token suportados** (ex.: apenas tokens ERC-20)

A interface detectará e exibirá automaticamente transferências inválidas.

***

### ⏳ Tempos de Transação e Rastreamento

#### Quanto Tempo Leva o Bridging?

As transferências de bridge normalmente são concluídas em alguns **minutos**, dependendo de:

* Chains de origem e destino
* Congestionamento da rede
* Eficiência do provedor de bridge

#### Rastreando Sua Transferência

Após o envio, você pode visualizar o status da transação através dos exploradores específicos de cada provedor:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Se uma transação ficar travada por muito tempo, verifique o explorador relevante ou entre em contato com nossos administradores pelos [canais sociais](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) para obter [ajuda](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Dicas Antes de Fazer Bridge

* **Mantenha tokens de gas em ambas as chains** (ex.: ETH + BNB)
* **Comece com valores pequenos** se for sua primeira vez fazendo bridge
* Evite fazer bridge durante períodos de alta atividade na chain (pode resultar em taxas de gas mais altas)
* Confirme a compatibilidade do token em ambas as chains
* Sempre verifique novamente as redes de origem e destino

***

### Adicional: Endereços do CAKE Omni-chain Fungible Token (OFT)

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
