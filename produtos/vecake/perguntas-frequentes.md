# Perguntas Frequentes

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FH1GTiSfrf2AgKloqfK20%2Fimage.png?alt=media\&token=36c94cba-9e7d-4642-ae9f-d7751a9c2c57)

### Qual é a diferença entre CAKE bloqueado e veCAKE?&#x20;

veCAKE é uma nova versão de staking de CAKE de prazo fixo com mais benefícios e poder para holders de CAKE bloqueados. Incluindo peso de medidores de votação, incentivos extras, aumento de rendimento e muito mais.&#x20;

### O que acontece com as recompensas da pool de CAKE quando o novo veCAKE é implantado&#x20;

As emissões de recompensa da pool de CAKE serão direcionadas para recompensar todos os holders de veCAKE de acordo com seu saldo de veCAKE em relação ao fornecimento total. As recompensas de CAKE e as recompensas semanais de compartilhamento de receitas agora podem ser reivindicadas semanalmente na quinta-feira. Observe que para continuar recebendo recompensas, os usuários precisarão migrar para o novo staking veCAKE.&#x20;

### Qual é a duração máxima que posso bloquear meu CAKE&#x20;

A duração máxima que você pode bloquear seu CAKE foi estendida para 4 anos.&#x20;

### O veCAKE é um novo token? Pode ser transferido?&#x20;

veCAKE é um número gerado ao vivo com base no número de CAKE bloqueados e no tempo restante de bloqueio. Não é um token padrão e não pode ser transferido.&#x20;

### Por que meu saldo veCAKE mudou? Como calcular seu saldo?&#x20;

O saldo do veCAKE está diminuindo linearmente para 0 com base na duração restante do bloqueio. Portanto, quando nos aproximamos do tempo de desbloqueio, o seu saldo diminui.&#x20;

O saldo de veCAKE pode ser calculado assim:

```
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

### Como aumentar meu veCAKE?&#x20;

Depois de ter uma posição veCAKE ativa, você pode adicionar mais CAKE ou renovar/estender a duração do bloqueio para aumentar seu saldo veCAKE.&#x20;

### O que acontece quando a posição é desbloqueada? Posso renovar imediatamente?&#x20;

Quando a posição de staking do veCAKE estiver desbloqueada, você poderá retirar todo o CAKE em stake. Para renovar sua posição, você precisa retirar todo o CAKE e configurar uma nova posição de staking, escolhendo o valor a ser bloqueado e a duração do bloqueio.&#x20;

### Bloqueei por 1 semana. Por que o tempo de bloqueio restante é inferior a 1 semana?&#x20;

Quando você bloqueia com o novo veCAKE, o tempo de desbloqueio é arredondado para a quinta-feira mais próxima com o horário UTC. Por exemplo, quando você bloqueia por 1 semana na terça-feira, o horário real de desbloqueio será na próxima quinta-feira, ou seja, 2 dias depois.&#x20;

Você pode visualizar seu tempo real de desbloqueio na parte inferior.&#x20;

### Posso bloquear mais CAKE na Pool  de CAKE?&#x20;

Não.&#x20;

Assim que o veCAKE for implantado, a pool de staking de CAKE será descontinuada e não aceitará mais nenhuma extensão ou depósito de CAKE.&#x20;

Para bloquear o CAKE e aproveitar seus benefícios, acesse a página do veCAKE.

### Por que não posso migrar?&#x20;

A migração da pool de CAKE para o veCAKE exige que você tenha uma posição ativa. Se a sua posição de stake da pool de CAKE já estiver desbloqueada, basta retirar esses CAKE e criar uma posição de stake veCAKE nativa.

Em alguns casos, a migração não pode ser executada quando o tempo restante de bloqueio da pool de CAKE for inferior a 7 dias. Nesse caso, basta aguardar o desbloqueio, retirar os CAKE e criar uma posição de staking nativa do veCAKE.&#x20;

### Posso retirar antecipadamente meu CAKE bloqueado?&#x20;

Não.&#x20;

Uma vez bloqueado, o CAKE será apostado no contrato veCAKE até o momento do desbloqueio.&#x20;

### Posso migrar parcialmente meu CAKE?&#x20;

Não.

Você só pode migrar toda a sua posição na pool de CAKE de uma só vez.&#x20;

### O que acontecerá com iCAKE, bCAKE, vCAKE e rCAKE?&#x20;

**Para iCAKE**:&#x20;

A cozinha está trabalhando duro para atualizar o iCAKE para suportar o novo veCAKE. Esperamos que todos os futuros IFOs sejam executados com o veCAKE como uma versão atualizada do iCAKE.&#x20;

**Para bCAKE:**&#x20;

O impulsionamento de FArm do bCAKE também será atualizado para suportar veCAKE. Em breve, os usuários poderão aumentar não apenas o V3, mas também outros tipos de liquidez da PancakeSwap com seu veCAKE.&#x20;

**Para vCAKE:**&#x20;

O poder de votação do snapshot será atualizado em breve para usar apenas o número de saldo veCAKE.&#x20;

**Para rCAKE:**&#x20;

Todos os holders de veCAKE (nativos ou migrados) serão automaticamente inscritos na nova pool de compartilhamento de receitas. O compartilhamento de receita são distribuídas de acordo com o cronograma existente. A antiga pool de compartilhamento de receita será descontinuada e os usuários poderão reivindicar suas recompensas pendentes acessando o card de benefícios.
