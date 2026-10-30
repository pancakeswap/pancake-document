---
description: '2026-08-21'
---

# Apresentando o Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Cotar cinco pares não deveria custar cinco vezes o capital. Mas on-chain, esse é o acordo que todo emissor de ativos recebe: a liquidez fica presa a cada par, então cada novo par significa colocar mais um bloco de capital, a maior parte parada, sem render nada até que aquele par exato seja negociado dentro da faixa de preço exata. Toda vez que você quer cotar um novo par, você coloca capital novo de LP nele, e esse capital fica travado naquele único par e não pode ser usado em nenhum outro lugar.

O Shared Inventory Hook (SIH) quebra esse vínculo. É o hook mais novo do PancakeSwap Infinity, e o primeiro criado para eficiência de capital.

_💡 Resumo: um hook é um smart contract (como um complemento) que se conecta a um pool do Infinity e executa lógica personalizada durante o swap, sem precisar criar um novo ambiente de negociação._

Então, como funciona?

Em vez de travar um estoque separado em cada pool, um emissor de ativos RWA financia **um único inventário compartilhado**, e o shared inventory hook cota profundidade a partir dele em qualquer par que esteja sendo negociado, just-in-time, no exato momento do swap. Pense em um único estoque abastecendo todos os pratos da cozinha, em vez de um estoque separado para cada um. Um só saldo faz o trabalho de vários.

Essa mudança é o que torna o SIH eficiente em capital, e isso aparece de três formas:

* **O capital permanece ativo e trabalhando.** A liquidez do inventário do hook é injetada just-in-time no swap, então ela está trabalhando ativamente e gerando taxas para você, em vez de ficar parada.
* **Oportunidade de taxas a partir de um único saldo, em vários pares.** Um inventário rende em todos os pares que atende, então você captura o fluxo de taxas com muito menos capital alocado.
* **Menor impacto de preço.** Como a liquidez cotada no momento do swap é mais profunda, negociações grandes têm menor impacto de preço sempre que o SIH está cotando o melhor preço.
* **Maior eficiência de capital.** Financie uma vez; o mesmo capital sustenta a profundidade em todos os pares com SIH ativado. Além disso, você pode ativar o SIH para um novo par sem adicionar capital.

> \*\*Já está convencido? Traga seus ativos on-chain do jeito eficiente em capital — preencha este formulário → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**A prova está on-chain**

O SIH entrou no ar com as bStocks em agosto, e o número que mais importa é o quanto esse capital trabalha. No snapshot mais recente do hook (21 de ago. de 2026), 75% do inventário compartilhado está ativamente alocado nos três pares (inventário do hook \~$297K, ativo \~$224K). Nos dois pares maduros, CRCLB e MUB, a utilização é de \~99% (98,96% / 98,95%). O capital que ficaria parado em pools CLAMM v3 tradicionais está dentro da faixa e cotando aqui.

Nas primeiras semanas (até 21 de ago.), os três pares negociaram \~$710K em 5.713 swaps, atendidos por um inventário compartilhado de \~$297K, gerando taxas de LP em uma faixa de 0,25%.

_**Fontes:** Dashboard interno da Dune_ **Pools ativos:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Para onde isso caminha**

O modelo foi feito para escalar: mais pares, um único saldo compartilhado se estendendo por milhares de mercados negociando 24/7. É o caminho mais rápido que já vimos para colocar toda a linha de pares de um token on-chain sem multiplicar o capital por trás dela.

Os pools SIH ativos estão na [página Earn da PancakeSwap](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001) — abra **Infinity** e procure por **Shared Inventory** nos recursos do pool. O SIH está atualmente ativado em CRCLB / USDT, MUB / USDT e GMEB / USDT.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Observação: LPs de varejo já podem adicionar liquidez a esses pools pela Earn; esse depósito se torna liquidez residente do pool, mantida separadamente do inventário compartilhado._

_**Importante:**_

_O SIH é menos exposto à variação de preço do que uma posição de LP padrão, porque o inventário só é colocado para trabalhar no momento de um swap. Não é livre de riscos. O operador ainda detém inventário que se move com o mercado. Como em qualquer estratégia on-chain, os resultados dependem de volume, inventário, hedge e condições de mercado._

Pronto para maximizar a eficiência de capital? Ative o SIH nos seus pares de tokens agora → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_Aviso legal: este conteúdo tem caráter exclusivamente informativo e educacional. Ele não deve ser interpretado como aconselhamento financeiro, jurídico ou profissional de qualquer natureza. Os preços de ativos digitais podem ser voláteis. O valor do seu investimento pode cair ou subir._
