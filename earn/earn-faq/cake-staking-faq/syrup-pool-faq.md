# FAQ e Solução de Problemas do Syrup Pool

## Solução de Problemas

### **Não consigo encontrar o Syrup Pool em que estava fazendo Staking!**

Você deve conseguir encontrar o Syrup Pool na aba "Finished" na página de Syrup Pools.&#x20;

Selecionando "Staked Only", será mais fácil encontrar seus ativos.

### **Por que não consigo retirar meus tokens do Staking de um Syrup Pool?**

Se você não conseguir retirar do Staking CAKE no pool "Stake Cake, Earn CAKE", verifique se você não vendeu os tokens SYRUP da sua carteira. Este token atua como uma "prova de propriedade" do seu CAKE no pool Manual CAKE.&#x20;

### **Por que meus tokens ganhos foram para zero após fazer Staking/Unstaking?**

Não se preocupe! Eles já estão na sua carteira.

Sempre que você faz Staking ou Unstaking em um Syrup Pool ou farm, seus tokens ganhos são colhidos e enviados para sua carteira ao mesmo tempo.

## **Perguntas Gerais**

### Como o APR dos Syrup Pools é calculado?

> APR do Syrup Pool = Recompensas anualizadas (USD) / Fundos do usuário em Staking no Syrup Pool (USD) \* 100

Como exemplo básico, vamos considerar um pool de 60 dias com $300.000 USD em recompensas e $3.000.000 USD em CAKE em Staking.

O APR flutua conforme mais CAKE é colocado em Staking pelos usuários e conforme o preço do CAKE e o token de recompensa variam.

|                                                           | **Cálculo**                       | Valor                                      |
| --------------------------------------------------------- | --------------------------------- | ------------------------------------------ |
| Total de recompensas a distribuir (valor em USD)          |                                   | $300.000 USD                               |
| Período de distribuição                                   |                                   | 60 dias                                    |
| Distribuição diária                                       | 300.000 / 60 =                    | $5.000 USD diários                         |
| **Recompensas anualizadas (valor em USD)**                | 5.000 \* 365 =                    | **$1.825.000 USD**                         |
| **Valor do CAKE em Staking pelos usuários no pool (USD)** |                                   | **$3.000.000 USD**                         |
| **APR**                                                   | (1.825.000 / 3.000.000) \* 100 =  | <p></p><p><strong>60,833% APR</strong></p> |

### **O que significa o número "End" no meu Syrup Pool?**

Isso mostra a quantidade de blocos restantes até que as recompensas para aquele pool parem de ser distribuídas. Assim que o pool atingir aquele bloco, você deve retirar seus tokens do Staking, pois não receberá mais recompensas após isso.

### **De onde vêm as recompensas dos Syrup Pools?**

Existem três tipos principais de Syrup Pools.

1. Stake CAKE, ganhe CAKE
2. Stake CAKE, ganhe outros tokens.&#x20;
3. Stake outros tokens, ganhe CAKE

As recompensas para os Syrup Pools "Stake CAKE, ganhe CAKE" vêm das [emissões de CAKE](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). A cada bloco, uma quantidade de tokens CAKE é alocada como recompensas para esses pools.

As recompensas para o tipo "Stake CAKE, ganhe outros tokens" são fornecidas pelas equipes de projetos que patrocinam um Syrup Pool.

Para o tipo "Stake outros tokens, ganhe CAKE", o tesouro da PancakeSwap recompra CAKE do mercado para distribuir como recompensas. Esses pools são financiados pela PancakeSwap, não pelos projetos.

### O que é o Token SYRUP?

O Token SYRUP da PancakeSwap é depositado na sua carteira quando você interage com o Syrup Pool Manual "Stake CAKE, Earn CAKE". Ele não é colocado em Staking por&#x20;

É basicamente um IOU que mostra quanto CAKE você colocou em Staking no pool.

Ele será devolvido automaticamente quando você retirar seu CAKE do Staking desse pool.

{% hint style="warning" %}
Não venda seus tokens SYRUP! Você precisa devolver seu SYRUP para retirar seu CAKE do Staking no pool Manual CAKE. A quantidade de SYRUP que você devolver deve ser igual à quantidade de CAKE que você retirar do Staking.
{% endhint %}
