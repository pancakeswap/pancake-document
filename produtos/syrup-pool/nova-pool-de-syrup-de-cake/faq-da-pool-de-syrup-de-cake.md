# FAQ da Pool de Syrup de CAKE

## FAQ

### Qual duração de bloqueio nós podemos escolher?

Você pode escolhar de 1-52 semanas. Quanto você prefere?

### Quais variáveis afetam os novos APYs da Pool de Syrup de CAKE (opções de Stake de prazo fixo e flexível)?

Como as opções de stake flexível e de prazo fixo fazem parte da mesma pool, as seguintes variáveis afetam o APY de ambos:

* Total de CAKE em stake flexível e de prazo fixo (a soma de ambos). Quanto mais CAKE em stake, menor o APY.
* A duração média do bloqueio de todos os CAKE bloqueados no stake de prazo fixo. Se a duração média do bloqueio aumentar, o APY diminuirá.

### Posso coletar as recompensas durante o período bloqueado?

Não. Você pode coletar as recompensas apenas quando a duraçao do bloqueio terminar. Isso é baseado no rendimento/retorno que estamos fornecendo, bem como nas implementações técnicas.

### Eu posso aumentar meu tempo de bloqueio?

Sim. Estender a duração do bloqueio adiciona mais tempo à duração inicial do bloqueio. Ao optar por estender a duração do bloqueio, observe:

Nova duração estendida do bloqueio = duração inicial do bloqueio + duração adicionada

### Eu posso remover meu CAKE do stake de Prazo Fixo através do Contrato Inteligente se eu mudar de ideia?

Não. Seu CAKE não pode ser removido ou sacado do stake de prazo fixo em algum momento até que a duração do bloqueio termine e seu CAKE seja desbloqueado.

### O que é a quantidade de "CAKE Locked"?

O valor "CAKE Locked" é o saldo inicial do CAKE bloqueado de um usuário mais as recompensas do CAKE até o momento.&#x20;

CAKE Bloqueado = Saldo inicial de CAKE bloqueado + recompensas de CAKE&#x20;

Ao adicionar mais CAKE ao staking de prazo fixo, o valor do "CAKE a ser bloqueado" é o saldo inicial do CAKE bloqueado do usuário, as recompensas do CAKE até o momento e o CAKE sendo adicionado.

### O APY do stake de Prazo Fixo de CAKE pode mudar depois que eu bloquear meu CAKE?

Sim, o APY da pool de stake de prazo fixo da CAKE é variável, assim como as pools de CAKE antigas. O APY da pool de stake de prazo fixo da CAKE não é fixo e depende de:

* Total de CAKE em stake na pool de CAKE (a soma de Stake Flexível + Prazo Fixo).
* A duração média do bloqueio de todos os CAKE bloqueados em staking de prazo fixo.
* Um ampliador de rendimento (semelhante a um multiplicador) calculado a partir da duração inicial do bloqueio de um usuário. Quanto mais tempo você bloquear seu CAKE, maior será o multiplicador de rendimento.

Por exemplo, se você bloquear seu CAKE por 52 semanas, o multiplicador do seu rendimento será maior do que se você bloquear seu CAKE por 26 semanas. O multiplicador de rendimento aumenta linearmente quanto mais tempo você trava seu CAKE.

### Eu posso ainda participar de IFOs se meu CAKE estiver bloqueado no stake de prazo fixo, ou eu preciso comprar mais CAKE?

Mais informações sobre isso serão divulgadas em breve.

### Eu posso votar se meu CAKE estiver bloqueado na Pool de stake de prazo fixo?

Mais informações sobre isso serão divulgadas em breve.

### Eu posso usar tanto a pool de CAKE de stake flexível quanto o stake de prazo fixo ao mesmo tempo?

Não. Conforme mencionado acima na seção "Qual é a diferença", ambas as opções fazem parte da mesma pool única. Atualmente, você nunca pode ter CAKE em stake de prazo fixo e flexível ao mesmo tempo.&#x20;

Temos várias soluções no futuro para permitir que os usuários usem stake flexível e stake de prazo fixo ao mesmo tempo, mas, por enquanto, você pode escolher apenas uma delas.

### Existe uma taxa para converter CAKE do stake Flexível para o Stakee de Prazo Fixo?

Não. Não existe taxas adicionais para mover o CAKE do stake flexível para o stake de prazo fixo, só a taxa da rede.

### O que acontece no fim do período de bloqueio? O que é "After Burning"?

Quando seu período de stake de prazo fixo termina e seu CAKE é desbloqueado, você tem 7 dias para concluir uma das duas opções:

* Bloquear seu CAKE para iniciar um novo período de stake de prazo fixo ou
* Converter seu CAKE em stake em stake flexível (sem taxa de retirada de 72 horas).

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F6h4oQWJdTFziWwwEMFkY%2Fcake-pool-lock-end.png?alt=media\&token=0d799ba6-0544-48ae-a320-69563cdca064)

Durante esses 7 dias, você ainda ganhará CAKE.

Após 7 dias, se você não tiver feito uma das duas opções, seu CAKE em stake entrará no que se chama de "After Burning/Queima posterior". **Com "After Burning", suas recompensas de CAKE (incluindo as recompensas já ganhadas) vão começar a ser enviadas para queima**. A % das recompensas de CAKE enviadas pra queima será aumenta linearmente ao longo de um período de 90 dias, o que significa que todas suas recompensas de CAKE ganhas serão queimadas.

Portanto, para evitar perder as recompensas de CAKE, recomendamos iniciar um novo período de stake de prazo fixo ou converter seu CAKE em stake flexível no final do período de stake bloqueado.

Aqui está um exemplo:

> John fez stake de 100 CAKE por 52 semanas, ganhou 50 CAKE durante seu período de stake e agora o período de stake acabou.&#x20;
>
> Ele então não realizou nenhuma ação e sua posição foi para o modo "Queima posterior/After Burn".&#x20;
>
> Durante o período de 90 dias após a queima, todos os 50 CAKE que ele ganhou serão queimados gradualmente junto com qualquer novo CAKE ganho.&#x20;
>
> Após 90 dias, as recompensas que ele realmente ganhará será 0. No entanto, os 100 CAKE que ele depositou inicialmente não serão afetados.&#x20;
>
> Inicie um novo período de staking de prazo fixo ou converta para staking flexível e não seja como John.

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FSov3mDReLzedqxYe5UeZ%2Fcake-pool-lock-burn.png?alt=media\&token=3e2587bb-9861-4c4f-9848-48f48464189d)
