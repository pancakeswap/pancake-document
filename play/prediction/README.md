# 🔮 Previsão

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction é um mercado de Previsão descentralizado, divertido e simples.

> **Preveja se o preço de BNB, BTC ou ETH vai subir ou cair – acerte para ganhar!**

### Plataformas

Você pode jogar PancakeSwap Prediction em:

* **Desktop / dApp**: [Guia de Previsão PancakeSwap](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini App (apenas BNBUSD)**: [Bot de Previsão](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Resumo: Como Funciona

1. **Escolha um ativo para apostar**: Disponível atualmente na **BNB Chain**, **zkSync Era** e **Arbitrum One**.
2. **Escolha CIMA ou BAIXO**: Preveja se o preço do ativo estará mais alto ou mais baixo quando a fase "AO VIVO" terminar (cada rodada = 5 minutos).
3. Informe o valor da aposta: Qualquer quantidade de BNB
4. **Confirme sua posição**: Uma vez registrada, sua aposta não pode ser alterada.
5. **Ganhe ou perca**:
   * Se você escolheu **CIMA**, você ganha se o _Preço de Fechamento_ > _Preço Bloqueado_ ao final da rodada.
   * Se você escolheu **BAIXO**, você ganha se o _Preço de Fechamento_ < _Preço Bloqueado_ ao final da rodada.

### Mecânicas e Taxas

* **Redes suportadas: BNB Chain, zkSync Era, Arbitrum One**
* **Frequência das rodadas**: A cada **5 minutos** (rodadas contínuas).
* **Taxa de participação**: **3%** do prêmio total de cada rodada, parte do qual é destinado à recompra de CAKE.
* **Ganhos**: Resgate a qualquer momento após a finalização dos resultados.
* **Pagamentos** são baseados na proporção das apostas em cada pool:
  * Razão de Pagamento (Pool CIMA) = _(Valor total de ambos os pools ÷ Valor do Pool CIMA)_
  * Razão de Pagamento (Pool BAIXO) = _(Valor total de ambos os pools ÷ Valor do Pool BAIXO)_
  * Veja: [FAQ](prediction-faq.md) para exemplo detalhado

### Resultados

* **Ganhou:** Você divide o prêmio total com os outros vencedores (menos a taxa de 3%)
* **Perdeu:** Você perde o valor total da sua aposta

**Casos Especiais**:

* **Empate** (Preço Bloqueado = Preço de Fechamento): A casa ganha todas as apostas.
* Se não houver apostas opostas:
  * Se você ganhar: recupera 97% da sua aposta inicial (taxa de 3% aplicada).
  * Se você perder: perde o valor total da aposta para a casa.
* **Cancelada:** ex.: falha no Oracle, os usuários recebem o reembolso do valor apostado

### Feeds de Preço (Oracles)

| Rede      | Mercados                                 | Finalidade                                                                         | Oracle                     |
| --------- | ---------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (pausado) | Define o _Preço Bloqueado_ e o _Preço de Fechamento_ (atualizado \~ a cada 20 segundos). | **Chainlink**              |
| BNB Chain | Todos                                    | Alimenta o gráfico ao vivo na interface (apenas para referência).                  | Binance / TradingView Feed |

#### **Oracle ChainLink**

* Utilizado para o Preço Bloqueado e o Preço Final de cada rodada do mercado de previsão. É atualizado em intervalos de até 20 segundos.
* Nosso contrato de previsão usa o feed de preço do Oracle ChainLink na BNB Chain para definir os preços que determinam se o usuário ganhou ou não.
* Utilizado para o gráfico "Chainlink" na interface.

#### **Binance**

* Utilizado para atualizações de preço em tempo real na interface do mercado de previsão PancakeSwap.
* Utilizado para o gráfico "TradingView" na interface.

Como estamos usando dois feeds de preço diferentes, as atualizações de preço em tempo real da Binance e o preço do Oracle ChainLink podem diferir levemente. No entanto, essa diferença não deve ser significativa.

### Endereços dos Contratos

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
