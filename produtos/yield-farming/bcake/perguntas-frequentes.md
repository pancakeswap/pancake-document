# Perguntas Frequentes

![](../../../.gitbook/assets/how-bCAKE-FAQ.png)

### Como são calculados os multiplicadores  de bCAKE?&#x20;

Você pode notar que obtém diferentes multiplicadores de impulsionamento de bCAKE ao fazer stake em diferentes farms.

Isso porque os multiplicadores bCAKE - Farm Boosters são calculados usando as seguintes métricas na ativação ou atualização:

* `userLpStakedAmount` : O número de LP tokens que você tem em stake no farm
* `totalLpStakedAmount` : O número total de LP tokens no farm
* `userLockedAmount` : O número de CAKE bloqueado que você tem em stake na pool de CAKE de prazo fixo
* `userLockedDuration` : A duração da sua posição de stake de prazo fixo
* `totalLockedAmount` : O número total de CAKE bloqueado na pool de CAKE de prazo fixo
* `averageLockedDuration` : A duração média do stake na pool de cake de prazo fixo

O multiplicador é calculado usando o seguinte método:

* `resultA = constantA * userLpStakedAmount`
* `resultB = (totalLpStakedAmount * userLockedAmount * userLockedDuration / constantB) / (totalLockedAmount * averageLockedDuration)`
* `boostMultiplier = min(userLpStakedAmount, (resultA + resultB)) / resultA`

`constantA` e `constantB`são definidos pela cozinha e sujeitos a ajustes futuros com base no feedback da comunidade e nas condições do mercado. A `constantB`varia entre farms diferentes para compensar as diferenças de preço de LP.

Mas:

{% hint style="info" %}
Resumo

Mais LP você quer impulsionar \
Mais CAKE você precisa bloquear por mais tempo
{% endhint %}

### Por que meus multiplicadores mudam mesmo após a ativação?

Observe que **qualquer ação do usuário nos farms ou na pool de stake de CAKE atualizará automaticamente seu multiplicador de impulsionamento** com base nos dados e estatísticas mais recentes dos farms e da pool de staking de CAKE, incluindo, mas não limitado a:&#x20;

* Ter feito Stake/unstake de tokens LP do Farm&#x20;
* Colheita de recompensas de CAKE do farm&#x20;
* Prolongamento da duração do seu stake de CAKE&#x20;
* Adição de mais CAKE à sua posição de staking de prazo fixo&#x20;
* Conversão de sua posição de stake de CAKE para flexível

{% hint style="warning" %}
Por favor note:&#x20;

Para garantir a justiça e evitar possíveis abusos e trapaças usando dados desatualizados. Farm booster é projetado para ser governado pela comunidade. Portanto, **qualquer pessoa** pode chamar a função `refresh(address _user, uint256 _pid)`no contrato de impulsionamento do farm (link) para atualizar os multiplicadores do impulsionamento de qualquer pessoa usando os dados mais recentes.

Além disso, a cozinha também monitorará todas as posições de farms habilitadas para bCAKE e atualizará qualquer posição com um multiplicador desatualizado.
{% endhint %}

### Onde estão minhas recompensas de CAKE depois de ativar ou desativar o impulsionamento/Booster?

No bCAKE V3, as recompensas de CAKE são coletadas automaticamente em sua carteira ao ativar ou desativar um booster.

#### Por que não consigo impulsionar uma posição

1. O reforço de farm está disponível apenas para farms selecionados. Mais farms serão disponibilizadas no futuro. Por enquanto, procure a tag "Boosted" na IU.![](<../../../.gitbook/assets/image (1).png>)
2. Há um limite para o número de posições que você pode aumentar simultaneamente. Para verificar o número de boosters restantes, consulte o painel na parte superior.![](<../../../.gitbook/assets/image (9).png>)\
   Você precisará desativar um booster ativo para ativar boosters em outros farms.
3. Devido ao envolvimento de vários contratos, algumas interações de contrato exigem um pouco mais de tokens de gás (BNB). Portanto, certifique-se de ter BNB suficiente em sua carteira.

### Qual é o multiplicador máximo de impulsionamento do bCAKE que posso obter?

Atualmente, o impulsionamento máximo que um usuário pode obter por um reforço de farm é 2x. O que lhes oferece o dobro das APRs básicas.

### Como posso aumentar meus multiplicadores de impulso com bCAKE?&#x20;

* Adicione mais CAKE na posição de staking de prazo fixo&#x20;
* Prolongue a duração da sua posição de staking de prazo fixo&#x20;

Basta colocar:

**Mais CAKE em stake, por mais tempo bloqueado**

[Saiba mais sobre como os multiplicadores de impulsionanmento de bCAKE são calculados.](https://docs.pancakeswap.finance/v/portuguese-brazilian/products/yield-farming/bcake/faq)

### De onde estão vindo as recompensas extras de CAKE?&#x20;

**Relaxe, nenhuma emissão extra acontece para tornar o bCAKE possível.**

Semelhante ao stake de CAKE de prazo fixo. bCAKE aumenta a participação de usuários individuais em relação aos outros.&#x20;

Mesmo que o APR de linha de base possa cair após a implantação do bCAKE. Os chefs acreditam que é uma boa troca, pois não apenas beneficia os amantes leais de CAKE, aumentando seu rendimento de farm, mas também cria mais demanda por CAKE e serve como um grande incentivo para o stake de CAKE.

### Por que o multiplicador que recebo é baixo?&#x20;

bCAKE - o farm booster funciona de certa forma avaliando sua posição de stake de CAKE de prazo fixo e sua posição no farm de liquidez. Simplesmente:&#x20;

> Se os usuários quiserem aumentar mais tokens LP no farm, eles precisarão bloquear mais CAKE por períodos mais longos na pool.&#x20;

Esse design garante que os benefícios não sejam oferecidos apenas a grandes proprietários, mas a qualquer usuário que tenha uma posição de stake de CAKE considerável quando comparada à posição de farm.&#x20;

Saiba mais sobre como o multiplicador é calculado [aqui](https://docs.pancakeswap.finance/v/portuguese-brazilian/products/yield-farming/bcake/faq).

## Por que há apenas um número x de farms disponíveis para impulsionamento?

Já que o bCAKE envolve a atualização de um dos principais produtos da PancakeSwap, que é o farm de liquidez. Os chefs querem ter uma abordagem mais lenta e estável para o lançamento.&#x20;

Portanto, na fase inicial de lançamento do produto. Muitos dos parâmetros são muito conservadores. Incluindo o número de farms que os usuários podem aumentar, quais farms os usuários podem aumentar, bem como o parâmetro de dificuldade em receber o multiplicador de impulsionamento.&#x20;

Após a fase de lançamento inicial, **os Chefs ajustarão os parâmetros com base no feedback da comunidade.**&#x20;

### O bCAKE V3 é auditado?&#x20;

O bCAKE foi auditado por auditores internos e externos.&#x20;

Confira o relatório de auditoria: [https://docs.pancakeswap.finance/v/portuguese-brazilian/readme/auditorias](https://docs.pancakeswap.finance/v/portuguese-brazilian/readme/auditorias)
