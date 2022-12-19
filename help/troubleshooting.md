---
description: >-
  Mensagens comuns de erros. Use a barra lateral ➡️ para pular para o erro que
  você está buscando.
---

# Soluções de Erros e Problemas

![](../.gitbook/assets/troubleshooting-header.png)

Às vezes, você pode se deparar com um problema que não tem uma solução clara. Essas dicas de solução de problemas podem ajudá-lo a resolver os problemas que você encontrou.

## **Problemas na Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

> A transação não pode ser bem-sucedida devido ao erro: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. Este é provavelmente um problema com um dos tokens que você está fazendo swap.&#x20;
>
> a transação não pode ser bem-sucedida devido a um erro: execução revertida: pancakerouter: insuficiente\_output\_amount.

Você está tentando fazer swap de tokens, mas sua slippage tolerance (tolerância de deslizamento) é muito baixa ou a liquidez é muito baixa.

{% tabs %}
{% tab title="Solução" %}
1. Atualize sua página e tente de novo mais tarde.
2. Tente negociar uma quantidade menor de uma vez só.
3. Aumente seu slippage tolerance:
   1. Clique no ícone de configurações na página de liquidez.
   2. Aumente seu slippage tolerance um pouco e tente de novo. ![](<../.gitbook/assets/image (9) (4) (2) (1) (1) (1) (1) (1) (1).png>)
4. Por último, tente diminuir o numero de casas decimais.
{% endtab %}

{% tab title="Razão" %}
**Isso geralmente acontece ao negociar tokens com baixa liquidez.**

Isso significa que não há o suficiente de um dos tokens que você está tentando fazer swap na Pool de Liquidez: provavelmente é um token de pequena capitalização que poucas pessoas estão negociando.

No entanto, também há a chance de você estar tentando negociar um token fraudulento que não pode ser vendido. Nesse caso, a PancakeSwap não pode bloquear um token ou devolver fundos.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Você está tentando adicionar/remover liquidez de uma pool de liquidez (LP), mas não há um dos dois tokens suficientes no par.

{% tabs %}
{% tab title="Solução" %}
**Atualize sua página e tente de novo, ou tente de novo depois.**

Não funcionou mesmo assim?

1. Clique no ícone de configurações na página de liquidez.
2. Aumente seu slippage tolerance um pouco e tente de novo.

![](<../.gitbook/assets/image (9) (4) (2) (1) (1) (1) (1) (1) (1) (1).png>)
{% endtab %}

{% tab title="Razão" %}
O erro é causado ao tentar adicionar ou remover liquidez para uma pool de liquidez (LP) com uma quantidade insuficiente de token A ou token B (um dos tokens do par).&#x20;

Pode ser que os preços sejam atualizados muito rápido quando e sua slippage esteja muito baixa.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs\_pxdobz\_kY\_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt\_FAwpEylaIJhff5ZcYlzB\_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solução para Nerds" %}
OK, então você está realmente determinado a consertar isso. Nós realmente não recomendamos fazer isso a menos que você saiba o que está fazendo.&#x20;

Atualmente, não há uma maneira simples de resolver esse problema no site da PancakeSwap: você precisará interagir diretamente com o contrato. Você pode adicionar liquidez diretamente por meio do contrato do router, ao definir amountAMin para um valor pequeno e, em seguida, sacar toda a liquidez.

**Aprove o contrato do LP**

Vá para o contrato do token LP que você está tentando aprovar. Por exemplo, aqui está o par ETH/WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Selecione **Write Contract**, então clique em **Connect to Web3** e conecte sua carteira. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
2. Na **seção "1. approve",** aprove o LP token pelo router for the router inserindo
   1. spender (address): entre o endereço do contrato do LP token que você está tentando interagir
   2. value (uint256): -1

**Query "balanceOf"**

1. Mude para **Read Contract.**
2. No **5. balanceOf**, coloque seu endereço de carteira e clique **Query**.
3. Acompanhe o número que é exportado. Ele mostra seu saldo no LP no formato uint256, que você precisará na próxima etapa.

![](<../.gitbook/assets/image (7) (1) (1).png>)

**Adicione ou Remova Liquidez**

Vá para o contrato do router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Selecione **Write Contract** e **Connect to Web3** como acima.
2. Encontre **addLiquidity** ou **removeLiquidity** (qualquer um que você está tentando fazer)
3. Entre com o endereço do token de ambos tokens no LP.
4. No **liquidity (uint256),** entre o número uint256 que você tem de "balanceOf" acima.
5. Defina um baixo **amountAMin** ou **amountBMin**: tente 1 para ambos.
6. Adicione o endereço de sua carteira em **to (address)**.
7. Deadline deve ser um tempo de época maior que o tempo em que a tx é executada.

