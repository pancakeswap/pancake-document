---
hidden: true
---

# FAQ do CAKE Syrup Pool

## FAQ

### Qual duração de bloqueio podemos escolher?

Você pode escolher de 1 a 52 semanas. O que você prefere?

### Quais variáveis afetam os rendimentos (%) do novo Syrup Pool CAKE (opções de Staking Flexível e Prazo Fixo)?

Como as opções de Staking flexível e de prazo fixo fazem parte do mesmo pool, as seguintes variáveis afetam o rendimento (APR/APY) de ambas:

* Total de CAKE em Staking flexível e Staking de prazo fixo (a soma de ambos). Quanto mais CAKE em Staking, menor o APR/APY.
* Total de CAKE bloqueado no Staking de prazo fixo. Mais CAKE bloqueado significa mais impulsionamentos de rendimento, resultando em menos recompensas de CAKE para outros (especialmente o Staking flexível).
* A duração média de bloqueio de todo o CAKE bloqueado no Staking de prazo fixo. Se a duração média de bloqueio aumentar, o APR/APY diminuirá.

### Posso colher as recompensas durante o período de bloqueio?

Não. Você só pode colher as recompensas quando a duração do bloqueio terminar. Isso é baseado no rendimento/retorno que estamos fornecendo, bem como nas implementações técnicas.

### Posso estender a duração do bloqueio?

Sim. Estender a duração do bloqueio adiciona mais tempo à sua **duração de bloqueio inicial**. Ao escolher estender a duração do bloqueio, note:

Nova duração estendida de bloqueio = duração de bloqueio inicial + duração adicionada

### Posso remover meu CAKE do Staking de Prazo Fixo via contrato se mudar de ideia?

Não. Seu CAKE não pode ser removido ou retirado do Staking de prazo fixo em nenhum momento até que a duração do bloqueio termine e seu CAKE seja desbloqueado.

### O que é o valor "CAKE Locked"?

O valor "CAKE Locked" é o saldo inicial de CAKE bloqueado do usuário mais as recompensas de CAKE até o momento.&#x20;

CAKE Locked = Saldo inicial de CAKE bloqueado + Recompensas de CAKE

Ao adicionar mais CAKE ao Staking de prazo fixo, o valor "CAKE to be locked" é o saldo inicial de CAKE bloqueado do usuário, as recompensas de CAKE até o momento e o CAKE sendo adicionado.

### O APR do pool CAKE de Staking de Prazo Fixo pode mudar após eu bloquear meu CAKE?

Sim, o APR do pool CAKE de Staking de prazo fixo é variável, assim como os antigos pools CAKE. O APR do pool CAKE de Staking de prazo fixo não é fixo e depende de:

* Total de CAKE em Staking no pool CAKE (a soma de Staking Flexível + Prazo Fixo).
* A duração média de bloqueio de todo o CAKE bloqueado no Staking de prazo fixo.
* Um impulsionamento de rendimento (semelhante a um multiplicador) calculado a partir da duração inicial de bloqueio do usuário. Quanto mais tempo você bloqueia seu CAKE, maior o impulsionamento de rendimento.

Por exemplo, se você bloquear seu CAKE por 52 semanas, seu impulsionamento de rendimento será maior do que se você bloquear por 26 semanas. O impulsionamento de rendimento aumenta linearmente quanto mais tempo você bloqueia seu CAKE.

### Ainda posso participar de IFOs se meu CAKE estiver bloqueado no pool de Staking de Prazo Fixo, ou precisarei comprar mais CAKE?

Não, uma quantidade separada de CAKE é necessária. No entanto, o Staking com bloqueio fornece entrada para vendas públicas de IFO. Confira o [iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md).

### Posso votar se meu CAKE estiver bloqueado no pool de Staking de Prazo Fixo?

Sim! Confira o [vCAKE](../../../welcome-to-pancakeswap/vecake-sunset/archive-vecake/vecake.md).

### Posso usar tanto o pool de Staking Flexível CAKE quanto o pool de Staking de Prazo Fixo CAKE ao mesmo tempo?

Sim, ao fazer Staking de CAKE com prazo fixo, um pool lateral de Staking flexível de CAKE aparecerá automaticamente para você escolher.

### Há alguma taxa para converter CAKE em Staking Flexível para CAKE em Staking de Prazo Fixo?

Não. Não há taxas adicionais para mover CAKE do Staking flexível para o Staking de prazo fixo, apenas taxas de gas.

### O que acontece ao final da duração do bloqueio? O que é "After Burning"?

{% hint style="warning" %}
**O After Burning queimará as recompensas futuras de CAKE e as recompensas de CAKE já ganhas.** Para evitar perder quaisquer recompensas de CAKE que você já ganhou, recomendamos iniciar um novo período de Staking de prazo fixo ou converter seu CAKE para Staking flexível ao final do seu período de Staking com bloqueio.
{% endhint %}

Quando o seu período de Staking de prazo fixo terminar e seu CAKE for desbloqueado, você terá 7 dias para completar uma de duas opções:

* Bloquear seu CAKE para iniciar um novo período de Staking de prazo fixo\
  ou
* Converter seu CAKE em Staking para Staking flexível (sem taxa de retirada de 72 horas).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20before%20after%20burning.png)

Durante esses 7 dias, você ainda ganhará CAKE.

Após 7 dias, se você não tiver completado nenhuma das duas opções, seu CAKE em Staking entrará no que é chamado de "After Burning". **Com o "After Burning", suas recompensas de CAKE (incluindo as recompensas já ganhas) começarão a ser enviadas para queima.** O % das recompensas de CAKE sendo enviadas para queima aumentará linearmente durante o período de "After Burning" de 90 dias até atingir 100%, o que significa que todas as recompensas de CAKE são queimadas.

Portanto, para não perder recompensas de CAKE, recomendamos iniciar um novo período de Staking de prazo fixo ou converter seu CAKE para Staking flexível ao final do seu período de Staking com bloqueio.

Aqui está um exemplo:

> João colocou 100 CAKE em Staking por 52 semanas, ganhou 50 CAKE durante seu período de Staking e agora o período de Staking expirou.&#x20;
>
> Ele então não realizou nenhuma ação e sua posição entrou no modo "After Burning".
>
> Durante o período de 90 dias de After Burning, todos os 50 CAKE que ele ganhou serão queimados gradualmente junto com qualquer novo CAKE ganho.&#x20;
>
> Após 90 dias, as recompensas que ele realmente ganha se tornarão 0. No entanto, os 100 CAKE que ele depositou inicialmente não serão afetados.
>
> Inicie um novo período de Staking de prazo fixo ou converta para Staking flexível, e não seja como o João.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20after%20burning%20started.png)
