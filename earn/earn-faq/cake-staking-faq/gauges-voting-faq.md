---
hidden: true
---

# FAQ de Votação de Gauges

### Tenho uma posição ativa, por que não consigo votar? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Certifique-se de que o tempo de desbloqueio seja igual ou posterior a 1 semana após o tempo de snapshot da época atual.&#x20;

Se sua posição for desbloqueada no tempo de snapshot, significa que você tem 0 veCAKE no tempo de snapshot. Portanto, você não poderá votar.



### Posso votar logo após configurar uma posição de veCAKE?

Sim.

Assim que sua posição for configurada, você pode usar seu CAKE para votar imediatamente.

No entanto:

* Nenhum voto pode ser lançado nas últimas 24 horas de uma época.
* Você não pode atualizar sua decisão de Votação em um gauge específico com mais frequência do que a cada 10 dias.
* Certifique-se de que sua posição não seja desbloqueada antes ou no tempo de snapshot.



### Posso obter mais veCAKE ou votos?

Sim, basta adicionar mais CAKE ou estender sua posição de bloqueio.

Observe que após obter mais veCAKE adicionando CAKE ou estendendo o tempo de bloqueio, você precisa atualizar manualmente todos os gauges reenviando a solicitação de voto.



### Por que os resultados da Votação mudaram após o período de contagem?

Durante o período de contagem, a Kitchen da PancakeSwap lançará seus votos com base em várias métricas de todos os gauges.&#x20;

O objetivo é:

* Garantir que os principais pools de liquidez recebam um retorno competitivo em suas posições LP
* Garantir que os acordos existentes com parceiros do Syrup Pool sejam cumpridos antes de migrá-los completamente para o sistema de Votação de gauge veCAKE
* Garantir que qualquer um dos farms menores que não recebeu votos após o lançamento do veCAKE receberá pelo menos alguma alocação no início da implementação, limitado aos seus níveis de emissão atuais.

Confira esta proposta para mais detalhes: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### Por que meus números de votos estão diminuindo?

Porque ao votar nos gauges, votamos usando nosso veCAKE. E o saldo de veCAKE diminui gradualmente com o tempo de bloqueio restante.&#x20;

Seus votos diminuirão até 0 quando sua posição de veCAKE for desbloqueada.

Para obter mais votos, adquira mais veCAKE adicionando mais CAKE ao bloqueio ou estendendo o bloqueio.



### Após obter mais veCAKE, por que não consigo votar em mais gauges?

Ao votar nos gauges, lançamos nossos votos definindo quanto % do nosso veCAKE vai para cada gauge.

Portanto, mesmo que você tenha obtido mais veCAKE, se você alocou 100% do seu veCAKE nos últimos 10 dias, você não pode alterar a decisão até o final do período de recarga de 10 dias.



### Os resultados da Votação foram contabilizados; por que a taxa de emissão não está mudando?

Leva cerca de 72 horas para aplicar os resultados da Votação a vários produtos de emissão na PancakeSwap. Os Chefs continuarão a automatizar esse processo para encurtar a lacuna e melhorar a precisão.



### Por que o gauge pelo qual votei não recebeu nenhuma emissão de CAKE na próxima época?

Os gauges na whitelist precisam receber votos que correspondam a no mínimo 1 CAKE por dia em emissões, antes de poderem receber qualquer CAKE.
