# Calculadora APR/ROI/IL

No V3 de Liquidez e Farms, com a nova liquidez não fungível e a capacidade de personalizar a faixa de preço, cada posição LP terá seu próprio APR de taxa LP e APR de farming de CAKE.

Para tornar o fornecimento de liquidez mais fácil e menos desafiador, os novos displays automáticos de APR com uma calculadora de ROI totalmente nova estão disponíveis para uso sempre que você estiver fornecendo liquidez ou fazendo farming.

## Cálculo e displays automáticos de APR <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Quando você está fornecendo liquidez, o display automático de APR reage às suas alterações de configuração e calcula o APR com base nas suas configurações.

Por exemplo, na maioria dos casos, se você apertar as configurações de faixa de preço, o APR aumenta.

Observe para APRs de taxa LP:

* A quantidade estimada de recompensas de taxa LP varia com base no nível de taxa selecionado; as recompensas de taxa requerem reivindicação e composição manual.
* Os valores de APR são calculados usando o volume histórico de negociação, que depende do Subgraph e pode estar sujeito a atrasos de indexação.

Para APRs de farming:

* A quantidade estimada de recompensas de CAKE é baseada nas emissões ao vivo de CAKE para os farms. Elas estão sujeitas a mudanças com base em futuros ajustes de emissão.

{% hint style="info" %}
Os números são calculados nas taxas e condições de pool atuais e estão sujeitos a mudanças com base em diversas variáveis externas. São estimativas fornecidas apenas para sua conveniência e de forma alguma representam retornos garantidos.
{% endhint %}

Você pode encontrar este display de APR em:

* Página "Add Liquidity" - mostrando APR de taxa LP
* Página de detalhes de cada posição de liquidez existente - mostrando APR de taxa LP\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Página do Farm, dentro da posição em cada farm - mostrando APR combinado com taxa LP e recompensas de CAKE\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Calculadora de ROI aprimorada <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Sempre que você vir os displays automáticos de APR, pode clicar e abrir a nova calculadora de ROI. A nova calculadora de ROI foi redesenhada com vários recursos adicionados para atender às necessidades do fornecimento de liquidez concentrada e farming do V3.

Vamos percorrer cada uma das seções juntos:

### Valor do Depósito, "Staked For" e "Compounding Every" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Esses três são os campos de entrada básicos, que também estavam presentes na calculadora de ROI anterior. Eles servem para definir:

1. Quantos ativos são fornecidos à posição de liquidez, em USD.
2. Por quanto tempo esses ativos ficarão em Staking na posição.
3. Com que frequência você irá compor as recompensas de volta para a posição.



⓵ **Valor do Depósito**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Você pode inserir manualmente o valor em USD, ou usar os botões de ação rápida para preencher rapidamente $100, $1000 ou o valor máximo permitido com base no saldo de tokens da sua carteira.



⓶ **Duração do Staking**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Você pode selecionar por quanto tempo os ativos ficam em Staking na posição de liquidez escolhendo entre: 1 dia, 7 dias, 30 dias, 1 ano e 5 anos.

O número de retorno será calculado com base na sua duração de Staking.



⓷ **Composição**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Você pode selecionar com que frequência irá colher as recompensas geradas pela posição e compô-las de volta para a posição. Você pode escolher entre: 12 horas, 1 dia, 7 dias e 30 dias.

O número de retornos e APY será calculado com base na sua escolha. Se você não planeja compor sua posição, desmarque a caixa de seleção à esquerda.

{% hint style="info" %}
No V3, as taxas LP e o CAKE ganho precisam ser colhidos e compostos manualmente.
{% endhint %}

### &#x20;⓸ Preço Histórico <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Esta é uma seção somente de visualização para referenciar o movimento histórico de preço do par selecionado.

Você pode referenciar os movimentos históricos de preço em diferentes períodos de tempo, como quanto o preço geralmente flutua, e então elaborar configurações de faixa de preço adequadas para equilibrar entre APR mais alto e menor risco de perda impermanente.

* MIN - preço mínimo
* MAX - preço máximo
* AVG - preço médio
* CURRENT - preço atual

{% hint style="info" %}
O gráfico de preços usa apenas dados do par V3 real. Portanto, dados de preço anteriores ao lançamento do V3 não estão disponíveis. As quatro métricas de preço representam o período de tempo selecionado atualmente e mudarão com base na seleção.
{% endhint %}

### ⓹ Faixa de Preço <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Usando esta seção, você pode verificar quanto de liquidez foi depositado em diferentes faixas de preço e elaborar e definir a faixa de preço para a qual está fornecendo liquidez.

Você pode encontrar o gráfico de distribuição abaixo do título. Quanto maior a quantidade de liquidez, mais alto o gráfico estará.

Você pode alterar as configurações de faixa de preço:

* Arrastando as duas alças no gráfico para aumentar ou reduzir o limite mínimo e máximo de preço.
* Usando o espaço entre as duas alças para deslocar a faixa selecionada.
* Clicando nos botões + e - nos campos de preço mínimo e máximo.
* Clicando nos números nos campos de preço e inserindo-os manualmente.

Se quiser navegar pelo gráfico de distribuição:

1. Use os botões de lupa de mais e menos para aumentar e diminuir o zoom
2. Arraste o eixo X (inferior) para deslocar para esquerda e direita

Se quiser fornecer liquidez para toda a faixa de preço, clique em "Full Range"

### ⓺ Inverter a direção do preço para visualizar preços com base diferente <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Para alguns pares de tokens, é mais fácil e intuitivo visualizar preços com determinados tokens base. Por exemplo, para o par BNB/USDT, a maioria das pessoas prefere visualizar os preços em "quantos USDT por BNB" em vez do contrário.

Você pode facilmente inverter os displays de preço. Basta clicar no botão após "View prices in:" para alternar a base entre os dois tokens do par.

### ⓻ Importar e exportar (aplicar) suas configurações <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Quando você abre a calculadora de ROI na janela "Add Liquidity", ou visualizando uma posição existente, as seguintes configurações serão automaticamente importadas para que você não precise defini-las novamente:

1. A quantidade de ativos que você está depositando
2. A faixa de preço
3. O nível de taxa selecionado

Quando terminar de configurar na calculadora de ROI, você pode clicar em "Apply Settings" para aplicar rapidamente as configurações da calculadora de volta à janela "Add Liquidity" sem precisar combiná-las manualmente.

### ⓼ Calcular recompensas de farming e APR <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

As recompensas de farming serão incluídas nos cálculos se você abrir a calculadora de ROI na página "Farm".

Você pode expandir as seções de detalhes para ver o detalhamento das recompensas.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
