---
description: Migrate to new CAKE Syrup Pool
---

# CAKE Syrup Pool

नया CakePool एक नया $CAKE Staking कॉन्ट्रैक्ट है जो CakeVault (वर्तमान auto CAKE Pool) के आधार पर बनाया गया है और PancakeSwap MasterChef v2 के साथ काम करने के लिए डिज़ाइन किया गया है, जो fixed-term Staking जैसी अधिक सुविधाओं के साथ "stake $CAKE, earn $CAKE" कार्यक्षमता प्रदान करता है। माइग्रेशन के बाद वर्तमान Manual CAKE Pool को बंद कर दिया जाएगा।

नया CakePool MasterChef v2 से $CAKE हार्वेस्ट करने और उन उपयोगकर्ताओं को रिवॉर्ड देने के लिए एक dummy token का उपयोग करेगा जो $CAKE Staking कर रहे हैं। जो उपयोगकर्ता अपना $CAKE लंबे समय के लिए लॉक करेंगे उन्हें अधिक शेयर (अवधि के आधार पर रैखिक रूप से बूस्टेड) मिलेंगे, इसलिए वे अधिक yield का आनंद लेंगे।

### क्या मुझे माइग्रेट करना होगा?&#x20;

यदि आप वर्तमान में PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)) पर `enterStaking` और `leaveStaking` का उपयोग कर रहे हैं, तो आपको नए कॉन्ट्रैक्ट में माइग्रेट करना होगा।

### अब compounding नहीं

नए CakePool के साथ, रिवॉर्ड शेयर के आधार पर सभी Pool उपयोगकर्ताओं को आनुपातिक रूप से वितरित किए जाते हैं। "interest-bearing tokens" या अन्य share-based मॉडल के समान, जब Pool में अधिक रिवॉर्ड डाले जाते हैं तो उपयोगकर्ताओं की Staking शेष राशि बढ़ेगी। उपयोगकर्ताओं को अपने रिवॉर्ड हार्वेस्ट और compound करने की जरूरत नहीं है।

### शुल्क&#x20;

नए CakePool में, सभी flexible Staking उपयोगकर्ता दो प्रकार के शुल्क के अधीन होंगे।&#x20;

#### Flexible Staking रिवॉर्ड पर शुल्क&#x20;

Flexible Staking द्वारा उत्पन्न सभी रिवॉर्ड पर 2% शुल्क लागू होगा। शुल्क की राशि की गणना और वसूली अगले जमा या निकासी क्रिया पर की जाएगी, उपयोगकर्ताओं के शेयर से काटी जाएगी। अवास्तविक performance fee की संख्या जानने के लिए, `calculatePerformanceFee(address _user)` का उपयोग करें।&#x20;

#### निकासी शुल्क&#x20;

अंतिम जमा क्रिया के 72 घंटों के भीतर निकासी करने पर अनस्टेकिंग राशि पर 0.1% निकासी शुल्क लागू होगा। CAKE ट्रांसफर से पहले निकासी शुल्क अंतिम निकासी राशि से काटा जाता है।

### अवलोकन

#### जमा

यदि आप वर्तमान PancakeSwap MasterChef पर `enterStaking(uint256 _amount)` का उपयोग कर रहे हैं। आपको `deposit(uint256 _amount, uint256 _lockDuration)` में माइग्रेट करना होगा। Flexible Staking के लिए, बस `_lockDuration` के रूप में "0" का उपयोग करें।

#### Staking शेष और शुल्क

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

**CAKE Staking राशि (सभी शुल्क घटाने से पहले)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Performance Fee**

कॉन्ट्रैक्ट से query करें:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

मैन्युअल रूप से गणना करें:

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

**Overdue Fee: (केवल locked Staking पर लागू)**

कॉन्ट्रैक्ट से query करें:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

मैन्युअल रूप से गणना करें:

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

**निकासी शुल्क**

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

**CAKE Staking राशि (सभी शुल्क घटाने के बाद)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Pending Rewards&#x20;

कृपया ध्यान दें कि नए Pool में कोई compounding आवश्यक नहीं है। रिवॉर्ड स्वचालित रूप से आपकी Staking शेष राशि में जोड़े जाते हैं।

हालांकि, आप अंतिम क्रिया के बाद से अर्जित CAKE की संख्या जान सकते हैं, वर्तमान Staking शेष राशि (ऊपर उल्लिखित) और `userInfo.cakeAtLastUserAction` से मिली संख्या के बीच का अंतर उपयोग करके।

#### निकासी

यदि आप वर्तमान PancakeSwap MasterChef पर `leaveStaking(uint256 _amount)` विधि का उपयोग कर रहे हैं। आपको `withdraw(uint256 _shares)` में माइग्रेट करना होगा।

Flexible Staking करते समय। कृपया ध्यान दें कि निकासी पर, pending reward fees की गणना की जाएगी और उपयोगकर्ताओं के शेयर की संख्या से काटी जाएगी, निकाले जाने वाले शेयर की वास्तविक संख्या को आपके कुल शेयर के मुकाबले आपके द्वारा निकाले जाने वाले शेयर के प्रतिशत के आधार पर पुनः-अंशांकित किया जाएगा। नीचे उदाहरण देखें:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

कृपया ध्यान दें कि अंतिम प्राप्त राशि निकासी शुल्क से प्रभावित होगी। यदि आपका फ़ंक्शन निकाले जा रहे CAKE की अंतिम संख्या पर महत्वपूर्ण रूप से निर्भर करता है, तो हम अनुशंसा करते हैं कि निकासी क्रिया से पहले और बाद में CAKE शेष में अंतर का उपयोग करके इसकी गणना करें:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

या राशि का अनुमान लगाते समय निकासी शुल्क की गणना करें और घटाएं।

#### नए CAKE Pool को वितरित प्रति ब्लॉक CAKE की गणना कैसे करें?

पहले, manual CAKE Pool में एक निश्चित 10 CAKE/block एमिशन था। MasterChef v2 और नए CAKE Pool में माइग्रेट करने के बाद, अब हम इसके एमिशन समायोजित कर सकते हैं।

और यहाँ बताया गया है कि आप नए CAKE Pool को वितरित प्रति ब्लॉक CAKE की गणना कैसे कर सकते हैं:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

आप `MasterChef.poolInfo(0)` का उपयोग करके `cakePool.allocPoint` query कर सकते हैं

### **Mainnet कॉन्ट्रैक्ट पता**

**कॉन्ट्रैक्ट का नाम:** CakePool\
**कॉन्ट्रैक्ट पता:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[BscScan पर PancakeSwap: Cake Pool Contract देखें।](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Testnet वातावरण**

आप नए PancakeSwap CAKE Pool के साथ अपने प्रोजेक्ट के एकीकरण का परीक्षण करने के लिए निम्नलिखित testnet वातावरण का उपयोग कर सकते हैं। यदि आपके कोई प्रश्न हैं, तो कृपया मौजूदा चैनलों के माध्यम से हमारी टीम से संपर्क करें, या Email के माध्यम से bun@pancakeswap.com पर पहुंचें।

**Dummy Tokens:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable by using `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory और Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### नया CAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
