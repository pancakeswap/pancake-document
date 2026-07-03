---
description: Migrer vers le nouveau CAKE Syrup Pool
---

# CAKE Syrup Pool

Le nouveau CakePool est un nouveau contrat de Staking $CAKE basé sur le CakeVault (l'actuel pool CAKE automatique) et conçu pour fonctionner avec PancakeSwap MasterChef v2 afin de proposer une fonctionnalité "staker $CAKE, gagner $CAKE" tout en offrant davantage de fonctionnalités, comme le Staking à terme fixe. Le pool CAKE Manuel actuel sera retiré après la migration.

Le nouveau CakePool utilisera un token fictif pour récolter des $CAKE depuis MasterChef v2 et les distribuer aux utilisateurs qui stakent des $CAKE. Les utilisateurs qui bloquent leurs $CAKE plus longtemps recevront un nombre de parts plus important (boosté linéairement selon la durée), et profiteront ainsi d'un rendement plus élevé.

### Dois-je migrer ?&#x20;

Si vous utilisez actuellement `enterStaking` et `leaveStaking` sur le PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), vous devrez migrer vers le nouveau contrat.

### Plus de composé automatique

Avec le nouveau CakePool, les récompenses sont distribuées proportionnellement à tous les utilisateurs du Pool en fonction de leurs parts. Similaire aux "interest-bearing tokens" ou à d'autres modèles basés sur les parts, le solde de Staking des utilisateurs augmentera automatiquement au fur et à mesure que davantage de récompenses sont ajoutées au Pool. Les utilisateurs n'ont pas besoin de récolter et de composer leurs récompenses manuellement.

### Frais&#x20;

Dans le nouveau CakePool, tous les utilisateurs en Staking flexible sont soumis à deux séries de frais.&#x20;

#### Frais sur les récompenses de Staking flexible&#x20;

Des frais de 2% s'appliquent à toutes les récompenses générées par le Staking flexible. Le montant des frais est calculé et prélevé lors de la prochaine action de dépôt ou de retrait, déduit des parts de l'utilisateur. Pour interroger le montant des frais de performance non réalisés, utilisez `calculatePerformanceFee(address _user)`.&#x20;

#### Frais de retrait&#x20;

Des frais de retrait de 0,1% s'appliquent au montant déstaké si vous effectuez un retrait dans les 72 heures suivant la dernière action de dépôt. Les frais de retrait sont déduits du montant final du retrait avant le transfert de CAKE.

### Présentation

#### Dépôt

Si vous utilisez actuellement `enterStaking(uint256 _amount)` sur le PancakeSwap MasterChef actuel, vous devez migrer vers `deposit(uint256 _amount, uint256 _lockDuration)`. Pour le Staking flexible, utilisez simplement "0" comme `_lockDuration`.

#### Solde de Staking et frais

```
Global variables: CakePoolContract // CAKE pool contract
struct UserInfo {
    uint256 shares; // number of shares for a user.
    uint256 lastDepositedTime; // timestamp of the last deposit action
    uint256 cakeAtLastUserAction; // number of CAKE at the last user action
    uint256 lastUserActionTime; // timestamp of the last user action
    uint256 lockStartTime; // timestamp of the start of the lock.
    uint256 lockEndTime; // timestamp of the end of the lock.
    uint256 userBoostedShare; // the amount of shares boosted/added to the user.
    bool locked; // status of the lock
    uint256 lockedAmount; // number of CAKE locked at the start of the lock period.
}
```

**Montant de Staking CAKE (avant déduction de tous les frais)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Frais de performance**

Requête depuis le contrat :

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Calcul manuel :

