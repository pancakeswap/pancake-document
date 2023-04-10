# Perguntas Frequentes

### Por que existem vários APRs?

Na V3, você pode concentrar seus ativos enquanto fornece liquidez para aumentar sua participação em relação à liquidez total disponível, ganhando uma porcentagem maior de recompensas.&#x20;

Portanto, dependendo das configurações da faixa de preço da posição, cada posição de liquidez terá sua própria APR de taxa de LP e sua própria APR de farm.&#x20;

O APR global é calculado com o valor total das recompensas de CAKE em USD, dividido pelo valor total dos ativos, nas posições ativas, que estão em stake atualmente no farm. Portanto, o APR do farm global é apenas uma referência genérica e não representará os APRs individuais para cada posição.&#x20;

Para visualizar seu APR do farm, verifique suas posições listadas em cada farm.

### O que acontece se minha posição de liquidez sair da faixa (range) de preço? <a href="#what-happens-if-my-liquidity-position-goes-out-of-range-while-staking-in-the-farm" id="what-happens-if-my-liquidity-position-goes-out-of-range-while-staking-in-the-farm"></a>

Na V3, apenas as posições de liquidez ativas (dentro da faixa) ganharão CAKE dos farms.&#x20;

A posição deixará de receber recompensas de CAKE quando o preço sair do intervalo.&#x20;

Se o preço voltar ao intervalo, a posição começará a receber recompensas de CAKE novamente. Nenhuma ação adicional é necessária das partes interessadas.

### Existem maneiras de ajustar automaticamente minha posição para que ela esteja sempre dentro da faixa e ganhando recompensas de taxas?

O recurso de gerenciamento automático de posição está chegando em breve à PancakeSwap v3 com depósito de liquidez com um clique (Zap!) e farm. Fique ligado para mais detalhes.

### É melhor farmar sempre com uma posição de liquidez com um range menor?&#x20;

Fornecer liquidez em uma faixa de preço menor ajudará a concentrar sua liquidez, aumentando sua participação relativa na liquidez total dentro da faixa de preço, potencialmente ganhando mais recompensas de CAKE.&#x20;

No entanto, lembre-se de que apenas posições de liquidez ativas ganharão recompensas de CAKE. Isso significa que você só ganhará recompensas quando o preço de negociação atual estiver dentro da faixa de preço definida na posição de liquidez.&#x20;

Se você precisar ajustar a faixa de preço da sua posição, precisará desfazer o stake, remover a liquidez e criar uma nova posição com a faixa de preço atualizada. Lembre-se de que ajustes frequentes nem sempre são a estratégia ideal, pois recebem a perda impermanente e custam uma certa quantidade de gás para concluir várias transações.

### Quantas posições posso fazer stake em um único farm?&#x20;

Não há limite máximo de posições que você pode fazer stake em um farm. Mas lembre-se de que você precisará gastar gás para colher manualmente de cada uma das posições. Sempre considere o custo do gás nas operações de rendimento.

### Com que frequência devo colher minhas recompensas?&#x20;

A frequência com que você colhe suas recompensas depende de você, mas ajuda lembrar que há uma pequena taxa envolvida na colheita. Você pode ver essa taxa em sua carteira ao confirmar depois de clicar em “Colheita”.&#x20;

Isso mostra a taxa de colheita conforme aparece na carteira MetaMask. Carteiras diferentes mostrarão as informações de maneira um pouco diferente. Considere deixar suas recompensas crescerem por um tempo para que você pague taxas com menos frequência.

### E se eu quiser ajustar minha posição enquanto faço stake no farm?&#x20;

Ao fazer stake no farm, você pode adicionar ou remover liquidez sem retirá-la. Simplesmente localize a posição de liquidez que deseja ajustar e clique em seu título/id, e você verá a página de detalhes da posição onde poderá usar os botões “Adicionar” e “Remover”.&#x20;

Se você quiser ajustar as configurações de faixa de preço de uma posição de liquidez, será necessário removê-la do farm, remover toda a liquidez e recriar uma nova posição adicionando liquidez.

### O que afeta o APR do farm?&#x20;

No Farm v3, o APR de recompensa do CAKE pode variar entre as posições de liquidez. É baseado nos seguintes fatores:&#x20;

* Taxa de emissão de CAKE para os Farms\
  \- mais CAKE gerará maior rendimento para todos os farms. Leia mais em nossa [página de tokenomics](https://docs.pancakeswap.finance/v/portuguese-brazilian/tokenomics/cake/tokenomics-de-cake)&#x20;
* Multiplicador de farm\
  \- farms com um multiplicador maior terão mais CAKE proporcional a todas os outros farms. Observe que os farms v3 e v2 + stableswaps estão usando dois conjuntos separados de multiplicadores. E os farms na Ethereum e BNB Chain também estão usando dois conjuntos separados de multiplicadores.&#x20;
* O número de tokens depositados na posição\
  \-mais token na posição se traduz em uma participação relativa maior em relação à liquidez ativa total na pool do farm e obtém mais recompensas de CAKE&#x20;
* A faixa de preço selecionada\
  \- faixa de preço menor permite uma concentração maior para a mesma quantidade de token depositado, o que se traduz em uma participação relativa maior em relação à liquidez ativa total no pool do farm e obtém mais recompensas de CAKE&#x20;
* A quantidade de liquidez atualmente ativa\
  \- se houver mais usuários que depositam e concentram sua liquidez com a mesma faixa de preço que você, você ganhará recompensas de CAKE devido a uma participação relativa menor em relação ao total&#x20;
* Se a posição de liquidez está ativa\
  \- apenas posições de liquidez ativas ganharão recompensas CAKE do farm

### Por que estou vendo um pop-up "Atualizar posições"?

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F6DXLNn6s2UrDcAC46Q7Y%2Fimage.png?alt=media\&token=0fba64d9-b317-489a-87dd-3aa5c6894925)

​Logo após o lançamento da V3, os Chefs implementaram uma atualização nos Farms para tornar os cálculos de recompensas mais precisos e confiáveis. Se você estiver vendo este pop-up, isso significa que algumas de suas posições exigirão uma atualização.&#x20;

Basta clicar em "Atualizar tudo" e confirmar no pop-up da sua carteira.&#x20;

Por favor observe que os Chefs também estão aplicando esta atualização aos dados históricos do stake entre o lançamento do Farm V3 e quando esta atualização for implementada. Se houver recompensas extras do CAKE, elas serão lançadas na sua carteira antes de 1º de maio de 2023.

### Por que um farm 2x na V3 tem menos APR do que um farm 1x na V2?&#x20;

Primeiro, ao comparar APRs, você precisa garantir que a liquidez total em stake entre as duas farms seja igual.&#x20;

Além disso, agora temos vários grupos de farms que têm seu próprio fluxo de emissões de CAKE. E cada grupo de farms compartilha conjuntos separados de multiplicadores.&#x20;

Um farm individual receberá emissões de CAKE com base em:&#x20;

* A = Total de CAKE por segundo/bloco para o grupo de farms ao qual pertence&#x20;
* B = Número total de multiplicadores dentro do grupo ao qual pertence&#x20;
* C = O multiplicador tem

`CAKE por bloco/segundo = C / B * A`

Os números acima podem ser encontrados em cada um dos contratos [MasterChef](https://docs.pancakeswap.finance/code/smart-contracts/main-staking-masterchef-contract).

### Posso usar bCAKE em farms v3?

Sim

O bCAKE para Farms V3 virá logo após a implantação do Farm V3 da PancakeSwap. Fique atento.
