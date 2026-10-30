# 🍯 \[Arquivado] Pottery

{% hint style="danger" %}
\[Arquivado] Pottery – A partir de 3 de novembro de 2023
{% endhint %}

O Pottery combina lock-staking de CAKE com elementos de loteria para dar a você a chance de ganhar um rendimento maior sobre o seu depósito de CAKE! É fácil e seguro, pois você sempre receberá de volta pelo menos todo o CAKE que depositou.

## Especificações:

* Deposite CAKE na página do Pottery com um mínimo de 1 CAKE&#x20;
* O depósito fecha na primeira segunda-feira de cada mês para cada coorte diferente do Pottery (23:59 UTC dessa segunda-feira) e fica aberto a partir da sexta-feira anterior, por volta das 10:00 UTC, a menos que haja acordos especiais anunciados com antecedência (o primeiro Pottery fecha em 8 de agosto de 2022, 23:59 UTC)
* Durante a fase beta do produto, há um limite para o depósito total de CAKE em cada coorte do Pottery (o limite máximo de depósito é de 600.000 CAKE)
* O CAKE depositado será direcionado ao pool de lock-staking e bloqueado por dez (10) semanas. 80% do total das recompensas de staking serão enviados ao pool do Pottery para sorteio, e 20% serão reservados para o seu saque
* Para cada coorte do Pottery (uma por mês), haverá dez (10) sorteios semanais, toda sexta-feira (ao meio-dia UTC) após o depósito, produzindo oito (8) vencedores por semana; cada endereço pode ganhar mais de uma das oito vagas de vencedor a cada semana \*
* Quanto maior o seu depósito em relação ao pool total, maior a chance de ganhar; os vencedores podem resgatar o prêmio logo após cada sorteio&#x20;
* Cada coorte do Pottery realiza o sorteio separadamente&#x20;
* Somente após 10 semanas da data de bloqueio da coorte do Pottery você poderá sacar seu CAKE&#x20;
* O Pottery usa a implementação de VRF da Chainlink para aleatoriedade genuína e segura

## Coorte do Pottery&#x20;

Na sexta-feira anterior à primeira segunda-feira de cada mês, uma coorte do Pottery será aberta para você depositar CAKE e participar pelas próximas 10 semanas. Esse arranjo combina os depósitos para direcioná-los ao pool de staking bloqueado, de modo que o contrato do Pottery da coorte consiga coordenar as recompensas de staking do depósito vindas do pool de staking bloqueado.

Cada depósito e data de bloqueio será uma coorte separada – uma por mês – por exemplo, todos os depósitos de 5 de setembro de 2022 ficarão em uma coorte, e todos os depósitos de 3 de outubro de 2022 ficarão em outra.

Embora os sorteios possam acontecer simultaneamente para coortes diferentes, os prêmios de cada coorte são separados para garantir a justiça.

![(Apenas para fins ilustrativos; a data real de bloqueio da coorte do primeiro Pottery foi definida para 8 de agosto de 2022)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

Por exemplo, há 2 sorteios separados em 9 de setembro de 2022: um para a coorte de 1º de agosto, como o sexto sorteio semanal, e outro para a coorte de 5 de setembro, como o primeiro sorteio semanal. Se a coorte de 1º de agosto tiver um total de 100.000 CAKE depositados e a coorte de 5 de setembro tiver um total de 300.000 CAKE depositados, o prêmio semanal da coorte de 1º de agosto virá apenas das recompensas de staking desses 100.000 CAKE, enquanto o prêmio semanal da coorte de 5 de setembro virá apenas das recompensas de staking desses 300.000 CAKE. Se você depositou CAKE apenas na coorte de 1º de agosto, tem chance de ganhar o prêmio semanal de 9 de setembro com base nas recompensas de staking de 100.000 CAKE. Se você depositou CAKE nas coortes de 1º de agosto e de 5 de setembro, tem chance de ganhar os dois prêmios semanais de 9 de setembro.

#### Por que precisamos do sistema de coortes? Por que não juntamos tudo?

Como o Pottery interage com o staking de prazo fixo do CAKE, qualquer depósito só pode ser sacado após o período de bloqueio. Se juntássemos todos os depósitos, embora seja possível adicionar mais depósitos após o bloqueio inicial e também bloqueá-los por 10 semanas, os primeiros depositantes não conseguiriam sacar no prazo.

## **Financiamento de Prêmios e Alocação das Recompensas de Staking**

Os depósitos são agrupados em coortes mensais para um arranjo mais eficiente das recompensas de staking, que também são agrupadas por coorte. As recompensas de staking são usadas para financiar o pool de prêmios e parte das recompensas de staking por depositar no Pottery.

80% das recompensas de staking serão direcionados para financiar o pool de prêmios dos 10 sorteios semanais, e os 20% restantes serão reservados como recompensas de staking quando você sacar seu depósito de CAKE após 10 semanas.

No entanto, como as recompensas de staking do pool de staking bloqueado de CAKE só são distribuídas após o período de bloqueio – 10 semanas, neste caso –, para uma melhor experiência do produto e para viabilizar os sorteios semanais logo após a data do depósito, o contrato toma emprestado da tesouraria de CAKE 80% do total estimado de recompensas de staking da coorte, com base na APR no momento do bloqueio. O CAKE emprestado é usado para o pagamento de cada sorteio semanal.

Ao final das 10 semanas, quando as recompensas forem distribuídas pelo pool de staking, a tesouraria de CAKE será reembolsada primeiro, e o restante será direcionado de volta ao vault para que os usuários o saquem junto com o depósito inicial na coorte.

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEF6IySHEmy1P1k5S3W_PvnFMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMZKuQ4TnNTfKRdU8s3UXO1n0Smnp8_6sAg)

