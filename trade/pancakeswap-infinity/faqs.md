# FAQs

1. **Como o Infinity é diferente do PancakeSwap V3?**\
   O Infinity adiciona novos recursos como hooks programáveis, mais [tipos de pool](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (como LBAMM e CLAMM), e economias de gas. No entanto, a mecânica principal de Swap e provisão de Liquidez é amplamente semelhante à v3, exceto por algumas diferenças menores nos pools LBAMM para provisão de Liquidez.\
   <br>
2.  **Qual é a diferença entre LBAMM e CLAMM?**

    1. **LBAMM (Liquidity Book AMM):** Usa bins de Liquidez, cada um contendo Liquidez em diferentes níveis de preço. Os LPs podem fornecer Liquidez entre bins, e os Swaps são executados em um único nível de preço dentro de um bin.
    2. **CLAMM (Concentrated Liquidity AMM):** Permite que os usuários forneçam Liquidez dentro de intervalos de preço personalizados, como no PancakeSwap V3.

    \
    Para mais detalhes, visite [aqui](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **Como faço para resgatar minhas recompensas de Farm e por que é limitado a cada 8 horas?**\
   Você pode resgatar as recompensas de Farm de suas posições de Liquidez clicando no botão "Harvest". O Infinity permite o resgate em lote de todas as posições de Farm ativas, economizando custos de gas. As recompensas são calculadas e processadas a cada 8 horas para otimizar os custos de gas e computação. \
   \
   Para mais detalhes sobre o mecanismo de farming, visite [aqui](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **Como os hooks do Infinity funcionam?**\
    Os hooks são extensões de contratos inteligentes personalizáveis que adicionam funcionalidade extra a um pool. Eles podem acionar ações adicionais durante Swaps ou eventos de Liquidez — por exemplo, ajustando taxas, oferecendo descontos ou aplicando outra lógica.<br>

    Os hooks são anexados a um pool quando ele é criado. Na maioria dos casos, **os usuários não precisam tomar nenhuma medida extra**. Desde que você esteja fazendo Swap ou fornecendo Liquidez normalmente, você se beneficiará automaticamente da lógica do hook se ela se aplicar a esse pool.<br>

    👉 **Você pode visualizar os hooks ativos e seus detalhes na página de cada pool, na seção "Recursos do Pool".**\
    <br>
5.  **Por que não recebi nenhuma taxa ao retirar minha posição de um pool LBAMM?**\
    Nos pools LBAMM (Liquidity Book AMM), as taxas são automaticamente adicionadas aos seus bins de Liquidez ativos. Isso significa que:

    1. Quando você retira sua posição, as taxas ganhas estão incluídas nos valores totais de tokens que você está retirando.
    2. Ao contrário dos AMMs tradicionais, não há um saldo separado de "taxas para coletar" — tudo está embutido no valor da sua posição.

    \
    Se você não notou tokens adicionais ao retirar, pode ser porque:

    1. Sua posição pode ter incorrido mais perda impermanente do que as taxas coletadas devido a movimentos de preço durante a duração da sua posição.
    2. Sua Liquidez não estava em bins ativos onde as negociações ocorreram.
