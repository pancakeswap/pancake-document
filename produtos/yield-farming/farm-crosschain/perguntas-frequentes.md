# Perguntas Frequentes

<figure><img src="../../../.gitbook/assets/image (1) (4).png" alt=""><figcaption></figcaption></figure>

### O que devo fazer na PancakeSwap na Ethereum?

Forneça liquidez, negocie e cultive como sempre foi. Se você já é um usuário multichain, lembre-se de fornecer liquidez na PancakeSwap na Ethereum, pois temos recompensas CAKE na BNB Smart Chain para você, permitindo que você ganhe ainda mais CAKE sem sobrecarregar esses ativos!

### Haverá mais pares? <a href="#will-there-be-more-pairs" id="will-there-be-more-pairs"></a>

Sim, mas estaremos implantando em etapas para garantir que priorizamos a segurança dos fundos dos usuários e a inflação de CAKE. Deixe-nos saber nos chats da comunidade o que você acha que deve ser adicionado na PancakeSwap na Ethereum.

### Por que o custo do gás para fazer stake em tokens LP é alto?

Uma pequena quantidade de token nativo (por exemplo, ETH para Ethereum) é necessária para a primeira configuração. Portanto, a primeira transação será um pouco cara.

Além disso, existem outras taxas (principalmente custos de gás) envolvidas no farm crosschain. Confira e[sta seção ](https://docs.pancakeswap.finance/v/portuguese-brazilian/produtos/yield-farming/farm-crosschain/perguntas-frequentes#ha-alguma-taxa-quando-faco-farm-crosschain)dedicada para saber mais.

### Por que fazer e desfazer o stake leva 30 minutos para ser concluído?

Todas as transações de crosschain levarão cerca de 30 minutos para serem concluídas. É porque:&#x20;

* As transações devem ser executadas tanto na blockchain do farm (como Ethereum) quanto na BNB chain.&#x20;
* Entregar mensagens crosschain leva tempo.&#x20;
* Para garantir a segurança de que todos os dados estão sincronizados e consistentes entre diferentes blockchains.

### Onde estão minhas recompensas CAKE colhidas?

Seu CAKE colhido será distribuído na BNB Smart Chain. Por favor, mude a rede blockchain em sua carteira para verificar o saldo de CAKE.

### Não posso colher porque minha carteira não suporta alternar entre diferentes blockchains!

Por favor, tente usar um aplicativo de carteira diferente que suporte troca de chains e multichain.&#x20;

Observe que fazer stake ou retirar do stake os LP tokens também coletam todo o CAKE ganho para sua carteira na BNB Smart Chain. Portanto, se você não quiser usar um aplicativo de carteira diferente, simplesmente faça stake de mais ou retire uma pequena quantidade de tokens de LP para coletar seu CAKE ganho.

### Há alguma taxa quando faço farm crosschain?

Ao contrário do farm nativo na BNB Chain, o farm em outras blockchains requer atividades de crosschain. Aqui estão as taxas envolvidas::

**1 - Taxa de gás para criar um contrato proxy**

Um contrato de proxy deve ser criado na BNB Chain para farm crosschain. O custo do gás para a criação do contrato proxy está incluído na transação.&#x20;

Esta taxa é cobrada apenas uma vez na primeira transação de "stake".

**2 - Taxa de gás por chamadas na BNB Chain**

Quando os usuários depositam ou sacam tokens LP. Um executor realizará transações chamando pelo comportamento dos usuários na BNB Chain. O custo do gás para essas chamadas está incluído na transação.&#x20;

Esta taxa é cobrada em cada transação de depósito ou retirada.

**3 - Taxa de gás por chamadas em outras blockchains**

Quando os usuários retiram tokens LP. Um executor realizará as transações finais chamando para liberar os tokens LP em outras blockchains (como Ethereum). O custo do gás para essas chamadas está incluído na transação.&#x20;

Esta taxa é cobrada apenas em transações de saque.

**4 - Taxa de mensagem Cross-chain**

Utilizamos um barramento de mensagens alimentado pelo Celer(Celer message bus) para rotear nossas mensagens crosschain. Portanto, uma taxa de mensagens é incluída com base no comprimento de bytes da mensagem.&#x20;

Esta taxa é cobrada em cada transação de stake. Em transações de desbloqueio, essa taxa é cobrada duas vezes, pois é necessária uma comunicação bidirecional entre a BNB Chain e outras blockchains por segurança.

```
messagingFee = feeBase + message.length * feePerByte;
```

Você pode encontrar as variáveis na fórmula no contrato bus da mensagem:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - O fundo inicial**&#x20;

Isso não é estritamente uma "taxa".&#x20;

Para cada novo usuário que começou a fazer farm crosschain na PancakeSwap, na primeira transação de “stake”, depositaremos 0,005 BNB em sua carteira BNB Chain. A quantidade correspondente de tokens nativos na chai do farm (como ETH no Ethereum) será cobrada da transação de depósito, usando a taxa de mercado fornecida pelo oráculo de preços.&#x20;

Isso é para ajudar os usuários a iniciar sua jornada na BNB Chain com facilidade. Entendemos a dor de ter todo o CAKE colhido, mas não poder explorar o vívido ecossistema da PancakeSwap sem encontrar outra maneira de adquirir BNB para gás. Esta taxa é cobrada apenas uma vez na primeira transação de "stake".

### De onde vêm as emissões?

_atualizado em 10 de Outubro de 2022_

Por enquanto, os Chefs desviaram 0,0189 CAKE por bloco da Pool de CAKE para todos os farm crosschain.&#x20;

Aqui está o detalhamento das emissões:

|                        | Multiplicador | CAKE por bloco |
| ---------------------- | ------------- | -------------- |
| Pool de CAKE           | -             | **8,9811**     |
| Todos Farms Crosschain | -             | **0,0189**     |
| Ethereum ETH/USDC      | 0,5x          | 0,0105         |
| Ethereum ETH/USDT      | 0,2x          | 0,0042         |
| Ethereum WBTC/ETH      | 0,2x          | 0,0042         |

### O que aconteceu durante o depósito, colheita e saque?

O Farm crosschain da PancakeSwap é como usar um token LP "stand-in" para farmar na BNB chain, com o mesmo MasterChef da PancakeSwap. As recompensas CAKE são calculadas e distribuídas na Rede BNB, controladas e guardadas pelo mesmo contrato MasterChef.

#### No Depósito:

1. Os usuários solicitam o depósito de tokens LP nos farms em blockchains (como Ethereum).
2. Os tokens LP são transferidos para contratos de vaults de farms.
3. O Celer message bus é utilizado para entregar a mensagem de "depósito" à BNB Chain.
4. AUm executor na BNB Chain cunha a mesma quantidade de tokens de farm como "stand-ins" e depois os deposita nos farms.

#### Após a colheita:

Já que as recompensas CAKE são calculadas e distribuídas na BNB Chain. Os usuários podem reivindicar suas recompensas de CAKE com uma única transação na BNB Chain sem a necessidade de operações de crosschain.

#### Após o saque:

1. Os usuários solicitam a retirada de tokens LP nos farms das blockchains (como Ethereum).
2. Celer message bus é utilizado para entregar a mensagem de "saque" para a Rede BNB.
3. Um executor na BNB Chain retira os tokens dos farms, queima esses tokens, transfere o CAKE ganho para os usuários e utiliza o Celer message bus para entregar a mensagem de confirmação de volta para a blockchain do farm original.
4. Um executor no blockchain do farm confirma tudo e depois libera os tokens LP dos contratos do cofre.
