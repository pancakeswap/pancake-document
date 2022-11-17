# Como fazer StableSwap?

<figure><img src="../../.gitbook/assets/how-to-stableswap.png" alt=""><figcaption></figcaption></figure>

## Fazendo Trade no StableSwap&#x20;

A negociação no StableSwap é muito semelhante ao uso do PancakeSwap AMM existente. Antes de começarmos, também requer uma carteira compatível com BNB Smart Chain e BNB para taxas de gás. Por favor, verifique nosso [guia de carteira](https://docs.pancakeswap.finance/v/portuguese-brazilian/get-started/wallet-guide) para mais detalhes.&#x20;

1 - Vá para a página de swap [aqui](https://pancakeswap.finance/swap#/swap)&#x20;

2 - Clique na aba “StableSwap”

![](<../../.gitbook/assets/image (1).png>)

3 - Escolha os pares de tokens que você gostaria de negociar. No lançamento, apenas um par (HAY-BUSD) será adicionado, pares de mais stables serão adicionados gradualmente

![](<../../.gitbook/assets/image (5).png>)

4 - A partir deste passo, o processo de swap é o mesmo da PancakeSwap normal! Por favor, verifique o guia [aqui](https://docs.pancakeswap.finance/v/portuguese-brazilian/produtos/pancakeswap-exchange/trade-guide) a partir do passo 4 em diante

## Adicionando e removendo liquidez

Adicionar e remover liquidez no StableSwap também é muito importante e semelhante ao AMM da PancakeSwap normal. Consulte o guia [aqui](https://docs.pancakeswap.finance/v/portuguese-brazilian/produtos/pancakeswap-exchange/liquidity-guide) para obter uma explicação mais detalhada.&#x20;

Existem algumas diferenças para a liquidez do StableSwap:&#x20;

1 - Quando você seleciona os pares de ativos que estão habilitados para StableSwap (por exemplo, HAY-BUSD), o frontend solicitará que você forneça “LP de Stable”

![](<../../.gitbook/assets/image (7).png>)

2 - O fornecimento dos dois ativos pode estar desequilibrado na fase de fornecimento, existindo uma página de confirmação para mostrar a proporção do seu fornecimento.

![](<../../.gitbook/assets/image (10) (1).png>)

3 - Você receberia um token Stable-LP como recibo do fornecimento de liquidez, para futuro saque e remoção.

![](<../../.gitbook/assets/image (6).png>)

4 - No entanto, OBSERVE que ao remover a liquidez, você sempre obterá 50%/50% dos ativos, independentemente da proporção de quando você adicionou. Como exemplo simplificado, se você forneceu 199 HAY e 1 BUSD, ao remover a liquidez, você receberá 100 HAY e 100 BUSD assumindo 0 de slippage/derrapagem e preços estáveis de 1:1.

![](<../../.gitbook/assets/image (3) (1).png>)

## Migre seu Stake de Farm HAY-BUSD&#x20;

Antes do lançamento do StableSwap, a liquidez HAY-BUSD e o farm de LP já estão disponíveis no PancakeSwap em seu swap AMM v2 normal. No entanto, como estamos lançando o HAY-BUSD como o primeiro par de negociação em nosso StableSwap, é provável que a maioria de vocês que gostaria de negociar este par acabe mudando para o StableSwap em vez de continuar usando o swap v2 AMM, porque:&#x20;

* Você pode fazer swap de forma mais eficiente com os mesmos passos de negociação&#x20;
* Com a função StableSwap, a slippage/derrapagem de negociação é menor do que o AMM normal, que usa apenas a fórmula do produto constante&#x20;
* As taxas de negociação são mais baixas em comparação com o AMM normal&#x20;

**OBSERVAÇÃO: Se você não estiver farmando com o HAY-BUSD LP, não precisará fazer nenhuma migração.**&#x20;

**Por que o farm? Por que o staking do farm precisa ser migrado? Staking precisa ser migrado?**&#x20;

Como a maioria das atividades de negociação do HAY-BUSD será no StableSwap usando o Stable LP daqui para frente, os incentivos de CAKE devem ser direcionados para recompensar os participantes do LP de Stable por incentivá-los a fornecer a liquidez. Haveria menos atividade para o LP HAY-BUSD original (com o v2 AMM).

## Como migrar o LP?

Haverá uma janela de 24 horas a partir do lançamento do StableSwap e antes que os incentivos CAKE sejam redirecionados e o novo farm de LP Stable de HAY-BUSD seja lançado. Aqui está o que você deve fazer se estiver atualmente fazendo stake de HAY-BUSD LP no farm:&#x20;

1 - Faça unstake do LP de HAY-BUSD da [página dos farms](https://pancakeswap.finance/farms)

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-21 at 7.27.18 PM.png" alt=""><figcaption></figcaption></figure>

2 - Remova a liquidez do seu LP de HAY-BUSD na [página de liquidez](https://pancakeswap.finance/liquidity)&#x20;

3 - Adicione liquidez novamente para HAY-BUSD (desta vez você deve ver que está adicionando no Stable LP durante o processo)

![](<../../.gitbook/assets/image (2) (1).png>)

4 - Coloque seu LP de Stable de HAY-BUSD na [página de farms](https://pancakeswap.finance/farms) - procure o card com o rótulo Stable LP

<figure><img src="../../.gitbook/assets/Screenshot 2022-09-21 at 7.48.09 PM.png" alt=""><figcaption></figcaption></figure>

## Linha do Tempo <a href="#timeline" id="timeline"></a>

* Lançamento do StableSwap e fornecimento de liquidez HAY-BUSD habilitada: 22 de setembro de 2022 11:00 UTC&#x20;
* Migração do farm (recompensas de CAKE redirecionadas do Farm de LP de HAY-BUSD para Farm de LP de Stable de HAY-BUSD): 23 de setembro de 2022 11:00 UTC

