---
hidden: true
---

# FAQ de Farming

### Por que há múltiplos APRs?

No V3, você pode concentrar seus ativos enquanto fornece liquidez para aumentar sua participação em relação à liquidez total disponível, ganhando uma % maior de recompensas.&#x20;

Portanto, dependendo das configurações de faixa de preço da posição, cada posição de liquidez terá seu próprio APR de taxa LP e seu próprio APR de farming.

O APR global é calculado com a quantidade total de recompensas de CAKE em USD, dividida pela quantidade total de ativos nas posições ativas que estão atualmente em Staking no farm. Portanto, o APR global de farming é apenas uma referência genérica e não representará APRs individuais para cada posição.

Para ver seu APR de farming, verifique suas posições listadas em cada farm.

###

### O que acontece se minha posição de liquidez sair do intervalo enquanto estou em Staking no Farm?

No V3, apenas posições de liquidez ativas (dentro do intervalo) ganharão CAKE dos farms.

A posição deixará de receber recompensas de CAKE quando o preço sair do intervalo.

Se o preço voltar ao intervalo, a posição começará a receber recompensas de CAKE novamente. Nenhuma ação adicional é necessária dos usuários em Staking.



### Há alguma maneira de ajustar automaticamente minha posição para que ela esteja sempre no intervalo e ganhando recompensas de taxa?

O PancakeSwap v3 suporta depósito de liquidez com um clique via Zap, disponível na BNB Chain e Ethereum.



### É melhor sempre fazer farming com uma posição de liquidez com um intervalo menor?

Fornecer liquidez a uma faixa de preço menor ajudará a concentrar sua liquidez, aumentando suas parcelas relativas em relação à liquidez total dentro da faixa de preço, potencialmente ganhando mais recompensas de CAKE.

No entanto, lembre-se de que apenas posições de liquidez ativas ganharão recompensas de CAKE. Isso significa que você só ganhará recompensas quando o preço de negociação atual estiver dentro da faixa de preço definida na posição de liquidez.

Se precisar ajustar a faixa de preço da sua posição, você precisará retirar do Staking, remover a liquidez e criar uma nova posição com a faixa de preço atualizada. Lembre-se de que ajustes frequentes nem sempre são a estratégia mais ideal, pois realizam a perda impermanente e custam uma certa quantidade de gas para completar múltiplas transações.



### Quantas posições posso colocar em Staking em um único farm?

Não há limite máximo de posições que você pode colocar em Staking em um farm.

Mas lembre-se de que você precisará gastar gas para colher manualmente cada uma das posições. Sempre considere o custo de gas nas operações de rendimento.



### Com que frequência devo colher minhas recompensas?

A frequência de colheita das recompensas é sua decisão, mas lembre-se de que há uma pequena taxa envolvida na colheita. Você pode ver essa taxa na sua carteira ao confirmar após clicar em "Harvest"**.**

Isso mostra a taxa de colheita conforme aparece na carteira MetaMask. Carteiras diferentes mostrarão as informações de forma ligeiramente diferente. Considere deixar suas recompensas crescerem por um tempo para pagar taxas com menos frequência.



### E se eu quiser ajustar minha posição enquanto estou em Staking no farm?

Enquanto estiver em Staking no farm, você pode adicionar ou remover liquidez sem retirar do Staking. Basta localizar a posição de liquidez que deseja ajustar, clicar em seu título/ID e você deverá ver a página de detalhes da posição onde pode usar os botões "Add" e "Remove".

Se quiser ajustar as configurações de faixa de preço de uma posição de liquidez, você precisará retirá-la do Staking no farm, remover toda a liquidez e criar uma nova posição adicionando liquidez.



### O que afeta o APR de Farming?

No Farm v3, o APR de recompensa de CAKE pode variar entre posições de liquidez. Ele é baseado nos seguintes fatores:

* Taxa de emissão de CAKE para os Farms\
  \- mais CAKE gerará um rendimento maior para todos os farms. Leia mais na [nossa página de tokenomics](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)
* Multiplicador do Farm\
  \- farms com um multiplicador maior receberão mais CAKE proporcionalmente a todos os farms. Observe que os farms v3 e v2 + stable swap usam dois conjuntos separados de multiplicadores. E os farms no Ethereum e BNB Chain também usam dois conjuntos separados de multiplicadores.
* A quantidade de tokens depositados na posição\
  \- mais tokens na posição se traduz em uma participação relativa maior em relação à liquidez ativa total no pool do farm e obtém mais recompensas de CAKE
* A faixa de preço selecionada\
  \- uma faixa de preço menor permite uma maior concentração para a mesma quantidade de tokens depositados, o que se traduz em uma participação relativa maior em relação à liquidez ativa total no pool do farm e obtém mais recompensas de CAKE
* A quantidade de liquidez atualmente ativa\
  \- se houver mais usuários que depositam e concentram sua liquidez com o mesmo intervalo que você, você ganhará recompensas de CAKE em razão de uma participação relativa menor em relação ao total
* Se a posição de liquidez está ativa\
  \- apenas posições de liquidez ativas ganharão recompensas de CAKE do farm



### Por que estou vendo um pop-up de "Update Positions"?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Logo após o lançamento do V3, os Chefs implementaram uma atualização nos Farms para tornar os cálculos de recompensa mais precisos e confiáveis. Se você estiver vendo este pop-up, significa que algumas de suas posições precisarão de uma atualização.

Basta clicar em "Update All" e confirmar no pop-up da sua carteira.

Observe que os Chefs também estão aplicando esta atualização aos dados históricos de Staking entre o lançamento do Farm V3 e quando esta atualização for implementada. Se houver recompensas extras de CAKE, elas serão lançadas via airdrop para sua carteira antes de 1º de maio de 2023.



### Por que um farm de 2x no V3 tem menos APR do que um farm de 1x no V2?

Primeiro, ao comparar APRs, você precisa garantir que a liquidez total em Staking entre dois farms seja igual.

Além disso, agora temos múltiplos grupos de farms que têm seu próprio fluxo de emissões de CAKE. E cada grupo de farms compartilha conjuntos separados de multiplicadores.

Um farm individual receberá emissões de CAKE com base em:

* A = Total de CAKE por segundo/bloco para o grupo de farm ao qual pertence
* B = Número total de multiplicadores dentro do grupo ao qual pertence
* C = O multiplicador que possui

`CAKE por bloco/segundo = C / B * A`

Os números acima podem ser encontrados em cada um dos contratos [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I).



### Posso usar bCAKE nos farms v3?

Sim

O bCAKE para os Farms V3 chegará muito em breve após a implantação do Farm V3 da PancakeSwap. Fique atento.
