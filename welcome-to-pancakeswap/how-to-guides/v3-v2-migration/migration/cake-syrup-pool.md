---
description: Zum neuen CAKE Syrup Pool migrieren
---

# CAKE Syrup Pool

Der neue CakePool ist ein neuer $CAKE-Staking-Vertrag, der auf dem CakeVault (dem aktuellen Auto-CAKE-Pool) basiert und so konzipiert ist, dass er mit PancakeSwap MasterChef v2 zusammenarbeitet, um die Funktionalität „$CAKE staken, $CAKE verdienen" bereitzustellen, während er zusätzliche Funktionen wie Festlaufzeit-Staking bietet. Der aktuelle manuelle CAKE-Pool wird nach der Migration eingestellt.

Der neue CakePool wird ein Dummy-Token verwenden, um $CAKE aus MasterChef v2 zu ernten und die Rewards an Benutzer zu verteilen, die $CAKE staken. Benutzer, die ihr $CAKE länger sperren, erhalten eine größere Anzahl an Anteilen (linear basierend auf der Dauer erhöht) und genießen daher eine höhere Rendite.

### Muss ich migrieren?&#x20;

Wenn Sie derzeit `enterStaking` und `leaveStaking` auf dem PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)) verwenden, müssen Sie zum neuen Vertrag migrieren.

### Kein Compounding mehr

Mit dem neuen CakePool werden Rewards proportional an alle Pool-Nutzer auf Basis von Anteilen verteilt. Ähnlich wie bei „zinsbringenden Token" oder anderen anteilsbasierten Modellen wächst der Staking-Betrag der Benutzer, wenn mehr Rewards in den Pool fließen. Benutzer müssen ihre Rewards nicht manuell ernten und zusammenlegen.

### Gebühren&#x20;

Im neuen CakePool sind alle flexiblen Staking-Benutzer zwei Gebührenarten unterworfen.&#x20;

#### Gebühr auf flexible Staking-Rewards&#x20;

Eine Gebühr von 2% wird auf alle durch flexibles Staking generierten Rewards erhoben. Der Gebührenbetrag wird bei der nächsten Einzahlungs- oder Auszahlungsaktion berechnet und von den Anteilen der Benutzer abgezogen. Zur Abfrage der nicht realisierten Performance-Gebühr verwenden Sie `calculatePerformanceFee(address _user)`.&#x20;

#### Auszahlungsgebühr&#x20;

Eine Auszahlungsgebühr von 0,1% wird auf den Entstaking-Betrag erhoben, wenn Sie innerhalb von 72 Stunden nach der letzten Einzahlung abheben. Die Auszahlungsgebühr wird vor der CAKE-Übertragung vom endgültigen Auszahlungsbetrag abgezogen.

### Überblick

#### Einzahlung

Wenn Sie derzeit `enterStaking(uint256 _amount)` auf dem aktuellen PancakeSwap MasterChef verwenden, müssen Sie zu `deposit(uint256 _amount, uint256 _lockDuration)` migrieren. Für flexibles Staking verwenden Sie einfach „0" als `_lockDuration`.

#### Staking-Guthaben und Gebühren

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

**CAKE-Staking-Betrag (vor Abzug aller Gebühren)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Performance-Gebühr**

Abfrage aus dem Vertrag:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Manuell berechnen:

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

**Überfälligkeitsgebühr: (gilt nur für gesperrtes Staking)**

Abfrage aus dem Vertrag:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Manuell berechnen:

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

**Auszahlungsgebühr**

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

**CAKE-Staking-Betrag (nach Abzug aller Gebühren)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Ausstehende Rewards&#x20;

Bitte beachten Sie, dass der neue Pool kein Compounding erfordert. Rewards werden automatisch Ihrem Staking-Guthaben hinzugefügt.

Sie können jedoch die Anzahl der seit der letzten Aktion verdienten CAKE abfragen, indem Sie die Differenz zwischen dem aktuellen Staking-Guthaben (oben erwähnt) und dem Wert von `userInfo.cakeAtLastUserAction` berechnen.

#### Abheben

Wenn Sie die Methode `leaveStaking(uint256 _amount)` auf dem aktuellen PancakeSwap MasterChef verwenden, müssen Sie zu `withdraw(uint256 _shares)` migrieren.

Beim flexiblen Staking ist zu beachten, dass beim Abheben die ausstehenden Reward-Gebühren berechnet und von der Anzahl der Anteile des Benutzers abgezogen werden. Die tatsächliche Anzahl der abgehobenen Anteile wird basierend auf dem Prozentsatz der abgehobenen Anteile im Verhältnis zu den Gesamtanteilen neu kalibriert. Siehe das folgende Beispiel:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Bitte beachten Sie, dass der endgültige Erhalt durch die Auszahlungsgebühr beeinflusst wird. Wenn Ihre Funktion entscheidend von der endgültigen Anzahl der abgehobenen CAKE abhängt, empfehlen wir, dies anhand der Differenz des CAKE-Guthabens vor und nach der Abhebung zu berechnen:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Oder berechnen und subtrahieren Sie die Auszahlungsgebühr bei der Schätzung des Betrags.

#### Wie berechnet man die CAKE pro Block, die dem neuen CAKE-Pool zugeteilt werden?

Früher hatte der manuelle CAKE-Pool eine feste Emission von 10 CAKE/Block. Nach der Migration zu MasterChef v2 und dem neuen CAKE-Pool können wir jetzt die Emissionen anpassen.

Und so können Sie die CAKE pro Block berechnen, die dem neuen CAKE-Pool zugeteilt werden:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Sie können das `cakePool.allocPoint` mit `MasterChef.poolInfo(0)` abfragen.

### **Mainnet-Vertragsadresse**

**Vertragsname:** CakePool\
**Vertragsadresse:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Den PancakeSwap: Cake Pool Vertrag auf BscScan anzeigen.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Testnet-Umgebung**

Sie können die folgende Testnet-Umgebung verwenden, um die Integration Ihres Projekts mit dem neuen PancakeSwap CAKE Pool zu testen. Wenn Sie Fragen haben, wenden Sie sich bitte über die bestehenden Kanäle an unser Team oder kontaktieren Sie uns per E-Mail unter bun@pancakeswap.com.

**Dummy-Token:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (prägbar mit `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory und Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manuelles CAKE
  * pid4: Dummy-Pool für MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### Neuer CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
