# FAQ

{% hint style="info" %}
Use a barra lateral para encontrar rapidamente as respostas às suas perguntas!
{% endhint %}

## Ordens Limitadas e TWAP

Consulte o FAQ fornecido pela Orbs:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (Descontinuado)

### Por que não consigo encontrar minhas ordens?

As ordens limitadas V2 foram descontinuadas, acesse usando este link:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Por que minha ordem não foi executada?

As ordens limitadas são executadas quando atingem o preço desejado; no entanto, devido a flutuações de gas, o preço de execução real pode variar do preço especificado na interface. Normalmente, o preço de execução e o preço desejado devem ser quase idênticos; no entanto, se você enviou uma ordem particularmente pequena (\~<1000$), o preço de execução pode ser ligeiramente mais alto para contabilizar as taxas.&#x20;

Portanto, sua ordem pode não ter sido executada porque:

* Não foi possível preencher toda a ordem ao preço e valor desejados devido ao impacto de preço.
* Um dos tokens na ordem limitada tem taxa de transferência (veja abaixo).

**Antes de enviar uma ordem, consulte a interface que indica o preço de execução real.**

{% hint style="info" %}
Observação: a tabela de histórico de ordens obtém os dados do Subgraph e pode mostrar informações com leve atraso.
{% endhint %}

### Posso enviar uma ordem limitada para tokens com taxa de transferência?

**Não.** Os tokens com taxa de transferência não devem ser usados com ordens limitadas. Prossiga por sua conta e risco.

### Como defino o Slippage ao usar ordens limitadas?

O Slippage não é relevante em ordens limitadas. Você especifica o valor de entrada (ex.: 1000 CAKE) e o valor de saída (ex.: 20 BNB). As ordens limitadas garantem que você receberá no mínimo o valor de saída especificado (20 BNB) pelo seu valor de entrada (1000 CAKE) se o preço do par atingir o preço desejado. **Observe que tokens com taxa de transferência não devem ser usados com ordens limitadas** (leia acima)

### O preço de execução real mostra "nunca executa". O que isso significa?

Basicamente significa que você está tentando fazer swap de um valor muito pequeno de tokens, portanto não há tokens suficientes para cobrir a taxa de gas. Em geral, você precisa aumentar o valor do campo "entrada" para eliminar esse erro.&#x20;

### Há uma data de expiração para minhas ordens limitadas?

As ordens abertas têm uma data de expiração de 90 dias. Após a expiração, sua ordem pode nunca ser executada. Cancele sua ordem após o vencimento.&#x20;

Um recurso de data de expiração personalizável está planejado para o futuro próximo.

### Por que não consigo criar ordens limitadas abaixo do preço de mercado?

Para vender abaixo do preço de mercado, você precisa de **Ordens Stop Limit**, não de ordens limitadas. O recurso de Ordens Stop Limit está chegando em breve.

### Fiz uma ordem e ela não aparece na tabela de ordens ou está presa em status "pendente".

O histórico de ordens vem do subgraph e, portanto, pode mostrar informações com leve atraso. Normalmente, os atrasos não são maiores que alguns minutos no pior caso. Consulte o indicador do subgraph no canto inferior direito da tabela de histórico de ordens.
