# Perguntas Frequentes da Loteria

## E se não houver vencedores?&#x20;

Se o CAKE da premiação não for ganho, ele não será desperdiçado! O CAKE não reivindicado passa para a próxima rodada da Loteria.

## Meu bilhete vários números sorteados, mas não consigo receber o prêmio&#x20;

Os bilhetes só são elegíveis para prêmios se corresponderem aos números da esquerda para a direita.\
Veja a [Documentação da Loteria v2](./) para uma explicação completa.

## Como a Loteria v2 é diferente da Loteria v1?&#x20;

A Loteria v2 distribui prêmios mais amplamente do que a Loteria v1. Isso dá a cada bilhete uma chance de 1 em 10 de acertar o primeiro número, o que significa que mais bilhetes ganharão pelo menos um pequeno prêmio. Ele também possui 6 (acima de 4) números que precisam ser combinados sequencialmente para ganhar o maior prêmio.

No geral, isso significa que mais bilhetes podem ganhar um prêmio, mas o maior prêmio acumulado será ganho com menos frequência, resultando em enormes prêmios no topo!&#x20;

**Loteria v2 introduz:**

* preços de bilhetes mais baratos (\~ $ 5 USD em CAKE por bilhete) que não variam muito com o preço do CAKE
* desconto de compra de bilhetes no atacado
* Faixas de prêmios de 6 níveis com prêmios crescentes à medida que mais números são combinados
* seleção manual de números (opcional), para que os usuários possam usar seus números da sorte
* [Implementação do VRF da Chainlink](https://docs.chain.link/docs/chainlink-vrf/) para aleatoriedade verdadeira e segura
* taxas gerais mais baixas (veja [abaixo nesta página](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) para mais informações)

[Saiba mais sobre as características, gameplay e prêmios da Loteria v2](./)

## Como os prêmios são divididos entre as faixas ?

A premiação de cada faixa é uma parte do CAKE total em cada rodada da Loteria.

* | Bracket (numbers matched in order) | CAKE Allocation |
  | ---------------------------------- | --------------- |
  | First 1 number                     | 2%              |
  | First 2 numbers                    | 3%              |
  | First 3 numbers                    | 5%              |
  | First 4 numbers                    | 10%             |
  | First 5 numbers                    | 20%             |
  | First 6 numbers                    | 40%             |
  | Burn                               | 20%             |

## Posso trocar meus bilhetes de volta para o CAKE?

Não, uma vez comprado, você não poderá converter seu bilhetes de volta para CAKE.&#x20;

### Se eu ganhar, preciso reivindicar o prêmio manualmente?&#x20;

Sim, você precisará clicar no botão **Check Now** em "Você é um vencedor?" na página da Loteria.

![](<../../.gitbook/assets/image (150).png>)

## Com qual frequência ocorre a loteria?&#x20;

Um sorteio de loteria ocorre a cada 12 ou 36 horas. Um sorteio de loteria ocorre todos os dias alternando entre 0:00 UTC e 12:00 UTC, as próximas rodadas após as 0:00 UTC serão após 36 horas, as próximas rodadas após as 12:00 UTC serão após 12 horas.

![Lottery injection schedule](<../../.gitbook/assets/Lottery Schedule Update Feb 4.png>)

## Qual taxa de transação pagarei pela compra dos bilhetes?&#x20;

Cada compra de bilhete que você fizer será uma transação. A compra de um único bilhete em uma compra de loteria custará o valor normal das taxas de uma transação.&#x20;

No entanto, comprar mais bilhetes nessa compra aumentará a taxa. A compra de 100 bilhetes em vez de 1 não multiplicará a taxa por 100, mas pode aumentar o valor da taxa em 5 a 6 vezes (embora isso varie).&#x20;

## Como funciona o desconto de atacado?&#x20;

O desconto de atacado recompensa a compra de quantidades maiores de bilhetes com um desconto escalonado. Se você estiver comprando apenas 2 bilhetes, o desconto é insignificante, mas aumentará rapidamente à medida que você aumentar o número de bilhetes para comprar em uma única transação.&#x20;

O desconto aplica-se apenas a cada transação até 100 bilhetes. O desconto não é transferido para a próxima transação ou próxima rodada.&#x20;

## Por que só posso comprar 100 bilhetes?&#x20;

Você só pode comprar no máximo 100 bilhetes em uma compra, mas pode fazer várias compras. Não há nada que o impeça de comprar mais bilhetes após os primeiros 100.&#x20;

## Se eu criar manualmente dois ou mais bilhetes com os mesmos números e eles ganharem, posso receber prêmios para cada bilhete?&#x20;

Sim, cada bilhete é tratado como uma entrada separada na Loteria. Lembre-se de que os prêmios não serão 1:1, pois cada bilhete premiado dilui cada parte dos prêmios totais da faixa de prêmio.&#x20;

## Cronograma de injeção: Quando o CAKE é adicionado à loteria?&#x20;

Quando as pessoas compram bilhetes, o CAKE que gastam é adicionado ao pote da loteria. Além disso, 10.000 CAKE também são adicionados (injetados) ao pote da loteria a cada duas rodadas em uma programação regular ao longo de sete rodadas por semana, conforme mostrado acima na figura da programação da loteria.&#x20;

Este cronograma de injeção começou com a rodada 440.