Por exemplo, se a coorte do Pottery de 1º de agosto de 2022 atraiu 100.000 CAKE em depósitos no total, o retorno estimado para 10 semanas de staking bloqueado é de cerca de 3.674 CAKE. O contrato tomará emprestado 80% disso, ou cerca de 2.940 CAKE, para o pool de prêmios dos 10 sorteios semanais, ou seja, 294 CAKE em prêmios totais para cada sorteio semanal antes das taxas.

É importante observar que as recompensas e a APR ao final do período a partir do depósito podem mudar ao longo das 10 semanas, com base em outros depósitos e seus períodos de bloqueio no pool de CAKE bloqueado, podendo haver um pequeno desvio em relação às porcentagens especificadas (+/- 10%).

Todas as recompensas de staking líquidas de taxas serão devolvidas aos depositantes por meio do pool de prêmios ou das recompensas. Se a APR real for menor que a APR estimada no momento do bloqueio, significa que mais recompensas são distribuídas aos depositantes nos sorteios semanais e menos na parcela de recompensas de staking. Se a APR real for maior que a APR estimada no momento do bloqueio, menos recompensas são distribuídas pelos sorteios semanais e mais são reservadas para as recompensas de staking disponíveis para saque. No fim das contas, o valor esperado é o mesmo.

## **Como Ganhar – Cálculo das Chances**

As chances são calculadas com base na participação do seu valor depositado em relação ao tamanho total de depósitos da coorte. Simplificando, quanto mais CAKE você depositar, maior a chance de ganhar cada sorteio semanal. Por exemplo, se você depositou 10.000 CAKE e o depósito total da coorte é de 100.000 CAKE, você tem 10% de chance de ganhar em cada sorteio semanal.

Cada endereço pode ganhar mais de 1 das 8 vagas de vencedor a cada semana.

No caso extremo, se todos os 100.000 CAKE da coorte forem depositados por você, você ganhará todos os prêmios de cada sorteio semanal. No entanto, isso significa que o retorno final será o mesmo de colocar 100.000 CAKE no pool de staking bloqueado por 10 semanas, mas você também pagará as taxas do Pottery.

## **Riscos – Importante!**

Você tem a garantia de receber de volta 100% do que depositou em 10 semanas. No entanto, você _só_ pode sacar seu depósito de CAKE após 10 semanas de bloqueio, sem qualquer outra forma de saque antecipado.

Ao participar do Pottery, você estará arriscando as recompensas de staking, junto com outras utilidades do CAKE bloqueado, como iCAKE e vCAKE. Caso você não ganhe nada nos 10 sorteios semanais, terá perdido 80% das recompensas de staking que deveria receber se tivesse bloqueado seu CAKE no pool de staking por 10 semanas.

Participe de acordo com a sua preferência de risco: depois que o CAKE é depositado, ninguém pode ajudar você a sacar antes do prazo.

## **Taxas**

Oito por cento (8%) do montante de prêmios distribuído a cada semana será cobrado como taxa para queima. Pretendemos revisar e ajustar a estrutura de taxas após a fase beta do produto.

## **Pronto para Participar?**

Se você entendeu a estrutura do produto, os riscos e as taxas, veja esta página sobre [como participar](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery/how-to-play-pottery) pela interface web da PancakeSwap e o outro [FAQ do Pottery](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery/pottery-faq)!



