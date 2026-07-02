---
hidden: true
---

# FAQ de Compartilhamento de Receita

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Como as parcelas (rCAKE) são calculadas? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

A cada distribuição semanal, as parcelas de cada usuário são recalculadas com base em:

1. A quantidade de CAKE bloqueado que possuem
2. A duração restante do bloqueio do CAKE, arredondada para semanas, e o tempo máximo de bloqueio permitido (atualmente 52 semanas)

Por exemplo:

Se um usuário tem 50 CAKE bloqueados e o tempo de bloqueio restante é de 10,3 semanas, então o usuário tem `50 * (10 / 52 ) ~= 9,61` parcelas.

### Atualizei minha posição; por que ainda tenho 0 parcelas? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

As parcelas (rCAKE) são atualizadas a cada distribuição semanal às 23:59 UTC toda quarta-feira. Verifique novamente após a próxima distribuição semanal para ver suas parcelas atualizadas.

### Por que minhas parcelas são 0 apesar de ter uma posição de Staking ativa? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Ao calcular as parcelas (rCAKE), a duração restante do bloqueio é arredondada para baixo em semanas. Portanto, para receber parcelas, você deve garantir que sua posição de Staking seja desbloqueada não antes da próxima distribuição.

Por exemplo, para receber parcelas para a distribuição da semana 1, você deve:

* Participar antes das 23:59 UTC de 2 de agosto.
* Ter uma posição ativa de Staking de CAKE com prazo fixo que seja desbloqueada após 23:59 UTC de 9 de agosto.

Se sua posição de Staking for desbloqueada antes de 23:59 UTC de 9 de agosto, você receberá 0 parcelas para a semana 1.

### Posso participar de um período de distribuição no meio da semana? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Não, pois as parcelas são calculadas no início do período de distribuição às 23:59 UTC toda quarta-feira. Portanto, você receberá parcelas a partir da próxima distribuição e começará a acumular recompensas a partir de então.

### Como posso receber mais parcelas? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Como as parcelas são calculadas com base na quantidade de CAKE e na duração restante do bloqueio, para receber mais parcelas, você pode:

* Bloquear mais CAKE
* Estender sua posição de Staking

Observe que após adicionar CAKE ou estender, as parcelas NÃO são atualizadas em tempo real e só são atualizadas a cada distribuição semanal.

### Preciso atualizar minha posição de Staking quando adiciono mais CAKE ou estendo o Staking? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

Não, você só precisará se registrar uma vez. Todas as operações subsequentes do pool de Staking de CAKE informarão automaticamente o pool de compartilhamento de receita e atualizarão suas parcelas nas próximas distribuições semanais.

### Por que as recompensas injetadas semanalmente não correspondem 100% ao volume exibido em vários rastreadores (como a página Info)?

A quantidade de recompensas de CAKE injetadas semanalmente pode não corresponder 100% aos números calculados a partir do volume exibido em vários rastreadores. Múltiplos fatores externos podem impactar a quantidade de recompensas de CAKE que podem ser convertidas:

* Preço do token CAKE enquanto a taxa de negociação está sendo convertida e processada
* Preços dos ativos subjacentes enquanto a taxa de negociação está sendo convertida e processada
* Para economizar gas e custo operacional, as receitas de blockchains diferentes da BNB Chain são processadas mensalmente. Elas serão injetadas com um atraso de um mês com média semanal.
* Alguns pares de negociação podem ter liquidez insuficiente ao processar a taxa de negociação.
* Alguns pares de negociação podem conter tokens com lógica personalizada que impede que sua taxa seja processada.

Os Chefs estão trabalhando arduamente para aplicar ferramentas e práticas para garantir que mais taxas de negociação geradas possam ser processadas e convertidas em CAKE.
