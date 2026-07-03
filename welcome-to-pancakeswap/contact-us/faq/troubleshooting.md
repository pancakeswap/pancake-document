---
description: Mensagens de erro comuns. Use a barra lateral ➡️ para ir ao erro que você está vendo.
---

# Solução de Erros

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

Às vezes você pode se encontrar diante de um problema que não tem uma solução clara. Estas dicas de solução de problemas podem ajudá-lo a resolver problemas que você encontrar.

## **Problemas na Corretora**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> A transação não pode ser concluída devido ao erro: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. Isso provavelmente é um problema com um dos tokens que você está trocando.
>
> a transação não pode ser concluída devido ao erro: execution reverted: pancakerouter: insufficient\_output\_amount.

Você está tentando fazer swap de tokens, mas sua tolerância de Slippage está muito baixa ou a liquidez está muito baixa.

{% tabs %}
{% tab title="Solução" %}
1. Atualize a página e tente novamente mais tarde.
2. Tente negociar uma quantidade menor de uma vez.
3. Aumente sua tolerância de Slippage:
   1. Toque no ícone de configurações na página de liquidez.
   2. Aumente um pouco sua tolerância de Slippage e tente novamente. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Por último, tente inserir uma quantidade com menos casas decimais.
{% endtab %}

{% tab title="Motivo" %}
**Isso geralmente acontece quando você negocia tokens com baixa liquidez.**

Isso significa que não há quantidade suficiente de um dos tokens que você está tentando trocar no Pool de Liquidez: provavelmente é um token de baixa capitalização que poucas pessoas estão negociando.

No entanto, também existe a possibilidade de que você esteja tentando negociar um token fraudulento que não pode ser vendido. Neste caso, o PancakeSwap não consegue bloquear um token ou devolver fundos.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT ou INSUFFICIENT\_B\_AMOUNT**

> Falha com o erro 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> ou\
> Falha com o erro 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Você está tentando adicionar/remover liquidez de um pool de liquidez (LP), mas não há quantidade suficiente de um dos dois tokens no par.

{% tabs %}
{% tab title="Solução" %}
**Atualize a página e tente novamente, ou tente mais tarde.**

Ainda não funciona?

1. Toque no ícone de configurações na página de liquidez.
2. Aumente um pouco sua tolerância de Slippage e tente novamente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Motivo" %}
O erro é causado ao tentar adicionar ou remover liquidez de um pool de liquidez (LP) com quantidade insuficiente do token A ou token B (um dos tokens do par).

Pode ser que os preços estejam se atualizando muito rapidamente e sua tolerância de Slippage esteja muito baixa.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solução para especialistas" %}
OK, então você está realmente determinado a resolver isso. Realmente não recomendamos fazer isso a menos que você saiba o que está fazendo.

Atualmente não há uma maneira simples de resolver esse problema pelo site do PancakeSwap: você precisará interagir diretamente com o contrato. Você pode adicionar liquidez diretamente pelo contrato do Router, definindo amountAMin para um valor pequeno e depois retirando toda a liquidez.

**Aprove o contrato LP**

Vá para o contrato do token LP que você está tentando aprovar.\
Por exemplo, aqui está o par ETH/WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Selecione **Write Contract**, depois **Connect to Web3** e conecte sua carteira. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. Na **seção "1. approve",** aprove o token LP para o router inserindo
   1. spender (address): insira o endereço do contrato do token LP com o qual está tentando interagir
   2. value (uint256): -1

**Consultar "balanceOf"**

1. Mude para **Read Contract.**
2. Em **5. balanceOf**, insira o endereço da sua carteira e clique em **Query**.
3. Anote o número exportado. Ele mostra seu saldo no LP no formato uint256, que você precisará no próximo passo.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Adicionar ou Remover Liquidez**

Vá para o contrato do router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Selecione **Write Contract** e **Connect to Web3** como acima.
2. Encontre **addLiquidity** ou **removeLiquidity** (o que você está tentando fazer)
3. Insira os endereços dos tokens de ambos os tokens no LP.
4. Em **liquidity (uint256),** insira o número uint256 que você obteve de "balanceOf" acima.
5. Defina um **amountAMin** ou **amountBMin** baixo: tente 1 para ambos.
6. Adicione o endereço da sua carteira em **to (address)**.
7. O Deadline deve ser um tempo epoch maior do que o momento em que a transação é executada.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Isso pode causar Slippage muito alto e pode fazer o usuário perder alguns fundos se houver frontrunning
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> A transação não pode ser concluída devido ao erro: PancakeRouter: EXPIRED. Isso provavelmente é um problema com um dos tokens que você está trocando.

