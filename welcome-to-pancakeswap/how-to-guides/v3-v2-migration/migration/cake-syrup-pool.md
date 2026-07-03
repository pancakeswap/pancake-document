---
description: Migrar para o novo CAKE Syrup Pool
---

# CAKE Syrup Pool

O novo CakePool é um novo contrato de Staking de $CAKE construído com base no CakeVault (o atual pool de CAKE automático) e projetado para funcionar com o PancakeSwap MasterChef v2 para fornecer a funcionalidade "faça Staking de $CAKE, ganhe $CAKE", enquanto oferece mais recursos como Staking de prazo fixo. O pool CAKE Manual atual será desativado após a migração.

O novo CakePool usará um token fictício para colher $CAKE do MasterChef v2 e recompensá-los aos usuários que estão fazendo Staking de $CAKE. Usuários que bloquearem seu $CAKE por mais tempo receberão um número mais significativo de shares (impulsionado linearmente com base na duração), portanto, desfrutarão de um rendimento maior.

### Preciso migrar?&#x20;

Se você está atualmente usando `enterStaking` e `leaveStaking` no PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), você precisará migrar para o novo contrato.

### Sem mais composição

Com o novo CakePool, as recompensas são distribuídas proporcionalmente a todos os usuários do pool com base em shares. Semelhante a "tokens que rendem juros" ou outros modelos baseados em shares, o saldo de Staking dos usuários crescerá quando mais recompensas forem colocadas no pool. Os usuários não precisam colher e compor suas recompensas.

### Taxas&#x20;

No novo CakePool, todos os usuários de Staking flexível estarão sujeitos a dois conjuntos de taxas.&#x20;

#### Taxa sobre recompensas de Staking flexível&#x20;

Uma taxa de 2% será aplicada a todas as recompensas geradas pelo Staking flexível. O valor da taxa será calculado e realizado na próxima ação de depósito ou saque, descontado das shares dos usuários. Para consultar o valor da taxa de performance não realizada, use `calculatePerformanceFee(address _user)`.&#x20;

#### Taxa de saque&#x20;

Uma taxa de saque de 0,1% será aplicada ao valor de retirada do Staking se você sacar dentro de 72 horas após a última ação de depósito. A taxa de saque é descontada do valor final de saque antes da transferência de CAKE.

### Visão Geral

#### Depósito

Se você está atualmente usando o `enterStaking(uint256 _amount)` no PancakeSwap MasterChef atual. Você precisa migrar para `deposit(uint256 _amount, uint256 _lockDuration)`. Para Staking flexível, simplesmente use "0" como `_lockDuration`.

#### Saldo de Staking e Taxas

```
Variáveis globais: CakePoolContract // contrato do pool CAKE
struct UserInfo {
    uint256 shares; // número de shares de um usuário.
    uint256 lastDepositedTime; // timestamp da última ação de depósito
    uint256 cakeAtLastUserAction; // número de CAKE na última ação do usuário
    uint256 lastUserActionTime; // timestamp da última ação do usuário
    uint256 lockStartTime; // timestamp do início do bloqueio.
    uint256 lockEndTime; // timestamp do fim do bloqueio.
    uint256 userBoostedShare; // a quantidade de shares impulsionadas/adicionadas ao usuário.
    bool locked; // status do bloqueio
    uint256 lockedAmount; // número de CAKE bloqueados no início do período de bloqueio.
}
```

