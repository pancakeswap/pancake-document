# Perguntas Frequentes

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FKBdfQkPj7K1TJ8HL33CY%2Fimage.png?alt=media\&token=426119f9-370c-4928-b01e-5cd9c91e6ad6)

### **Posso usar carteiras móveis para ponte CAKE? Posso usar outras carteiras além da MetaMask?**&#x20;

Até o momento, a bridge de CAKE da PancakeSwap suporta apenas Coinbase, MetaMask (e quaisquer carteiras compatíveis com MetaMask). Mais suporte de carteira será adicionado muito em breve. Para evitar copiar e colar chaves privadas ou frases iniciais entre seus dispositivos. Recomendamos a criação de um conjunto de novas carteiras nas extensões de carteira do Desktop para fazer a bridge.

### Erro ao enviar transações na bridge&#x20;

Tente inserir o valor manualmente sem clicar no botão “MAX”.&#x20;

Por favor, tente remover os números decimais do valor que deseja fazer bridge.

### O botão está mostrando "**not enough native for gas**"

Observe que para enviar CAKE para sua carteira na chain de destino. O executor precisa gastar gás. O custo do gás será cobrado via transação da bridge no token nativo da chain de origem:&#x20;

* BNB Chain- BNB&#x20;
* Ethereum - ETH&#x20;
* Aptos - APT&#x20;

Portanto, se você não tiver tokens nativos suficientes em sua carteira na chain de origem, não poderá fazer a ponte. Se o seu endereço de destino já for utilizado com um saldo utilizável do token da chain nativa, você pode tentar desligar o “gás no destino”.

### Posso fazer uma ponte de BNB Chain para Ethereum, mas para um endereço diferente

Não, você não pode.&#x20;

Para evitar erro do usuário, permitimos apenas a ponte entre o mesmo endereço ao fazer a ponte entre EVMs.

### Por que o botão mostra "X CAKE Exceeded"?&#x20;

Por segurança, há um limite de capacidade diária de quanto CAKE pode ser transposto entre BSC e Aptos. Tente novamente com uma quantidade menor de CAKE. Ou tente novamente mais tarde. Os chefs ajustarão esse limite dinamicamente com base nas demandas.

### E se a transação estiver parada em "pending"?&#x20;

As transações de bridge levarão até 30 minutos para serem processadas. Aguarde e tente pesquisar sua transação inserindo seu hash/id na [LayerZero Scan](https://layerzeroscan.com/).

Se a transação intermediária ainda estiver pendente após 60 minutos. Entre em contato com nossos administradores através de nossas [redes sociais](https://docs.pancakeswap.finance/v/portuguese-brazilian/contact-us/telegram) para obter [ajuda](https://docs.pancakeswap.finance/v/portuguese-brazilian/help).

### Eu nunca recebi meu CAKE&#x20;

As transações de transição levarão até 30 minutos para serem processadas. Aguarde e tente pesquisar seu tx inserindo seu hash/id em [LayerZero Scan](https://layerzeroscan.com/).

Ao conectar o CAKE à Aptos pela primeira vez, você pode precisar reivindicar seu CAKE manualmente. Certifique-se de que ativou "Gás no destino" ou que o seu endereço Aptos tinha APT suficiente para gás. Confira o [guia para passos detalhados para ponte para Aptos](entre-evm-e-aptos.md).

Ao fazer a bridge de CAKE para BNB Chain ou Ethereum, para algumas carteiras, você precisará adicionar manualmente o endereço do token CAKE à sua carteira para ver seu saldo.

### Por que não consigo fazer bridge com menos de 0,00000001 de CAKE?&#x20;

As Aptos Coins têm um decimal máximo de 8. Isso se aplica ao token CAKE na Aptos. Portanto, ao fazer o bridging do CAKE, as txs com valor inferior a 0,00000001 serão rejeitadas. Observe que isso também se aplica à ponte de Ethereum.&#x20;

Se você estiver fazendo bridge de uma quantia de CAKE com um decimal maior que 8, qualquer quantia menor que 0,00000001 será arredondada, ignorada e não será feita. O valor restante será deixado em sua carteira de origem.
