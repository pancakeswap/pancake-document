---
description: Migre para o MasterChef v2
---

# MasterChef v2

O MasterChef v2 da PancakeSwap é um novo contrato do stake principal para Farms, proporcionando mais flexibilidade para ajustar as emissões de $CAKE, incluindo Pool de CAKE, burn e outros produtos da PancakeSwap.

### Preciso migrar?

Se você está atualmente usando o MasterChef PancakeSwap ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), você precisará migrar para o novo contrato.

### Visão Geral

#### Depósito

Se você está atualmente usando `enterStaking(uint256 _amount)` no MasterChef atual da PancakeSwap. Você precisa migrar para o novo contrato da pool de CAKE. Cheque a documentação relacionada [aqui](../cake-syrup-pool.md).

A função de depósito para pools de farm está inalterado. No entanto, você precisará atualizar o endereço do MasterChef e o `pid` , cheque a [lista dos farms](list-of-farms.md) para a lista dos novos `pids` no MasterChef v2.

#### Tipos de Pool&#x20;

MasterChef v2 tem 2 tipos de pool: pools de farm regulares e pools de farm especiais, você pode usar `poolInfo(_pid).isRegular` para consultar o tipo de farm. Eles compartilham um diferente`totalAllocPoint`, tornando-os dois conjuntos de piscinas independentes.

Pools de farms especiais: somente endereços na lista de permissões podem depositar. Eles geralmente são utilizados internamente por produtos PancakeSwap para distribuições de recompensas.

Pools de farms regulares: os farms de tokens LP regulares. Por exemplo, CAKE-BNB, BNB-BUSD, etc…

#### Saque

Se você estiver usando o `leaveStaking(uint256 _amount)` no MasterChef atual da PancakeSwap. Você precisa migrar para o novo contrato da pool de CAKE. Confira a documentação relacionada [aqui](../cake-syrup-pool.md).

A função de saque para os pools de farm não foi alterada. No entanto, você precisará atualizar o endereço do MasterChef e o `pid` , cheque a [lista dos farms](list-of-farms.md) para a lista dos novos `pids` no MasterChef v2.

#### Saldo de Stake

Use `userInfo[_pid][_user].amount`para consultar o saldo do stake.

#### Token em Stake&#x20;

Observe que o novo `PoolInfo` struct **não contém** o campo de endereço do token lp, você precisará usar `lpToken(_pid)` para consultar o token de stake de qualquer pool.

#### Total de stake Participação/Quantidade

Use `lpToken.balanceOf(MasterChef.address)` para obter o valor total em stake para qualquer pool de farm.

No entanto, no MasterChef v2, a participação dos usuários pode ser aumentada (em breve). Portanto, as recompensas são calculadas usando um novo `totalBoostedShare` campo em `PoolInfo` como o total de participação de cada pool. Por exemplo, se o pool 0 tem 2 usuários, user1 faz stake de 100 LPs (sem boost), user2 faz stake de 100 (com `boostMultiplier` sendo 1.05), então o `totalBoostedShare` vai se tornar 205. Resultando no user2 ganhando mais recompensas.

#### CakePerBlock

Você pode usar `cakePerBlock(bool _isRegular)` para consultar a recompensa de CAKE por blocp que vai para todos os farm da PancakeSwap.

### Ambiente de Testnet&#x20;

Você pode usar o seguinte ambiente de testnet para testar a integração do seu projeto com o novo MasterChef v2 da PancakeSwap. Em caso de dúvidas, entre em contato com nossa equipe pelos canais existentes ou entre em contato bun@pancakeswap.com via Email.

**Tokens Fictícios:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable by using `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  \`\`(mintable by using `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory e Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Pares de LP&#x20;

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
