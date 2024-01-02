---
description: Use seu veCAKE para votar e decidir como a emissão de CAKE será distribuída
---

# Medidores de Votação

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FbdAaemJ2yaQPP3ryTKQJ%2Fimage.png?alt=media\&token=e755016f-a788-4e9a-afcc-59b994ee6d99)

## O que é um medidor?&#x20;

Para entender os medidores de votação, você pode pensar em qualquer produto que exija emissões de CAKE como uma série de medidores. Isso inclui farms, conjunto de recompensas semanais de CAKE, cofres de gerenciador de posição, etc.&#x20;

Os holders de veCAKE agora podem usar seu veCAKE como votos para decidir quanto% do CAKE vai para qual produto. Quanto mais veCAKE um medidor acumula por meio da votação, mais emissões de CAKE serão alocadas à pool de liquidez/cofre do gerenciador de posição subjacente.

{% hint style="info" %}
Os votos em cada época (E-0) determinam a emissão de CAKE para a próxima época (E+1), e essas alterações entram em vigor somente após a conclusão da época atual.
{% endhint %}

### Tipos de medidores&#x20;

Existem dois tipos de medidores - 'principais' e 'não-principais'. As emissões de CAKE para os primeiros são controladas pela Cozinha, enquanto a comunidade influencia as emissões para grupos “não-principais” votando com veCAKE.&#x20;

1. Os medidores 'principais' incluem pares com os principais tokens e stablecoins (WBTC, ETH, BNB, USDC, USDT, etc.) - a Cozinha garantirá que esses pares recebam recompensas de CAKE suficientes, pois contribuem significativamente para a receita do protocolo&#x20;
2. Os medidores ‘não-principais’ representam todos os outros medidores não classificados como medidores ‘principais’

## Como votar?

### 1 - Entenda o cronograma de votação <a href="#id-1-understand-the-voting-schedule" id="id-1-understand-the-voting-schedule"></a>

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FJ8jzSEDRJCWSlhfRzx63%2Fimage.png?alt=media\&token=9f758ee2-4fc9-40f4-ab8a-1d50f3375cbc)

A votação do peso dos medidores é realizada a cada duas semanas. O início de uma época, assim como o compartilhamento de receitas, é às 00:00 UTC, todas as quintas-feiras pares.&#x20;

No exemplo acima:&#x20;

* A Época 1 começa às 00:00 UTC, 1ª, quinta-feira, na Semana 1.&#x20;
* A Época 1 termina 2 semanas depois, às 00:00 UTC, dia 15, quinta-feira da Semana 3.&#x20;
* Os usuários podem votar durante 00:00 UTC de 1 a 14.&#x20;
* NENHUM voto pode ser dado durante 00:00 UTC de 14 a 15, pois os votos estão sendo ajustados e computados.&#x20;
* Os resultados da votação serão capturados às 00:00 UTC do dia 15. O fim da Época 1.&#x20;
* Os resultados da votação serão aplicados dentro de 72 horas após o encerramento de uma época.

### 2 - Torne-se elegível

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FJ8jzSEDRJCWSlhfRzx63%2Fimage.png?alt=media\&token=9f758ee2-4fc9-40f4-ab8a-1d50f3375cbc)

Como o veCAKE está diminuindo gradualmente de acordo com o tempo de bloqueio restante, os resultados da votação serão obtidos por meio de um instantâneo no final de cada época. Isso inclui o número total de veCAKE e o veCAKE que cada usuário possui.&#x20;

No exemplo acima:&#x20;

* Os resultados da Época 1 serão baseados nos saldos do veCAKE às 00:00 UTC do dia 15.&#x20;
* Usuários cuja posição veCAKE for desbloqueada antes ou igual à 15ª, terão 0 saldo de veCAKE no momento do snapshot. Portanto, eles não têm poder de voto para a Época 1.&#x20;

Portanto, para se tornar elegível, você deve obter uma posição veCAKE ativa, que é desbloqueada MAIS TARDE do horário de término/instantâneo da época atual.&#x20;

No exemplo acima:&#x20;

* Se quiser votar na época 1, você deve ter uma posição de veCAKE que desbloqueia no dia 21 ou depois do dia 21, ou quinta-feira na semana 3.

### 3 - Verifique os resultados da votação atual <a href="#id-3-check-the-current-voting-results" id="id-3-check-the-current-voting-results"></a>

Vá para "Staking de CAKE", role para baixo e procure a seção "Votação de Medidores" e clique em "Verificar medidores".

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FEt7ze9D4vqqrP6Je22RN%2Fimage.png?alt=media\&token=2c459559-a29c-434d-908e-602f29e6c741)

Na seção superior esquerda. Você pode encontrar:&#x20;

* Seu veCAKE.&#x20;
* Hora do Snapshot e hora de término da votação para a época atual.&#x20;
* O número total de recompensas de CAKE a serem distribuídas na próxima época é baseado nos resultados da votação da época atual. A quantidade total de votos expressos no veCAKE.&#x20;

No canto superior direito, você encontrará um gráfico de pizza representando a % de cada medidor recebido.&#x20;

Na parte inferior, há uma lista completa de todos os medidores de votação. Com o número de votos que receberam e o peso percentual esperado, estão ganhando na época atual. Há também um campo “boost” e “caps”, detalhando duas características importantes do medidor. Continue lendo para mais detalhes.&#x20;

