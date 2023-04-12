# Calculador de APR/ROI/IL

Na Liquidez e Farms V3, com a nova liquidez não-fungível e capacidade de faixa de preço personalizável. Cada posição de LP terá sua própria taxa de LP e APR de farm de CAKE.&#x20;

Para tornar o fornecimento de liquidez mais suave e menos desafiador, os novos monitores de APR automáticos com uma nova calculadora de ROI estão disponíveis para uso sempre que você estiver fornecendo liquidez ou farmando.

### Cálculo Automático de  APR e displays <a href="#12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F76hQbgenBdAwjLrRCz9W%2Fimage.png?alt=media\&token=5ce0e895-e984-4692-8742-f8a26af1f1b0)

Quando você está fornecendo liquidez, a exibição automática de APR reage às suas alterações de configuração e calcula o APR com base em suas configurações.&#x20;

Por exemplo, na maioria dos casos, se você apertar suas configurações de faixa de preço, o APR sobe.&#x20;

Por favor, note para APRs de taxa de LP:

* O valor estimado das recompensas de taxa de LP varia de acordo com o nível de taxa selecionado, as recompensas de taxa exigem reivindicação e reinvestimentos manuais.&#x20;
* Os valores de APR são calculados usando o volume histórico de negociação, que depende do Subgraph e pode estar sujeito a atrasos de indexação.&#x20;

Para APRs de farm:&#x20;

* A quantidade estimada de recompensas de CAKE é baseada nas emissões de CAKE para os farms. Eles estão sujeitos a alterações com base em futuros ajustes de emissão.

{% hint style="info" %}
Os números são calculados de acordo com as taxas e condições atuais da pool e estão sujeitos a alterações com base em várias variáveis externas. São estimativas fornecidas apenas para sua conveniência e de forma alguma representam retornos garantidos.
{% endhint %}

Você pode encontrar esta exibição de APR em:&#x20;

* Página "Adicionar liquidez" - mostrando APR da taxa de LP
* Página de detalhes de cada posição de liquidez existente - mostrando APR de taxa de LP

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FoX2q9WpmbutjcYOTaKbT%2Fimage.png?alt=media\&token=7a756974-548d-4323-a59e-4cfebc1374a4)

*   Página do farm, dentro da posição de cada farm - mostrando o APR combinado com taxa de LP e recompensas de CAKE

    ![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2Fv8eCjGpa9KucBkn482iz%2Fimage.png?alt=media\&token=bf9ddf07-8c5a-44e6-94bd-1bf2318c6883)

### Calculadora de ROI Melhorada <a href="#6f06dc46-ff61-4022-a29d-3ebe67a50607" id="6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FzZ4cVUNeONb10YOysgn6%2Fimage.png?alt=media\&token=b226af58-af86-4fdc-b8da-a2271bd75d46)

Sempre que vir as exibições automáticas de APR, você pode clicar e abrir a nova calculadora de ROI. A nova calculadora de ROI foi redesenhada com recursos adicionais para atender às necessidades de fornecimento e farm de liquidez concentrada V3.&#x20;

Vamos passar por cada uma das seções juntos:&#x20;

### Valor do Depósito, “Staked For” e “Compounding Every”&#x20;

Essas três são as entradas básicas, que também são apresentadas na calculadora de ROI anterior. Eles estão lá para definir:&#x20;

1. Quantos ativos são fornecidos para a posição de liquidez, em USD.
2. Por quanto tempo esses ativos serão apostados na posição.
3. Com que frequência você estará acumulando recompensas de volta à posição.

### **​**⓵ Quantidade de **Depósito**

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FxeGFM0iiW9gaKO4Z1sUE%2Fdeposit-amount.gif?alt=media\&token=eef5bf76-619b-4e88-9079-2d390887c232)

Você pode inserir manualmente o valor em USD ou usar os botões de ação rápida para preencher rapidamente $100, $1.000 ou o valor máximo permitido com base no saldo de token em sua carteira.

### ⓶ Duração de **Stake**

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2Fv3i11M6T9hNDBLFMM8Ti%2Fstake-durations.gif?alt=media\&token=97787a14-219e-46fe-b0ce-e82893807f41)

Você pode selecionar por quanto tempo os ativos estão em stake na posição de liquidez, escolhendo entre: 1 dia, 7 dias, 30 dias, 1 ano e 5 anos.&#x20;

O número de retorno será calculado com base na duração do stake.

### ⓷ **Reinvestimento**

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FQizMwRiC2jKsS4a2TdJB%2Fcompounding.gif?alt=media\&token=3d7b2fb1-217b-4e23-b5ad-fc50065e55bb)

