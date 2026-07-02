---
hidden: true
---

# Dumb Mode

### Visão Geral

O [**Dumb Mode**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) no PancakeSwap Perpetuals oferece uma experiência de trading simplificada, ideal para traders que preferem negociar nas flutuações minuto a minuto do valor de um ativo subjacente. O Dumb Mode simplifica o trading reduzindo o ruído, permitindo que os usuários entrem e saiam de posições de curto prazo facilmente.

### Como Funciona

Os usuários recebem uma seleção de janelas de expiração de 5 minutos, 15 minutos, 30 minutos e 1 hora com diferentes proporções de retorno sobre o investimento. Os usuários podem escolher fazer long ou short de um ativo subjacente.

Ao final do período de expiração, se o ativo subjacente estiver em uma posição vencedora (preço maior que o preço de abertura para long, preço menor que o preço de abertura para short), os usuários poderão lucrar.

Cada período de expiração tem um retorno sobre o investimento (ROI) diferente. Quanto maior o período de expiração, maior o ROI. As porcentagens e taxas são as seguintes:<br>

| Período de Expiração | ROI Vencedor (líquido de taxas)\* | ROI Perdedor | Taxas (em ganhos) |
| -------------------- | --------------------------------- | ------------ | ----------------- |
| 5 minutos            | 50%                               | -100%        | 6% do colateral   |
| 15 minutos           | 55%                               | -100%        | 6% do colateral   |
| 30 minutos           | 70%                               | -100%        | 6% do colateral   |
| 1 hora               | 83%                               | -100%        | 6% do colateral   |

\*O ROI vencedor pode ser ajustado ocasionalmente dependendo das condições de mercado. Verifique esta página para quaisquer atualizações

Por exemplo, no seguinte cenário:

* Posição Selecionada: Long
* Colateral Colocado: 100 USDT
* Período de Expiração: 60 segundos
* Preço BTCUSD na abertura: $50.000
* Preço BTCUSD após 60s: $50.001

O usuário lucrará **100USDT \* 75%= 75USDT**

Para mais informações sobre como abrir uma posição no Dumb Mode, clique [aqui](dumb-mode-guide.md).

### Mercados e Ativos de Margem

O Dumb Mode suporta trading nos seguintes mercados e ativos de margem na **BNB Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Mercado</td><td>Ativos de Margem</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

O Dumb Mode suporta trading nos seguintes mercados e ativos de margem nas **Chains Arbitrum, opBNB e Base**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Mercado</td><td>Ativos de Margem</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

O suporte para mais ativos/chains está em desenvolvimento.

### Taxas

Uma taxa de **6%** do principal ou colateral é cobrada em caso de trade vencedor. Isso já é calculado antes do ROI.

<br>
