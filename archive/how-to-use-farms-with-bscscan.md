# Como Usar Farms com a BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Por exigir várias etapas, usar Farms na PancakeSwap pode parecer intimidante no início. Este guia mostra como usar o contrato de Farms diretamente pela BscScan.

{% hint style="warning" %}
Saiba que usar a BscScan para interagir com contratos não é recomendado para iniciantes. Se você não se sentir confiante, sugerimos usar o guia [Como Usar Farms](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms).
{% endhint %}

## Encontrando o identificador de processo da Farm

Para interagir corretamente com o smart contract de farming, você precisará do identificador de processo (PID) correspondente ao seu par de LP. Por enquanto, a forma mais fácil de encontrá-lo é consultar o GitHub.

1\. Abra o [código das Farms do site da PancakeSwap no GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Pressione **Control**/**command** + **F** e procure seu par pelo ticker (não pelo nome do projeto). Por exemplo, 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Anote ou copie o número do PID (neste caso, 389) em um lugar de fácil acesso. Você vai precisar dele mais tarde.

## Depositando Tokens de LP pela BscScan

Depositar Tokens de LP pela BscScan envolve algumas etapas. Dividimos o processo em passos para facilitar o acompanhamento.

### Obtendo o endereço do Main Staking Contract

O endereço do Main Staking Contract é: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Mas, se você quiser confirmar isso, acesse a [página PancakeSwap: Main Staking Contract na BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Você verá o endereço no canto superior esquerdo. Clique no **ícone de páginas** para copiá-lo para a área de transferência. Você vai precisar dele em breve.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Abra o contrato do seu Token de LP

Você precisará aprovar o smart contract para o Token de LP que deseja colocar em uma farm antes de poder gastá-lo.

### A partir do código-fonte

1\. Primeiro, abra o [farms.ts no GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Pressione **Control**/**command** + **F** e procure seu par pelo ticker (não pelo nome do projeto). Por exemplo, 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Com o código do par de LP que você procura aberto, encontre o endereço depois de "56:". Esse será o endereço do seu contrato.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### A partir da interface

1\. Primeiro, acesse a [página de Farms da PancakeSwap](https://pancakeswap.finance/farms) e procure o par escolhido usando o campo "SEARCH" no canto superior direito. Neste exemplo, estamos usando CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Clique em **Details** para expandir a linha e mostrar mais informações.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Clique em **View Contract** para abrir o smart contract na BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Dando permissão ao contrato do Token de LP

Agora que o contrato do seu Token de LP está aberto na BscScan, você vai aprovar o gasto dos seus Tokens de LP na Farm.

1\. Na página do contrato do Token de LP, vá em **Contract** e depois em **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clique em **Connect to Web3** para conectar a MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirme a conexão.

3\. Na função 1, “approve”, você verá “spender:address”. Cole o endereço do Main Staking Contract que você copiou para a área de transferência anteriormente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Você também precisará aprovar a quantidade de Tokens de LP que o contrato pode gastar. No campo de valor, você deve inserir a quantidade em Wei. Você pode usar o [Conversor de Unidades da BscScan](https://www.bscscan.com/unitconverter) para converter facilmente sua quantidade em Wei. Aqui vamos usar 5 Tokens de LP CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Você também pode usar `-1` como valor para dar aprovação de gasto ilimitado. Isso não significa que você gastará tudo por padrão, apenas que uma transação de qualquer tamanho usando este contrato será permitida pela sua carteira.
{% endhint %}

6\. Clique em **Write** e aceite a ação na sua carteira MetaMask. Agora você pode colocar Tokens de LP na Farm até a quantidade que aprovou.

### Depositando Tokens de LP com o smart contract Main Staking Contract

Com o Main Staking Contract agora aprovado para gastar seus Tokens de LP, é hora de fazer um depósito.

1\. De volta à [página PancakeSwap: Main Staking Contract na BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vá em **Contract** e depois em **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clique em **Connect to Web3** para conectar a MetaMask.

3\. Role até a função 2, "deposit", e digite seu PID no campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Se você não copiou seu PID antes, pode aprender como obtê-lo na seção **Encontrando o identificador de processo da Farm**, mais acima nesta página.

4\. Abaixo de \_pid você verá "\_amount". Insira a quantidade de LP que o contrato poderá gastar, que você aprovou anteriormente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Confira as informações e clique em **Write**. Confirme sua ação na MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Você pode confirmar que o depósito funcionou clicando em **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Retirando de um Pool

Retirar seus Tokens de LP de um Pool é muito parecido com fazer um depósito. A diferença está na função com que você vai interagir.

1\. De volta à [página PancakeSwap: Main Staking Contract na BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vá em **Contract** e depois em **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clique em **Connect to Web3** para conectar a MetaMask.

3\. Role até o final, até a função 15, "withdraw", e digite seu PID no campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Se você não copiou seu PID antes, pode aprender como obtê-lo na seção **Encontrando o identificador de processo da Farm**, mais acima nesta página.

4\. Abaixo de \_pid você verá "\_amount". Insira a quantidade de LP que você deseja retirar do Pool.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Confira as informações e clique em **Write**. Confirme sua ação na MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Você pode confirmar que a retirada funcionou clicando em **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Fazendo uma retirada de emergência**

‌Usar a função de retirada de emergência permite sacar todos os seus fundos de um pool quando nenhuma outra forma está funcionando.

{% hint style="danger" %}
**Usar a função de retirada de emergência fará você perder suas recompensas em CAKE!**

A equipe da PancakeSwap recomenda fortemente evitar esta função, a menos que isso seja orientado oficialmente pela equipe da PancakeSwap ou que você esteja muito à vontade para interagir com smart contracts e entenda o código subjacente.
{% endhint %}

‌1. Na [página PancakeSwap: Main Staking Contract na BscScan](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vá em **Contract** e depois em **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Clique em **Connect to Web3** para conectar a MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Role para baixo até a função 4, "emergencyWithdraw", e digite seu PID no campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Se você não copiou seu PID antes, pode aprender como obtê-lo na seção **Encontrando o identificador de processo da Farm**, mais acima nesta página.

5\. Confira as informações e clique em **Write**. Confirme sua ação na MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Você pode confirmar que a retirada funcionou clicando em **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
