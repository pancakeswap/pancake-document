---
hidden: true
---

# Wormhole Bridge गाइड

### अस्वीकरण

Wormhole Bridge का उपयोग शुरू करने से पहले इस गाइड को पढ़ना आवश्यक है। यह गाइड Bridge का उपयोग चरण-दर-चरण तरीके से समझाती है, साथ ही कुछ उपयोगी सुविधाओं को भी प्रदर्शित करती है जो यह डिफ़ॉल्ट रूप से सपोर्ट करता है, जैसे ट्रांजैक्शन खोज और ट्रांजैक्शन रिज्यूम। यह गाइड समस्या निवारण के लिए कदम भी बताती है।

### Bridge करना

<figure><img src="https://lh7-us.googleusercontent.com/ZnR2zSNBpjyrzAs_JVlYdKCMDVYmOw4AVdJj_VIk0dmkvqTNxAC1ror2bEQlmSLeVGNV-PwhQSZdyquv-nCBPsHLjACy6LQsyM7M98dFrT9xKnZqC0aWYgUj0fjwC5pbZ9g1UwLalAU6DV-ORgPs-UY" alt=""><figcaption></figcaption></figure>

1. **PancakeSwap Wormhole Bridge पर जाएं -** [**https://bridge.pancakeswap.finance/wormhole**](https://bridge.pancakeswap.finance/wormhole)
2. **स्रोत चेन वॉलेट कनेक्ट करें** - पहला कदम वॉलेट कनेक्ट करना है। विजेट का उपयोग करते समय यह आवश्यक नहीं है कि आपका वॉलेट उस नेटवर्क पर प्रीसेट हो जिससे आप Bridge करना चाहते हैं। Wormhole आपके द्वारा चुने गए नेटवर्क के आधार पर स्वचालित रूप से सही नेटवर्क सेट करेगा। EVM चेन के लिए केवल Metamask समर्थित है।
3. **स्रोत चेन नेटवर्क चुनें** - PancakeSwap वर्तमान में Wormhole Bridge के साथ 4 नेटवर्क सपोर्ट करता है (Ethereum, Binance Smart Chain, Arbitrum और Base)
4. **स्रोत चेन की संपत्ति चुनें** - वह टोकन चुनें जिसे आप Bridge करना चाहते हैं।
5. **चरण 4, 5 और 6 के लिए** - गंतव्य चेन के साथ चरण 1, 2 और 3 दोहराएं
6. Bridge राशि दर्ज करें - Bridge राशि दर्ज करें और ट्रांजैक्शन को अनुमोदित करने के लिए आगे बढ़ें। रूट और Bridge इस प्रकार दिखाया जाएगा:

<figure><img src="https://lh7-us.googleusercontent.com/k6VhFctTcH__ojn3fMScEUUONGP_uPHk-s8OvVonboim7Cm37xCQhNiReTpUuo90_c81jg51pHVKsxhok50I6dwHWjBGZgB-yaIksikYP0aQB7uUaI1Wm6wK9uoYdZdygkViWnXWZcGnsBrPnivbij0" alt="" width="563"><figcaption></figcaption></figure>

7. अनुमोदन और ट्रांजैक्शन भेजने के बाद, एक ट्रांजैक्शन स्थिति पृष्ठ दिखाई देगा:

<figure><img src="https://lh7-us.googleusercontent.com/RpERMKVOpXOJn56_-awggVO63Pl_KkkvQBzrwlD3jdEssKk7H6gznb7Np8ampHm3quG3doPGReqKFMyU1Fa4b0nlxjmSiZgSlY1WfEEAzbM_PcpZVRtESmXWol50wku4SE5oT8MgjfIwdoj8-rf-IBE" alt="" width="563"><figcaption></figcaption></figure>

Bridge प्रक्रिया के तीन चरण होते हैं। इन चरणों में कुछ समय लग सकता है और आमतौर पर स्रोत चेन ट्रांजैक्शन पर एक निश्चित संख्या में ब्लॉक कन्फर्मेशन की आवश्यकता होती है। एक बार यह पुष्टि सीमा पूरी हो जाने पर, Wormhole यह पुष्टि करने वाला प्रमाण उत्पन्न करेगा कि ट्रांजैक्शन सफल रही। गंतव्य चेन पर Bridge की गई संपत्ति क्लेम करने के लिए यह प्रमाण आवश्यक है।

8. सत्यापन पूरा होने के बाद, आप दिखाए गए क्लेम बटन पर क्लिक करके अपनी Bridge की गई संपत्ति क्लेम कर सकते हैं:

<figure><img src="https://lh7-us.googleusercontent.com/1OQVN7yTv2LcyZVpuwdZx4xxHsWFkGoSmfNSDDwJDSib47EVxmY-c_mD5EcfVGyb72KNdtZ-BC3CH_cWZtXNXVflFV8PP_577nIb4dG_Z1_O3rdoXETRWORZmgn4eUKyGAdmavmdzzA6YRA3aVA8_R8" alt="" width="563"><figcaption></figcaption></figure>