Tente novamente, mas confirme (assine e transmita) a transação assim que a gerar.

Isso aconteceu porque você começou a fazer uma transação, mas não assinou e transmitiu até que o prazo tivesse expirado. Isso significa que você não clicou em "Confirmar" rápido o suficiente.

### Pancake: K

> A transação não pode ser concluída devido ao erro: Pancake: K. Isso provavelmente é um problema com um dos tokens que você está trocando.

Tente modificar o valor no campo "Para". Portanto, colocando o símbolo "(estimado)" em "De". Em seguida, inicie o swap imediatamente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Isso geralmente acontece quando você está tentando fazer swap de um token que tem sua própria taxa.

### Pancake: TRANSFER\_FAILED

> A transação não pode ser concluída devido ao erro: execution reverted: Pancake: TRANSFER\_FAILED.

Certifique-se de ter 30% a mais de tokens na sua carteira do que você pretende negociar, ou tente negociar uma quantidade menor. Se você quiser vender o máximo possível, tente 70% ou 69% em vez de 100%.\
Causado pelo design de tokens Restorative Rebase como tDoge ou tBTC.\
[Entenda como funcionam os tokens restorative rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Outra causa possível deste problema é que o emissor do token malicioso suspendeu as negociações do seu token. Ou eles tornaram a ação de venda possível apenas para endereços de carteira selecionados. Sempre faça sua própria pesquisa para evitar possíveis fraudes. Se o token que você está tentando fazer swap mas falhou com este código de erro veio de um airdrop, muito provavelmente é um golpe. Não faça nenhuma aprovação de token nem siga nenhum link, seus fundos podem estar em risco se você tentar fazer isso.

### A transação não pode ser concluída

Tente negociar uma quantidade menor, ou aumente a tolerância de Slippage pelo ícone de configurações e tente novamente. Isso é causado por baixa liquidez.

### **Impacto de Preço muito Alto**

Tente negociar uma quantidade menor, ou aumente a tolerância de Slippage pelo ícone de configurações e tente novamente. Isso é causado por baixa liquidez.

### estimateGas falhou

> Esta transação falharia. Por favor entre em contato com o suporte

{% tabs %}
{% tab title="Solução" %}
**Se você recebeu este erro ao remover liquidez de um par BNB:**

Por favor, selecione "Receive WBNB" e tente novamente.

**Se você recebeu este erro ao tentar fazer swap:**

Por favor, entre em contato com a equipe do projeto do token que você está tentando trocar. \*\*\*\* Este problema deve ser resolvido pela equipe do projeto.
{% endtab %}

{% tab title="Motivo" %}
**Este problema (ao fazer swap) é causado por tokens que incorporaram o router V1 do PancakeSwap em seus contratos.**

Embora essa prática seja no mínimo não recomendada, a razão pela qual esses projetos fizeram isso parece se dever à sua tokenomics, em que cada compra envia uma % do token para LPs.

Os projetos afetados provavelmente não funcionarão com o router V2: eles provavelmente precisarão criar novas versões de seus tokens apontando para nosso novo endereço de router e migrar os detentores de tokens existentes para o novo token.

Recomendamos que quaisquer projetos que criaram tais tokens também façam esforços para impedir que seus usuários os adicionem ao LP V2.

O endereço do router atualizado é [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Ao tentar fazer swap de tokens, a transação falha e esta mensagem de erro é exibida. Este erro foi reportado em dispositivos móveis usando Trust Wallet.

{% tabs %}
{% tab title="Solução" %}
1. Tente a transação novamente com tolerância de Slippage aumentada.
2. Se 1. não resolver seu problema, considere usar outra carteira como SafePal para sua transação.
{% endtab %}

{% tab title="Motivo" %}
**Isso geralmente acontece quando você negocia tokens com tolerância de Slippage insuficiente na Trust Wallet.**

Os detalhes exatos do problema ainda estão sendo investigados.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> A transação não pode ser concluída devido ao erro: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Ao tentar fazer swap de tokens, a transação falha e esta mensagem de erro é exibida. Este erro foi reportado em várias plataformas.

{% tabs %}
{% tab title="Solução" %}
1. Verifique se você tem fundos suficientes disponíveis.
2. Certifique-se de que você deu permissão ao contrato para gastar a quantidade de fundos que está tentando negociar.
{% endtab %}

{% tab title="Motivo" %}
Este erro acontece quando você negocia tokens com permissão insuficiente, ou quando uma carteira tem fundos insuficientes.\
Se você estiver negociando tokens com Restorative Rebase como ativos tau tDoge ou tBTC, certifique-se de entender como eles funcionam primeiro com este [guia para tokens Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Problemas com Farms**

### Falha com o erro 'ds-math-sub-underflow'

Você esgotou a permissão do seu token LP para o contrato MasterChef.

**Use um gerenciador de aprovação de tokens como unrekt ou BscScan para**

## **Problemas com Syrup Pools**

### BEP20: burn amount exceeds balance

> Falha com o erro 'BEP20: burn amount exceeds balance'

Você não tem SYRUP suficiente na sua carteira para fazer unstake do pool CAKE-CAKE.

**Obtenha pelo menos a mesma quantidade de SYRUP que a quantidade de CAKE que você está tentando retirar do staking.**

1. Compre SYRUP na corretora. Se você quiser retirar 100 CAKE do staking, você precisa de pelo menos 100 SYRUP.
2. Tente fazer o unstake novamente.

Se isso ainda falhar, você pode realizar um "emergencyWithdraw" diretamente do contrato para retirar seus tokens do staking.

1. Vá para: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Clique em **"Connect to Web3"** e conecte sua carteira. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Na seção **"4. emergencyWithdraw"**, insira "0" e clique em "Write".

Isso retirará seus tokens do staking e você perderá qualquer rendimento de CAKE não coletado.

{% hint style="warning" %}
**Isso fará com que você perca qualquer rendimento que ainda não colheu.**
{% endhint %}

Para evitar que isso aconteça novamente, **não venda seu SYRUP.** Você ainda precisa dele para retirar do staking o pool "Stake CAKE Earn CAKE".

Este erro ocorreu porque você vendeu ou transferiu tokens SYRUP. O SYRUP é cunhado em uma proporção de 1:1 com CAKE quando você faz staking no Syrup Pool CAKE-CAKE. O SYRUP deve ser queimado em uma proporção de 1:1 com CAKE ao chamar leaveStaking (retirando seu CAKE do pool), então se você não tiver o suficiente, não poderá retirar do pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Erro de Out of Gas

> Aviso! Erro encontrado durante a execução do contrato \[out of gas]

Você definiu um limite de gas baixo ao tentar fazer uma transação.

{% tabs %}
{% tab title="Solução" %}
Tente aumentar manualmente o **limite de gas** (não o preço do gas!) na sua carteira antes de assinar a transação.

Um limite de 200000 geralmente é suficiente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

O exemplo acima é do Metamask; verifique a documentação da sua carteira se não tiver certeza de como ajustar o limite de gas.
{% endtab %}

{% tab title="Motivo" %}
Basicamente, sua carteira (Metamask, Trust Wallet, etc.) não consegue concluir o que está tentando fazer.

Sua carteira estima que o limite de gas está muito baixo, então a chamada de função fica sem gas antes de ser concluída.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Falha com o erro 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Solução" %}
1. Use Unrekt.net para revogar a aprovação do smart contract com o qual está tentando interagir
2. Aprove o contrato novamente, sem definir um limite na permissão de gasto
3. Tente interagir com o contrato novamente.
{% endtab %}

{% tab title="Motivo" %}
Isso acontece quando você define um limite na sua permissão de gasto ao aprovar o contrato pela primeira vez e depois tenta fazer swap de mais do que o limite.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Falha com o erro 'BEP20: transfer amount exceeds balance'

Provavelmente você está tentando retirar o staking de um Syrup Pool com poucas recompensas. Solução abaixo.

Se não for isso, você pode estar tentando enviar tokens que não tem na sua carteira (por exemplo, tentando enviar um token que já está atribuído a uma transação pendente). Neste caso, apenas certifique-se de ter os tokens que está tentando usar.

{% tabs %}
{% tab title="Solução" %}
Primeiramente,[ informe a equipe](../social-accounts.md) qual pool você está tentando retirar do staking, para que possam recarregar as recompensas. Se você estiver com pressa para retirar do staking e não se importar em perder seu rendimento pendente, tente um emergencyWithdraw:

Você pode realizar um "emergencyWithdraw" diretamente do contrato para retirar seus tokens do staking.

1. Encontre o endereço do contrato do Syrup Pool do qual você está tentando retirar o staking. Você pode encontrá-lo no log de transações da sua carteira.
2. Vá para [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) e na barra de pesquisa, insira o endereço do contrato.
3. Selecione **Write Contract.**
4. Clique em **"Connect to Web3"** e conecte sua carteira.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Na seção **"3. emergencyWithdraw",** clique em "Write".

Isso retirará seus tokens do staking e você perderá qualquer rendimento não coletado.

{% hint style="warning" %}
**Isso fará com que você perca qualquer rendimento que ainda não colheu.**
{% endhint %}
{% endtab %}

{% tab title="Motivo" %}
Este erro tende a aparecer quando você está tentando retirar o staking de um Syrup Pool antigo, mas não há recompensas suficientes restantes no pool para você colher ao retirar. Isso faz a transação falhar.
{% endtab %}
{% endtabs %}

## **Problemas com Previsão**

Verifique [Link Quebrado](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Outros problemas**

### Erro de Provider

> Provider Error\
> No provider was found

Isso acontece quando você tenta se conectar por meio de uma extensão de navegador como MetaMask ou Binance Chain Wallet, mas não instalou a extensão.

{% tabs %}
{% tab title="Solução" %}
Instale a extensão oficial do navegador para se conectar, ou leia nosso guia sobre [como conectar uma carteira ao PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### ID de Rede Não Suportado

Mude sua rede para BNB Smart Chain. Verifique a documentação da sua carteira para obter um guia se precisar de ajuda.

### Already processing eth\_requestAccounts. Please wait.

Certifique-se de que está conectado ao aplicativo da sua carteira e que ele está conectado à BNB Smart Chain.

### Problemas ao comprar SAFEMOON e tokens similares

Para negociar SAFEMOON, você deve clicar no ícone de configurações e **definir sua tolerância de Slippage para 12% ou mais.**\
Isso ocorre porque **o SafeMoon cobra uma taxa de 10% em cada transação**:

* 5% de taxa = redistribuída para todos os detentores existentes
* 5% de taxa = usada para adicionar liquidez

É por isso que você pode não receber tantos tokens quanto espera ao comprar.\
Leia mais em [Como Comprar Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Erros internos de JSON-RPC

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Acontece ao tentar remover liquidez em alguns tokens via Metamask. A causa raiz ainda é desconhecida. Tente usar uma carteira alternativa.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Por favor tente novamente.

Você não tem BNB suficiente para pagar as taxas de transação. Você precisa de mais BNB de rede BEP-20 na sua carteira.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Aumente o limite de gas para a transação na sua carteira. Verifique a documentação da sua carteira para aprender como aumentar o limite de gas.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Causa não clara. Tente estas etapas antes de tentar novamente:

1. Aumente o limite de gas
2. Aumente o Slippage
3. Limpe o cache

## **Problemas com Perfil**

### Ops! Não encontramos nenhum Pancake Collectible na sua carteira.

Estamos investigando a lógica por trás deste problema. Enquanto isso, tente a solução alternativa.

{% tabs %}
{% tab title="Solução 1" %}
1. Vá para a página "Collectible", depois volte para a página de perfil.\
   Se não encontrar o link, acesse [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) diretamente.
2. Tente criar o perfil novamente.
{% endtab %}

{% tab title="Solução 2" %}
Mude o ambiente.

* Limpe o cache e tente novamente.
* Tente em um navegador diferente.
* Tente em aplicativos de carteira diferentes.
* Tente em uma rede diferente (alterne entre Wi-Fi e dados móveis)
{% endtab %}
{% endtabs %}

### A verificação do nome de usuário continua girando

Há duas causas possíveis.

1. Você tem múltiplas carteiras instaladas no navegador.
2. Problema de rede.

{% tabs %}
{% tab title="Solução 1" %}
Causa raiz: Você tem múltiplas carteiras instaladas no navegador.\
\
Isso pode causar conflito entre as carteiras. Isso está fora do controle do PancakeSwap e não há nada que possamos fazer.

1. Tenha apenas uma carteira instalada no navegador, remova as outras.
2. Reconecte a carteira e tente definir o nome de usuário novamente.
{% endtab %}

{% tab title="Solução 2" %}
Causa raiz: A rede está instável.

Você precisa tentar novamente.

1. Delete completamente o que foi inserido no campo de texto.
2. Digite o nome de usuário novamente e aguarde alguns segundos.
3. Se não funcionar, recarregue a página e tente novamente.
{% endtab %}
{% endtabs %}
