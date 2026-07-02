# FAQ de Swap

## Swap

### O que há de novo na Exchange V3?

* Liquidez concentrada — a liquidez será concentrada na faixa de preço mais negociada, o que significa:
  * Menor Slippage de negociação para os traders
  * Potencialmente mais recompensas em taxas de LP para os provedores de liquidez
* Uma estrutura de taxas de negociação flexível — os provedores de liquidez podem escolher entre múltiplas camadas de taxas de negociação ao criar pares de liquidez ou fornecer liquidez
* Faixa de preço personalizável — os provedores de liquidez também podem escolher para quais faixas de preço desejam fornecer liquidez
* Posições de liquidez não fungíveis — cada posição de liquidez terá seu próprio ID único correspondente às suas configurações (como faixa de preço). Portanto, você poderá criar e manter múltiplas posições com o mesmo par de negociação, mas com configurações e valores de liquidez diferentes
* Compatibilidade retroativa — a Exchange v3 também utilizará os pares de liquidez legados v2 e stable swap para sempre fornecer a melhor rota de negociação
* Ordem limitada integrada — usuários avançados podem utilizar a nova faixa de preço personalizável no fornecimento de liquidez para criar efetivamente uma ordem limitada que converterá todos os tokens no desejado quando o preço atingir o alvo



### Posso adicionar meus próprios tokens à Exchange V3?

Todos podem criar pools de liquidez depositando liquidez na V3.

No entanto, os seguintes tokens atualmente **NÃO** são suportados:

* Tokens com taxa de transferência
* Tokens de rebase

Para esses tokens, por favor **NÃO** adicione liquidez na Exchange V3. Seus ativos podem ficar presos na posição de liquidez.



### **Por que minha transação não está sendo processada?**

PancakeSwap é uma aplicação DeFi que interage com a carteira para completar transações on-chain de swap, criação de LPs, staking em farms e pools, etc.

**Taxas de Gas**

