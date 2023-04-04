# MasterChef v2

PancakeSwap MasterChef v2 es un nuevo contrato de staking principal para Farms, al tiempo que proporciona más flexibilidad para ajustar las emisiones de $CAKE, incluido el Pool de CAKE, la quema y otros productos de PancakeSwap.

### Necesito migrar?

Si actualmente estás usando el contrato MasterChef de PancakeSwap ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), necesitarás migrar al nuevo contrato.

### Resumen

#### Depositar

Si actualmente estás usando `enterStaking(uint256 _amount)` en el contrato MasterChef de PancakeSwap. Deberás migrar al nuevo contrato. Consulte la documentación relacionada aquí.

La función de depósito para los pools de farms no ha cambiado.

#### Pool types

MasterChef v2 tiene 2 tipos de pool: Pools de farm regulares y Pools de farm especiales, puedes usar `poolInfo(_pid).isRegular` para consultar el tipo de grupo. Comparten un totalAllocPoint diferente, lo que los convierte en dos conjuntos de pools independientes.

Pools de farm especiales: solo las direcciones incluidas en la lista blanca pueden depositar. Por lo general, son utilizados por productos internos de PancakeSwap para distribuciones de recompensas.

Pools de farm regulares: LP farm tokens regulares. Por ejemplo CAKE-BNB, BNB-BUSD, etc…

#### Retiro

Si actualmente estás usando `leaveStaking(uint256 _amount)` en el contrato MasterChef de PancakeSwap. Deberás migrar al nuevo contrato. Consulte la documentación relacionada aquí.

La función de retiro para los pools de farms no ha cambiado.



#### Staking Balance

Usa `userInfo[_pid][_user].amount` para consultar el staking balance.

#### Staking Token&#x20;

Tenga en cuenta que la nueva estructura `PoolInfo` no contiene el campo de dirección de token lp, deberá usar`lpToken(_pid)` para consultar el staking token de cualquierpool.

#### Total Staking Shares/Amount

Puedes usar`lpToken.balanceOf(MasterChef.address)` para obtener el total depositado en cualquier pool.

Sin embargo, en MasterChef v2, la participación de los usuarios se puede boostear (próximamente). Por lo tanto, las recompensas se calculan utilizando un nuevo campo totalBoostedShare en PoolInfo como los recursos compartidos totales de cada pool. Por ejemplo, si el pool 0 tiene 2 usuarios, el usuario1 deposita 100 LP (sin boost), el usuario2 deposita 100 (con boostMultiplier siendo 1.05), entonces el totalBoostedShare se convertirá en 205. Lo que resulta en que el usuario2 obtenga más recompensas.

#### CakePerBlock

Puedes usar `cakePerBlock(bool _isRegular)`para consultar el CAKE por bloque que se dirige a los farms de PancakeSwap.

### Entorno Testnet

Puede utilizar el siguiente entorno de testnet para probar la integración de tu proyecto con el nuevo PancakeSwap MasterChef v2. Si tienes alguna pregunta, comuníquese con nuestro equipo a través de los canales existentes o a través de bun@pancakeswap.com.

**Dummy Tokens:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable usando `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  ``(mintable usando `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory & Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Pares LP

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
