# 🎯 PancakeSwap Auto Slippage

A PancakeSwap introduziu o Auto Slippage para tornar o Trading mais fácil e eficiente. O Auto Slippage ajusta automaticamente o Slippage para você com base nas condições atuais do mercado, ajudando a evitar negociações com falha e reduzindo o risco de perder dinheiro por erros de Slippage.

## O que é Slippage?

**Slippage** ocorre quando o preço que você espera para uma negociação é diferente do preço em que a negociação é realmente concluída. Isso pode acontecer por vários motivos:

* Volatilidade do mercado – Os preços podem mudar rapidamente entre o momento em que você faz e confirma a ordem
* Baixa Liquidez – não há tokens suficientes disponíveis pelo preço esperado
* Atrasos no blockchain – os tempos de confirmação podem fazer o preço mudar antes de a negociação ser finalizada

{% hint style="info" %}
Exemplo:

Você tenta fazer Swap de 100 CAKE por BNB, esperando que 1 CAKE = 0,01 BNB. Mas quando sua negociação é processada, o preço mudou e você recebe apenas 0,0098 BNB por CAKE. Essa pequena diferença é o que chamamos de Slippage.
{% endhint %}

## O que é Tolerância de Slippage?

**Tolerância de Slippage** é a diferença máxima de preço que você está disposto a aceitar antes de sua negociação ser cancelada. Se o preço se mover além da sua tolerância definida, sua transação falhará para evitar perdas inesperadas.

{% hint style="info" %}
Exemplo:

Se você definir uma tolerância de Slippage de 1% e o preço mudar mais de 1% antes da conclusão da negociação, a negociação não será processada.
{% endhint %}

## O que acontece se minha Tolerância de Slippage for muito baixa?

Se sua tolerância de Slippage for **definida muito baixa**, há uma chance maior de sua transação falhar — especialmente quando:

* O mercado está volátil
* Você está fazendo Swap de tokens com baixa Liquidez
* Usando tokens com taxas ou mecânicas complexas

{% hint style="warning" %}
Importante: Mesmo que a transação falhe, você ainda consumirá taxas de gas pela tentativa.
{% endhint %}

## Apresentando o Auto Slippage - Por que o Auto Slippage é útil?

O Auto Slippage ajusta automaticamente seu Slippage com base nas condições atuais do mercado, economizando seu tempo e reduzindo o risco de negociações com falha.&#x20;

Com o **Auto Slippage**, não há necessidade de ajustar manualmente sua tolerância de Slippage. Isso ajuda a evitar problemas comuns como:

* **Definir Slippage muito baixo**, o que pode fazer as transações falharem devido a pequenas variações de preço durante a execução.
* **Definir Slippage muito alto**, o que pode resultar em receber menos tokens do que o esperado por aceitar uma faixa de preço mais ampla.

{% hint style="info" %}
Para garantir a melhor experiência de Trading, o Auto Slippage foi **ativado automaticamente**. Se uma tolerância de Slippage manual tiver sido definida, a nova configuração de Slippage será aplicada.
{% endhint %}



## Como o Auto Slippage funciona?

<pre class="language-html"><code class="lang-html"><strong>Auto Slippage (%) = (Custo de Gas em USD / Valor do Token de Saída em USD) * 100%
</strong></code></pre>

* Se o custo de gas for alto em comparação ao valor do token de saída, o Auto Slippage definirá um Slippage maior para garantir que a negociação seja concluída.
* Se o gas for barato e o valor do token de saída for grande, um Slippage menor será usado.

O Auto Slippage escolherá um valor entre **0,5%** e **5,0%**, dependendo das condições do token e da rede.



## O Auto Slippage está disponível em todas as redes?

Não — o Auto Slippage é suportado apenas em redes Layer 1 (L1) como BNB Chain, Ethereum, etc.

Não é suportado em redes Layer 2 (L2), porque:

* A fórmula de Auto Slippage depende de valores de custo de gas significativos para calcular uma configuração de Slippage útil
* Como as taxas de gas em L2 são muito baixas, aplicar Auto Slippage em L2s não melhoraria as taxas de sucesso das negociações

{% hint style="success" %}
&#x20;Se o Auto Slippage **não for suportado** em uma rede:

* Sua configuração de Slippage usada anteriormente será aplicada
* Se você não tiver definido uma antes, o padrão será 0,5%
{% endhint %}