![](<../.gitbook/assets/image (5) (1) (1).png>)

{% hint style="warning" %}
Isso pode causar uma slippage(derrapagem) muito alta, e pode causar a perda de alguns fundo do usuários caso sofra frontrun
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

> A transação não pode ser bem-sucedida devido ao erro: PancakeRouter: EXPIRED. \
> Este é provavelmente um problema com um dos tokens que você está negociando.

Tente novamente, mas confirme (assine e transmita) a transação assim que você a gerar.&#x20;

Isso aconteceu porque você começou a fazer uma transação, mas não a assinou e transmitiu até o prazo final. Isso significa que você não clicou em "Confirmar" com rapidez suficiente.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

> A transação não pode ser bem-sucedida devido a um erro: Pancake: K. Este é provavelmente um problema com um dos tokens que você está negociando.

Tente modificar a quantidade no campo “To”. Portanto, colocando o símbolo "(estimado)" em "From". Em seguida, inicie o swap imediatamente.

![](<../.gitbook/assets/pancake-k-solution (2).png>)

Isso geralmente acontece quando você está tentando trocar um token com taxa própria.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

> A transação não pode ser bem-sucedida devido a um erro: execução revertida: Pancake: TRANSFER\_FAILED.

Certifique-se de ter 30% mais tokens em sua carteira do que pretende negociar ou tente negociar uma quantidade menor. Se você quiser vender o máximo possível, tente 70% ou 69% em vez de 100%. \
Pode ser causado pelo design de tokens Restorative Rebase como tDoge ou tBTC.[ \
Entenda como funciona restorative rebase tokens](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Outra possível causa desse problema é que o emissor do token malicioso acabou de suspender a negociação de seu token. Ou eles tornaram a ação de venda possível apenas para endereços de carteira selecionadas. Por favor, sempre faça sua própria pesquisa para evitar qualquer fraude em potencial. Se o token que você está tentando trocar e falhou com esse código de erro, vem de um airdrop, provavelmente é um golpe. Por favor, não execute nenhuma aprovação de token, nem clique ou siga nenhum link, seus fundos podem estar em risco se você tentar fazê-lo.

### Transaction cannot succeed (Transação não pode se suceder)

Tente negociar uma quantidade menor ou aumente a tolerância de derrapagem através do ícone de configurações e tente novamente. Isso é causado pela baixa liquidez.

### **Price Impact too High (Impacto do preço muito alto)**

Tente negociar uma quantidade menor ou aumente a tolerância de derrapagem através do ícone de configurações e tente novamente. Isso é causado pela baixa liquidez.

### estimateGas failed (falhou)

> This transaction would fail. Please contact support\
> \
> Essa transação falharia. Por favor contacte  o suporte

{% tabs %}
{% tab title="Solução" %}
**Se você recebeu este erro ao remover a liquidez de um par de BNB:**&#x20;

Selecione "Receber WBNB" e tente novamente.&#x20;

**Se você recebeu este erro ao tentar fazer swap:**&#x20;

Entre em contato com a equipe do projeto do token que você está tentando trocar. \*\*\*\* Este problema deve ser resolvido pela equipe do projeto.
{% endtab %}

{% tab title="Razão" %}
Esse problema (durante o swap) é causado por tokens que codificaram o router V1 da PancakeSwap em seu contrato.&#x20;

Embora essa prática seja, na melhor das hipóteses, desaconselhada, a razão para esses projetos terem feito isso parece ser devido à seu tokenomics, na qual cada compra envia uma % do token para os LPs.&#x20;

Os projetos afetados provavelmente não funcionarão com o router V2: eles provavelmente precisarão criar novas versões de seus tokens apontando para nosso novo endereço de rouoter e migrar quaisquer holders de token existentes para seu novo token.&#x20;

Recomendamos que todos os projetos que criaram esses tokens também se esforcem para impedir que seus usuários os adicionem ao LP V2.&#x20;

O endereço do router atualizado é\
[https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

> "Erro desconhecido: "Não é possível ler a propriedade 'toHexString' de indefinido"

Ao tentar fazer swap de tokens, a transação falha e esta mensagem de erro é exibida. Este erro foi relatado em dispositivos móveis usando a Trust Wallet.

{% tabs %}
{% tab title="Solução" %}
1. Tenta fazer a transação novamente aumentando o slippage.
2. Se 1. não resolver seu problema, considere usar outra carteira como SafePal para sua transação.
{% endtab %}

{% tab title="Razão" %}
**Isso  geralmente acontece ao negociar tokens com pouca slippage na Trust Wallet.**

O detalhe exato do problema ainda está sendo investigado.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

> A transação não pode ser bem-sucedida devido ao erro: execução revertida: TransferHelper: TRANSFER\_FROM\_FAILED.

Ao tentar trocar os tokens, a transação falha e esta mensagem de erro é exibida. Este erro foi relatado em todas as plataformas.

{% tabs %}
{% tab title="Solução" %}
1. Verifique se você tem fundos disponíveis suficientes.
2. Assegure de dar permissão ao contrato para gastar a quantidade de fundos que você está tentando negociar.
{% endtab %}

{% tab title="Razão" %}
Este erro ocorre ao negociar tokens com permissão insuficiente ou quando uma carteira tem fundos insuficientes.&#x20;

Se você estiver negociando tokens com Restorative Rebase como ativos tau tDoge ou tBTC, certifique-se de entender como eles funcionam primeiro com este [guia de Rebase tokens](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Problemas com Pools de Syrup**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

> Falha com erro 'BEP20: quantidade queimada excede saldo'

Você não tem SYRUP suficiente em sua carteira para sacar da pool CAKE-CAKE.&#x20;

Obtenha pelo menos tanto SYRUP quanto a quantidade de CAKE que você está tentando sacar.&#x20;

1. Compre SYRUP na exchange. Se você quiser retirar do stake 100 CAKE, precisará de pelo menos 100 SYRUP.&#x20;
2. Tente sacar novamente.&#x20;

Se isso ainda falhar, você pode realizar um “emergencyWithdraw” diretamente do contrato para sacar seus tokens em stake.

1. Vá para: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Clique em **“Connect to Web3”** e conecte sua carteira. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
3. Na seção **“4. emergencyWithdraw”**, entre "0" e clique “Write”.

Isso retirará seus tokens do stake e você perderá qualquer rendimento de CAKE não coletado.

{% hint style="warning" %}
**Isso faz com que você perca algum rendimento que você não tenha  sacado antes.**
{% endhint %}

Para impedir que isso aconteça novamente, não venda seu SYRUP. Você precisa dele para sacar o stake da pool “Stake CAKE Earn CAKE”.&#x20;

Este erro ocorreu porque você vendeu ou transferiu tokens SYRUP. SYRUP é cunhado em uma proporção de 1:1 para CAKE quando você faz stake na Pool de Syrup CAKE-CAKE. O SYRUP deve ser queimado na proporção de 1:1 para CAKE ao chamar leaveStaking (retirar seu CAKE do pool), portanto, se você não tiver o suficiente, não poderá sacar da pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]

> Aviso! Erro encontrado durante a execução do contrato \[sem gás]

Você definiu um limite de gás baixo ao tentar fazer uma transação.

{% tabs %}
{% tab title="Solução" %}
Tente aumentar manualmente o limite do gás (não o preço do gás!) em sua carteira antes de assinar a transação.&#x20;

Um limite de 200.000 geralmente é suficiente.

![](<../.gitbook/assets/image (2) (1).png>)

O exemplo acima é da Metamask; verifique a documentação da sua carteira se não tiver certeza de como ajustar o limite de gás.
{% endtab %}

{% tab title="Razão" %}
Basicamente, sua carteira (Metamask, Trust Wallet, etc.) não consegue terminar o que está tentando fazer.&#x20;

Sua carteira estima que o limite de gás é muito baixo, então a chamada da função fica sem gás antes que a chamada de função seja concluída.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

> Falha com erro 'BEP20: valor da transferência excede o permitido'

{% tabs %}
{% tab title="Solução" %}
1. Use o Unrekt.net para revogar a aprovação do contrato inteligente com o qual você está tentando interagir
2. Aprove o contrato novamente, sem definir um limite para gastos&#x20;
3. Tente interagir com o contrato novamente.
{% endtab %}

{% tab title="Reason" %}
Isso acontece quando você define um limite para o seu limite de gastos ao aprovar o contrato pela primeira vez e, em seguida, tenta trocar mais do que o limite.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

> Falha com erro 'BEP20: valor da transferência excede o permitido'

Você provavelmente está tentando retirar do stake de uma Pool de Syrup com baixas recompensas. Solução abaixo.&#x20;

Se não, então você pode estar tentando enviar tokens que não possui em sua carteira (por exemplo, tentando enviar um token que já está atribuído a uma transação pendente). Nesse caso, apenas certifique-se de ter os tokens que está tentando usar.

{% tabs %}
{% tab title="Solução" %}
Primeiramente,[ ](../contact-us/telegram.md)[conte ao time](https://docs.pancakeswap.finance/v/portuguese-brazilian/contact-us/telegram) qual pool você está tentando sacar o stake, para que eles possam completar as recompensas. Se você está com pressa para retirar o stake e não se importa em perder seu rendimento pendente, tente um saque de emergência:

Você pode realizar um “emergencyWithdraw” do contrato diretamente para sacar seus tokens em stake.

1. Encontre o endereço de contrato da Pool de Syrup que você está tentando retirar do stake. Você pode encontrar isso no log de transações da sua carteira.
2. Vá para [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) e na barra de busca, entre com o endereço do contrato.
3. Selecione **Write Contract.**
4. Clique **“Connect to Web3”** e conecte sua carteira.![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
5. Na seção **“3. emergencyWithdraw”,** e clique “Write”.

Isso vai retirar seus tokens do stake e vai perder algum rendimento não coletado.

{% hint style="warning" %}
**Isso fará com que você perca algum rendimento que você não sacou antes.**
{% endhint %}
{% endtab %}

{% tab title="Razão" %}
This error tends to appear when you're trying to unstake from an old Syrup Pool, but there aren't enough rewards in the pool left for you to harvest when withdrawing. This causes the transaction to fail.
{% endtab %}
{% endtabs %}

## **Problemas com Prediction**

Verifique [prediction-troubleshooting.md](../produtos/prediction/prediction-troubleshooting.md "mention")

## **Outros problemas**

### Provider Error

> Provider Error\
> No provider was found

> Erro do provedor \
> Nenhum provedor foi encontrado

Isso acontece quando você tenta se conectar por meio de uma extensão do navegador como MetaMask ou Binance Chain Wallet, mas não instalou a extensão.

{% tabs %}
{% tab title="Solução" %}
Instale a extensão oficial do navegador para conectar ou leia nosso guia sobre [como conectar uma carteira na PancakeSwap.](https://docs.pancakeswap.finance/v/portuguese-brazilian/get-started/connection-guide)
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

Mude sua chain para BNB Smart Chain. Verifique a documentação da sua carteira para obter um guia se precisar de ajuda.

### Already processing eth\_requestAccounts. Please wait.

Verifique se você está conectado ao seu aplicativo de carteira e conectado à BNB Smart Chain.

### Problemas comprando SAFEMOON e tokens similar

Para negociar SAFEMOON, você deve clicar no ícone de configurações e **definir sua tolerância de derrapagem para 12% ou mais.**\
Isso ocorre porque o **SafeMoon cobra uma taxa de 10% em cada transação**:

* 5% de taxa = redistribuído para todos os holderrs existentes
* 5% de taxa = usado para adicionar liquidez

É também por isso que você pode não receber tanto do token quanto espera ao comprar.\
Leia mais em [Como comprar Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Acontece ao tentar remover a liquidez de alguns tokens via Metamask. A causa raiz ainda é desconhecida. Tente usar uma carteira alternativa.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

Você não tem BNB suficiente para pagar as taxas de transação. Você precisa de mais BNB da rede BEP-20 em sua carteira.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Aumente o limite de gás para a transação em sua carteira. Verifique a documentação da sua carteira para saber como aumentar o limite de gás.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Causa pouco clara. Tente estas etapas antes de tentar novamente:

1. Aumente o limite de gás
2. Aumente o slippage
3. Limpe o cache

## **Problmas com Perfil**

### Oops! We couldn't find any Pancake Collectibles in your wallet.

(Ops! Não encontramos nenhum Colecionável da Pancake em sua carteira.)

Estamos investigando a lógica por trás desse problema. Enquanto isso, tente a solução alternativa.

{% tabs %}
{% tab title="Solução 1" %}
1. Vá para a página “Collectible”, então vá de volta para página de perfil.\
   Se você não pode encontrar o link, vá diretamente para [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles).
2. Tente novamente a criar o perfil.
{% endtab %}

{% tab title="Solução 2" %}
Mude o ambiente.

* Limpe o cache e tente novamente.
* Tente novamente em um navegador diferente.
* Tente novamente com aplicativos de carteira diferentes.
* Tetne novamente mudando rede de internet (troque entre Wi-Fi e celular)
{% endtab %}
{% endtabs %}

### Verificando username continua rodando

Existem duas possíveis causas.

1. Você tem muitas carteiras instaladas no navegador.
2. Problema na rede.

{% tabs %}
{% tab title="Solução 1" %}
Causa Raiz: Você tem várias carteiras instaladas no navegador.

Pode causar um conflito entre carteiras. Isso está fora do controle da PancakeSwap e não podemos fazer nada.&#x20;

1. Tenha apenas uma única carteira instalada no navegador, remova as outras.&#x20;
2. Reconecte a carteira e tente definir o nome de usuário novamente.
{% endtab %}

{% tab title="Solução 2" %}
Causa Raiz: Rede está instável.

Tente novamente.

1. Exclua completamente o que foi inserido no campo de texto.
2. Digite novamente o nome de usuário e aguarde alguns segundos.&#x20;
3. Se não funcionar, recarregue a página e tente novamente.
{% endtab %}
{% endtabs %}
