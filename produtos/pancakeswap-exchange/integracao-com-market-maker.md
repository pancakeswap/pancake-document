# Integração com Market Maker

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

### Integração do Market Maker no Ethereum&#x20;

A PancakeSwap é integrada aos formadores de mercado na Ethereum para ajudar os traders a executar negociações a um custo menor. Além do AMM, as negociações na PancakeSwap agora podem ser roteadas para formadores de mercado(market maker) designados na whitelist se eles oferecerem uma execução de trade melhor do que os preços atuais do AMM. Esse roteamento é feito automaticamente por um [Smart Router ](https://docs.pancakeswap.finance/v/portuguese-brazilian/produtos/pancakeswap-exchange/smart-router)para que as negociações sejam roteadas apenas para os formadores de mercado quando eles estiverem cotando ativamente preços melhores. Onde o AMM for mais competitivo, os traders serão encaminhados para os AMMs para execução. Existem 2 cenários em que os foramadores de mercado operam na PancakeSwap.&#x20;

### Cenário 1: Existem Pools de Liquidez AMM &#x20;

Se a PancakeSwap na Ethereum já tiver liquidez para um determinado token (por exemplo, WETH/USDC) no AMM, a PancakeSwap solicitará aos formadores de mercado uma cotação no mesmo trade. O Smart Router da PancakeSwap encaminhará a solicitação de negociação para o AMM ou para os formadores de mercado, dependendo de qual fonte de liquidez está dando o melhor preço a qualquer momento.&#x20;

### Cenário 2: Não existem pools de liquidez AMM &#x20;

Nesse cenário, o Smart Router encaminhará automaticamente a negociação para os formadores de mercado. No entanto, isso não impede que os projetos configurem sua pool de liquidez no AMM posteriormente e trabalhem conosco para manter a liquidez da DEX descentralizada.&#x20;

### Taxas

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

A PancakeSwap não cobra dos traders quaisquer taxas executadas através de nós e que são executadas pelos formadores de mercado. No entanto, a PancakeSwap recebe **taxas de negociação de 0,05%** dos formadores de mercado da whitelist para volumes executados por eles. A PancakeSwap recebe uma **taxa de negociação reduzida de 0,01%** se as negociações executadas forem entre pares de stablecoin.

| Trades                                 | Taxas de Trade | Taxa para PCS  do MM | Queima de Cake | Pancakeswap Treasury |
| -------------------------------------- | -------------- | -------------------- | -------------- | :------------------: |
| Não-stablecoin (Por exemplo, ETH/USDC) | N/A            | 0,05%                | 0,017%         |        0,033%        |
| Stablecoin para Stablecoin             | N/A            | 0,01%                | 0,003%         |        0,007%        |

### Recursos atualmente suportados&#x20;

Os seguintes ativos são atualmente suportados e podem aumentar/diminuir dependendo do(s) formador(es) de mercado:&#x20;

* **Principais**: WETH, WBTC&#x20;
* **Stablecoins**: USDT, USDC, DAI, BUSD&#x20;
* **Outros ativos ERC-20 populares:** MATIC, SAND, DYDX, CRV, MANA, SUSHI, FTM, LINK, APE, CVX, STG, LDO, AAVE, MKR, UNI&#x20;

Observe que, diferentemente dos AMMs, os formadores de mercado não poderão negociar qualquer valor e os valores que estão dispostos a executar dependerão de sua própria liquidez. Não é incomum que, às vezes, pedidos muito grandes não possam ser totalmente atendidos. Aconselhamos os usuários a revisar as cotações cuidadosamente para garantir que cada negociação reflita o preço e a quantidade de acordo com suas necessidades.&#x20;

### Tempos de inatividade do criador de mercado&#x20;

Não se espera que os criadores de mercado façam cotações 24 horas por dia, 7 dias por semana. Existem alguns casos (por exemplo, eventos econômicos importantes, atualizações do sistema) em que o formador de mercado pode estar temporariamente indisponível para fornecer uma cotação. Por favor, observe que, durante esses períodos, esses tokens simplesmente não serão negociáveis e aconselhamos os usuários a aguardar algum tempo antes que o formador de mercado volte a ficar online.&#x20;

### Perguntas Frequentes&#x20;

**P.** Os formadores de mercado serão integrados na BSC e na Aptos?&#x20;

**Resposta**: Possivelmente, estamos apenas lançando a integração dos formadores de mercado na Ethereum por enquanto para aumentar a liquidez para uma melhor experiência do usuário. Continuaremos monitorando outras chains.&#x20;

**P**. Como a PancakeSwap gerará receita se não cobrar uma taxa dos usuários?&#x20;

**Resposta**: A PancakeSwap não cobrará nenhuma taxa dos usuários, mas a PancakeSwap receberá uma pequena comissão dos formadores de mercado e a usará isso para financiar a recompra e a queima do CAKE.&#x20;

**P**. Os provedores de liquidez continuarão a receber taxas de LP?&#x20;

**Resposta**: Sim, os provedores de liquidez continuarão a ganhar 0,17% de recompensa de taxa de negociação (taxas LP) e rendimento nos farms de CAKE.&#x20;

**P**. Os formadores de mercado adicionarão liquidez ao AMM? Isso fará com que o APR diminua?&#x20;

**Resposta**: Os formadores de mercado mantêm sua própria liquidez separada e, portanto, não ganharão APR de negociações no AMM. Somente os LPs ganharão taxas e APRs por fornecer liquidez às pools de AMM.&#x20;

**P**. Estou fornecendo liquidez na PancakeSwap na Ethereum. Preciso fazer alguma coisa?&#x20;

**Resposta**: Não, você não precisa fazer nada. Você continuará ganhando as taxas de LP pelas negociações executadas através do AMM e continuará obtendo o rendimento em CAKE.&#x20;

**P**. Como alguém pode se tornar um formador de mercado?&#x20;

**Resposta**: Nós avaliamos e trabalhamos com formadores de mercado individualmente. Entre em contato conosco diretamente ou por meio de nossos administradores se tiver interesse em trabalhar conosco.
