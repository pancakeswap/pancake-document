# Glossário do Perpétuos

**Aqui você encontrará a definição de todos os termos inerentes à negociação de futuros**

### **Trade de Perpétuos**

Perpétuos, swaps perpétuos ou perps são um tipo especial de contrato futuro sem data de vencimento.

### **Alavancagem**

A alavancagem é um mecanismo de negociação. Os traders podem usá-lo para aumentar sua exposição ao mercado, permitindo que paguem menos do que o valor total do investimento. Em palavras simples, você pega um empréstimo de dinheiro para alavancar seu investimento.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9\_QPioIxT9sFRuY-EEtuSXgCn\_D8Muwqh60PFr3EcEu3kkH)

### **Margem**

É a garantia que você coloca para suas posições alavancadas. Tem dois modos de usá-la:&#x20;

* Modo de Margem Cruzada(Cross Margin): Todas as posições cruzadas sob o mesmo ativo de margem compartilham o mesmo saldo de margem cruzada de ativo. Em caso de liquidação, o saldo total da margem de seus ativos, juntamente com quaisquer posições abertas restantes sob o ativo, podem ser perdidos.&#x20;
* Modo de Margem Isolada(Isolated Margin): Gerencie seu risco em posições individuais, restringindo a quantidade de margem alocada a cada uma. Se o índice de margem de uma posição atingir 100%, a posição será liquidada. A margem pode ser adicionada ou removida de posições usando este modo.

![](https://lh3.googleusercontent.com/zVEa2C\_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55\_ZKRNTy8WoCpUs)

**Proporção de Margem(Margin Ratio):** Proporção **** de Margem = Margem de Manutenção / Saldo de Margem. Suas posições serão liquidadas assim que o Taxa de Proporção de Margem atingir 100%.&#x20;

**Taxa de Manutenção**: A quantidade mínima de saldo de margem necessária para manter suas posições abertas.&#x20;

**Saldo de margem** = Saldo da carteira + PNL não realizado. Suas posições serão liquidadas assim que Saldo de Margem <= Margem de Manutenção.

![](https://lh6.googleusercontent.com/BGaNOmsOkew\_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Ativos:

**Depósito**: Deposite seus ffundos em sua conta de futuros

**Saque**: Saque seus fundos da sua conta de futuros para sua carteira

**Balance**: Saldo da Carteira = Transferência Líquida Total + Lucro Total Realizado + Taxa de Financiamento Líquido Total - Comissão Total.

**Lucro ou perda não realizada (PNL)**: Lucros e perdas não realizadas nesta posição calculados com base no Mark Price e no percentual de retorno sobre o patrimônio líquido.

**Modos:**

* Modo de ativo único: Suporta negociação de futuros de USDⓈ-M usando apenas o ativo de margem única estipulada no símbolo. PNL das mesmas posições de ativos de margem podem ser compensadas. Suporta Modo de Margem Cruzada e Modo de Margem Isolada.&#x20;
* Modo Multi-Ativos: Negociação de futuros de USDⓈ-M em vários ativos de margem. O PNL pode ser compensado entre as diferentes posições de ativos de margem. Suporta apenas o Modo de Margem Cruzada.

{% hint style="info" %}
Nota: Se houver posições ou ordens abertas em USDⓈ-M Futures, o Modo Multi-Ativos não pode ser ativado. O Modo Multiativos aplica-se apenas aos Futuros USDⓈ-M. Antes de ativar o Modo Multiativos, leia o guia em detalhes para gerenciar melhor o risco da conta de Futuros USDⓈ-M de acordo ao usar o Modo Multiativos.
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa\_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-\_3KzjAl3f8VSGyoLrtudoUqBr)

### Ordens

**Compra/Long:** Abra um pedido de long. Nesta ordem você compra um ativo e espera vender quando o preço subir. "Comprar" e "Long" são usados para dizer a mesma coisa.

**Venda/Short:** Abra um pedido de short. Nesta ordem, você pega um ativo emprestado, vende-o e espera comprá-lo de volta quando o preço cair. "Vender" e "Short" são usados para dizer a mesma coisa.

**Ordem Limite:** Uma ordem de limite é uma ordem de compra ou venda a um preço específico ou melhor. Não há garantia de execução de ordens limite.

**Ordem à Mercado:** Uma ordem de mercado é uma ordem de compra ou venda ao melhor preço atual disponível. É executado contra as ordens limites que foram colocadas anteriormente no livro de ordens. Ao fazer uma ordem de mercado, você pagará taxas como tomador de mercado.

**Ordem de Stop Limite:** A maneira mais fácil de entender uma ordem limite de Stop é dividi-la em preço de stop e preço limite. O preço de stop é simplesmente o preço que aciona a ordem de limite, e o preço de limite é o preço da ordem de limite que é acionada. Isso significa que, assim que seu preço de stop for atingido, sua ordem de limite será imediatamente colocada no livro de ordens.

**Ordem à Mercado de Stop:** Semelhante a uma ordem de limite de stop, uma ordem de stop à mercado usa um preço de parada como gatilho. No entanto, quando o preço de parada é atingido, ele aciona uma ordem à mercado.

**Trailing Stop:** Um trailing stop é um tipo de ordem projetado para bloquear lucros ou limitar perdas à medida que uma negociação se move favoravelmente. Trailing stops só se movem se o preço se mover favoravelmente. Uma vez que ele se move para garantir um lucro ou reduzir uma perda, ele não volta na outra direção.&#x20;

**Post Only:** Modo Post-only significa que os Traders só podem fazer uma Ordem se ela for postada no Livro de Ordens como uma Ordem Maker. Uma Ordem que seria postada como um Pedido de Comprador será rejeitado. Nenhuma Ordem de Mercado pode ser colocada e nenhuma Ordem será executada. Ordens de descanso podem ser canceladas no modo pós-somente.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf\_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym\_aSz\_)

**Reduce Only:** A ordem de redução apenas reduzirá sua posição, não a aumentará.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME\_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF instructions** permitem que você especifique a quantidade de tempo que seus pedidos permanecerão ativos antes de serem executados ou expirados. Você pode selecionar uma destas opções para instruções TIF:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7\_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93\_7bq7gDmyg1-jyblSQ8eANv\_fH9bvJ-)

* **GTC** (Good Till Cancel): A ordem permanecerá ativa até que seja preenchida ou cancelada.&#x20;
* **IOC** (Imediate Or Cancel): A ordem será executada imediatamente (total ou parcialmente). Se for executada apenas parcialmente, a parte não preenchida da ordem será cancelada.&#x20;
* **FOK** (Fill Or Kill): O pedido deve ser totalmente preenchido imediatamente. Caso contrário, não será executado.
