# Perguntas Frequente Da Previsão

{% hint style="info" %}
Use a barra lateral para encontrar rapidamente as respostas para suas perguntas!
{% endhint %}

## Questões Gerais

### Qual é o endereço do contrato da Previsão da PancakeSwap?

Endereço do Contrato Verificado: [https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)

### Existe um limite de tempo antes que eu possa coletar meus ganhos?&#x20;

Não, você poderá coletar seus ganhos a qualquer momento no futuro.&#x20;

### Como é calculado o pagamento?&#x20;

* Taxa de pagamento para pool UP = Valor total de ambos as pools ÷ Valor da pool UP&#x20;
* Taxa de pagamento para pool DOWN = Valor total de ambos as pools ÷ Valor da pool DOWN&#x20;

Por exemplo, se houver 15 BNB no lado DOWN de uma rodada e a premiação geral for de 150 BNB, a taxa de pagamento DOWN será (150/15) = 10x.&#x20;

* Valor do Pagamento = Taxa de Pagamento × Posição × (1 - Taxa do Tesouro)&#x20;

No caso acima, se a rodada terminar com um resultado DOWN, se você comprometer 2 BNB para uma posição DOWN, receberá um pagamento de (2\*10) × (1-0,03) = 19,4 BNB. Seu lucro seria de 17,4 BNB (19,4 - 2).&#x20;

A taxa do tesouro está atualmente fixada em 3%: isso pode estar sujeito a alterações, que seriam anunciadas nos canais de comunicação oficiais da PancakeSwap. As taxas do Tesouro são usadas para recomprar e queimar tokens CAKE.

### **O que são as taxas?**

3% do pote total de cada rodada irá para o tesouro, que será usado para recomprar e queimar CAKE na queima de todas as segundas-feiras.

### O que está sendo usado como fonte do preço?

O PancakeSwap usa duas fontes para nossas fontes de preços. Cada um deles tem seu próprio propósito dentro do mercado de previsão:&#x20;

### Oráculo da ChainLink&#x20;

* Usado para o preço de bloqueio e o preço final de cada rodada do mercado de previsão. Isso atualiza em intervalos de 20 segundos.
* Nosso contrato de previsão usa o feed de preçosdo Oráculo da ChainLink para definir os preços usados para determinar se um usuário ganhou ou não.
* Usado para o gráfico "Chainlink" na interface.&#x20;

### Binance&#x20;

* Usado para atualizações de preços em tempo real na interface de mercado de previsão da PancakeSwap.&#x20;
* Usado para o gráfico "TradingView" na interface.&#x20;

Como estamos usando dois feeds de preços diferentes, as atualizações de preços em tempo real da Binance e o preço do Oráculo da ChainLink podem diferir um pouco. No entanto, eles não devem variar significativamente

### O resultado da rodada mudou após o término da rodada! Por quê?&#x20;

Às vezes, após o encerramento de uma rodada, o resultado final pode ser diferente do último resultado exibido durante a rodada. Se você assistir a uma rodada terminanda em "DOWN", pode parecer virar para "UP" alguns segundos depois.&#x20;

Isso ocorre porque usamos o feed de preços do Oráculo da ChainLink para determinar o resultado final de uma rodada. O período entre o final de uma rodada e o início da próxima é de 30 segundos, mas o Oráculo é atualizado a cada 20 segundos. É possível que, durante esse curto período, o Oracáculo envie uma atualização enquanto a transação para acionar a próxima rodada está sendo cunhada. Isso pode parecer "inverter" o resultado da rodada anterior.

## Sobre as Posições

### O que acontece se ninguém entrar em uma posição oposta?&#x20;

Se apenas um lado de uma rodada tiver posições inseridas, esse lado perde, os fundos perdedores serão enviados ao tesouro. Por exemplo: o usuário A insere uma posição PARA CIMA, ninguém mais insere uma posição PARA BAIXO. O usuário A perde e não há posições opostas para as quais os ganhos sejam pagos. Os fundos são enviados para o tesouro.

### O que acontece se o preço bloqueado e o preço fechado forem exatamente iguais?

Na raríssima ocorrência de o preço bloqueado ser exatamente o mesmo que o preço fechado, ninguém ganha e todos os fundos inseridos nas posições serão enviadas ao tesouro para serem usados nas recompras de CAKE para queimar.&#x20;

### Posso alterar ou remover minha posição?&#x20;

Não. Depois de inserir uma posição, você NÃO pode alterar a direção, adicionar ou remover sua posição. Está bloqueado, portanto, certifique-se de que está 100% satisfeito com a direção da sua posição antes de confirmar.

## Pausas do Mercado

### O que significa quando os mercados estão em pausa?&#x20;

Os mercados são pausados quando existem condições que afetam a confiabilidade do contrato. Os mercados em pausa significam que nenhuma aposta será realizada em nenhuma rodada.&#x20;

### O que faz com que o mercado de previsão da PancakeSwap pare?&#x20;

O mercado de previsão será interrompido nas seguintes condições:&#x20;

* O contrato de previsão não conseguiu obter o preço do oráculo ChainLink devido ao oráculo não ter postado o preço no momento em que a rodada terminou.&#x20;
* O contrato de previsão não conseguiu executar uma ação (encerrar uma rodada ou obter um preço do oráculo) porque o tx ficou presa na mempool por mais de 15 blocos.&#x20;

### Quando os mercados serão retomados após uma pausa?&#x20;

Os mercados serão retomados quando um administrador (um dos chefs) reiniciar manualmente o mercado.&#x20;

### O que acontece com minha posição se o mercado parar?&#x20;

Se os mercados pausarem enquanto você tiver uma posição ativa, seus fundos estarão disponíveis para serem recuperados, da mesma forma que você normalmente reivindicaria seus ganhos.&#x20;

Para recuperar fundos, você precisará pagar algumas taxas de gás. Não podemos compensá-lo pelas taxas de gás, portanto, tenha em mente esse pequeno risco antes de participar.
