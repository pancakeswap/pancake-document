# Como usar TWAP

## O que é TWAP?

TWAP (Time-weighted Average Price) é um tipo de ordem comum usado em CeFi que divide uma ordem em tamanhos menores e as executa em intervalos regulares. O principal objetivo de uma ordem TWAP é reduzir o impacto de preço da ordem. Também pode ser útil se um usuário quiser implementar uma estratégia de custo médio em dólares (DCA) e comprar um determinado token em um cronograma consistente (ou seja, uma vez por mês).

Portanto, o TWAP é melhor utilizado quando o tamanho da ordem é grande em comparação com a liquidez disponível, ou quando um usuário antecipa um período de alta volatilidade de preços sem uma tendência clara de alta ou baixa.

## Como configurar uma ordem TWAP?

1. Vá para a página de Swap e selecione a opção de ordem TWAP clicando em TWAP
2. Selecione os tokens "De" e "Para" e insira o valor que deseja negociar.
3. A interface habilita tanto ordens dTWAP de mercado, que executam todas as negociações ao preço de mercado disponível, quanto ordens dTWAP limitadas, que só executam negociações individuais se estiverem dentro do limite de preço definido pelo usuário. \
   Neste exemplo, optamos por executar as ordens TWAP ao preço de mercado.
4. Em seguida, especificamos os parâmetros do TWAP. Existem 3 parâmetros principais que controlam a eficácia da ordem dTWAP:
   1. Total de negociações: Permite ao usuário especificar o número de negociações individuais nas quais sua ordem será dividida. O controle deslizante da interface começa com 1 negociação e permite ao usuário aumentar a quantidade de negociações individuais, ou permite que o usuário insira manualmente o total de negociações diretamente no campo de entrada.\
      Os usuários devem notar que há uma certa troca ao especificar este parâmetro: mais negociações significa tamanhos menores por negociação, o que significa menor impacto de preço. No entanto, mais negociações também significa mais transações e taxas de gas totais mais altas.&#x20;
   2. Intervalo de Negociação: Define o intervalo de tempo entre cada negociação individual. A interface começa com o mínimo permitido (2 min), o que deixa o tempo mínimo para a guerra de lances dos tomadores e liquidação de bloco entre cada tranche. O usuário pode definir qualquer duração desejada. Uma negociação nunca será executada antes que esse tempo decorra após a negociação anterior.\
      Novamente, os usuários devem estar atentos ao definir este parâmetro: intervalos mais longos permitem que os arbitragistas tenham uma janela mais longa para fechar quaisquer discrepâncias de preço nos pools afetados e trazer as reservas de volta ao equilíbrio (em linha com o preço à vista). No entanto, levaria mais tempo para a ordem ser preenchida e adicionaria incerteza ao preço final de preenchimento, especialmente em momentos de maior volatilidade.
   3. Duração Máxima: O tempo máximo durante o qual o valor total de todas as negociações individuais que compõem a ordem dTWAP completa pode ser executado. Após esse prazo, a negociação expira, independentemente dos valores realmente trocados.\
      Observe que todas as tranches podem não ser executadas em ordens limitadas, dependendo se o preço permanece dentro dos parâmetros definidos. \
      A duração padrão recomendada é calculada multiplicando o número de intervalos pelo intervalo de negociação e, em seguida, dobrando esse valor para servir como buffer e permitir tempo suficiente para a atividade on-chain. (observe que definir uma duração mais curta do que o padrão acima pode resultar em uma ordem parcialmente preenchida).

Como pode ser visto, esses parâmetros fornecem flexibilidade significativa na personalização de cada ordem, levando em consideração fatores como condições de mercado, taxas de gas atuais, etc.

8. Pressione "Colocar ordem". Verifique novamente os detalhes da sua ordem, aceite o aviso de isenção de responsabilidade e pressione "Confirmar ordem".
9. Após o processamento da transação, você poderá ver o status da sua ordem na seção de histórico de ordens, em "Ordens abertas".
10. As ordens abertas podem ser canceladas a qualquer momento expandindo a ordem e clicando no botão "Cancelar Ordem".

Pontos a considerar

* As ordens são executadas em negociações menores ao longo de um período de tempo especificado e estão sujeitas às condições de mercado e outros riscos.
* Sua negociação pode ser executada a um preço significativamente diferente do preço de mercado atual (embora não pior do que o preço limite definido, se você tiver definido um), o que pode resultar em perdas significativas. Se o preço de mercado disponível for pior do que o preço limite definido, algumas das negociações da sua ordem podem não ser executadas, resultando em uma ordem parcialmente preenchida.
* As negociações são baseadas em um protocolo descentralizado que utiliza tomadores off-chain que competem para preencher as ordens. Esses tomadores têm o direito de solicitar uma taxa, que o protocolo desconta do tomador vencedor a partir dos tokens de saída.&#x20;
* Os tomadores podem levar em conta as taxas de gas das suas transações ao definir suas taxas, o que pode resultar em flutuações nos valores das taxas.

<br>
