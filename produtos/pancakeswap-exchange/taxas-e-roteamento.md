# Taxas e Roteamento

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Na Exchange V3, por padrão, o  Smart Router da PancakeSwap utilizará a liquidez da V3, V2, StableSwap (BNB Chain) e dos AMM e formadores de mercado (BNB Chain & Ethereum), para executar negociações e encontrar o melhor preço para os traders.&#x20;

No entanto, os usuários sempre podem personalizar sua negociação, escolhendo quais fontes de liquidez o roteador deve utilizar e habilitar ou desabilitar o multihops e roteamento dividido.

### **Verifique o nível da taxa e a quantidade de taxa que está atualmente sendo aplicado**

### ![](<../../.gitbook/assets/image (2) (2).png>)

Para verificar quanto de negociação será cobrado em seu swap atual, verifique a seção “Taxa” na seção de detalhes do swap.![](<../../.gitbook/assets/image (3).png>)

Para verificar por qual tipo de pool e o nível de taxa sua negociação está atualmente roteada, confira a seção "Rota".

![](<../../.gitbook/assets/image (7).png>)

Para saber mais detalhes, clique no ícone da lupa para mostrar as exibições completas da rota de trade.

### **Personalizar fontes de liquidez**

![](<../../.gitbook/assets/image (6).png>)

Na parte superior da interface em “Personalizar roteamento”, você pode escolher qual fonte de liquidez a rota usará ao rotear sua negociação. Para abrir esta interface, você pode:&#x20;

* Clicar em “Personalizar roteamento” na parte inferior das exibições da rota de trade.&#x20;
* Clicar no ícone de engrenagem na interface do swap e clicarem “Personalizar roteamento” na parte inferior.&#x20;

Por padrão, todas as fontes de liquidez estão habilitadas e o Smart Router aproveitará ao máximo todas a liquidez disponível na PancakeSwap. Observe que o roteador NÃO encaminhará negociações entre pools de liquidez AMM e formadores de mercado (MM). Quando sua negociação é executada por formadores de mercado (MM), ela não passará por nenhuma pool de liquidez AMM.

![](<../../.gitbook/assets/image (12).png>)

Você pode clicar no botão “Redefinir” no canto superior direito para redefinir as configurações para o padrão.

### **Personalizar preferências de roteamento**

![](<../../.gitbook/assets/image (4).png>)

Na parte inferior da interface “Personalizar roteamento”, você pode personalizar suas preferências de roteamento ativando ou desativando o multihops e o roteamento dividido.&#x20;

Multihops permitem que os tokens façam swaps por vários saltos entre várias pools de liquidez para alcançar o melhor trade. Desligá-lo restringirá as negociações a swaps diretos, o que pode causar maior derrapagem ou até mesmo perda de fundos.&#x20;

O roteamento dividido permite que os swaps de token sejam divididas em várias rotas para alcançar o melhor trade. Desligá-lo impedirá que as negociações sejam executadas com uma única rota, o que pode resultar em baixa eficiência ou maior derrapagem.&#x20;

{% hint style="warning" %}
Quando sua negociação não puder ser executada devido a uma configuração de negociação personalizada, um aviso aparecerá, você pode clicar em "Verificar suas configurações" para abrir rapidamente a interface "Personalizar roteamento". Ou escolha “Redefinir para o padrão” para redefinir rapidamente suas configurações de volta ao padrão.
{% endhint %}
