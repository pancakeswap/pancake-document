---
description: Use seu veCAKE para votar e decidir como a emissão de CAKE é distribuída
hidden: true
---

# Votação de Gauges

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### O que é um gauge?

Para entender a votação de gauges, você pode pensar em qualquer produto que exija emissões de CAKE como uma série de gauges. Isso inclui farms, pool de recompensa semanal de CAKE, vaults de gerenciadores de posição, etc.

Os detentores de veCAKE agora podem usar seu veCAKE como votos para decidir qual % de CAKE vai para qual produto. Quanto mais veCAKE um gauge acumula por meio da Votação de Gauges, mais emissões de CAKE serão alocadas para o pool de Liquidez / vault do gerenciador de posição subjacente.

{% hint style="info" %}
Os votos em cada época (E-0) determinam a emissão de CAKE para a próxima época (E+1), e essas mudanças só entram em vigor após o término da época atual.
{% endhint %}

#### Tipos de Gauge

Existem dois tipos de gauges: 'core' e 'non-core'. As emissões de CAKE para os primeiros são controladas pela Cozinha, enquanto a comunidade influencia as emissões para os pools 'non-core' votando com veCAKE.

1. Os gauges 'core' incluem pares com tokens principais e stablecoins (WBTC, ETH, BNB, USDC, USDT, etc.) - a Cozinha garantirá que esses pares recebam recompensas de CAKE suficientes, pois contribuem significativamente para a receita do protocolo
2. Os gauges 'non-core' representam todos os outros gauges não classificados como gauges 'core'

## Como Votar?

### 1 - Entenda o calendário de votação

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

A votação de peso dos gauges é realizada a cada duas semanas. O início de uma época, assim como o compartilhamento de receita, ocorre às 00:00 UTC toda quinta-feira de semana par.

No exemplo acima:

* A Época 1 começa às 00:00 UTC, dia 1, quinta-feira na Semana 1.
* A Época 1 termina 2 semanas depois, às 00:00 UTC, dia 15, quinta-feira na Semana 3.
* Os usuários podem votar durante 00:00 UTC do dia 1 ao dia 14.
* **Nenhum** voto pode ser feito durante 00:00 UTC do dia 14 ao dia 15, pois os votos estão sendo ajustados e contabilizados.
* Os resultados da votação serão registrados em snapshot às 00:00 UTC no dia 15. O final da Época 1.
* Os resultados da votação serão aplicados dentro de 72 horas após o encerramento de uma época.

### 2 - Torne-se elegível

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Como o veCAKE diminui gradualmente de acordo com o tempo restante de bloqueio, os resultados da votação serão coletados via snapshot ao final de cada época. Isso inclui o número total de veCAKE e o veCAKE de cada usuário.

No exemplo acima:

* Os resultados da Época 1 serão baseados nos saldos de veCAKE às 00:00 UTC do dia 15.
* Usuários cujas posições de veCAKE desbloqueiam antes ou igual ao dia 15 terão saldo de veCAKE igual a 0 no momento do snapshot. Portanto, não têm poder de voto para a Época 1.

Portanto, para se tornar elegível, você deve ter uma posição ativa de veCAKE que desbloqueie **DEPOIS** do horário de término/snapshot da época atual.

No exemplo acima:

* Se você quiser votar na época 1, deve ter uma posição de veCAKE que desbloqueie no dia 21 ou depois do dia 21, ou quinta-feira na semana 3.

### 3 - Verifique os resultados atuais da votação

Vá para "Staking de CAKE", role para baixo e procure a seção "Votação de Gauges", depois clique em "Verificar Gauges".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Na seção superior esquerda, você pode encontrar:

* Seu veCAKE.
* Horário do snapshot e horário de término da votação para a época atual.
* O número total de recompensas de CAKE a serem distribuídas na próxima época é baseado nos resultados da votação da época atual.
* A quantidade total de votos de veCAKE lançados.

No canto superior direito, você pode encontrar um gráfico de pizza representando o % de cada gauge recebido.

Na parte inferior, há uma lista completa de todos os gauges de votação. Com o número de votos que receberam e o % de peso esperado que estão obtendo na época atual. Também há um campo de "boost" e "caps", detalhando duas características importantes dos gauges. Continue lendo para mais detalhes.

#### Boost de Gauge e Limites de Emissão

