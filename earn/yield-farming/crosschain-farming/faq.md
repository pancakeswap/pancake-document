# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### O que devo fazer na PancakeSwap em outras blockchains?

Forneça liquidez, negocie e faça farming como sempre fez. Se você já é um usuário multichain, lembre-se de fornecer liquidez na PancakeSwap em outras blockchains nas quais implantamos (como Ethereum), pois temos recompensas de CAKE na BNB Smart Chain para você, permitindo que ganhe ainda mais CAKE sem precisar fazer Bridge desses ativos!

### **Haverá mais pares?**

Sim, mas faremos a implantação em etapas para garantir que priorizemos a segurança dos fundos dos usuários e a inflação do CAKE. Nos avise nos chats da comunidade o que você acha que deve ser adicionado à PancakeSwap em outras blockchains, assim como em quais outras blockchains devemos implantar a PancakeSwap.

### **Por que o custo de gas para fazer Staking de LP tokens é alto?**

Uma pequena quantidade de token nativo (por exemplo, ETH na Ethereum) é necessária para a configuração inicial. Portanto, a primeira transação será ligeiramente mais cara.

Além disso, existem outras taxas (principalmente custos de gas) envolvidas no farming cross-chain. Confira [esta](faq.md#are-there-any-fees-when-i-do-crosschain-farming) seção dedicada para saber mais.

### **Por que o Staking e o Unstaking levam 30 minutos para serem concluídos?**

Todas as transações cross-chain levam cerca de 30 minutos para serem concluídas. Isso ocorre porque:

* As transações precisam ser executadas tanto na blockchain de farming (como Ethereum) quanto na BNB Chain.
* A entrega de mensagens cross-chain leva tempo.
* Para garantir a segurança e que todos os dados estejam sincronizados e consistentes entre as diferentes blockchains.

### **Onde estão minhas recompensas de CAKE colhidas?**

Seu CAKE colhido será distribuído na BNB Smart Chain. Por favor, troque a rede blockchain na sua carteira para verificar o saldo de CAKE.

### **Não consigo colher porque minha carteira não suporta troca entre diferentes blockchains!**

Por favor, tente usar um aplicativo de carteira diferente que suporte multichain e troca de rede.

Observe que fazer Staking e Unstaking de LP tokens também colherá todo o CAKE ganho para sua carteira na BNB Smart Chain. Portanto, se não quiser usar um aplicativo de carteira diferente, basta fazer Staking de mais LP tokens, ou retirar uma pequena quantidade de LP tokens para colher seu CAKE ganho.

### Há alguma taxa quando faço farming cross-chain?

Ao contrário do farming nativo na BNB Chain, o farming em outras blockchains requer atividades cross-chain. Aqui estão as taxas envolvidas:

**1 - Taxa de gas para criar um contrato proxy**

Um contrato proxy precisa ser criado na BNB Chain para o farming cross-chain. O custo de gas para a criação do contrato proxy está incluído na transação.

Esta taxa é cobrada apenas uma vez na primeira transação de "stake".

**2 - Taxa de gas para chamadas na BNB Chain**

Quando os usuários depositam ou retiram LP tokens, um executor realizará transações chamando em nome dos usuários na BNB Chain. O custo de gas para essas chamadas está incluído na transação.

Esta taxa é cobrada em cada transação de depósito ou retirada.

**3 - Taxa de gas para chamadas em outras blockchains**

Quando os usuários retiram LP tokens, um executor realizará as transações finais para liberar os LP tokens em outras blockchains (como Ethereum). O custo de gas para essas chamadas está incluído na transação.

Esta taxa é cobrada apenas em transações de retirada.

**4 - Taxa de mensagens cross-chain**

Utilizamos um message bus desenvolvido pela Celer para rotear nossas mensagens cross-chain. Portanto, uma taxa de mensagem é incluída com base no comprimento em bytes da mensagem.

Esta taxa é cobrada em cada transação de stake. Em transações de unstake, esta taxa é cobrada duas vezes, pois uma comunicação bidirecional entre a BNB Chain e outras blockchains é necessária por segurança.

```
messagingFee = feeBase + message.length * feePerByte;
```

Você pode encontrar as variáveis na fórmula no contrato do message bus:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - O fundo inicial**

Isso não é estritamente uma "taxa".&#x20;

Para cada novo usuário que começa a fazer farming cross-chain na PancakeSwap, na primeira transação de "stake", depositaremos 0,005 BNB na carteira BNB Chain deles. A quantidade correspondente de tokens nativos na blockchain de farming (como ETH na Ethereum) será cobrada da transação de depósito, usando a taxa de mercado fornecida pelo oráculo de preço.

Isso é para ajudar os usuários a iniciar sua jornada na BNB Chain com facilidade. Entendemos a dificuldade de ter todo o CAKE colhido, mas não conseguir explorar o vibrante ecossistema PancakeSwap sem encontrar outra forma de adquirir BNB para gas.

Esta taxa é cobrada apenas uma vez na primeira transação de "stake".

### De onde vêm as emissões?&#x20;

_atualizado em 10 out 2022_

Por enquanto, os Chefs desviaram 0,0189 CAKE por bloco do pool CAKE para todos os farms cross-chain.&#x20;

Aqui está o detalhamento das emissões:

<table><thead><tr><th width="249"></th><th>Multiplicador</th><th>CAKE por bloco</th></tr></thead><tbody><tr><td><strong>Pool CAKE</strong></td><td>-</td><td><strong>8,9811</strong></td></tr><tr><td><strong>Todos os Farms Cross-chain</strong></td><td>-</td><td><strong>0,0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0,5x</td><td>0,0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0,2x</td><td>0,0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0,2x</td><td>0,0042</td></tr></tbody></table>

### O que acontece durante o depósito, colheita e retirada?

O farming cross-chain da PancakeSwap é como usar um LP token "substituto" para fazer farming na BNB Chain, com o mesmo MasterChef da PancakeSwap. As recompensas de CAKE são calculadas e distribuídas na BNB Chain, controladas e protegidas pelo mesmo contrato MasterChef.

#### Ao Depositar:

1. Os usuários solicitam o depósito de LP tokens nas blockchains de farming (como Ethereum).
2. Os LP tokens são transferidos para contratos de cofre de farming.
3. O message bus Celer é utilizado para entregar a mensagem de "depósito" à BNB Chain.
4. Um executor na BNB Chain cunha a mesma quantidade de tokens de farming como "substitutos" e os deposita nos farms.

#### Ao Colher:

Como as recompensas de CAKE são calculadas e distribuídas na BNB Chain, os usuários podem reivindicar suas recompensas de CAKE com uma única transação na BNB Chain, sem necessidade de operações cross-chain.

#### Ao Retirar:

1. Os usuários solicitam a retirada de LP tokens nas blockchains de farming (como Ethereum).
2. O message bus Celer é utilizado para entregar a mensagem de "retirada" à BNB Chain.
3. Um executor na BNB Chain retira os tokens de farming dos farms, queima esses tokens, transfere o CAKE ganho para os usuários e utiliza o message bus Celer para entregar a mensagem de confirmação de volta à blockchain de farming original.
4. Um executor na blockchain de farming confirma tudo e então libera os LP tokens dos contratos de cofre.
