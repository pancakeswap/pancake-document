# 🍯 Pottery

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/pottery-header.png)

Pottery combina o stake bloqueado de CAKE com elementos de loteria para dar a você a chance de ganhar um rendimento maior em seu depósito de CAKE! É fácil e seguro, pois você sempre receberá de volta pelo menos todo o CAKE que depositou.

## Características:

* Deposite CAKE  na página do Pottery com o mínimo de 1 CAKE&#x20;
* O depósito fecha na primeira segunda-feira de cada mês para um grupo de Pottery diferente (23:59 UTC nessa segunda-feira) e está aberto a partir da sexta-feira anterior por volta das 10:00 UTC, a menos que haja acordos especiais que serão anunciados com antecedência (Primeiro Pottery está fechando em 8 de agosto de 2022 23:59 UTC)&#x20;
* Durante a fase beta do produto, há um limite para o depósito total de CAKE para cada grupo de Pottery (o limite máximo de depósito é de 600.000 CAKE)&#x20;
* O CAKE depositado será direcionado para a pool de stake bloqueada por dez (10) semanas onde 80% do total de recompensas de stake serão enviados para o pool da Pottery para sorteio, 20% serão reservados para seu saque&#x20;
* Para cada grupo de Pottery (um por mês), haverá dez (10) sorteios semanais em cada sexta-feira (ao meio-dia UTC) mediante os depósitos produzindo oito (8) vencedores por semana, cada endereço pode ganhar mais de um dos oito slots vencedores de cada semana&#x20;
* Quanto maior o seu depósito em relação à pool geral, maior a chance de ganhar, os vencedores podem reivindicar seu prêmio logo após cada sorteio&#x20;
* Cada grupo de Pottery realiza o sorteio separadamente&#x20;
* Somente após 10 semanas da data de bloqueio do seu grupo de Pottery, você poderá retirar seu CAKE&#x20;
* O Pottery usa a implementação de VRF da Chainlink para aleatoriedade verdadeira e segura

## Grupo de Pottery <a href="#pottery-cohort" id="pottery-cohort"></a>

Na primeira segunda-feira de cada mês, um grupo de Pottery estará aberta para você depositar CAKE e participar dele pelas próximas 10 semanas. Esse arranjo combina o depósito para direcionar à pool de stake bloqueado, de modo que o contrato de do grupo de Pottery seja capaz de coordenar as recompensas do stake do depósito da pool de stake.&#x20;

Cada depósito e data de bloqueio será um grupo separado - uma para cada mês - por exemplo todos os depósitos em 5 de setembro de 2022 estarão em um grupo, todos os depósitos em 3 de outubro de 2022 estarão em outro grupo.&#x20;

Embora os sorteios possam acontecer simultaneamente para diferentes grupos, os prêmios para cada grupo são separados para serem justos.

![(Apenas para fins de ilustração, a data real de bloqueio do grupo para o primeiro Pottery foi definido para 8 de agosto de 2022)](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202022-07-27%20at%201.04.10%20PM.png)

Por exemplo, há 2 sorteios separados em 9 de setembro de 2022, um para o grupo de 1º de agosto como o sexto sorteio semanal e outro para a grupo de 5 de setembro como o primeiro sorteio semanal. Se o grupo de 1º de agosto tiver um total de 100.000 CAKE depositados e o grupo de 5 de setembro tiver um total de 300.000 CAKE depositados, o prêmio semanal para o grupo de 1º de agosto virá apenas das recompensas de stake desses 100.000 CAKE, enquanto o prêmio semanal para o grupo de 5 de setembro virá apenas das recompensas de staking desses 300.000 CAKE. Se você depositou CAKE apenas no grupo de 1º de agosto, terá a chance de ganhar o prêmio semanal em 9 de setembro com base nas recompensas de stake de 100.000 CAKE. Se você depositou CAKE no grupo de 1º de agosto e 5 de setembro, terá a chance de ganhar os dois prêmios semanais em 9 de setembro.

## Financiamento de Prêmios e Alocação de Recompensas de Stake

Os depósitos são agrupados em grupos mensais para um arranjo mais eficiente das recompensas de stake que também são agrupadas para cada grupo. As recompensas de staking são usadas para financiar o prêmio e algumas recompensas de staking por depósito no Pottery.

80% das recompensas de stake serão direcionadas para financiar o prêmio total para 10 sorteios semanais e os 20% restantes serão reservados como recompensas de stake quando você retirar seu depósito  de CAKE após 10 semanas.&#x20;

