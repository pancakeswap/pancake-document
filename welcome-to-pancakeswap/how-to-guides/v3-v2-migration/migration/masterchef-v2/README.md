---
description: Migrar a MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 es un nuevo contrato principal de Staking para Farms, mientras proporciona más flexibilidad para ajustar las emisiones de $CAKE, incluyendo el pool de CAKE, la quema y otros productos de PancakeSwap.

### ¿Necesito migrar?

Si actualmente usas PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), necesitarás migrar al nuevo contrato ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Descripción general

#### Depósito&#x20;

Si actualmente usas `enterStaking(uint256 _amount)` en el PancakeSwap MasterChef actual, necesitas migrar al nuevo contrato del pool de CAKE. Consulta la documentación relacionada [aquí](../cake-syrup-pool.md).

La función de depósito para los pools de farm no ha cambiado. Sin embargo, necesitarás actualizar la dirección de MasterChef y el `pid`, consulta la [lista de farms](list-of-farms.md) para ver la lista de nuevos `pids` en MasterChef v2.

#### Tipos de pool

MasterChef v2 tiene 2 tipos de pool: pools de farm regulares y pools de farm especiales, que puedes consultar usando `poolInfo(_pid).isRegular` para el tipo de pool. Comparten un `totalAllocPoint` diferente, convirtiéndolos en dos conjuntos de pools independientes.

Pools de farm especiales: solo las direcciones en la lista blanca pueden depositar. Suelen ser utilizados por productos internos de PancakeSwap para distribución de recompensas.

Pools de farm regulares: los farms de tokens LP regulares. Por ejemplo CAKE-BNB, BNB-BUSD, etc.

#### Retiro

Si actualmente usas `leaveStaking(uint256 _amount)` en el PancakeSwap MasterChef actual, necesitas migrar al nuevo contrato del pool de CAKE. Consulta la documentación relacionada [aquí](../cake-syrup-pool.md).

La función de retiro para los pools de farm no ha cambiado. Sin embargo, necesitarás actualizar la dirección de MasterChef y el `pid`, consulta la [lista de farms](list-of-farms.md) para ver la lista de nuevos `pids` en MasterChef v2.

#### Saldo de Staking

Usa `userInfo[_pid][_user].amount` para consultar el saldo de Staking.

#### Token de Staking&#x20;

Ten en cuenta que el nuevo struct `PoolInfo` **no** contiene el campo de dirección del token LP; deberás usar `lpToken(_pid)` para consultar el token de Staking de cualquier pool.&#x20;

#### Total de participaciones/monto de Staking

Usa `lpToken.balanceOf(MasterChef.address)` para obtener el monto total de Staking para cualquier pool de farm.

Sin embargo, en MasterChef v2, las participaciones de los usuarios pueden ser potenciadas (próximamente). Por lo tanto, las recompensas se calculan usando un nuevo campo `totalBoostedShare` en `PoolInfo` como el total de participaciones de cada pool. Por ejemplo, si el pool 0 tiene 2 usuarios, el usuario1 hace Staking de 100 LPs (sin potenciación), el usuario2 hace Staking de 100 (con `boostMultiplier` de 1.05), entonces el `totalBoostedShare` se convertirá en 205. Resultando en que el usuario2 gane más recompensas.

#### CakePerBlock

Puedes usar `cakePerBlock(bool _isRegular)` para consultar la recompensa de CAKE por bloque que va a todos los farms de PancakeSwap.

### Dirección del contrato en Mainnet

**Nombre del contrato:** MasterChef v2\
**Dirección del contrato:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Ver el contrato PancakeSwap: Main Staking Contract v2 en BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Entorno de Testnet

Puedes usar el siguiente entorno de testnet para probar la integración de tu proyecto con el nuevo PancakeSwap MasterChef v2. Si tienes alguna pregunta, contáctanos a través de los canales existentes, o comunícate con bun@pancakeswap.com por correo electrónico.

**Tokens ficticios:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (acuñable usando `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (acuñable usando `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory y Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Pares LP

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Pool ficticio para MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
