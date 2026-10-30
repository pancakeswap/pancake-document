# CLAMM Options

{% hint style="danger" %}
\[ARQUIVADO] Options – A partir de 11 de março de 2025\
Se você ainda tem liquidez para sacar, faça isso imediatamente acessando https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options apresenta uma abordagem inovadora para a negociação de opções on-chain, oferecendo aos provedores de liquidez uma plataforma para aproveitar a liquidez v3 na PancakeSwap. Isso permite que eles utilizem a liquidez tanto nos pools de liquidez v3 quanto para vender opções, ganhando as taxas de negociação padrão do AMM, prêmios de opções e recompensas adicionais, enquanto os traders podem usar essa liquidez para comprar opções de estilo americano sobre diversos tokens.

Criado pela equipe da Stryke (antiga Dopex), o protocolo de opções CLAMM introduz um sistema eficiente de provisão de liquidez dupla para traders de opções (compradores) e pools PancakeSwap v3.

Veja uma explicação estruturada de como o CLAMM Options funciona:

1. Os LPs que adicionam liquidez ao CLAMM options contribuem simultaneamente para o pool PancakeSwap v3 designado, dentro da faixa de preço escolhida por eles.
2. Quando um trader de opções (comprador) abre uma posição, a liquidez é retirada do pool v3 para viabilizar a venda de opções. O LP correspondente passa a ser um vendedor de opções e recebe um prêmio.
3. A liquidez não utilizada pelos compradores de opções permanece no pool PancakeSwap v3, podendo gerar taxas de negociação.
4. O retorno da venda de opções e do fornecimento de liquidez em um pool v3 reflete a mesma perda impermanente, garantindo que os usuários não enfrentem um risco maior do que no método convencional de adicionar liquidez a pools v3.
5. Os LPs enfrentam alguns riscos, pois a liquidez pode ficar sem uso devido à menor demanda por compra de opções. Além disso, como a liquidez é adicionada ao pool em uma faixa inativa, ela pode não gerar nenhuma taxa.

As opções CLAMM de estilo americano da PancakeSwap farão sua estreia na rede Arbitrum, oferecendo flexibilidade com diversos prazos de vencimento, de 1 hora a 24 horas.

| **Mercados**         | ARB/USDC, ETH/USDC e wBTC/USDC    |
| -------------------- | --------------------------------- |
| **Tipos de opção**   | Call e Put                        |
| **Preços de strike** | Com base nos ticks do pool v3     |
| **Prazos de vencimento** | 1H, 2H, 6H, 12H e 24H         |

**Condições de exercício:** os usuários podem exercer as posições antes do encerramento para evitar que opções in-the-money expirem sem valor. O exercício automático pode ser ativado para realizar os lucros automaticamente no vencimento, dispensando ações adicionais.

### Guia passo a passo

Aqui está o guia passo a passo de como usar o PancakeSwap CLAMM Options.

**Para traders:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Para LPs:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