Para garantir que as recompensas de CAKE vão para os gauges mais produtivos, cada gauge pode ter um boost e/ou um limite de emissão aplicado. Essas duas características podem coexistir.

O Boost de Gauge é um multiplicador aplicado ao número de votos que um gauge recebe, variando de 1x a 2,5x (gauges para pools V3 são limitados a 2x). Isso é para incentivar votos e Liquidez para pares de negociação importantes.

O limite de emissão é um teto máximo no % de peso que um gauge pode receber, variando de 2% a 20%. Isso é para promover equidade na alocação e prevenir o abuso do sistema de gauges.

Por exemplo:

* Um gauge tem 10 votos, boost de 2x e limite de 15%. O total de votos é 100.
* Após aplicar o boost, este gauge terá 20 votos, 20% de peso em relação ao total (100).
* No entanto, como tem um limite de 15%, o % final de recompensas de CAKE que este gauge recebe na próxima época será ajustado para 15%.

#### Como o Boost de Gauge e os Limites de Emissão são determinados?

Durante o processo de candidatura de um gauge, pedimos aos candidatos que proponham o valor do multiplicador de boost e o % do limite de emissões que desejam atribuir ao gauge. Estes devem ser votados pelos detentores de veCAKE, juntamente com toda a candidatura do gauge.

A opção padrão para todos os gauges é multiplicador de 1,00x e limite de emissão de 5%. Eles podem ser alterados com propostas futuras.

{% hint style="info" %}
Observe que os resultados da votação são atualizados semanalmente. Os números são calculados com base nos saldos de veCAKE às 00:00 UTC na próxima quinta-feira.
{% endhint %}

### 4 - Adicionar gauges para votar

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Para votar em um gauge, role para baixo e procure a seção "Meus Votos". Clique em "Adicionar Gauge".

Na janela pop-up, você pode adicionar gauges à sua lista de votos clicando no ícone azul "+". Você pode encontrar os resultados atuais da votação na lista, junto com boost e limites.

Para localizar rapidamente um gauge, você pode usar a filtragem para filtrar gauges por blockchains, faixas de taxa e tipos de Liquidez. Ou digite o ticker do token no campo de pesquisa.

### 5 - Selecione quanto % de veCAKE votar em cada gauge

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Depois de adicionar os gauges, você pode selecionar quanto % do seu veCAKE vai para cada um dos gauges.

Isso porque:

* O veCAKE diminui gradualmente com o tempo restante de bloqueio. É impraticável estimar e calcular exatamente quantos veCAKE votar.
* É trabalhoso votar novamente em cada época futura. Portanto, a votação de gauges é projetada para carregar suas decisões de votação em todas as épocas futuras até você fazer uma nova.

No exemplo acima:

* No momento, tenho 2,62 veCAKE.
* Decidi alocar 80% para CAKE-BNB, que são 2,10 veCAKE no momento.
* 20% para USDC-ETH, que são 0,52 veCAKE, também no momento.
* Meu total de veCAKE diminuirá gradualmente com o tempo restante de bloqueio. No momento do snapshot, posso ter menos veCAKE, mas minha decisão de divisão 80% - 20% ainda será aplicada aos resultados finais.
* Além disso, essa decisão de 80% - 20% será aplicada a todas as épocas futuras até eu atualizá-la enviando uma nova solicitação de voto. Ou até meu veCAKE chegar a 0 devido ao desbloqueio.

Após confirmar sua decisão, clique em "Enviar voto" e confirme em sua carteira.

### 6 - Atualize seus votos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Após enviar seu voto, você pode ver seus votos sendo atualizados para "Votos Atuais". E o veCAKE restante é atualizado.

Observe que a decisão de votação para cada gauge só pode ser atualizada a cada 10 dias. Depois de enviar uma solicitação de voto, todos os gauges votados terão um período de espera de 10 dias antes de você poder enviar outra solicitação de atualização.

Para atualizar sua decisão de voto, altere a porcentagem e envie novamente.

{% hint style="info" %}
Observe que após ganhar mais veCAKE adicionando CAKE ou estendendo o tempo de bloqueio, você precisa atualizar manualmente todos os gauges reenviando a solicitação de voto.

O período de espera de 10 dias ainda se aplica independentemente de você ter alterado suas decisões de % ou não.
{% endhint %}