```
async function calculatePerformanceFeeAmount(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user);  //normal free fee users are some special contracts , so you can set default false

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

**Frais de dépassement : (applicable uniquement au Staking bloqué)**

Requête depuis le contrat :

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Calcul manuel :

```
async function calculateOverdueFee(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //normal free fee users are some special contracts , so you can set default false
    const UNLOCK_FREE_DURATION = 1 week seconds (or you can get from smart contract,  const UNLOCK_FREE_DURATION = await CakePoolContract.UNLOCK_FREE_DURATION())
    const DURATION_FACTOR_OVERDUE = 180 * 24 * 3600; // 180 days, in order to calculate overdue fee. you can get it from contract too.

    if (
        user.shares > 0 &&
        user.locked &&
        !isFreeFee &&
        ((user.lockEndTime + UNLOCK_FREE_DURATION) < block.timestamp)
    ) {
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 currentAmount = user.shares * PricePerFullShare / 1e18 - user.userBoostedShare;
        uint256 earnAmount = currentAmount - user.lockedAmount;
        uint256 overdueDuration = block.timestamp - user.lockEndTime - UNLOCK_FREE_DURATION;  //  you can use UTC timestamp to replace current block.timestamp.
        if (overdueDuration > DURATION_FACTOR_OVERDUE) {
            overdueDuration = DURATION_FACTOR_OVERDUE;
        }
        // Rates are calculated based on the user's overdue duration.
        uint256 overdueWeight = (overdueDuration * overdueFee) / DURATION_FACTOR_OVERDUE;
        uint256 currentOverdueFee = (earnAmount * overdueWeight) / PRECISION_FACTOR;
        return currentOverdueFee;
    }
    return 0;
}
```

**Frais de retrait**

```
const user = await CakePoolContract.userInfo(address);
const withdrawFee = await  CakePoolContract.withdrawFee();
const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //normal free fee users are some special contracts , so you can set default false
let WithdrawFeeAmount = 0;
// you can use UTC timestamp to replace current block.timestamp.
// withdrawFeePeriod = 72 * 3600 (S)
// _amount : withdraw amount
if (!isFreeFee && (block.timestamp < user.lastDepositedTime + withdrawFeePeriod)) {
     WithdrawFeeAmount = _amount * withdrawFee;
}
```

**Montant de Staking CAKE (après déduction de tous les frais)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Récompenses en attente&#x20;

Veuillez noter que le nouveau Pool ne nécessite aucun composé automatique. Les récompenses sont automatiquement ajoutées à votre solde de Staking.

Cependant, vous pouvez interroger le nombre de CAKE gagnés depuis la dernière action, en calculant la différence entre le solde de Staking actuel (mentionné ci-dessus) et la valeur issue de `userInfo.cakeAtLastUserAction`.

#### Retrait

Si vous utilisez la méthode `leaveStaking(uint256 _amount)` sur le PancakeSwap MasterChef actuel, vous devez migrer vers `withdraw(uint256 _shares)`.

Pour le Staking flexible, veuillez noter que lors du retrait, les frais de récompenses en attente seront calculés et déduits des parts de l'utilisateur. Le nombre réel de parts retirées sera recalibré en fonction du pourcentage des parts que vous retirez par rapport à vos parts totales. Voir l'exemple ci-dessous :

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Veuillez noter que le montant final reçu sera affecté par les frais de retrait. Si votre fonction repose de manière critique sur le nombre final de CAKE retirés, nous recommandons de le calculer en utilisant la différence de solde CAKE avant et après l'action de retrait :

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Ou calculez et soustrayez les frais de retrait lors de l'estimation du montant.

#### Comment calculer les CAKE par bloc distribués au nouveau CAKE Pool ?

Auparavant, le pool CAKE Manuel avait une émission fixe de 10 CAKE/bloc. Après la migration vers MasterChef v2 et le nouveau CAKE Pool, il est désormais possible d'ajuster ses émissions.

Voici comment calculer les CAKE par bloc distribués au nouveau CAKE Pool :

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Vous pouvez interroger le `cakePool.allocPoint` via `MasterChef.poolInfo(0)`.

### **Adresse du contrat Mainnet**

**Nom du contrat :** CakePool\
**Adresse du contrat :** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Voir le contrat PancakeSwap : Cake Pool sur BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Environnement de test (Testnet)**

Vous pouvez utiliser l'environnement de test suivant pour tester l'intégration de votre projet avec le nouveau PancakeSwap CAKE Pool. Si vous avez des questions, veuillez contacter notre équipe via les canaux existants ou par e-mail à bun@pancakeswap.com.

**Tokens fictifs :**

* $CAKE : `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable via `mint(address _to, uint256 _amount) public`)
* $WBNB : `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory et Router

* Factory v2 : `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2 : `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1 : `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0 : CAKE Manuel
  * pid4 : Pool fictif pour MasterChef v2
* v2 : `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Nouveau CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
