# FAQ do Pottery

{% hint style="danger" %}
\[Arquivado] Pottery – A partir de 3 de novembro de 2023
{% endhint %}

## Por que precisamos do Pottery se já temos a Loteria v2?

O Pottery é um produto completamente diferente da Loteria v2. Ele combina o pool de CAKE bloqueado com a função de loteria, utilizando a implementação de VRF da Chainlink para uma aleatoriedade verdadeira e segura. Ao participar do Pottery, você não perde nenhum dos CAKE que depositou, apenas arrisca as recompensas de staking dos CAKE depositados. Este produto foi pensado para os CAKErs mais avessos a risco, mas que ainda assim gostariam de participar de um produto desse tipo. É uma forma fácil, divertida e segura de ter a chance de ganhar alguns CAKE. Saiba mais sobre [a estrutura do produto aqui](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery).

## O Pottery está substituindo a Loteria v2 original?

O Pottery não está substituindo a Loteria v2 original. Os dois produtos são operados e executados separadamente. Você pode participar de ambos!

## Como o Pottery ajuda a PancakeSwap e o CAKE?

Oito por cento (8%) do prêmio total distribuído a cada semana serão cobrados como taxas para queima, o que agrega valor ao CAKE. Pretendemos revisar e ajustar a estrutura de taxas conforme necessário após a fase beta do produto.

## Para que serve a fase beta do Pottery?

Por causa das operações deste novo produto, como empréstimo da tesouraria, gerenciamento de coortes e sorteio. O produto começará na fase beta, com um depósito total limitado para cada Pottery, para garantir que tudo funcione sem problemas. Depois de passarmos da fase beta, poderemos revisar e ajustar diferentes parâmetros com base nas operações e no feedback da comunidade, como as taxas, a frequência de cada coorte, o período de bloqueio etc.

## Por que meus CAKE precisam ficar bloqueados por 10 semanas?

Se o Pottery pudesse simplesmente usar o pool de staking flexível, a estrutura do produto seria muito mais simples, semelhante a produtos como PoolTogether e Moonpot. No entanto, o rendimento atual do pool de staking flexível não é suficiente para gerarmos um prêmio significativo para o sorteio. Por isso, a decisão foi bloquear os CAKE por uma duração moderada, para equilibrar as recompensas que podem ser usadas para financiar o prêmio. Com mais operações e feedback da comunidade, poderemos revisar e ajustar a duração do bloqueio no futuro.

## Por que não consigo sacar?

Observe que o botão de saque só ficará ativo e disponível após 10 semanas da data de bloqueio. A data de saque é calculada com base em 10 semanas após a data e hora do bloqueio – 23:59 UTC na primeira segunda-feira de cada mês.

## Por que não consigo ver meu depósito?

Pode haver algum atraso ocasional por causa da leitura do Subgraph. Haverá um aviso quando houver atrasos – normalmente o valor correto deve aparecer se você verificar novamente após 15 minutos.

## Como sei se ganhei no sorteio semanal?

Após cada sorteio, na sexta-feira por volta do meio-dia UTC, você pode ver os resultados e os vencedores no painel Finished Rounds. Outra forma de verificar se você ganhou em algum sorteio semanal é consultar o painel Claim para ver se há algum prêmio a ser resgatado. Confira [esta página sobre como participar](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery/how-to-play-pottery)!

## Qual é a fonte de financiamento do prêmio?

Os prêmios são financiados pelas recompensas de staking dos depósitos. No entanto, como as recompensas de staking do pool de staking bloqueado de CAKE só são distribuídas após a duração do bloqueio – 10 semanas neste caso, para uma melhor experiência do produto e para viabilizar os sorteios semanais logo após a data do depósito, o contrato toma emprestado da tesouraria de CAKE 80% do total estimado de recompensas de staking da coorte, com base no APR no momento do bloqueio. Os CAKE emprestados são usados para o pagamento de cada sorteio semanal. Saiba mais sobre [a estrutura do produto aqui](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery)!

## Se eu ganhar, preciso resgatar o prêmio manualmente?

Sim, você precisará clicar no botão Claim no painel Claim da página do Pottery.

## Com que frequência acontece o Pottery?

Cada coorte do Pottery fica aberta para depósitos a partir da sexta-feira anterior, por volta das 10:00 UTC, e fecha na primeira segunda-feira de cada mês às 23:59 UTC, salvo algum arranjo especial com aviso prévio. Cada coorte terá 10 sorteios semanais, em 10 sextas-feiras consecutivas, ao meio-dia UTC.

O primeiro Pottery abrirá para depósitos em 5 de agosto de 2022 e o bloqueio ocorrerá em 8 de agosto de 2022 às 23:59 UTC.

## Por que o depósito no Pottery só abre uma vez por mês?

Esse arranjo combina os depósitos para enviá-los diretamente ao pool de staking bloqueado, de modo que o contrato Pottery da coorte consiga coordenar as recompensas de staking do depósito a partir do pool de staking bloqueado. Com mais operações e feedback da comunidade, poderemos revisar e ajustar a frequência no futuro.

## Qual é o limite para depositar?

Há um depósito mínimo de 1 CAKE. Na fase beta do produto, também haverá um limite máximo de depósito para cada coorte, que você pode ver no painel Deposit ao fazer o depósito. Isso serve para garantir que tudo do lado operacional, incluindo o empréstimo da tesouraria, o staking bloqueado e o sorteio, funcione sem problemas. Embora o máximo que você pode depositar seja o limite máximo de depósito daquela coorte (se ninguém mais tiver depositado CAKE), você ganharia todos os prêmios; porém, isso também significa que o retorno final que você receberá é o mesmo que colocar seus CAKE no pool de staking bloqueado por 10 semanas, mas você também estaria pagando as taxas do Pottery.

## Por que precisamos do sistema de coortes? Por que não juntamos tudo?

Como o Pottery interage com o staking de prazo fixo de CAKE, qualquer depósito só pode ser sacado após a duração do bloqueio. Se quiséssemos juntar todos os depósitos, embora possamos adicionar mais depósitos após o bloqueio inicial e também bloqueá-los por 10 semanas (a partir do momento do novo depósito), os primeiros depositantes não conseguiriam sacar no prazo.

## O que é o token SHARE?

Os tokens SHARE são gerados e distribuídos quando você deposita no Pottery. Eles representam e servem como comprovante da sua participação no pool de depósitos.

No saque, o token SHARE será transferido de volta ao contrato do Pottery e queimado.

## Onde posso dar feedback sobre este produto?

Fique à vontade para falar conosco no [Telegram](https://t.me/pancakeswap) ou no [Discord](https://discord.gg/pancakeswap) se ainda tiver dúvidas sobre o formato ou se tiver algum feedback para nos ajudar a melhorar ainda mais!
