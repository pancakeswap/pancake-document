# Perguntas Frequentes sobre Aptos

<figure><img src="../.gitbook/assets/Aptos-faq-header.png" alt=""><figcaption></figcaption></figure>

Esta página de perguntas frequentes responde a algumas das perguntas mais comuns da comunidade PancakeSwap sobre nossa implantação na Aptos.

## Geral

### Como fazer a ponte da BSC (Binance Smart Chain) para Aptos?&#x20;

Confira nosso [guia de bridge ](obter-aptos-coins.md)para várias soluções de pontes. Se você deseja fazer a ponte do token CAKE, confira nosso [guia de bridge de CAKE](tutorial-para-fazer-bridge-de-cake.md)[.](tutorial-para-fazer-bridge-de-cake.md)&#x20;

### Qual carteira posso usar para Aptos Chain?&#x20;

Confira nosso [tutorial de carteira](crie-uma-carteira.md) para baixar e configurar sua carteira para Aptos.&#x20;

### Mostrando "Impacto de preço muito alto" ao negociar moedas

Provavelmente, isso se deve a conexões de rede ruins com os nodes da blockchain. Atualize a página e verifique sua conexão de rede.&#x20;

Se o erro persistir, significa que o par de moedas que você está tentando fazer swap não tem liquidez suficiente para o valor que você está tentando trocar. A liquidez das principais moedas será aprimorada de forma lenta e constante ao longo do tempo, e o problema de liquidez provavelmente será resolvido quando nossos Farms Aptos forem implantados. (EM BREVE!)&#x20;

### Não consegui encontrar a moeda que queria negociar&#x20;

A lista padrão no  Swap na Aptos mostra apenas moedas de projetos conhecidos com uma quantidade suficiente de liquidez. Se você deseja trocar outras moedas que não estão na lista padrão, importe-as usando o endereço da moeda.&#x20;

### Por que não consigo trocar CAKE no Swap na Aptos?&#x20;

_atualizado em 13/12/2022_

O token/moeda CAKE agora está disponível na Aptos. Confira nosso [tutorial de ponte de CAKE](tutorial-para-fazer-bridge-de-cake.md) para saber mais sobre a ponte de tokens CAKE entre Aptos e BNB Smart Chain.&#x20;

### Preciso fazer stake de CAKE na Aptos para participar dos IFOs na Aptos?&#x20;

O IFO da PancakeSwap ainda não foi implantado na Aptos. (BREVE!) Continue fazendo stake de seu CAKE, e fique ligado para mais novidades.

## Ponte de CAKE&#x20;

### Por que o pop-up e a barra de progresso mostram um tempo de espera enorme?&#x20;

Observe que, para ativos que não sejam CAKE, as transferências de saída da Aptos estão sujeitas a 1 milhão de confirmações de bloco, com duração estimada de aproximadamente 4 dias. O tempo pode mudar devido a flutuações nos tempos do bloco.&#x20;

**Para a ponte de CAKE, o tempo de espera deve ser de 3 a 10 minutos.**&#x20;

### Posso usar carteiras móveis para ponte de CAKE? Posso usar outras carteiras além da MetaMask?&#x20;

Até o momento, a bridge de Aptos da PancakeSwap suporta apenas MetaMask (e quaisquer carteiras compatíveis com MetaMask) no navegador Desktop. Mais suporte de carteira será adicionado muito em breve.&#x20;

Para evitar copiar e colar chaves privadas ou frases iniciais entre seus dispositivos. Recomendamos a criação de um conjunto de novas carteiras nas extensões de carteira do Desktop para fazer a ponte.&#x20;

### Por que o botão mostra "X CAKE Exceeded"?&#x20;

Por segurança, há um limite de capacidade diária de quanto CAKE pode ser transposto entre BSC e Aptos. Tente novamente com uma quantidade menor de CAKE. Ou tente novamente mais tarde.&#x20;

Os chefs ajustarão esse limite dinamicamente com base nas demandas.&#x20;

### E se a transação estiver parada em "pendente"?&#x20;

As transações de ponte levarão até 30 minutos para serem processadas. Aguarde e tente pesquisar sua tx inserindo seu hash/id no [LayerZero Scan](https://layerzeroscan.com/).&#x20;

Se a transação intermediária ainda estiver pendente após 60 minutos. Entre em contato com nossos administradores através de nossos canais/grupos sociais para obter ajuda.&#x20;

Observe que, para ativos que não sejam CAKE, as transferências de saída da Aptos estão sujeitas a 1 milhão de confirmações de bloco, com duração estimada de aproximadamente 4 dias. O tempo pode mudar devido a flutuações nos tempos dos blocos.&#x20;

### Eu nunca recebi meu CAKE&#x20;

As transações de ponte levarão até 30 minutos para serem processadas. Aguarde e tente pesquisar sua tx inserindo seu hash/id no [LayerZero Scan](https://layerzeroscan.com/).&#x20;

Ao fazer a ponte do CAKE para Aptos pela primeira vez, você deve reivindicar seu CAKE manualmente. Certifique-se de que ativou "Gás no destino" ou que o seu endereço Aptos tinha APT suficiente para gás. Confira o [tutorial](perguntas-frequentes-sobre-aptos.md#como-fazer-a-ponte-da-bsc-binance-smart-chain-para-aptos) para obter as etapas detalhadas para a ponte.&#x20;

Ao conectar o CAKE à BNB Smart Chain, para algumas carteiras, você precisará adicionar manualmente o endereço do token CAKE à sua carteira para verificar seu saldo. Se você não recebeu seu CAKE após 60 minutos. Entre em contato com nossos administradores através de [nossos canais/grupos sociais](../contact-us/)[ ](https://docs.pancakeswap.finance/contact-us/telegram)para obter ajuda.&#x20;

### Por que não consigo fazer bridge com menos de 0,00000001 CAKE?&#x20;

As Moedas na Aptos têm um decimal máximo de 8. Isso se aplica ao token CAKE na Aptos. Então, quando você fizer a ponte de CAKE para Aptos, txs com valor menor que 0,00000001 serão rejeitados. Se você estiver conectando uma quantia de CAKE com um decimal maior que 8, qualquer quantia menor que 0,00000001 será arredondada, ignorada e não será processada. O valor restante será deixado em sua carteira BNB Smart Chain.
