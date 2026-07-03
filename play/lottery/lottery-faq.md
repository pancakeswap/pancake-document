# FAQ da Loteria

## E se não houver vencedores?

Se o CAKE nos pools de prêmios não for ganho, ele não é desperdiçado! O CAKE não reclamado é transferido para a próxima rodada de Loteria.

## Meu bilhete corresponde a vários números, mas não consigo reivindicar um prêmio

Os bilhetes só são elegíveis para prêmios se os números corresponderem da esquerda para a direita. Veja a [documentação da Loteria v2](./) para uma explicação detalhada.

## Como a Loteria v2 é diferente da Loteria v1?

A Loteria v2 distribui prêmios de forma mais ampla do que a Loteria v1. Ela dá a cada bilhete 1 chance em 10 de corresponder ao primeiro número, o que significa que mais bilhetes ganharão pelo menos um pequeno prêmio. Ela também tem 6 números (acima dos 4 anteriores) que precisam ser correspondidos sequencialmente para ganhar o maior prêmio.

No geral, isso significa que mais bilhetes podem ganhar um prêmio, mas o maior jackpot será ganho com menos frequência, criando enormes pools de prêmio máximo!

**A Loteria v2 introduz:**

* preços de bilhetes mais acessíveis (\~$5 USD em CAKE por bilhete) que não oscilam muito com o preço do CAKE
* descontos por compra em volume
* 6 níveis de pool de prêmios com pools crescentes conforme mais números são correspondidos
* seleção manual de números (opcional), para que os usuários possam usar seus números da sorte
* [implementação de VRF da Chainlink](https://docs.chain.link/docs/chainlink-vrf/) para verdadeira aleatoriedade e segurança
* taxas gerais mais baixas (veja [mais abaixo nesta página](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) para mais informações)

[Saiba mais sobre os recursos, jogabilidade e prêmios da Loteria v2](./)

## Como os prêmios são distribuídos entre os níveis?

O pool de prêmios de cada nível é uma parte do total de CAKE em cada rodada de Loteria.

* | Nível (números correspondidos em ordem) | Alocação de CAKE |
  | --------------------------------------- | ---------------- |
  | Primeiro 1 número                       | 2%               |
  | Primeiros 2 números                     | 3%               |
  | Primeiros 3 números                     | 5%               |
  | Primeiros 4 números                     | 10%              |
  | Primeiros 5 números                     | 20%              |
  | Primeiros 6 números                     | 40%              |
  | Queima                                  | 20%              |

## Posso trocar meus bilhetes de volta por CAKE?

Não, uma vez comprados, você não poderá converter seus bilhetes de volta para CAKE.

## Se eu ganhar, preciso reivindicar o prêmio manualmente?

Sim, você precisará clicar no botão **Verificar Agora** em "Você é vencedor?" na página da Loteria.

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png>)

## Com que frequência ocorre a loteria?

Um sorteio de loteria ocorre a cada 12 ou 36 horas. Um sorteio ocorre por dia, alternando entre 0h UTC e 12h UTC; as próximas rodadas após as rodadas de 0h UTC serão após 36 horas, e as próximas rodadas após as rodadas de 12h UTC serão após 12 horas.

![Cronograma de injeção da Loteria](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png>)

## Qual taxa de transação pagarei ao comprar bilhetes?

Cada compra de bilhetes que você fizer será uma transação. Comprar um único bilhete em uma compra de Loteria custará a quantidade normal de taxas para uma transação.

No entanto, comprar mais bilhetes nessa compra aumentará a taxa. Comprar 100 bilhetes em vez de 1 não multiplicará a taxa por 100, mas pode aumentar o valor da taxa em 5 a 6 vezes (embora isso varie).

## Como funciona o desconto por volume?

O desconto por volume recompensa a compra de maiores quantidades de bilhetes com um desconto progressivo. Se você está comprando apenas 2 bilhetes, o desconto é insignificante, mas aumenta rapidamente conforme você aumenta o número de bilhetes a comprar em uma transação.

O desconto se aplica apenas a cada transação de até 100 bilhetes. O desconto não é transferido para a próxima transação ou próxima rodada.

## Por que só posso comprar 100 bilhetes?

Você só pode comprar no máximo 100 bilhetes em uma compra, mas pode fazer várias compras. Nada impede você de comprar mais bilhetes após seus primeiros 100.

## Se eu criar manualmente dois ou mais bilhetes com os mesmos números e eles ganharem, sou elegível para prêmios por cada bilhete?

Sim, cada bilhete é tratado como uma entrada separada na Loteria. Lembre-se de que os prêmios não serão proporcionais 1:1, pois cada bilhete vencedor que você tiver diluirá cada parte dos prêmios totais do nível.

## Cronograma de injeção: Quando o CAKE é adicionado à loteria?

Quando as pessoas compram bilhetes, o CAKE que gastam é adicionado ao pool da loteria. Além disso, 8.000 CAKE também são adicionados (injetados) ao pool da loteria a cada outra rodada em um cronograma regular ao longo de sete rodadas por semana, conforme mostrado acima na figura do cronograma da loteria.
