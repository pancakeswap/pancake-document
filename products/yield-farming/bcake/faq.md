# FAQ

![](../../../.gitbook/assets/how-bCAKE-FAQ.png)

### Como são calculados os multiplicadores  de bCAKE?&#x20;

Você pode notar que obtém diferentes multiplicadores de impulsionamento de bCAKE ao fazer stake em diferentes farms. Isso porque os multiplicadores bCAKE - Farm Boosters são calculados usando as seguintes métricas na ativação ou atualização:

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

`constantA` e `constantB`são definidos pela cozinha e sujeitos a ajustes futuros com base no feedback da comunidade e nas condições do mercado.

Seguem alguns exemplos do cálculo:

![](<../../../.gitbook/assets/image (3).png>)

![](../../../.gitbook/assets/image.png)

{% hint style="info" %}
Resumo

Quanto mais LP você quiser impulsionar , mais CAKE você precisa bloquear por mais tempo
{% endhint %}

### Por que meus multiplicadores mudam mesmo após a ativação?

Observe que qualquer ação do usuário nos farms ou na pool de stake de CAKE atualizará automaticamente seu multiplicador de impulsionamento com base nos dados e estatísticas mais recentes dos farms e da pool de staking de CAKE, incluindo, mas não limitado a:&#x20;

* Ter feito Stake/unstake de tokens LP do Farm&#x20;
* Colheita de recompensas de CAKE do farm&#x20;
* Prolongamento da duração do seu stake de CAKE&#x20;
* Adição de mais CAKE à sua posição de staking de prazo fixo&#x20;
* Conversão de sua posição de stake de CAKE para flexível

{% hint style="warning" %}
Por favor note:&#x20;

Para garantir a justiça e evitar possíveis abusos e trapaças usando dados desatualizados. Farm booster é projetado para ser governado pela comunidade. Portanto, qualquer pessoa pode chamar a função `refresh(address _user, uint256 _pid)`no contrato de impulsionamento do farm (link) para atualizar os multiplicadores do impulsionamento de qualquer pessoa usando os dados mais recentes.
{% endhint %}

### Onde estão minhas recompensas de CAKE depois de ativar ou desativar o impulsionamento/Booster?

![](<../../../.gitbook/assets/image (16).png>)

Ao farmar com bCAKE - Farm Boosters, algumas de suas recompensas de CAKE colhidas podem ser armazenadas temporariamente no contrato do farm booster. Sempre que isso acontecer, você verá uma linha pontilhada abaixo do seu "CAKE EARNED", indicando que, além do número mostrado, você tem mais recompensas de CAKE no contrato de impulsionamento de farm.&#x20;

**Esta parte das recompensas de CAKE será enviada automaticamente para sua carteira na próxima colheita, depósito ou saque.**&#x20;

Para colhê-los logo agora, basta clicar no botão "Harvest/Colheita".

![](<../../../.gitbook/assets/image (4).png>)

Para verificar o número de recompensas extras no contrato de impulsionamento de farm, passe o mouse ou pressione e segure o número com a linha pontilhada.

### Por que não consigo impulsionar um farm?

1. O impulsionamento de farm está disponível apenas para farms selecionadas. Mais farms serão disponibilizadas no futuro. Por enquanto, procure a tag "Boosted" na interface do usuário\
   \
   ![](<../../../.gitbook/assets/image (1).png>)
2. Há um limite para o número de farms que podem aumentar simultaneamente. Para verificar o número de impulsionamentos restantes, consulte o painel na parte superior. \
   ![](<../../../.gitbook/assets/image (12).png>)\
   \
   Você precisará desativar um impulsionamento ativo para ativar o impulsionamento em outras farms.
3. Certifique-se de ter concluído a configuração uma vez.
4. Devido ao envolvimento de vários contratos, algumas das interações do contrato exigem um pouco mais de tokens de gás (BNB). Portanto, certifique-se de ter BNB suficiente em sua carteira.

### Qual é o multiplicador máximo de impulsionamento do bCAKE que posso obter?

Atualmente, o impulsionamento máximo que um usuário pode obter por um reforço de farm é 2x. O que lhes oferece o dobro das APRs básicas.

### Como posso aumentar meus multiplicadores de impulso com bCAKE?&#x20;

* Adicione mais CAKE na posição de staking de prazo fixo&#x20;
* Prolongue a duração da sua posição de staking de prazo fixo&#x20;

Basta colocar:

> Mais CAKE em stake, por mais tempo bloqueado

[Saiba mais sobre como os multiplicadores de impulsionanmento de bCAKE são calculados.](https://docs.pancakeswap.finance/v/portuguese-brazilian/products/yield-farming/bcake/faq)

### De onde estão vindo as recompensas extras de CAKE?&#x20;

**Relaxe, nenhuma emissão extra acontece para tornar o bCAKE possível.**

Semelhante ao stake de CAKE de prazo fixo. bCAKE aumenta a participação de usuários individuais em relação aos outros.&#x20;

Mesmo que o APR de linha de base possa cair após a implantação do bCAKE. Os chefs acreditam que é uma boa troca, pois não apenas beneficia os amantes leais de CAKE, aumentando seu rendimento de farm, mas também cria mais demanda por CAKE e serve como um grande incentivo para o stake de CAKE.

### Por que o uso de gás é alto ao ativar o impulsionamento de farm pela primeira vez?&#x20;

Para habilitar o bCAKE - farm booster, os usuários devem configurar um endereço de carteira proxy, o que requer a implantação de um novo contrato. Este processo é relativamente pesado em gás. (cerca de US $ 2 \~ 5 com base no preço do BNB e na condição do blockchain).

No entanto, o processo de configuração é apenas uma vez para cada endereço de carteira. Você só precisa realizá-lo uma vez.

### Por que o multiplicador que recebo é baixo?&#x20;

bCAKE - o farm booster funciona de certa forma avaliando sua posição de stake de CAKE de prazo fixo e sua posição no farm de liquidez. Simplesmente:&#x20;

> Se os usuários quiserem aumentar mais tokens LP no farm, eles precisarão bloquear mais CAKE por períodos mais longos na pool.&#x20;

Esse design garante que os benefícios não sejam oferecidos apenas a grandes proprietários, mas a qualquer usuário que tenha uma posição de stake de CAKE considerável quando comparada à posição de farm. Saiba mais sobre como o multiplicador é calculado [aqui](https://docs.pancakeswap.finance/v/portuguese-brazilian/products/yield-farming/bcake/faq).

### Por que apenas CAKE/BUSD? Por que apenas 1 farm?&#x20;

Já que o bCAKE envolve a atualização de um dos principais produtos da PancakeSwap, que é o farm de liquidez. Os chefs querem ter uma abordagem mais lenta e estável para o lançamento.&#x20;

Portanto, na fase inicial de lançamento do produto. Muitos dos parâmetros são muito conservadores. Incluindo o número de farms que os usuários podem aumentar, quais farms os usuários podem aumentar, bem como o parâmetro de dificuldade em receber o multiplicador de impulsionamento.&#x20;

Após a fase de lançamento inicial, os Chefs ajustarão os parâmetros com base no feedback da comunidade.&#x20;

### O bCAKE é auditado?&#x20;

O bCAKE foi auditado por auditores internos e externos.&#x20;

Confira o relatório de auditoria da PeckShield [aqui](https://github.com/peckshield/publications/tree/master/audit\_reports/PeckShield-Audit-Report-PancakeSwap-FarmBooster-v1.0.pdf).
