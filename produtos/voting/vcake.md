# vCAKE

## O que é vCAKE?&#x20;

vCAKE é um número que representa o poder de votação incrementado com base na posição de stake de CAKE de prazo fixo de um usuário.&#x20;

O número vCAKE será adicionado ao seu poder de voto total.&#x20;

**Semelhante ao iCAKE, o vCAKE NÃO é um novo token.**&#x20;

vCAKE NÃO É transferível ou negociável.&#x20;

## Como o vCAKE é calculado?&#x20;

O vCAKE é calculado com base em duas variáveis:&#x20;

1. A quantidade de CAKE localizada na Pool de Staking de Prazo Fixo&#x20;
2. As durações de bloqueio restantes das posições em stake&#x20;

Para o ponto 2., é importante esclarecer que a duração restante do bloqueio não é (a) quantas semanas você comprometeu seu CAKE quando o bloqueou pela primeira vez (por exemplo, 52 semanas), mas (b) o tempo restante em seu bloqueio . Nesse caso, se você bloqueou o CAKE por 52 semanas há cerca de 10 semanas, a duração restante do stake é de 42 semanas, não de 52 semanas.&#x20;

Se a duração restante da stake for inferior a uma semana, seu vCAKE é igual à quantidade de CAKE bloqueado na pool de CAKE.&#x20;

Se a duração restante do stake for superior a uma semana, seu vCAKE é igual à quantidade de CAKE bloqueado, multiplicado pelo número de semanas restantes na posição do stake.&#x20;

Por exemplo:&#x20;

* Alice bloqueou 100 CAKE por 52 semanas; sua posição de stake será desbloqueada em 40 semanas. Ela tem `100 x 40 = 4000 vCAKE`
* Bob bloqueou 100 CAKE por 52 semanas; sua posição de stake será desbloqueada em 52 semanas. Ele tem `100 x 52 = 5200 vCAKE`
* Carole bloqueou 100 CAKE por dez semanas; e sua posição de stake terminou. Ela tem `100 vCAKE`

``![](<../../.gitbook/assets/image (103) (1).png>)``

## Como verificar o número do vCAKE?&#x20;

Se você estiver votando, encontrará o número de vCAKE no detalhamento do poder de votação clicando no botão ">" na janela "Confirmar votação".

![](<../../.gitbook/assets/image (136).png>)

Se estiver fazendo uma proposta para a comunidade, você pode verificar seu poder de votação clicando em "Verificar seu poder de votação" na parte inferior do painel "Ações".