No entanto, como as recompensas de staking do Pool de CAKE são distribuídas apenas após a duração do bloqueio - 10 semanas neste caso, para melhor experiência do produto e para facilitar os sorteios semanais logo após a data do depósito, o contrato está tomando emprestado 80% do valor das recompensas totais estimadas de stake do grupo do tesouro de CAKE com base no APY no momento do bloqueio. O CAKE tomado emprestado é usado para o pagamento de cada sorteio semanal.&#x20;

No final das 10 semanas, quando as recompensas são distribuídas da pool de stake, o tesouro de CAKE será reembolsado primeiro, depois o restante será direcionado de volta ao cofre para os usuários retirarem junto com seu depósito inicial no grupo.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202022-07-27%20at%201.23.36%20PM.png)

Por exemplo, se o grupo de Pottery em 1º de agosto de 2022 atraiu 100.000 depósitos CAKE no total, o retorno estimado para 10 semanas de staking bloqueado é de cerca de 3.674 CAKE. O contrato emprestará 80% dele, ou cerca de 2.940 CAKE, para o prêmio total de 10 sorteios semanais, ou seja, 294 CAKE no total de prêmios para cada sorteio semanal antes das taxas.&#x20;

É importante observar que as recompensas e APY no final da duração do depósito podem mudar ao longo da duração de 10 semanas com base em outros depósitos e seus períodos de bloqueio na pool de CAKE bloqueado, pode haver um pequeno desvio das percentagens especificadas (+/- 10%).&#x20;

Todas as recompensas do stake líquido de taxas serão devolvidas aos depositantes por meio de prêmios ou recompensas. Se o APY real for menor que o APY estimado no momento do bloqueio, significa que mais recompensas são distribuídas aos depositantes durante os sorteios semanais e menos para a porção de recompensas de stake. Se o APY real for maior que o APY estimado no momento do bloqueio, menos recompensas serão distribuídas pelos sorteios semanais e mais serão reservadas para as recompensas de stake disponíveis para retirada. Em última análise, o valor esperado é o mesmo.

## Como vencer - Cálculos das Probabilidades <a href="#how-to-win-odds-calculation" id="how-to-win-odds-calculation"></a>

As probabilidades são calculadas com base na parcela do valor do depósito em relação ao tamanho total do depósito do grupo. Simplesmente, quanto mais CAKE você depositar, maior a chance de ganhar cada sorteio semanal. Por exemplo, se você depositou 10.000 CAKE e o depósito total do grupo é de 100.000 CAKE, há 10% de chance de você ganhar em cada sorteio semanal.&#x20;

Cada endereço pode ganhar mais de 1 dos 8 slots vencedores a cada semana.&#x20;

No caso extremo, se todos os 100.000 BOLOS do grupo forem depositados por você, você ganhará todos os prêmios de cada sorteio semanal. No entanto, isso significa que o retorno final que você obterá é o mesmo que colocar 100.000 CAKE na Pool de Stake bloqueada por 10 semanas, mas você também pagará as taxas do Pottery.

## Riscos - Importante! <a href="#risks-important" id="risks-important"></a>

Você terá a garantia de receber de volta 100% do que depositou em 10 semanas. No entanto, você só pode sacar seu depósito de CAKE após 10 semanas de bloqueio, sem outra forma de sacar antecipadamente.&#x20;

Ao participar do Pottery, você estará arriscando as recompensas do stake, juntamente com outras utilidades do CAKE bloqueado, como iCAKE e vCAKE. No caso de você não ganhar nada dos 10 sorteios semanais, você teria perdido 80% das recompensas de staking que deveria receber se você bloqueasse seu CAKE no staking pool por 10 semanas.&#x20;

Por favor, participe com base na sua preferência de risco, uma vez que o CAKE é depositado, não há nada que alguém possa fazer para ajudá-lo a retirar antecipadamente.

## Taxas <a href="#fees" id="fees"></a>

Oito por cento (8%) do pote de prêmios distribuído a cada semana será cobrado como taxas para queima. Nosso objetivo é revisar e ajustar a estrutura de taxas de acordo com a fase beta do produto.

## Pronto para Participar? <a href="#ready-to-participate" id="ready-to-participate"></a>

Se você está esclarecido sobre a estrutura do produto, os riscos e as taxas - veja esta página sobre [como participar ](https://docs.pancakeswap.finance/v/portuguese-brazilian/products/pottery/how-to-play-pottery)da interface do usuário da web PancakeSwap e outras [perguntas frequentes](https://docs.pancakeswap.finance/v/portuguese-brazilian/products/pottery/pottery-faq) sobre Pottery!
