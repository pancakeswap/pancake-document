# FAQ

### Bloqueei meu CAKE ou migrei minha posição do pool de CAKE. Por que ainda tenho 0 cotas? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

As cotas são atualizadas a cada distribuição semanal às 00:00 UTC toda quinta-feira.

As recompensas são acumuladas sempre que você termina de fazer Staking por uma época completa.&#x20;

As épocas são períodos de 7 dias, começando toda quinta-feira às 00:00 UTC. Por exemplo, se você fizer Staking na terça-feira, sua primeira época começará na quinta-feira. Assim que terminar de fazer Staking até a próxima quinta-feira, você poderá resgatar suas recompensas desta quinta-feira até a próxima quinta-feira, ou seja, a época 1.

Volte toda quinta-feira para ver os números de recompensas atualizados.

### Por que minhas cotas/recompensas estão em 0 mesmo tendo uma posição ativa de Staking? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Ao calcular as recompensas, a duração restante do bloqueio é arredondada para baixo em semanas. Portanto, para receber cotas, você deve garantir que sua posição de Staking desbloqueie não antes da próxima quinta-feira às 00:00 UTC.

Por exemplo, a semana 1 começa às 00:00 UTC, quinta-feira, 1 de janeiro. Para receber recompensas para a distribuição da semana 1, você deve:

* Participar antes de 00:00 UTC, 1 de jan.
* Ter uma posição ativa de Staking de veCAKE, que desbloqueie igual ou depois de 00:00 UTC, 15 de jan. (quinta-feira na semana 3)

Observe que se sua posição de Staking desbloquear às 00:00 UTC, 8 de jan (quinta-feira na semana 2), você ainda receberá 0 recompensas para a semana 1 devido ao seu saldo de veCAKE se zerando às 00:00 UTC, 8 de jan.

### Posso participar de um período de distribuição no meio da semana? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Não, como mencionado, as recompensas só podem começar a acumular quando você já está fazendo Staking no início da época, que é toda semana às 00:00 UTC, quinta-feira.&#x20;

### Como recebo mais recompensas? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Como suas cotas nos pools são calculadas com base no saldo de veCAKE no momento da distribuição, que ocorre às 00:00 UTC na próxima quinta-feira, para receber mais recompensas, simplesmente aumente seu saldo de veCAKE:

* Bloqueando mais CAKE na posição de Staking de veCAKE
* Renovando sua posição de Staking

Observe que após adicionar CAKE ou estender, suas cotas só serão atualizadas após o início da próxima época, que é às 00:00 UTC na próxima quinta-feira.

### Por que as recompensas injetadas semanalmente não correspondem 100% ao volume exibido em vários rastreadores (como a página de Informações)? Por que as recompensas semanais do pool de CAKE não correspondem 100% aos resultados da votação de gauges?

O número de recompensas de CAKE injetadas semanalmente pode não corresponder 100% aos números calculados a partir do volume exibido em vários rastreadores. Múltiplos fatores externos podem impactar o número de recompensas de CAKE que podem ser convertidas:

* Preço do token CAKE enquanto a taxa de negociação está sendo convertida e processada
* Preços dos ativos subjacentes enquanto a taxa de negociação está sendo convertida e processada
* Para economizar gás e custo operacional, as receitas de blockchains outras que não a BNB Chain são processadas mensalmente. Elas serão injetadas com um atraso de um mês com média semanal.
* Alguns pares de Trading podem ter Liquidez insuficiente durante o processamento da taxa de negociação.
* Alguns pares de Trading podem conter tokens com lógica personalizada que impede o processamento de suas taxas.
* Atrasos nas transações devido ao desempenho de infraestruturas e sistemas de suporte.

Os Chefs estão trabalhando arduamente para aplicar ferramentas e práticas para garantir que mais taxas de negociação geradas possam ser processadas e convertidas em CAKE.
