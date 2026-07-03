# Taxas e Rotas

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

No Exchange V3, por padrão, o Smart Router do PancakeSwap utilizará Liquidez do V3, V2, StableSwap (BNB Chain) e dos AMM e formadores de mercado (BNB Chain e Ethereum) para executar negociações e encontrar o melhor preço para os traders.

No entanto, os usuários sempre podem personalizar sua negociação escolhendo quais fontes de Liquidez o roteador deve utilizar, e habilitar ou desabilitar multihops e roteamento dividido.

### **Verificar a taxa e o valor da taxa aplicados atualmente**

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png>)

Para verificar quanto será cobrado pela sua negociação atual, confira a seção "Taxa" nos detalhes do Swap.

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png>)

Para verificar o tipo de pool e o nível de taxa pelo qual sua negociação está sendo roteada, confira a seção "Rota".

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png>)

Para saber mais detalhes, clique no ícone de lupa para exibir a rota de negociação completa.



### **Personalizar fontes de Liquidez**

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png>)

Na parte superior da interface "Personalizar Roteamento", você pode escolher qual fonte de Liquidez o roteador deve usar ao rotear sua negociação. Para abrir esta interface, você pode:

* Clicar em "Personalizar Roteamento" na parte inferior da exibição de rota de negociação.
* Clicar no ícone de engrenagem na interface de Swap e, em seguida, clicar em "Personalizar Roteamento" na parte inferior.

Por padrão, todas as fontes de Liquidez estão habilitadas e o Smart Router aproveitará ao máximo todas as liquideces disponíveis dentro do PancakeSwap.

Observe que o roteador NÃO roteará negociações entre pools de Liquidez AMM e formadores de mercado MM. Quando sua negociação é executada pelos formadores de mercado MM, ela não passará por nenhum pool de Liquidez AMM.

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png>)

Você pode clicar no botão "Redefinir" no canto superior direito para restaurar as configurações padrão.



### **Personalizar preferências de roteamento**

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png>)

Na parte inferior da interface "Personalizar Roteamento", você pode personalizar suas preferências de roteamento habilitando ou desabilitando multihops e roteamento dividido.

Os multihops permitem que os tokens façam Swap através de múltiplos saltos entre vários pools de Liquidez para obter o melhor negócio. Desativá-los restringirá as negociações a trocas diretas, o que pode causar maior Slippage ou até perda de fundos.

O roteamento dividido permite que os Swaps de tokens sejam divididos em múltiplas rotas para obter o melhor negócio. Desativá-lo restringirá as negociações a uma única rota, o que pode resultar em baixa eficiência ou maior Slippage.

{% hint style="warning" %}
Quando sua negociação não puder ser executada devido a uma configuração de roteamento personalizada, um aviso será exibido. Você pode clicar em "Verificar suas configurações" para abrir rapidamente a interface "Personalizar Roteamento", ou escolher "Redefinir para padrão" para restaurar rapidamente suas configurações ao padrão.
{% endhint %}
