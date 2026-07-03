---
description: Fornecimento de liquidez simples com apenas um clique
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### O que é o Zap? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

O Zap permite o fornecimento de liquidez de forma simples. Adicione liquidez com apenas um token e um único clique, sem necessidade de swap manual ou balanceamento de tokens.

* Adicionar liquidez com apenas um token: Você pode adicionar liquidez usando apenas um token do par de negociação. O Zap realizará swaps automaticamente usando o token que você fornecer e balanceará automaticamente o par de negociação em uma proporção 50/50 antes de adicionar liquidez.
* Adicionar liquidez com uma quantidade desequilibrada de tokens no par de negociação: Você pode adicionar liquidez mesmo que a quantidade de tokens que fornecer no par de negociação não seja perfeitamente balanceada com o pool atual. Por exemplo, 30:70, que difere do peso padrão do pool de 50:50. O Zap rebalanceará automaticamente os tokens em uma proporção 50/50 antes de adicionar liquidez.
* Remover liquidez e escolher qual(is) token(s) deseja receber: Ao remover liquidez, o Zap permite receber apenas um token do par de negociação. O Zap realizará swaps automaticamente antes de devolver seus tokens.

### Habilitar o Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Por padrão, o recurso Zap está ativado para todos os usuários. Se você não vir a nova interface do Zap ao adicionar ou remover liquidez, habilite-o no painel de configurações. Você pode abrir o painel de configurações clicando no ícone de engrenagem.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Nota: Atualmente, o recurso Zap está em beta. Observe que não suporta alguns tokens, como tokens com taxas em transferências. Se você encontrar algum problema ao adicionar ou remover liquidez, desative-o no painel de configurações.
{% endhint %}

### Zap In (Adicionar Liquidez) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Visite a [página de Liquidez](https://pancakeswap.finance/liquidity) e escolha "Add Liquidity".

Escolha o par de negociação para o qual deseja fornecer liquidez selecionando dois tokens de entrada; confira o [guia de Liquidez](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) para saber mais.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Clique no botão "Add Liquidity" para prosseguir.

Se o token no par de negociação para o qual você está adicionando liquidez tiver saldo na sua carteira, a caixa de seleção para esse token será automaticamente marcada. Se você tiver saldo em ambos os tokens, ambas as caixas serão marcadas.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap usando um token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Você pode adicionar liquidez usando apenas um token do par de negociação. Simplesmente marque apenas uma caixa para o token que deseja usar. O Zap trocará automaticamente metade dos tokens marcados pelo outro token do par de negociação antes de adicionar liquidez. Você verá uma mensagem de aviso indicando qual token será convertido.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Se o impacto de preço for muito alto, o Zap o protegerá por Slippage. Clique em "Reduce TOKEN" para reduzi-lo ao limite preferido.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap usando dois tokens com valores desequilibrados <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Se ambos os tokens estiverem marcados, mas as quantidades dos tokens de entrada não corresponderem a uma proporção 50/50, o balanceamento do Zap será ativado. Você verá uma mensagem de "Some of your Token A will be converted to Token B".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Se não quiser que o Zap balance a quantidade de tokens antes de adicionar liquidez, basta clicar em "Don't Convert". Nesse caso, o Zap ajustará a quantidade de tokens de entrada para corresponder a uma proporção 50/50 em vez de tentar realizar o swap e rebalanceamento.
{% endhint %}

### Prosseguir com o Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Quando você clicar em "Supply", os detalhes do Zap serão exibidos e aguardarão sua confirmação.

Você verá:

1. Quantos LP Tokens você receberá.
2. Quais são os tokens de entrada e a quantidade de tokens que você está comprometendo.
3. Como os tokens de entrada são negociados para corresponder a uma proporção 50/50.
4. A tolerância de Slippage que você está usando.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out (Remover Liquidez) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

O Zap também permite receber um único token do par de negociação ao remover liquidez.

1. Visite a[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj_97-YuUMQjQbYbfN4)[página de Liquidez](https://pancakeswap.finance/swap#/pool).
2. Clique no par do qual deseja remover liquidez em "Your Liquidity".
3. Clique em "Remove". Um novo pop-up aparecerá.

Na seção "You Will Receive", você pode desmarcar o token que não deseja receber. O Zap realizará swaps automaticamente e converterá 100% dos retornos no token marcado ao remover liquidez.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
