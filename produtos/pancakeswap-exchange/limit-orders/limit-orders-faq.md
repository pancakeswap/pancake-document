# Perguntas Frequentes sobre Ordens Limite

{% hint style="info" %}
Use a barra lateral para encontrar rapidamente as respostas para suas perguntas!
{% endhint %}

## Questões Gerais

### Por que minha ordem não foi executada?

As ordens limite são executadas quando atingem o preço desejado, no entanto, devido às flutuações do gás, o preço real de execução pode variar do preço especificado na interface. Normalmente, o preço de execução e o preço desejado devem ser quase idênticos, no entanto, se você enviou uma ordem particularmente pequeno (\~<1000$), o preço de execução pode ser um pouco maior para levar em conta as taxas.

Portanto, sua ordem não pode ser executada porque:

* Não foi possível preencher toda a ordem com o preço e a quantidade desejados devido ao impacto no preço(price impact).
* Um dos tokens na ordem limite tem taxa de transferência (veja abaixo).

**Antes de enviar uma ordem, consulte a interface do usuário que indica o preço real de execução.**

{% hint style="info" %}
Observe: a tabela de histórico de pedidos obtém os dados do Subgraph e pode mostrar informações ligeiramente atrasadas.
{% endhint %}

### Posso submeter uma ordem limite para tokens com taxa na transferência?

**NÃO.** Os tokens com taxa de transferência não devem ser usados com ordens limite. Prossiga por sua conta e risco. Você poderá perder seus tokens se fizer isso.

### Como defino o slippage enquanto uso ordem limites?

A derrapagem(slippage) não é relevante em ordens limite. Você especifica o valor de entrada (por exemplo, 1000 CAKE) e o valor de saída (por exemplo, 20 BNB). A ordem limite garante que você não vai receber nada menos que a quantidade especificada no valor de saída (20 BNB) para o valor de entrada(1000 CAKE) se o preço do par alcançar o preço desejado. **Observe que os tokens com taxa de transferência não devem ser usados com ordens limite** (leia acima)

### O preço real de execução mostra "nunca executa" (never executes). O que é isso?

Basicamente isso significa que você está tentando trocar uma quantidade muito pequena de tokens, portanto, não há tokens suficientes para contabilizar a taxa de gás. Em geral, você precisa aumentar a quantidade no campo de entrada dos tokens para se livrar desse erro.

### Existe uma data de expiração para minhas ordens limite?

Ordens abertas permanecerão abertas indefinidamente até serem executadas ou canceladas pelos usuários. Um recurso de data de expiração personalizável está planejado para um futuro próximo.

### Por que não posso criar ordens limites abaixo do preço do mercado?

Para vender abaixo do preço de mercado, você precisa de O**rdens Stop Limite**, não ordens limite. O recurso Ordens Stop Limit será lançado em breve.

### Fiz um pedido e ele não aparece na tabela de pedidos ou trava no status “pendente”.

O histórico de pedidos vem do subgraph e, portanto, pode mostrar informações um pouco atrasadas. Normalmente, os atrasos não são superiores a alguns minutos, na pior das hipóteses. Consulte o indicador de subgraph no canto inferior direito da tabela de histórico de pedidos.
