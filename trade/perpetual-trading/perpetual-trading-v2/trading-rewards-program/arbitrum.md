# Arbitrum

Em 31 de agosto de 2023, o PancakeSwap Perpetuals lançará o Programa de Recompensas de Trading V2 no Arbitrum. Os usuários que fazem staking de [ALP no Syrup Pool de CAKE](https://pancakeswap.finance/pools?chain=arb) no Arbitrum podem desfrutar de multiplicadores de impulso. Além disso, não há período de vesting para as recompensas ganhas neste programa. Os usuários podem resgatar suas recompensas em USDC a qualquer momento. Os detalhes são os seguintes:

Hora de início: 31 de agosto de 2023, 08:00 (UTC)

Período de Atividade (Época): Toda quinta-feira das 08:00:00 UTC até a próxima quinta-feira às 07:59:59, com duração de 1 semana

Tempo de Distribuição de Recompensas: Cada ciclo é de 00:00 (UTC) a 23:59 (UTC) diariamente. As recompensas são emitidas toda quinta-feira por volta das 08:00 (UTC). Após a atualização do nível do usuário, as recompensas serão calculadas e distribuídas. Os usuários devem resgatar suas recompensas dentro de 30 dias após as recompensas serem emitidas. Caso contrário, a plataforma revogará as recompensas.&#x20;

Valor da recompensa: Pelas primeiras 5 semanas, 25% das taxas de trading (em USDC). Este pool de prêmios será então distribuído de acordo com os níveis.

Regras de atividade: Os usuários que negociam no PancakeSwap Perpetuals V2 no Arbitrum se qualificarão para o pool de prêmios

### Detalhamento de Níveis

Toda quinta-feira às 08:00:00 UTC, calculamos os dados de trading da quinta-feira anterior às 08:00:00 UTC até esta quinta-feira às 07:59:59 e então atualizamos o Nível do usuário de acordo com as regras de Nível. As regras de Nível são as seguintes (configuração suportada):

<table><thead><tr><th width="161">Nível</th><th width="249.33333333333331">Descrição</th><th>Peso</th></tr></thead><tbody><tr><td>Diamante</td><td>Volume de trading na época >=1M USD</td><td>5</td></tr><tr><td>Ouro</td><td>Volume de trading na época >=500K USD</td><td>3</td></tr><tr><td>Prata</td><td>Volume de trading na época >=250K USD</td><td>1</td></tr></tbody></table>

**Nota: Os critérios de nível e pesos estão sujeitos a alterações com base na liquidez do pool e na atividade geral de trading na plataforma**

As recompensas serão distribuídas igualmente entre todos os usuários que se qualificarem para um determinado nível

### Fórmula de cálculo das Recompensas de Trading:&#x20;

Ao final de cada ciclo de recompensas de trading, o volume de trading efetivo do usuário naquele ciclo será calculado para determinar o peso e o valor das recompensas em USDC.

A fórmula para o número de recompensas específicas é: r = min{R \* W/Sum(Wi), R \* 20%\}, os parâmetros são os seguintes:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Quantidade de recompensa em USDC a ser minerada pelo usuário para a época atual</td></tr><tr><td>R</td><td>A recompensa da época atual R=(valor em USDC da taxa ETH + valor em USDC da taxa DAI + valor em USDC da taxa BTC + taxa USDC)*0,25, dos quais 1% de taxa de Swap precisa ser deduzida na liquidação, por exemplo: quando a taxa semanal de ETH é 1 e o preço do ETH é 2.000, o valor em USDC da taxa ETH = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Peso correspondente ao nível do usuário</td></tr><tr><td>Sum(Wi)</td><td>Pontuação de peso total de todos os usuários. Wi representa o peso de qualquer usuário, e sum(Wi) representa a soma dos pesos de todos os usuários.</td></tr></tbody></table>

* A participação máxima de receita por usuário é limitada a 20% da receita reservada para o programa

Termos e Condições

* Devido à diferença nas taxas de trading para cada par de trading na V2, as recompensas que os usuários recebem podem variar mesmo que seus volumes de trading efetivos sejam iguais.
* As recompensas a serem distribuídas para cada ciclo serão armazenadas no seguinte endereço de contrato:&#x20;
* O PancakeSwap/ApolloX reserva o direito de interpretação final para esta atividade.



Aviso de Risco: O trading de futuros de criptomoedas carrega um risco substancial. Todas as atividades de trading são feitas a seu critério e por sua conta e risco. As informações aqui não devem ser consideradas como conselho financeiro ou de investimento do PancakeSwap/ApolloX. O PancakeSwap/ApolloX não será responsável por qualquer perda que possa surgir do seu uso do PancakeSwap/ApolloX.

<br>
