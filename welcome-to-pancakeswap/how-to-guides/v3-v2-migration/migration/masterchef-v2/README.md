---
description: Migrar para o MasterChef v2
---

# MasterChef v2

O PancakeSwap MasterChef v2 é um novo contrato principal de Staking para Farms que oferece mais flexibilidade para ajustar as emissões de $CAKE, incluindo o pool de CAKE, queima e outros produtos do PancakeSwap.

### Preciso migrar?

Se você está atualmente usando o PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), você precisará migrar para o novo contrato ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Visão Geral

#### Depósito&#x20;

Se você está atualmente usando o `enterStaking(uint256 _amount)` no PancakeSwap MasterChef atual. Você precisa migrar para o novo contrato do pool de CAKE. Confira a documentação relacionada [aqui](../cake-syrup-pool.md).

A função de depósito para os pools de farm é inalterada. No entanto, você precisará atualizar o endereço do MasterChef e o `pid`, confira a [lista de farms](list-of-farms.md) para a lista de novos `pids` no MasterChef v2.

#### Tipos de pool

O MasterChef v2 tem 2 tipos de pool: pools de farm regulares e pools de farm especiais, que você pode usar `poolInfo(_pid).isRegular` para consultar o tipo de pool. Eles compartilham um `totalAllocPoint` diferente, tornando-os dois conjuntos de pools independentes.

Pools de farm especiais: apenas endereços na lista branca podem depositar. Geralmente são utilizados por produtos internos do PancakeSwap para distribuição de recompensas.

Pools de farm regulares: os farms de tokens LP regulares. Por exemplo CAKE-BNB, BNB-BUSD, etc…

#### Saque

Se você está atualmente usando o `leaveStaking(uint256 _amount)` no PancakeSwap MasterChef atual. Você precisa migrar para o novo contrato do pool de CAKE. Confira a documentação relacionada [aqui](../cake-syrup-pool.md).

A função de saque para os pools de farm é inalterada. No entanto, você precisará atualizar o endereço do MasterChef e o `pid`, confira a [lista de farms](list-of-farms.md) para a lista de novos `pids` no MasterChef v2.

#### Saldo de Staking

Use `userInfo[_pid][_user].amount` para consultar o saldo de Staking.

#### Token de Staking&#x20;

Observe que o novo struct `PoolInfo` **não** contém o campo de endereço do token LP, você precisará usar `lpToken(_pid)` para consultar o token de Staking de qualquer pool.&#x20;

#### Total de Shares/Valor em Staking

Use `lpToken.balanceOf(MasterChef.address)` para obter o total de valor em Staking de qualquer pool de farm.

No entanto, no MasterChef v2, as shares dos usuários podem ser impulsionadas (em breve). Portanto, as recompensas são calculadas usando um novo campo `totalBoostedShare` em `PoolInfo` como total de shares de cada pool. Por exemplo, se o pool 0 tem 2 usuários, user1 faz Staking de 100 LPs (sem boost), user2 faz Staking de 100 (com `boostMultiplier` sendo 1.05), então o `totalBoostedShare` se tornará 205. Resultando em user2 ganhando mais recompensas.

#### CakePerBlock

Você pode usar `cakePerBlock(bool _isRegular)` para consultar a recompensa de CAKE por bloco que vai para todos os farms do PancakeSwap.

### Endereço do Contrato na Mainnet

**Nome do contrato:** MasterChef v2\
**Endereço do contrato:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Ver o PancakeSwap: Main Staking Contract v2 no BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Ambiente de Testnet

Você pode usar o seguinte ambiente de testnet para testar a integração do seu projeto com o novo PancakeSwap MasterChef v2. Se tiver dúvidas, entre em contato com nossa equipe pelos canais existentes ou envie um e-mail para bun@pancakeswap.com.

**Tokens Fictícios:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (pode ser mintado usando `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (pode ser mintado usando `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory e Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Pares LP

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: CAKE Manual
  * pid4: Pool Fictício para MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
