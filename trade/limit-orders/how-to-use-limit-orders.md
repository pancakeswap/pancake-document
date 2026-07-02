---
hidden: true
---

# Como usar Ordens Limitadas

## O que são Ordens Limitadas

Uma ordem limitada é uma ferramenta que permite aos usuários comprar ou vender ativos a um preço especificado ou melhor, em vez de depender do preço de mercado no momento da execução. Em uma ordem limitada, embora o preço seja garantido, a execução da ordem não é — as ordens limitadas serão executadas apenas se o preço atender às qualificações da ordem.

## Como configurar uma ordem limitada

1. Vá para a página de Swap e selecione a opção de ordem limitada clicando em "LIMIT", ou use este link: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Selecione os tokens "De" e "Para" que deseja negociar. Neste exemplo, escolhemos USDC e ETH respectivamente, o que significa que queremos comprar ETH com USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Insira o valor que deseja negociar. Observe que o preço limite mostrará o preço de mercado atual, que então estimará o valor de saída dos tokens de destino (ETH)
2. Defina o preço limite desejado. As negociações SOMENTE serão executadas quando o preço de mercado disponível for melhor ou igual ao preço limite. O valor de saída do token de destino será atualizado de acordo.

No exemplo abaixo, desejamos comprar ETH quando o preço for $1.900 ou melhor. A quantidade de ETH recebida será igual ou maior que 0,037 ETH. Apenas lances iguais ou melhores que esse valor serão elegíveis para preencher a ordem. Esse valor leva em conta os custos de gas e as taxas. &#x20;

{% hint style="info" %}
Nota importante: Como as taxas são pagas a partir do valor do token de saída, o preço limite inclui as taxas de gas e de negociação, portanto, os usuários devem levar isso em conta ao configurar o preço. Por exemplo, as taxas de gas de uma ordem muito pequena podem totalizar uma porcentagem muito grande do resultado da ordem, refletindo um preço limite real que não é competitivo com o preço de mercado à vista.
{% endhint %}

3.  Pressione "Colocar ordem". Verifique novamente os detalhes da sua ordem, aceite o aviso de isenção de responsabilidade e pressione "Confirmar ordem".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Após a confirmação da transação, você poderá ver sua ordem na seção de histórico de ordens, em "Ordens abertas". \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. As ordens abertas podem ser canceladas a qualquer momento expandindo a ordem e clicando no botão "Cancelar Ordem".

Pontos a considerar:

* Sua ordem pode não ser executada se o preço de mercado disponível for pior do que o preço limite definido.
* As negociações são baseadas em um protocolo descentralizado que utiliza tomadores off-chain que competem para preencher as ordens. Esses tomadores têm o direito de solicitar uma taxa, que o protocolo desconta do tomador vencedor a partir dos tokens de saída.&#x20;
* Os tomadores podem levar em conta as taxas de gas das suas transações ao definir suas taxas, o que pode resultar em flutuações nos valores das taxas.
* Ao especificar um preço limite, os usuários verão na interface o valor mínimo de tokens de destino que receberão se a ordem for preenchida. Apenas tomadores que fizerem lances iguais ou melhores que esse valor serão elegíveis para preencher a ordem. Esse valor leva em conta os custos de gas e as taxas de negociação.
