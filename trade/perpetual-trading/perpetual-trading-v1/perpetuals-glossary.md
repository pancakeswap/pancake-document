# Glossário de Perpétuos V1

**Aqui você encontrará definidos todos os termos inerentes ao trading de futuros**

### **Trading Perpétuo**

&#x20;Perpétuos, swaps perpétuos ou perps são um tipo especial de contrato futuro sem data de vencimento.



### **Alavancagem**

A alavancagem é um mecanismo de trading. Os traders podem usá-la para aumentar sua exposição ao mercado, permitindo que paguem menos do que o valor total do investimento. Em termos simples, você toma dinheiro emprestado para alavancar seu investimento.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Margem**

é a garantia que você coloca para suas posições alavancadas. Tem dois Modos de uso:

* Modo de Margem Cross: Todas as posições cross sob o mesmo ativo de margem compartilham o mesmo saldo de margem cross do ativo. Em caso de Liquidação, o saldo de margem completo dos seus ativos juntamente com quaisquer posições abertas restantes sob o ativo podem ser perdidos.
* Modo de Margem Isolada: Gerencie seu risco em posições individuais restringindo a quantidade de margem alocada para cada uma. Se a taxa de margem de uma posição atingir 100%, a posição será liquidada. A margem pode ser adicionada ou removida das posições usando este modo.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Taxa de Margem**: Taxa de Margem = Margem de Manutenção / Saldo de Margem. Suas posições serão liquidadas quando a Taxa de Margem atingir 100%.

**Taxa de Manutenção**: O valor mínimo de saldo de margem necessário para manter suas posições abertas.

**Saldo de Margem** = Saldo da Carteira + PNL Não Realizado. Suas posições serão liquidadas quando o Saldo de Margem <= Margem de Manutenção.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Ativos:

**Depósito**: Deposite seus fundos na sua conta de futuros

**Saque**: Retire seus fundos da sua conta de futuros para sua carteira

**Saldo**: Saldo da Carteira = Total de Transferências Líquidas + Total de Lucro Realizado + Total de Taxa de Financiamento Líquida - Total de Comissões.

**PNL Não Realizado**: Lucro e perda não realizados nesta posição calculados com base no Preço de Marcação, e porcentagem de retorno sobre o patrimônio.

**Modos:**&#x20;

* Modo de Ativo Único: Suporta trading de Futuros USDⓈ-M usando apenas o ativo de margem único do símbolo. O PNL das posições do mesmo ativo de margem pode ser compensado. Suporta Modo de Margem Cross e Modo de Margem Isolada.
* Modo Multi-Ativos: Trading de Futuros USDⓈ-M em múltiplos ativos de margem. O PNL pode ser compensado entre as diferentes posições de ativos de margem. Suporta apenas o Modo de Margem Cross.

{% hint style="info" %}
Nota: Se houver posições abertas ou ordens abertas em Futuros USDⓈ-M, o Modo Multi-Ativos não pode ser ativado. O Modo Multi-Ativos se aplica apenas a Futuros USDⓈ-M. Antes de ativar o Modo Multi-Ativos, leia o guia em detalhes para gerenciar melhor o risco da conta de Futuros USDⓈ-M ao usar o Modo Multi-Ativos.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### Ordens

**Comprar/Long:** Abrir uma ordem Long. Nesta ordem você compra um ativo e espera para vender quando o preço subir. "Comprar" e "long" são usados de forma intercambiável.

**Vender/Short:** Abrir uma ordem Short. Nesta ordem, você toma emprestado um ativo, vende-o e espera recomprá-lo quando o preço cair. "Vender" e "short" são usados de forma intercambiável.

**Ordem Limitada:** Uma ordem limitada é uma ordem para comprar ou vender a um preço específico ou melhor. Ordens limitadas não têm execução garantida.

**Ordem de Mercado:** Uma ordem de mercado é uma ordem para comprar ou vender ao melhor preço corrente disponível. É executada contra as ordens limitadas que foram colocadas anteriormente no order book. Ao fazer uma ordem de mercado, você pagará taxas como taker de mercado.

**Ordem Stop Limitada:** A maneira mais fácil de entender uma ordem stop limitada é dividi-la em preço stop e preço limite. O preço stop é simplesmente o preço que aciona a ordem limitada, e o preço limite é o preço da ordem limitada que é acionada. Isso significa que quando seu preço stop for atingido, sua ordem limitada será imediatamente colocada no order book.

**Ordem Stop de Mercado:** Semelhante a uma ordem stop limitada, uma ordem stop de mercado usa um preço stop como gatilho. No entanto, quando o preço stop é atingido, ele aciona uma ordem de mercado em vez disso.

**Trailing Stop:** Um trailing stop é um tipo de ordem projetada para bloquear lucros ou limitar perdas à medida que um trade se move favoravelmente. Trailing stops só se movem se o preço se mover favoravelmente. Uma vez que se move para bloquear um lucro ou reduzir uma perda, não se move de volta na outra direção.

**Somente Post:** O Modo Post-only significa que os Traders só podem colocar uma Ordem se ela for postada no Order Book como uma Ordem Maker. Uma Ordem que seria postada como uma Ordem Taker será rejeitada. Nenhuma Ordem de Mercado pode ser colocada e nenhuma Ordem será preenchida. Ordens em espera podem ser canceladas no modo post-only.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Somente Reduzir:** A ordem Reduce-Only apenas reduzirá sua posição, não a aumentará.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**Instruções TIF** permitem que você especifique a quantidade de tempo que suas ordens permanecerão ativas antes de serem executadas ou expirarem. Você pode selecionar uma dessas opções para instruções TIF:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel / Válido até Cancelar): A ordem permanecerá ativa até ser preenchida ou cancelada.&#x20;
* **IOC** (Immediate Or Cancel / Imediata ou Cancelar): A ordem será executada imediatamente (total ou parcialmente). Se for executada apenas parcialmente, a parte não preenchida da ordem será cancelada.&#x20;
* **FOK** (Fill Or Kill / Preencher ou Cancelar): A ordem deve ser totalmente preenchida imediatamente. Caso contrário, não será executada.