**Valor de Staking de CAKE (antes de subtrair todas as taxas)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // quantidade de cake (wei), no Staking flexível, userInfo.userBoostedShare deve ser 0.
```

**Taxa de Performance**

Consultar no contrato:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Calcular manualmente:

```
async function calculatePerformanceFeeAmount(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user);  //usuários normais com taxa livre são alguns contratos especiais, então você pode definir o padrão como false

    if(user.shares > 0 && !user.locked && !isFreeFee){
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 totalAmount = user.shares * PricePerFullShare / 1e18; 
        uint256 earnAmount = totalAmount - user.cakeAtLastUserAction;
        uint256 performanceFee = await  CakePoolContract.performanceFee();
        uint256 currentPerformanceFee = (earnAmount * performanceFee) / 10000;
        return currentPerformanceFee;
    }
    return 0;
}
```

**Taxa de Atraso: (aplica-se apenas ao Staking bloqueado)**

Consultar no contrato:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Calcular manualmente:

```
async function calculateOverdueFee(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //usuários normais com taxa livre são alguns contratos especiais, então você pode definir o padrão como false
    const UNLOCK_FREE_DURATION = 1 week seconds (ou você pode obter do contrato inteligente,  const UNLOCK_FREE_DURATION = await CakePoolContract.UNLOCK_FREE_DURATION())
    const DURATION_FACTOR_OVERDUE = 180 * 24 * 3600; // 180 dias, para calcular a taxa de atraso. você pode obtê-lo do contrato também.

    if (
        user.shares > 0 &&
        user.locked &&
        !isFreeFee &&
        ((user.lockEndTime + UNLOCK_FREE_DURATION) < block.timestamp)
    ) {
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 currentAmount = user.shares * PricePerFullShare / 1e18 - user.userBoostedShare;
        uint256 earnAmount = currentAmount - user.lockedAmount;
        uint256 overdueDuration = block.timestamp - user.lockEndTime - UNLOCK_FREE_DURATION;  //  você pode usar o timestamp UTC para substituir o block.timestamp atual.
        if (overdueDuration > DURATION_FACTOR_OVERDUE) {
            overdueDuration = DURATION_FACTOR_OVERDUE;
        }
        // As taxas são calculadas com base na duração de atraso do usuário.
        uint256 overdueWeight = (overdueDuration * overdueFee) / DURATION_FACTOR_OVERDUE;
        uint256 currentOverdueFee = (earnAmount * overdueWeight) / PRECISION_FACTOR;
        return currentOverdueFee;
    }
    return 0;
}
```

**Taxa de Saque**

```
const user = await CakePoolContract.userInfo(address);
const withdrawFee = await  CakePoolContract.withdrawFee();
const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //usuários normais com taxa livre são alguns contratos especiais, então você pode definir o padrão como false
let WithdrawFeeAmount = 0;
// você pode usar o timestamp UTC para substituir o block.timestamp atual.
// withdrawFeePeriod = 72 * 3600 (S)
// _amount : valor do saque
if (!isFreeFee && (block.timestamp < user.lastDepositedTime + withdrawFeePeriod)) {
     WithdrawFeeAmount = _amount * withdrawFee;
}
```

**Valor de Staking de CAKE (após subtrair todas as taxas)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Recompensas Pendentes&#x20;

Por favor, note que o novo pool não requer nenhuma composição. As recompensas são colocadas no seu saldo de Staking automaticamente.

No entanto, você pode consultar o número de CAKE ganhos desde a última ação, usando a diferença entre o saldo de Staking atual (mencionado acima) e o número de `userInfo.cakeAtLastUserAction`.

#### Saque

Se você está usando o método `leaveStaking(uint256 _amount)` no PancakeSwap MasterChef atual. Você precisa migrar para `withdraw(uint256 _shares)`.

Ao fazer Staking flexível. Por favor, note que ao sacar, as taxas de recompensa pendentes serão calculadas e descontadas do número de shares dos usuários, o número real de shares sendo sacadas será recalibrado, com base na porcentagem das shares que você está sacando em relação ao total de shares que você possui. Veja o exemplo abaixo:

```
// o número de CAKE sendo sacados pode ser calculado por:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Por favor, note que o valor final recebido será afetado pela taxa de saque. Se sua função depende crucialmente do número final de CAKE sendo sacados, recomendamos calcular isso usando a diferença no saldo de CAKE antes e depois da ação de saque:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Ou calcule e subtraia a taxa de saque ao estimar o valor.

#### Como calcular o CAKE por bloco distribuído ao novo pool de CAKE?

Anteriormente, o pool CAKE manual tinha uma emissão fixa de 10 CAKE/bloco. Após migrar para o MasterChef v2 e o novo pool de CAKE, agora podemos ajustar suas emissões.

E aqui está como você pode calcular o CAKE por bloco distribuído ao novo pool de CAKE:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Você pode consultar o `cakePool.allocPoint` usando `MasterChef.poolInfo(0)`

### **Endereço do Contrato na Mainnet**

**Nome do contrato:** CakePool\
**Endereço do contrato:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Ver o PancakeSwap: Cake Pool Contract no BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Ambiente de Testnet**

Você pode usar o seguinte ambiente de testnet para testar a integração do seu projeto com o novo PancakeSwap CAKE Pool. Se tiver dúvidas, entre em contato com nossa equipe pelos canais existentes ou envie um e-mail para bun@pancakeswap.com.

**Tokens Fictícios:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (pode ser mintado usando `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory e Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: CAKE Manual
  * pid4: Pool Fictício para MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Novo CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