#### Impulsionamento do Medidor e Limites de Emissão&#x20;

Para garantir que as recompensas de CAKE vão para os medidores mais produtivos. Cada medidor pode ser aplicado com um impulsionamento e/ou limite de emissão. Duas das características podem existir ao mesmo tempo.&#x20;

Impulsionamento de Medidor é um multiplicador aplicado ao número de votos que um medidor recebe, variando de 1x a 2,5x (os medidores para pools V3 são limitados a 2x). Isto é para encorajar votos e liquidez para pares de trade importantes.&#x20;

O limite de emissão é o limite máximo da porcentagem de peso que um medidor pode receber, variando de 2% a 20%. Isto visa promover a justiça na atribuição e evitar o abuso do sistema de medição.&#x20;

Por exemplo:&#x20;

* Um medidor tem 10 votos, aumento de 2x e limite de 15%. A votação total é de 100.&#x20;
* Após a aplicação do impulsionamento, este medidor terá 20 votos, peso de 20% sobre o total (100).&#x20;
* No entanto, como tem um limite de 15%, a % final de recompensas de CAKE que este medidor receberá na próxima época será ajustada para 15%.&#x20;

#### Como são determinados o aumento do medidor e os limites de emissão?

Durante o processo de aplicação de um medidor, pedimos aos candidatos que proponham o valor do multiplicador de impulso e a % do limite de emissões que desejam atribuir ao medidor. Estes devem ser votados pelos holders do veCAKE, juntamente com todo o aplicativo do medidor.&#x20;

A opção padrão para todos os medidores é multiplicador de 1,00x e limite de emissão de 5%. Eles podem ser alterados com propostas futuras.

{% hint style="info" %}
Observe que os resultados da votação são atualizados semanalmente. Os números são calculados com base nos saldos do veCAKE às 00:00 UTC da próxima quinta-feira.
{% endhint %}

### 4 - Adicione Medidores para votação

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F40vIxOweSEs7bjuhRQXJ%2Fimage.png?alt=media\&token=946a76cd-465c-4d26-9c5c-c8dd61d66823)

Para votar em um medidor, role para baixo e procure a seção “Meus votos”. Clique em "Adicionar medidor".&#x20;

Na janela pop-up, você pode adicionar medidores à sua lista de votos clicando no ícone azul “+”. Você pode encontrar os resultados da votação atual na lista, junto com aumento e limites.&#x20;

Para localizar rapidamente um medidor, você pode usar a filtragem para filtrar os medidores por blockchains, níveis de taxas e tipos de liquidez. Ou digite o ticker do token no campo de pesquisa.&#x20;

### 5 - Selecione quanto % de veCAKE para votação em cada medidor

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FhjGWyjDJdg1cbp5MXkyB%2Fimage.png?alt=media\&token=fa83e56f-e942-434e-8979-bed5351e1c02)

Depois de adicionar os medidores, você pode selecionar quanto % do seu veCAKE vai para cada um dos medidores.&#x20;

Isto é assim porque:&#x20;

* veCAKE diminui gradualmente com o tempo de bloqueio restante. É impraticável estimar e calcular quantos veCAKE exatos votarão.&#x20;
* É problemático revotar novamente em cada época futura. Portanto, a votação dos medidores foi projetada para levar suas decisões de votação ao longo de toda a época seguinte, até que você lance uma nova.&#x20;

No exemplo acima:&#x20;

* No momento, tenho 2,62 veCAKE.&#x20;
* Decidi destinar 80% para CAKE-BNB, que no momento é 2,10 veCAKE.&#x20;
* 20% para USDC-ETH, que é 0,52 veCAKE, novamente, no momento.&#x20;
* Meu veCAKE total diminuirá gradualmente junto com o tempo de bloqueio restante. No momento do Snapshot, posso ter menos veCAKE, mas minha decisão de divisão de 80% a 20% ainda será aplicada aos resultados finais.&#x20;
* Além disso, esta decisão de 80% a 20% será aplicada a todas as épocas futuras até que eu a atualize com um novo pedido de voto. Ou até que meu veCAKE chegue a 0 devido ao desbloqueio.&#x20;

Depois de confirmar sua decisão, clique em “Submit vote” e confirme em sua carteira.&#x20;

### 6 – Atualize seus votos

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FsEmFgeZ1XgGKbj6EdgzG%2Fimage.png?alt=media\&token=cc6df617-fa2d-4920-8a27-d59115fab192)

Assim que seu voto for enviado, você poderá ver seus votos sendo atualizados para "Votos Atuais". E o veCAKE restante é atualizado.&#x20;

Observe que a decisão de votação para cada medidor só pode ser atualizada a cada 10 dias. Depois de enviar uma solicitação de voto, todos os medidores votados terão um período de espera de 10 dias antes que você possa enviar outra solicitação de atualizações.&#x20;

Para atualizar sua decisão de voto, altere a porcentagem percentual e envie novamente.

{% hint style="info" %}
Observe que depois de ganhar mais veCAKE, adicione CAKE ou estenda o tempo de bloqueio. Você precisa atualizar manualmente todos os medidores reenviando a solicitação de voto. O período de espera de 10 dias ainda se aplica independentemente de você ter alterado suas decisões de %.
{% endhint %}
