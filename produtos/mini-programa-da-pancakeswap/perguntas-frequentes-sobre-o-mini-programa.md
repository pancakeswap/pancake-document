# Perguntas Frequentes sobre o Mini-Programa

### &#x20;<a href="#what-are-the-future-developments-of-the-mini-program" id="what-are-the-future-developments-of-the-mini-program"></a>

## Quais são os desenvolvimentos futuros do Mini-Programa?&#x20;

Desde a primeira versão lançada em março de 2022, milhares de usuários já o utilizam diariamente. Como o primeiro Miniprograma de grande escala, a equipe da Binance também está descobrindo alguns novos problemas de infraestrutura e desempenho conosco, atualizando assim sua arquitetura. Antes de adicionar mais recursos, estamos focados em melhorar o desempenho geral e a experiência do usuário do Miniprograma. Além disso, estamos trabalhando com a Binance para adicionar gradualmente mais entradas ao Mini-Programa para que possa ser descoberto mais facilmente pelos usuários da Binance - como nas funções de pesquisa ou ganho no aplicativo.&#x20;

## Como o Mini-Programa ajudará a PancakeSwap?&#x20;

PancakeSwap é atualmente a plataforma descentralizada mais popular (em termos de número de usuários), mas a Cozinha está sempre procurando por mais maneiras de convidar novos usuários para nossa plataforma. Embora a maioria dos usuários DeFi no mercado já deva ter ouvido falar ou usado a PancakeSwap, imagine o potencial dos recém-chegados à cripto integrados pela Binance e seu CEX. Esses novos usuários podem não ter a experiência de criar uma carteira Web3, adicionar liquidez, farmar, fazer stake, negociar uma ampla variedade de ativos etc. O Miniprograma PancakeSwap oferece o melhor caminho para convidar e educar esses usuários para a experiência DeFi.&#x20;

## É controlado pela Binance ou PancakeSwap?&#x20;

O front-end do Mini-Programa é desenvolvido sob as diretrizes e arquitetura de seu sistema de Mini-Programa da Binance. A Binance também tem o direito de revisar e aprovar qualquer conteúdo e função no Mini-Programa. No entanto, os contratos inteligentes subjacentes com os quais você interage no Miniprograma são o mesmo conjunto de contratos inteligentes da nossa web.&#x20;

## Quando outros recursos serão adicionados ao Mini-Programa?&#x20;

Devido a questões regulatórias, outros recursos como Loteria, IFO e perfis ainda não podem ser adicionados ao Mini-Programa. Nosso objetivo é educar os usuários da Binance sobre os fundamentos do DeFi primeiro e, gradualmente, atraí-los para nossa versão da web para experimentar o conjunto completo de nossos recursos!

## Por que devo usar o Mini-Programa quando posso usar a versão web com uma carteira de navegador?&#x20;

O Mini-Programa foi projetado como uma versão simplificada para atrair usuários da Binance que não estão familiarizados com o DeFi – esses usuários podem não ter a experiência de criar uma carteira Web3, adicionar liquidez, farmar, fazer stake, negociar uma ampla variedade de ativos, etc. Para usuários experientes que estão familiarizados com carteiras de navegador e interagem com a versão web da PancakeSwap, a versão web oferece um conjunto completo de recursos. Também é nosso objetivo educar esses novos usuários sobre os fundamentos do DeFi primeiro e depois atraí-los para nossa versão da web!

## Por que minha transação não vai?&#x20;

O Mini-Programa ainda é totalmente um aplicativo DeFi, de modo que opera da mesma forma que a interface do usuário final da web - ele interage com a carteira (carteira Binance DeFi, neste caso) para concluir transações on-chain para swap, criando LPs, fazendo stake em farms e pools.

### Taxas de gás&#x20;

Assim, a primeira coisa é **garantir que você tenha BNB suficiente para pagar a taxa de gás** das transações on-chain. Normalmente, a taxa de gás varia dependendo do número de transações na fila, se houver mais transações, uma taxa de gás mais alta pode ser necessária para realizar a transação. Na BNB Smart Chain onde o Mini-Programa é operado, a taxa de gás normalmente varia de centavos a um dólar USD em BNB. Saiba mais sobre a [taxa de gás aqui](https://academy.binance.com/en/glossary/gas).&#x20;

### Taxas de transação&#x20;

Se sua ação de troca ainda não for concluída e estiver exibindo um erro para você revisar o deslizamento(slippage) - verifique se os tokens que você está tentando trocar têm taxas e restrições nas transações.&#x20;

Não é incomum que os tokens da BNB Smart Chain incluam uma taxa de transação em seus contratos, geralmente essas taxas poderiam ser usadas para queimar, financiar uma tesouraria de um projeto de lançamento justo - por exemplo, este token APX tem um imposto de 1% sobre cada transação para enviar para um endereço de queima, de modo que mais transações significassem mais queima, agregando valor aos holders de token APX.

Com a taxa de transação, seja ela inclusiva (uma parte do valor do swap é enviada para outro lugar além do seu endereço, de modo que a saída seja menor do que o esperado para a entrada estimada) ou exclusiva (exigindo uma transferência adicional do seu endereço para enviar tokens extras para que o entrada é mais do que o esperado para a saída estimada), isso afeta o valor de entrada e saída que você concorda para assinar a transação. Em muitos casos, a transação não consegue cumprir os requisitos de entrada e saída por causa desta taxa embutida.&#x20;

### Swap com taxas de transação&#x20;

Antes de trocar quaisquer tokens, certifique-se de ter visitado o site deles para entender se eles têm um mecanismo de taxa de transação (ou imposto como muitos projetos o colocam). Se houver, certifique-se de definir uma derrapagem suficiente para acomodar a taxa de transação - por exemplo, se houver uma taxa de transação de 5%, sua derrapagem terá que ser definida em pelo menos 5% mais a derrapagem normal de negociação, dependendo do valor da negociação e da liquidez do token, digamos 5,5%-6%.&#x20;

Em alguns casos extremos, incluindo alguns golpes, alguns tokens ainda bloqueiam a maioria ou todas as transferências onchain, ou permitem apenas a venda de determinados endereços; nesse caso, é impossível trocar o token com sucesso. Aprenda sobre o token que você está tentando trocar e esteja ciente de quaisquer taxas e restrições!&#x20;

## Onde posso fornecer feedback para o Mini-Programa?&#x20;

Todos os comentários são bem-vindos e estamos sempre tentando melhorar para nossa comunidade. Para qualquer feedback sobre o Miniprograma, além do habitual [Telegram](https://t.me/PancakeSwapPortuguese) ou [Discord](https://discord.gg/pancakeswap), você também pode enviar seu feedback dentro do Miniprograma, no botão de feedback após clicar nos três pontos no canto superior direito.