Você pode selecionar a frequência com que colherá as recompensas geradas pela posição e combiná-las de volta à posição. Você pode escolher um número entre: 12 horas, 1 dia, 7 dias e 30 dias.&#x20;

O número de devoluções e o APY serão calculados com base na sua escolha. Se você não planeja aumentar sua posição, desmarque a caixa de seleção à esquerda.&#x20;

{% hint style="info" %}
Na V3, as taxas de LP e o CAKE ganho devem ser colhidos e reinvestidos manualmente.
{% endhint %}

### ⓸ HIstórico de Preço <a href="#19cd815c-ef3d-496a-8469-fb0164f3946b" id="19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FpLg9IUMS6ixVx1B6Ains%2Fimage.png?alt=media\&token=7b1e1b28-da50-4724-b655-96b63de226b4)

​Esta é uma seção somente para visualização de refrência ao movimento histórico de preços do par selecionado.&#x20;

Você pode fazer referência aos movimentos históricos de preços em diferentes prazos, como o quanto o preço geralmente flutua e, em seguida, definir configurações de faixa de preço adequadas para equilibrar entre APR mais alto e menor risco de perda impermanente.

* MIN - preço mínimo
* MAX - preço máximo
* AVG - preço médio
* CURRENT - preço atual

{% hint style="info" %}
O gráfico de preços está usando apenas dados reais do par V3. Portanto, os dados de preço antes da implantação da V3 não estão disponíveis. As quatro métricas de preço representam o período de tempo atualmente selecionado e serão alteradas com base na seleção.
{% endhint %}

### ​⓹ Faixa de Preço&#x20;

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FdkCIM5NYI1VLXsk9UEdF%2Fprice-range.gif?alt=media\&token=6eea25b6-a602-48c3-9f87-8baf6ccc87cf)

​

Usando esta seção, você pode verificar quanta liquidez foi depositada em diferentes faixas de preço e definir a faixa de preço para a qual está fornecendo liquidez.&#x20;

Você pode encontrar o gráfico de distribuição abaixo do título. Quanto maior a quantidade de liquidez, maior será o gráfico.&#x20;

Você pode alterar suas configurações de faixa de preço:&#x20;

* Arrastando as duas alças no gráfico para aumentar ou descrever o limite de preço mínimo e máximo.&#x20;
* Usando o espaço entre duas alças para deslocar o intervalo selecionado.&#x20;
* Clicando no botão + e - nos campos de preço mínimo e máximo.&#x20;
* Clicando nos números nos campos de preços e inserindo-os manualmente.&#x20;

Se você quiser navegar no gráfico de distribuição:&#x20;

1. Use os botões de lupa de mais e menos para aumentar e diminuir o zoom&#x20;
2. Arraste o eixo X (inferior) para deslocar para a esquerda e para a direita

Se você deseja fornecer liquidez para toda a faixa de preço, clique em “Full Range”

### ⓺ Mude a direção do preço para ver os preços com base diferente

​

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F4wCpMZYq7LoIJhCqK5kY%2Fflip-directions.gif?alt=media\&token=70be9e06-1ca1-402e-8555-d3d8faeae6ac)

​Para alguns pares de tokens, é mais fácil e intuitivo visualizar preços em base a determinados tokens. Por exemplo, para o par BNB/USDT, a maioria das pessoas prefere ver os preços em “quantos USDT por BNB” em vez do contrário.&#x20;

Você pode facilmente inverter as exibições de preços. Basta clicar no botão “Ver preços em:” para alternar a base entre os dois tokens do par.

### ⓻ Importar e exportar (aplicar) suas configurações

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FHlHRPEirzoNWlV3OuNgO%2Fapply-settings.gif?alt=media\&token=cfcc5816-334c-4114-aa90-248e58fc5d09)

​Ao abrir a calculadora de ROI na janela “Adicionar liquidez” ou ao visualizar uma posição existente, as seguintes configurações serão importadas automaticamente para que você não precise defini-las novamente:

1. A quantidade de ativos que você está depositando
2. A faixa (range) de preço
3. O nível de taxa selecionado

Quando terminar de configurar na calculadora de ROI, você pode clicar em “Aplicar as configurações” para aplicar rapidamente as configurações da calculadora de volta à janela “Adicionar liquidez” para que você não precise combiná-las manualmente.

### ⓼ Calcule as recompensas de farms e APR

As recompensas de farm serão incluídas nos cálculos se você abrir a calculadora de ROI na página de "Farm".

Você pode expandir as seções de detalhes para ver o detalhamento das recompensas.

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F0rhvwVZvMFUvjHEOy0KW%2Fimage.png?alt=media\&token=be6c8e4c-2574-4a9c-9f76-18321fc68ce5)
