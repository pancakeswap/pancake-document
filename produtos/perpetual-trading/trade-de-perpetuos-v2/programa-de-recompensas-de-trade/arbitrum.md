# Arbitrum

Em 31 de agosto de 2023, Perpétuos da PancakeSwap lançará o Programa de Recompensas de Negociação V2 na Arbitrum. Os usuários que fazem stake de [ALP na Pool de Syrup de CAKE ](https://pancakeswap.finance/pools?chain=arb)na Arbitrum podem aproveitar o aumento dos multiplicadores. Além disso, não há período de carência para os prêmios ganhos neste programa. Os usuários podem reivindicar suas recompensas em USDC a qualquer momento. Detalhes a seguir:&#x20;

Horário de início: 31 de agosto de 2023, 08:00 (UTC)&#x20;

Período de atividade (época): Toda quinta-feira às 08:00:00 UTC até a próxima quinta-feira às 07:59:59, com duração de 1 semana&#x20;

Horário de distribuição de recompensas: Cada ciclo é das 00h00 (UTC) às 23h59 (UTC) diariamente.&#x20;

As recompensas são emitidas todas as quintas-feiras por volta das 08:00 (UTC). Após a atualização do nível do usuário, as recompensas serão calculadas e distribuídas. Os usuários devem reivindicar suas recompensas dentro de 30 dias após a emissão das recompensas.&#x20;

Caso contrário, a plataforma revogará as recompensas.&#x20;

Valor da recompensa: Nas primeiras 5 semanas, 25% das taxas de negociação (em USDC). Este prêmio será então distribuído de acordo com os níveis.&#x20;

Regras da atividade: Os usuários que negociarem nos Perpétuos v2 da  PancakeSwap na Arbitrum se qualificarão para o prêmio total&#x20;

Divisão de níveis&#x20;

Todas as quintas-feiras às 08:00:00 UTC, calculamos os dados de negociação da última quinta-feira às 08:00:00 UTC até esta quinta-feira às 07:59:59 e depois atualizamos o nível do usuário de acordo com as regras do nível. As regras do nível são as seguintes (a configuração é suportada):

<table><thead><tr><th width="161">Nível</th><th width="249.33333333333331">Descrição</th><th>Peso</th></tr></thead><tbody><tr><td>Diamante</td><td>Montante de Trade da época >=1M USD</td><td>5</td></tr><tr><td>Ouro</td><td>Montante de Trade da época  >=500K USD</td><td>3</td></tr><tr><td>Prata</td><td>Montante de Trade da época  >=250K USD</td><td>1</td></tr></tbody></table>

Nota: Os critérios e pesos do nível estão sujeitos a alterações com base na liquidez do pool e na atividade geral de negociação na plataforma.&#x20;

As recompensas serão distribuídas igualmente entre todos os usuários qualificados para um determinado nível&#x20;

Fórmula de cálculo de Recompensas de Trade:&#x20;

No final de cada ciclo de recompensa de trade, o volume de negociação efetivo do usuário nesse ciclo será calculado para determinar a ponderação e o valor das recompensas em USDC. A fórmula para o número de recompensas específicas é: r = min{R \* W/Sum(Wi), R \* 20%\}, os parâmetros são os seguintes:



<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Quantidade de recompensa em USDC a ser extraída pelo usuário na época atual</td></tr><tr><td>R</td><td>A recompensa da época atual R = (valor USDC da taxa ETH + valor USDC da taxa DAI + valor USDC da taxa BTC + taxa USDC) * 0,25, dos quais 1% da taxa de swap precisa ser deduzido quando se trata da liquidação, por exemplo: quando a taxa ETH semanal é 1 e o preço ETH é 2.000, a taxa ETH para o valor USDC = 1 * 2.000 * 0,99</td></tr><tr><td>W</td><td>Peso correspondente ao nível do usuário</td></tr><tr><td>Sum(Wi)</td><td>Pontuação de peso total de todos os usuários. Wi representa o peso de qualquer usuário e sum(Wi) representa a soma das pontuações de peso de todos os usuários.</td></tr></tbody></table>

* A participação máxima na receita por usuário é limitada a 20% da receita reservada para o programa&#x20;

Termos e Condições&#x20;

* Devido à diferença nas taxas de negociação para cada par de negociação na V2, as recompensas que os usuários recebem podem variar, mesmo que seus volumes de negociação efetivos sejam os mesmos.&#x20;
* As recompensas a serem distribuídas para cada ciclo serão armazenadas no seguinte endereço de contrato:
* PancakeSwap/ApolloX reserva-se o direito de interpretação final desta atividade.

Aviso de risco: a negociação de futuros de cripto acarreta um risco substancial. Todas as atividades de negociação são realizadas a seu critério e por sua própria conta e risco. As informações aqui não devem ser consideradas como conselhos financeiros ou de investimento da PancakeSwap/ApolloX. PancakeSwap/ApolloX não será responsável por qualquer perda que possa surgir do uso da PancakeSwap/ApolloX.



