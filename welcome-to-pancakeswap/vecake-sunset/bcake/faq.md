# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### Como os multiplicadores de bCAKE são calculados?

Você pode notar que obtém diferentes multiplicadores de boost de bCAKE ao fazer Staking em diferentes farms.

Isso ocorre porque os multiplicadores do bCAKE - Farm Boosters são calculados usando as seguintes métricas na ativação ou atualização:

* `userLpBalanceInFarm` : A quantidade de Liquidez que você está colocando em Staking no farm.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : A quantidade total de Liquidez em Staking no farm ou a quantidade ativa atual de Liquidez no pool de LP V3. bCAKE escolherá o número menor entre os dois.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : O número em tempo real de veCAKE que você possui
* `veCAKE.totalSupply` : O fornecimento total em tempo real de veCAKE

O multiplicador é calculado usando o seguinte método:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` e `constantB` são definidos pela cozinha e sujeitos a ajustes futuros com base no feedback da comunidade e nas condições de mercado. `constantB` varia entre diferentes farms para compensar as diferenças de preço de LP.

`constantA` e `constantB` podem ser obtidos via:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Mas:

{% hint style="info" %}
**Resumo**

Quanto mais LP (Liquidez) você quer impulsionar

Mais CAKE você precisa bloquear por durações mais longas
{% endhint %}

### Por que meus multiplicadores mudam mesmo após a ativação?

Observe que **qualquer ação do usuário na posição de farming ou no pool de Staking de CAKE atualizará automaticamente seu multiplicador de boost** com base nos dados e estatísticas mais recentes dos farms e do pool de Staking de CAKE, incluindo, mas não se limitando a:

* Stake/Unstake de posição no/do farm
* Colheita de recompensas de CAKE do farm
* Extensão da duração do Staking de CAKE
* Adição de mais CAKE à sua posição de Staking de prazo fixo
* Conversão da sua posição de Staking de CAKE para flexível

{% hint style="warning" %}
Observe:&#x20;

Para garantir a equidade e prevenir possíveis abusos e trapaças usando dados desatualizados, o Farm Booster foi projetado para ser sem permissão e governado pela comunidade. Portanto, **qualquer pessoa** pode chamar a função `updateLiquidity(address _tokenId)` no contrato MasterChef V3 para atualizar os multiplicadores de boost de qualquer um usando os dados mais recentes.

Além disso, a cozinha também monitorará todas as posições de farming habilitadas para bCAKE e atualizará qualquer posição com multiplicador desatualizado.
{% endhint %}

### Por que não consigo impulsionar uma posição

1. O Farm Booster está disponível apenas para farms selecionados. Mais farms estarão disponíveis no futuro. Por enquanto, **procure o valor de APR em verde com um ícone de foguete verde.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. Devido ao envolvimento de múltiplos contratos, algumas interações de contratos exigem um pouco mais de tokens de gás (BNB). Então, certifique-se de ter BNB suficiente na sua carteira. Se o erro persistir, tente aumentar manualmente o limite de gás da transação.

### Qual é o Multiplicador de Boost Máximo do bCAKE que posso obter?

Atualmente, o boost máximo que um usuário pode obter para um farm booster é de 2,5x, o que oferece 2,5x os APRs originais.

Observe que o boost máximo que você pode obter varia entre os tipos de Liquidez que você está tentando colocar em Staking:

* V3: 2x máximo
* V2, StableSwap: 2,5x máximo
* Gerenciadores de Posição: 2,5x máximo

### Como posso aumentar meus Multiplicadores de Boost do bCAKE?

* Adicionar mais CAKE à posição de Staking de veCAKE
* Estender ou renovar a duração da sua posição de Staking de veCAKE

Resumindo:

**Faça Staking de mais CAKE, faça Staking por mais tempo**

[Saiba mais sobre como os multiplicadores de boost do bCAKE são calculados](faq.md#how-are-the-bcake-multipliers-calculated).

### De onde vêm as recompensas extras de CAKE impulsionadas?

**Fique tranquilo, nenhuma emissão extra é alocada para tornar o bCAKE possível.**

Similar ao Staking de CAKE com veCAKE, o bCAKE impulsiona a participação individual dos usuários em relação aos outros.

Mesmo que o APR base possa cair após o deploy do bCAKE, os Chefs acreditam que é uma boa troca, pois beneficia os amantes fiéis de CAKE ao impulsionar seu rendimento de farming, cria mais demanda por CAKE e serve como um ótimo incentivo para o Staking de CAKE.

### Por que o multiplicador que recebo é baixo?&#x20;

bCAKE - Farm Booster funciona avaliando tanto sua posição de Staking de veCAKE quanto sua posição de farming de Liquidez em comparação com outros usuários. Resumindo:

> Se os usuários querem impulsionar mais Liquidez no farm, eles precisam bloquear mais CAKE por durações mais longas no pool.

Esse design garante que os benefícios não sejam oferecidos apenas aos grandes detentores, mas a qualquer usuário que tenha uma posição de Staking de CAKE considerável em comparação com a posição de farming.

Saiba mais sobre como o multiplicador é calculado [aqui](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Por que há apenas x farms disponíveis para boost?

Como o bCAKE envolve a atualização de um dos principais produtos da PancakeSwap, que é o farming de Liquidez, os Chefs querem adotar uma abordagem mais lenta e gradual no lançamento.

Portanto, na fase inicial de lançamento do produto, muitos dos parâmetros são muito conservadores. Incluindo o número de farms que os usuários podem impulsionar, qual farm os usuários podem impulsionar, bem como o parâmetro de dificuldade para receber o multiplicador de boost.

**Os Chefs ajustarão os parâmetros com base no feedback da comunidade.**

### **O bCAKE V3 foi auditado?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE foi auditado por auditores internos e externos.

Confira os relatórios de auditoria aqui: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
