---
description: Migrate to MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 Farms के लिए एक नया मुख्य Staking कॉन्ट्रैक्ट है जो CAKE Pool, burn और अन्य PancakeSwap उत्पादों सहित $CAKE एमिशन समायोजित करने में अधिक लचीलापन प्रदान करता है।

### क्या मुझे माइग्रेट करना होगा?

यदि आप वर्तमान में PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)) का उपयोग कर रहे हैं, तो आपको नए कॉन्ट्रैक्ट ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)) में माइग्रेट करना होगा।

### अवलोकन

#### जमा&#x20;

यदि आप वर्तमान PancakeSwap MasterChef पर `enterStaking(uint256 _amount)` का उपयोग कर रहे हैं। आपको नए CAKE Pool कॉन्ट्रैक्ट में माइग्रेट करना होगा। संबंधित दस्तावेज़ [यहाँ](../cake-syrup-pool.md) देखें।

Farm Pools के लिए जमा फ़ंक्शन अपरिवर्तित है। हालांकि, आपको MasterChef पता और `pid` अपग्रेड करना होगा, MasterChef v2 पर नए `pid` की सूची के लिए [Farm की सूची](list-of-farms.md) देखें।

#### Pool प्रकार

MasterChef v2 में 2 प्रकार के Pool हैं: Regular farm pools और Special farm pools, जिन्हें आप `poolInfo(_pid).isRegular` का उपयोग करके Pool प्रकार query कर सकते हैं। वे एक अलग `totalAllocPoint` साझा करते हैं, जिससे वे दो स्वतंत्र Pool सेट बन जाते हैं।

Special farm pools: केवल whitelisted पते ही जमा कर सकते हैं। इनका उपयोग आमतौर पर रिवॉर्ड वितरण के लिए आंतरिक PancakeSwap उत्पादों द्वारा किया जाता है।

Regular farm pools: नियमित LP टोकन Farms। उदाहरण के लिए CAKE-BNB, BNB-BUSD, आदि...

#### निकासी

यदि आप वर्तमान PancakeSwap MasterChef पर `leaveStaking(uint256 _amount)` का उपयोग कर रहे हैं। आपको नए CAKE Pool कॉन्ट्रैक्ट में माइग्रेट करना होगा। संबंधित दस्तावेज़ [यहाँ](../cake-syrup-pool.md) देखें।

Farm Pools के लिए निकासी फ़ंक्शन अपरिवर्तित है। हालांकि, आपको MasterChef पता और `pid` अपडेट करना होगा, MasterChef v2 पर नए `pid` की सूची के लिए [Farm की सूची](list-of-farms.md) देखें।

#### Staking शेष

Staking शेष query करने के लिए `userInfo[_pid][_user].amount` का उपयोग करें।

#### Staking टोकन&#x20;

ध्यान दें कि नए `PoolInfo` struct में lp token address field **नहीं** है, किसी भी Pool का Staking टोकन query करने के लिए आपको `lpToken(_pid)` का उपयोग करना होगा।&#x20;

#### कुल Staking Shares/राशि

किसी भी Farm Pool के लिए कुल Staking राशि प्राप्त करने के लिए `lpToken.balanceOf(MasterChef.address)` का उपयोग करें।

हालांकि, MasterChef v2 में, उपयोगकर्ताओं का शेयर बूस्ट किया जा सकता है (जल्द आ रहा है)। इसलिए, रिवॉर्ड की गणना प्रत्येक Pool के कुल शेयर के रूप में `PoolInfo` में एक नए `totalBoostedShare` फ़ील्ड का उपयोग करके की जाती है। उदाहरण के लिए, यदि Pool 0 में 2 उपयोगकर्ता हैं, user1 ने 100 LP (बिना boost के) stake किए हैं, user2 ने 100 stake किए हैं (`boostMultiplier` 1.05 के साथ), तो `totalBoostedShare` 205 हो जाएगा। जिसके परिणामस्वरूप user2 को अधिक रिवॉर्ड मिलेगा।

#### CakePerBlock

सभी PancakeSwap Farms को जाने वाले प्रति ब्लॉक CAKE रिवॉर्ड query करने के लिए `cakePerBlock(bool _isRegular)` का उपयोग करें।

### Mainnet कॉन्ट्रैक्ट पता

**कॉन्ट्रैक्ट का नाम:** MasterChef v2\
**कॉन्ट्रैक्ट पता:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[BscScan पर PancakeSwap: Main Staking Contract v2 देखें।](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Testnet वातावरण

आप नए PancakeSwap MasterChef v2 के साथ अपने प्रोजेक्ट के एकीकरण का परीक्षण करने के लिए निम्नलिखित testnet वातावरण का उपयोग कर सकते हैं। यदि आपके कोई प्रश्न हैं, तो कृपया मौजूदा चैनलों के माध्यम से हमारी टीम से संपर्क करें, या Email के माध्यम से bun@pancakeswap.com पर पहुंचें।

**Dummy Tokens:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable by using `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (mintable by using `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory और Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP Pairs

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
