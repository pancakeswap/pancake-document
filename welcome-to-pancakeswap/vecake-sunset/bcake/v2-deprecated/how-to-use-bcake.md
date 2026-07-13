# bCAKE का उपयोग कैसे करें?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-use-bCAKE.png)

iCAKE और vCAKE की तरह, bCAKE भी उन उपयोगकर्ताओं के लिए डिज़ाइन किया गया लाभ है जो fixed-term CAKE staking pool में अपना CAKE lock करते हैं। Boost multiplier की गणना इस आधार पर की जाती है कि आप कितना CAKE stake करते हैं, कितने समय के लिए stake करते हैं, और साथ ही उस farm में आप कितने LP tokens stake कर रहे हैं जिसे आप boost करना चाहते हैं।

## तैयारी

### Fixed-term CAKE staking position शुरू करें

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-no-cake-locked.png)

यदि आपने CAKE staking pool में कोई CAKE lock नहीं किया है, तो "Go to Pool" पर क्लिक करें और fixed-term staking position शुरू करने के निर्देशों का पालन करें।

Fixed-term CAKE staking कैसे करें, इसके बारे में अधिक जानने के लिए, [यहाँ](../../../../archive/legacy-products/new-cake-pool/#fixed-term-staking) पढ़ें।

### Farm boosters enable करें

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-enable-booster.png)

Farm boosters enable करने के लिए, आपको एक बार का setup process पूरा करना होगा। आगे बढ़ने के लिए, बस "Enable" पर क्लिक करें और अपने वॉलेट से transaction confirm करें।

### अपनी stakings Migrate करें

{% hint style="info" %}
यदि आप उस farm में staking नहीं कर रहे हैं जिसके लिए आप bCAKE activate करना चाहते हैं, तो आप इस चरण को छोड़ सकते हैं और farm में LP tokens stake करके शुरू कर सकते हैं।
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-staking-migration-needed.png)

यदि आप उस farm में पहले से staking कर रहे हैं जिसके लिए आप farm booster activate करना चाहते हैं, तो एक बार की staking migration भी आवश्यक है।

"Migrate" पर क्लिक करें और migrations पूरी करने के लिए step-by-step guide का पालन करें। आपके CAKE rewards स्वचालित रूप से harvest होकर आपके वॉलेट में भेज दिए जाएंगे।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-migration-inprogress.png)

## Boosters Activate करें

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-activation%20%281%29.png)

तैयार होने पर, आपको उस farm के लिए उपलब्ध boost multiplier और boosted APR दिखेगा जिसमें आप वर्तमान में staking कर रहे हैं। bCAKE multiplier की गणना कैसे होती है, इसके बारे में अधिक जानने के लिए, [यहाँ](../faq.md#how-are-the-bcake-multipliers-calculated) पढ़ें।

Boost activate करने के लिए, "Boost" बटन पर क्लिक करें और अपने वॉलेट से transaction confirm करें।

{% hint style="info" %}
कृपया ध्यान दें कि farms या CAKE staking pool में कोई भी user action, farms और CAKE staking pool से नवीनतम data और statistics के आधार पर आपके boost multiplier को स्वचालित रूप से अपडेट करेगा।

अधिक जानें [यहाँ](../faq.md#why-do-my-multipliers-change-even-after-activation)।
{% endhint %}

### ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-farm-number-limit.png)

एक साथ boost होने वाली farms की संख्या की एक सीमा है। remaining boosters की संख्या जाँचने के लिए, ऊपर के panel को देखें।

अन्य farms पर boosters activate करने के लिए आपको एक सक्रिय booster unset करना होगा।

## Boosters Unset करें

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-unset%20%281%29.png)

Farm booster unset करने के लिए, बस "Unset" बटन पर क्लिक करें और अपने वॉलेट से transaction confirm करें।

कृपया ध्यान दें कि unset करने पर, CAKE rewards farm booster contract में harvest होंगे और अगली harvest, deposit या withdrawal पर स्वचालित रूप से आपके वॉलेट में भेजे जाएंगे। अधिक जानें [यहाँ](../faq.md#where-are-my-cake-rewards-after-activating-or-unsetting-the-booster)।
