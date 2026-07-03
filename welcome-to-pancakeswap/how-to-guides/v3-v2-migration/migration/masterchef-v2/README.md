---
description: Migrer vers MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 est un nouveau contrat principal de Staking pour les Farms, offrant davantage de flexibilité pour ajuster les émissions de $CAKE, notamment pour le CAKE Pool, la destruction (burn) et d'autres produits PancakeSwap.

### Dois-je migrer ?

Si vous utilisez actuellement le PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), vous devrez migrer vers le nouveau contrat ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Présentation

#### Dépôt&#x20;

Si vous utilisez actuellement `enterStaking(uint256 _amount)` sur le PancakeSwap MasterChef actuel, vous devez migrer vers le nouveau contrat CAKE Pool. Consultez la documentation correspondante [ici](../cake-syrup-pool.md).

La fonction de dépôt pour les Pools de Farms reste inchangée. Cependant, vous devrez mettre à jour l'adresse du MasterChef et le `pid`. Consultez la [liste des Farms](list-of-farms.md) pour les nouveaux `pids` sur MasterChef v2.

#### Types de Pool

MasterChef v2 dispose de 2 types de Pool : les Pools de Farms réguliers et les Pools de Farms spéciaux. Vous pouvez utiliser `poolInfo(_pid).isRegular` pour interroger le type de Pool. Ils partagent un `totalAllocPoint` différent, ce qui en fait deux ensembles de Pools indépendants.

Pools de Farms spéciaux : seules les adresses figurant sur liste blanche peuvent déposer. Ils sont généralement utilisés par les produits internes de PancakeSwap pour la distribution des récompenses.

Pools de Farms réguliers : les Farms de LP tokens habituels. Par exemple CAKE-BNB, BNB-BUSD, etc.

#### Retrait

Si vous utilisez actuellement `leaveStaking(uint256 _amount)` sur le PancakeSwap MasterChef actuel, vous devez migrer vers le nouveau contrat CAKE Pool. Consultez la documentation correspondante [ici](../cake-syrup-pool.md).

La fonction de retrait pour les Pools de Farms reste inchangée. Cependant, vous devrez mettre à jour l'adresse du MasterChef et le `pid`. Consultez la [liste des Farms](list-of-farms.md) pour les nouveaux `pids` sur MasterChef v2.

#### Solde de Staking

Utilisez `userInfo[_pid][_user].amount` pour interroger le solde de Staking.

#### Token de Staking&#x20;

Notez que la nouvelle structure `PoolInfo` **ne contient pas** le champ d'adresse du LP token. Vous devrez utiliser `lpToken(_pid)` pour interroger le token de Staking de n'importe quel Pool donné.&#x20;

#### Parts/Montant total de Staking

Utilisez `lpToken.balanceOf(MasterChef.address)` pour obtenir le montant total de Staking de n'importe quel Farm Pool donné.

Cependant, dans MasterChef v2, les parts des utilisateurs peuvent être boostées (à venir prochainement). Par conséquent, les récompenses sont calculées à l'aide d'un nouveau champ `totalBoostedShare` dans `PoolInfo` comme total des parts de chaque Pool. Par exemple, si le Pool 0 a 2 utilisateurs, l'utilisateur1 stake 100 LP (sans boost) et l'utilisateur2 stake 100 LP (avec un `boostMultiplier` de 1,05), alors le `totalBoostedShare` sera de 205, ce qui donnera à l'utilisateur2 davantage de récompenses.

#### CakePerBlock

Vous pouvez utiliser `cakePerBlock(bool _isRegular)` pour interroger la récompense CAKE par bloc allouée à l'ensemble des Farms PancakeSwap.

### Adresse du contrat Mainnet

**Nom du contrat :** MasterChef v2\
**Adresse du contrat :** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Voir le contrat PancakeSwap : Contrat principal de Staking v2 sur BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Environnement de test (Testnet)

Vous pouvez utiliser l'environnement de test suivant pour tester l'intégration de votre projet avec le nouveau PancakeSwap MasterChef v2. Si vous avez des questions, veuillez contacter notre équipe via les canaux existants ou par e-mail à bun@pancakeswap.com.

**Tokens fictifs :**

* $CAKE : `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable via `mint(address _to, uint256 _amount) public`)
* $BUSD : `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (mintable via `mint(uint256 amount) public`)
* $WBNB : `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory et Router

* Factory v2 : `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2 : `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### Paires LP

* CAKE-WBNB : `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD : `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1 : `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0 : CAKE Manuel
  * pid4 : Pool fictif pour MasterChef v2
  * pid5 : CAKE-BUSD : `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6 : CAKE-WBNB : `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2 : `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3 : CAKE-BUSD : `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4 : CAKE-WBNB : `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
