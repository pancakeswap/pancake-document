# अक्सर पूछे जाने वाले सवाल (FAQ)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### bCAKE multipliers की गणना कैसे होती है?

आप देख सकते हैं कि विभिन्न farms में stake करने पर आपको अलग-अलग bCAKE boost multipliers मिलते हैं।

ऐसा इसलिए है क्योंकि bCAKE - Farm Boosters multipliers को activation या refresh पर निम्नलिखित metrics का उपयोग करके गणना किया जाता है:

* `userLpBalanceInFarm` : farm में आप जितनी तरलता stake कर रहे हैं।&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : farm में stake की गई कुल तरलता राशि या V3 LP pool में वर्तमान सक्रिय तरलता राशि। bCAKE दोनों में से छोटी संख्या चुनेगा।
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : आपके पास real-time में veCAKE की संख्या
* `veCAKE.totalSupply` : veCAKE की real-time total supply

Multiplier की गणना निम्नलिखित method का उपयोग करके की जाती है:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` और `constantB` kitchen द्वारा निर्धारित किए जाते हैं और community feedback और बाजार की स्थितियों के आधार पर भविष्य में समायोजन के अधीन हैं। `constantB` LP price के अंतर की भरपाई के लिए विभिन्न farms में भिन्न होता है।

`constantA` और `constantB` को इस प्रकार प्राप्त किया जा सकता है:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

लेकिन:

{% hint style="info" %}
**संक्षेप में**

आप जितनी अधिक LP (तरलता) boost करना चाहते हैं

आपको उतने अधिक CAKE को अधिक लंबे समय के लिए lock करना होगा
{% endhint %}

### Activation के बाद भी मेरे multipliers क्यों बदलते हैं?

कृपया ध्यान दें कि **farming position या CAKE staking pool में कोई भी user action, farms और CAKE staking pool से नवीनतम data और statistics के आधार पर आपके boost multiplier को स्वचालित रूप से अपडेट करेगा**, जिसमें शामिल हैं लेकिन इन्हीं तक सीमित नहीं:

* Farm में position stake/unstake करना
* Farm से CAKE rewards harvest करना
* अपनी CAKE staking duration extend करना
* अपनी fixed-term staking position में अधिक CAKE जोड़ना
* अपनी CAKE staking position को flexible में convert करना

{% hint style="warning" %}
कृपया ध्यान दें:&#x20;

पुराने data का उपयोग करके संभावित दुरुपयोग और धोखाधड़ी को रोकने और निष्पक्षता सुनिश्चित करने के लिए, Farm booster को permissionless और community governance के रूप में डिज़ाइन किया गया है। इसलिए, **कोई भी** नवीनतम data का उपयोग करके किसी के भी boost multipliers को refresh करने के लिए MasterChef V3 contract पर `updateLiquidity(address _tokenId)` function call कर सकता है।

इसके अतिरिक्त, kitchen सभी bCAKE-enabled farming positions की निगरानी करेगा और पुराने multiplier वाली किसी भी position को refresh करेगा।
{% endhint %}

### मैं किसी position को boost क्यों नहीं कर पा रहा हूँ?

1. Farm booster केवल चुनिंदा farms के लिए उपलब्ध है। भविष्य में अधिक farms उपलब्ध कराई जाएंगी। अभी के लिए, **हरे rocket icon के साथ हरे APR figure की तलाश करें।**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. कई contracts की संलिप्तता के कारण, कुछ contract interactions के लिए थोड़े अधिक gas tokens (BNB) की आवश्यकता होती है। इसलिए कृपया सुनिश्चित करें कि आपके वॉलेट में पर्याप्त BNB हो। यदि error बनी रहे, तो transaction का gas limit मैन्युअल रूप से बढ़ाने का प्रयास करें।

### मुझे अधिकतम bCAKE Boost Multiplier कितना मिल सकता है?

वर्तमान में, एक उपयोगकर्ता को farm booster के लिए अधिकतम 2.5x boost मिल सकता है, जो उन्हें मूल APRs का 2.5x प्रदान करता है।

कृपया ध्यान दें कि आप जिस प्रकार की तरलता stake करने की कोशिश कर रहे हैं, उसके अनुसार अधिकतम boost भिन्न होता है:

* V3: अधिकतम 2x
* V2, StableSwap: अधिकतम 2.5x
* Position Managers: अधिकतम 2.5x

### मैं अपने bCAKE Boost Multipliers कैसे बढ़ा सकता हूँ?

* veCAKE staking position में अधिक CAKE जोड़ें
* अपनी veCAKE staking position की duration extend या renew करें

सरल शब्दों में:

**अधिक CAKE stake करें, अधिक समय के लिए stake करें**

[bCAKE boost multipliers की गणना कैसे होती है, इसके बारे में अधिक जानें](faq.md#how-are-the-bcake-multipliers-calculated)।

### अतिरिक्त boosted CAKE rewards कहाँ से आते हैं?

**निश्चिंत रहें, bCAKE को संभव बनाने के लिए कोई अतिरिक्त emissions आवंटित नहीं की जाती हैं।**

veCAKE CAKE staking की तरह, bCAKE individual users की share को दूसरों के मुकाबले बढ़ाता है।

हालाँकि bCAKE deployment के बाद baseline APR घट सकता है, Chefs का मानना है कि यह एक अच्छा tradeoff है क्योंकि यह loyal CAKE प्रेमियों को उनकी farming yield boost करके लाभान्वित करता है, CAKE की अधिक मांग बनाता है और CAKE staking के लिए एक बेहतरीन incentive के रूप में काम करता है।

### मुझे प्राप्त multiplier कम क्यों है?&#x20;

bCAKE - farm booster इस प्रकार काम करता है कि यह आपकी veCAKE staking position और आपकी liquidity farming position दोनों का मूल्यांकन अन्य उपयोगकर्ताओं के मुकाबले करता है। सरल शब्दों में:

> यदि उपयोगकर्ता farm में अधिक तरलता boost करना चाहते हैं, तो उन्हें pool में अधिक CAKE को अधिक लंबे समय के लिए lock करना होगा।

यह डिज़ाइन सुनिश्चित करता है कि लाभ केवल बड़े holders को नहीं, बल्कि किसी भी ऐसे उपयोगकर्ता को मिले जिसकी farming position की तुलना में CAKE staking position उल्लेखनीय हो।

Multiplier की गणना कैसे होती है, इसके बारे में अधिक जानें [यहाँ](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated)।

### केवल x संख्या की farms ही booster-available क्यों हैं?

चूँकि bCAKE में PancakeSwap के एक core उत्पाद, यानी liquidity farming को अपडेट करना शामिल है, Chefs launch के प्रति धीमे और अधिक स्थिर दृष्टिकोण अपनाना चाहते हैं।

इसलिए, प्रारंभिक product release phase में, कई parameters बहुत conservative हैं। जिसमें उन farms की संख्या शामिल है जिन्हें उपयोगकर्ता boost कर सकते हैं, कौन सी farm को boost कर सकते हैं, साथ ही boost multiplier प्राप्त करने की कठिनाई parameter।

**Chefs community feedback के आधार पर parameters समायोजित करेंगे।**

### **क्या bCAKE V3 audited है?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE को internal और external दोनों auditors द्वारा audit किया गया है।

Audit reports यहाँ देखें: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