Portanto, a primeira coisa é **certificar-se de que você tem BNB suficiente para pagar a taxa de gas** das transações on-chain. Normalmente, a taxa de gas flutua dependendo do número de transações na fila; se houver mais transações, uma taxa de gas mais alta pode ser necessária para processar a transação. Na BNB Smart Chain, a taxa de gas normalmente varia de centavos a um dólar USD em BNB. Saiba mais sobre [taxa de gas aqui](https://academy.binance.com/en/glossary/gas).

**Taxas de Transação**

Se a sua ação de swap ainda não for processada e estiver exibindo um erro para você revisar o Slippage — você pode querer verificar se os tokens que está tentando fazer swap têm **quaisquer taxas e restrições em transações**.

Não é incomum que tokens na BNB Smart Chain incluam uma **taxa de transação** em seus contratos; geralmente essas taxas podem ser usadas para queima, financiamento de um tesouro de um projeto de lançamento justo — por exemplo, este [token APX tem um imposto de 1% em cada transação](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) para envio a um endereço de queima, de modo que mais transações significam mais queima, acumulando valor para os detentores do token APX.

Com a taxa de transação, seja ela inclusiva (uma parte do valor do swap é enviada para outro endereço que não o seu, de modo que a saída é menor do que o esperado para a entrada estimada) ou exclusiva (exigindo uma transferência adicional do seu endereço para enviar tokens extras, de modo que a entrada é maior do que o esperado para a saída estimada), ela afeta os valores de entrada e saída que você concorda ao assinar a transação. Em muitos casos, a transação não consegue atender aos requisitos de entrada e saída por causa do imposto.

**Fazendo Swap com Taxas de Transação**

Antes de fazer swap de qualquer token, certifique-se de ter visitado o site deles para entender se há um mecanismo de taxa de transação (ou _imposto_, como muitos projetos chamam). Se houver, certifique-se de definir um Slippage suficiente para acomodar a taxa de transação — ex.: se houver uma taxa de transação de 5%, seu Slippage terá que ser definido em pelo menos 5% mais o Slippage normal de negociação dependendo do seu volume de negociação e da liquidez do token, digamos 5,5%-6%.

Em alguns casos extremos, incluindo alguns golpes, alguns tokens até têm um bloqueio na maioria ou em todas as transferências on-chain, ou apenas permitem que certos endereços vendam; nesse caso é impossível fazer swap do token com sucesso. Aprenda sobre o token que está tentando fazer swap e esteja ciente de quaisquer taxas e restrições!



### A nova interface de Swap usa liquidez v2 ou stable swap?

Sim. O novo Swap v3 usa liquidez da PancakeSwap v3, v2 e stable swap para obter a melhor rota de negociação.



### O que é roteamento dividido?

No Swap v3, sua negociação pode ser dividida em múltiplas rotas para executar sua negociação com a melhor taxa.

Para ver mais detalhes sobre como sua negociação é roteada, toque no botão "v" na seção "Rota" para expandir e ver os detalhes.

Saiba mais [aqui](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Como personalizar ou desabilitar certas fontes de liquidez?

O novo Swap v3 usa liquidez da PancakeSwap v3, v2 e stable swap para obter a melhor rota de negociação. No entanto, você pode personalizar ou desabilitar certas fontes de liquidez se não quiser que sua negociação seja roteada por elas.

Ao visualizar uma rota de negociação, clique no botão "Personalizar Roteamento". Ou clique no botão de engrenagem ⚙️ no canto superior direito da interface de Swap e escolha "Personalizar Roteamento".

No pop-up "Personalizar Roteamento", você poderá escolher qual fonte de liquidez deseja utilizar. Ou desabilitar completamente os multihops.

Nota: desabilitar os multihops pode levar a um aumento do Slippage ou a uma taxa de negociação pior em pares de negociação específicos. Prossiga com cautela.

Saiba mais [aqui](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Liquidez

### O que são camadas de taxa e como escolher a correta?

Na Exchange v3, ao fornecer liquidez, você pode escolher entre várias taxas de negociação diferentes (0,01%, 0,05%, 0,25% e 1%) para o mesmo par de tokens.

Por exemplo, para CAKE-BNB, pode haver um par de 0,25%, o que significa que uma taxa de negociação de 0,25% está em vigor para cada negociação. No entanto, alguns provedores de liquidez podem optar por fornecer liquidez a um par de negociação CAKE-BNB com uma taxa de 0,05%, oferecendo uma cotação melhor e atraindo mais volume de negociação.

Não há uma resposta "correta" sobre qual configuração de taxa de negociação escolher. Depende dos tokens dentro do par de negociação. Normalmente, tokens voláteis devem ter uma taxa de negociação mais alta para compensar melhor a perda impermanente causada pela volatilidade. Por outro lado, tokens como stablecoins têm movimentos de preço menores e perdas impermanentes menores, portanto, sua taxa de negociação deve ser menor.

Ao selecionar um par de tokens, a interface "Adicionar Liquidez" escolherá automaticamente a camada de taxa mais popular para você.



### Por que meus dois tokens depositados não têm valor igual em USD?

Na Exchange V3, os ativos subjacentes em uma posição de liquidez nem sempre terão valor igual em USD. Isso dependerá das configurações de faixa de preço de uma posição e do preço atual do par.

Na verdade, se sua posição sair da faixa, todos os tokens serão convertidos em um único ativo. Além disso, você pode fornecer liquidez a uma faixa de preço que não cobre o preço atual e depositar apenas um único ativo. Continue lendo para saber mais ⬇️



### O que acontece se minha posição de liquidez sair da faixa?

Você não ganhará nenhuma recompensa de taxa de negociação se o preço atual sair da faixa de preço definida em sua posição.

Além disso, todos os tokens serão convertidos em um único ativo dependendo da direção da condição de preço.

Por exemplo, se uma posição de CAKE/BUSD estiver configurada com uma faixa de preço de 3 BUSD por CAKE a 5 BUSD por CAKE. Todos os ativos na posição serão convertidos para BUSD se o preço de CAKE for maior ou igual a 5 BUSD por CAKE, e vice-versa.

Observe que se o preço voltar para a faixa, você começará a receber recompensas de taxa de negociação novamente. Nenhuma ação adicional é necessária.



### É melhor sempre fornecer liquidez com uma faixa menor?

Fornecer liquidez a uma faixa de preço menor ajudará a concentrar sua liquidez em uma faixa de preço específica, aumentando suas participações relativas em relação à liquidez total dentro da faixa de preço, potencialmente ganhando mais recompensas de taxa de negociação.

No entanto, tenha em mente que apenas posições de liquidez ativas ganharão recompensas de taxa de negociação das negociações. Isso significa que você só ganhará recompensas quando o preço de negociação atual estiver dentro da faixa de preço definida na posição de liquidez.



### Há alguma forma de ajustar automaticamente minha posição para que ela esteja sempre na faixa e ganhando recompensas de taxas?

O PancakeSwap v3 suporta depósito de liquidez com um clique via Zap, disponível na BNB Chain e na Ethereum.



### Qual será a distribuição das taxas de negociação para a Exchange v3?

|                        | 0,01% | 0,05% | 0,25% | 1%  |
| ---------------------- | ----- | ----- | ----- | --- |
| Provedor de Liquidez   | 67%   | 66%   | 68%   | 68% |
| Queima de CAKE         | 15%   | 15%   | 23%   | 23% |
| Tesouro                | 18%   | 19%   | 9%    | 9%  |

### As recompensas de taxa de LP são compostas automaticamente como na Exchange v2?

Não.

Na Exchange v3, você precisará reivindicar as recompensas de taxa de negociação manualmente. Você pode fazer isso na página de detalhes da posição. Você pode encontrar todas as suas posições de liquidez v3 na página de liquidez.



### O que afeta o APR de LP?

Na Exchange v3, o APR de recompensa de taxa de LP pode variar entre as posições de liquidez. É baseado nos seguintes fatores:

* Volume de negociação\
  \- mais volume gera mais recompensas de taxas
* Camada de taxa do par de liquidez\
  \- camada de taxa mais alta gera mais recompensas de taxas de negociações individuais
* O número de tokens depositados\
  \- mais tokens na posição se traduz em uma participação relativa maior em relação à liquidez ativa total, o que obtém mais recompensas de taxa de negociação
* A faixa de preço selecionada\
  \- faixa de preço menor permite uma concentração maior para o mesmo valor de token depositado, o que se traduz em uma participação relativa maior em relação à liquidez ativa total, e obtém mais recompensas de taxa de negociação
* A quantidade de liquidez atualmente ativa\
  \- se houver mais usuários que depositam e concentram sua liquidez na mesma faixa que você, você ganhará menos taxa de negociação devido a uma participação relativa menor em relação ao total
* Se a posição de liquidez está ativa\
  \- apenas posições de liquidez ativas ganharão recompensas de taxa de negociação



### Posso fornecer liquidez v2?

Fornecer liquidez v2 não é mais aconselhável. Recomendamos usar a liquidez v3 para aproveitar os novos recursos e melhorar a eficiência.

Se quiser prosseguir com a adição de liquidez v2:

* Se o par de tokens não tiver um pool v3, ou se tiver mais liquidez em v2 do que o maior pool em v3. Um botão "Adicionar Liquidez V2" aparecerá. Basta clicar para mudar para adicionar liquidez v2
* Alternativamente, use `/v2` na URL para sempre usar o fornecimento de liquidez v2



### Por que não consigo adicionar liquidez a um par que acabei de criar?

Devido a um bug do Exchange V2 legado (presente em todos os forks UniSwap V2), você não conseguirá adicionar liquidez a um par usando a interface normal de liquidez da PancakeSwap e suas chamadas de contrato se um par for:

* Criado chamando `createPair` no FactoryV2 sem depositar liquidez inicial e cunhar os tokens LP iniciais
* Em seguida, um dos tokens do par foi transferido manualmente para o contrato do pool ao chamar `sync`

{% hint style="info" %}
Recentemente, um aumento na quantidade de tais ataques foi detectado na Exchange V2 da PancakeSwap na BNB Chain.&#x20;

Recomendamos fortemente o uso de nossa interface para criar o par de negociação para o seu token adicionando a liquidez inicial com a criação do par.
{% endhint %}

Enquanto os Chefs trabalham arduamente em uma solução para resolver este problema, aqui está um guia passo a passo para resolver usando o BscScan:

#### Localize o endereço do pool e sua página no BscScan

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Se o seu par for afetado, você verá o link para a página do BscScan para o par/pool de negociação na mensagem de erro.

Alternativamente, você pode ir ao Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), ir para "Read Contract", "6. getPair", inserir o endereço dos dois tokens em seu par de negociação e clicar em "Query". Você deve ver o endereço do par no campo de retorno.

#### Verifique qual token foi depositado e transfira o outro token para o par manualmente

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

No campo de saldo de tokens no BscScan, você pode verificar qual token foi depositado no pool. Normalmente, deve ser o token pareado. (Como WBNB, USDT, etc…)

Após confirmar, você deve transferir manualmente o outro ativo para o contrato do pool. Você pode fazer isso no aplicativo de carteira de sua preferência inserindo o endereço do pool como destinatário.

Você pode transferir qualquer valor, mas como isso é efetivamente "doando" ativos para um pool, você estará transferindo seus ativos para uma liquidez sem cunhar tokens de liquidez. Portanto, recomendamos manter esse valor mínimo.

{% hint style="warning" %}
IMPORTANTE: Após transferir o token, você deve chamar `sync()` imediatamente no pool.
{% endhint %}

Você pode fazer isso indo à página do BscScan para o par de negociação, indo para "Write Contract", "8. Sync" e clicando no botão "Write". Você precisará conectar sua carteira antes de realizar a transação.

Após a confirmação da transação, você pode adicionar a liquidez subsequente na interface da PancakeSwap.

#### E se eu quiser definir o preço de lançamento?

Você deve ajustar o pool para o preço de lançamento ao transferir o token e corrigir o pool.

O valor a transferir pode ser calculado usando:

* `tokenInside`: o token que já foi transferido para o pool. Normalmente deve ser o token pareado. (Como WBNB, USDT, etc…)
* `tokenToSend`: o token que está prestes a ser enviado ao pool. Normalmente deve ser o token do seu projeto
* `tokenInside.price`: o preço USD do tokenInside
* `tokenToSend.price`: o preço USD do tokenToSend (o preço de lançamento)
* `pool`: o pool V2

Com a seguinte fórmula:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Se o resultado for menor que 0 (geralmente acontece quando o preço de lançamento é muito grande. Você pode precisar primeiro depositar mais `tokenInside` no pool)



### Como gerenciar LP stable e LP legado v2?

Você pode gerenciá-los normalmente acessando a página de [Liquidez](https://pancakeswap.finance/liquidity).



### Por que preciso redefinir a aprovação do USDT antes de habilitar/aprovar?

Ao operar na mainnet do Ethereum, o token USDT segue uma lógica diferente para gerenciar aprovações e permissões de token.&#x20;

Portanto, quando as permissões de gasto estão muito baixas, é necessário redefinir a aprovação antes de definir uma nova.
