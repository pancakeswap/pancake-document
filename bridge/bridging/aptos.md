---
description: EVM चेन और Aptos के बीच CAKE Bridge करें
---

# Bridge कैसे करें - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
निम्नलिखित गाइड में EVM चेन के उदाहरण के रूप में BNB Chain का उपयोग किया गया है। यही प्रक्रिया Ethereum पर भी लागू होती है।
{% endhint %}

## BNB Smart Chain से Aptos पर CAKE Bridge करें

1 - सुनिश्चित करें कि आपका वॉलेट BNB Smart Chain और Aptos Mainnet दोनों को सपोर्ट करता हो। या आपके ब्राउज़र में दोनों वॉलेट इंस्टॉल हों।

फिर [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/) खोलें।

2 - पहले, हमें अपना BNB Smart Chain वॉलेट कनेक्ट करना होगा।

"Connect" पर क्लिक करें और "EVM" सेक्शन के अंतर्गत अपना पसंदीदा वॉलेट चुनें। फिर अपने वॉलेट पॉपअप में पुष्टि करें और अनुमति दें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - फिर, हमें अपना Aptos वॉलेट कनेक्ट करना होगा।

वॉलेट कनेक्ट मोडल में, "Aptos" सेक्शन के अंतर्गत अपना पसंदीदा वॉलेट चुनें। फिर अपने वॉलेट पॉपअप में पुष्टि करें और अनुमति दें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - ऊपरी टोकन चयन फ़ील्ड में "v" पर क्लिक करें और "CAKE" चुनें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - वह CAKE की संख्या दर्ज करें जिसे आप Aptos पर Bridge करना चाहते हैं।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - यदि आपका Aptos वॉलेट नया बना है और उसमें कोई APT (Aptos Coin) बैलेंस नहीं है। हम सुझाव देते हैं कि "gas on destination" विकल्प को उसके डिफ़ॉल्ट पर रखें। Bridge आपके वॉलेट में थोड़ी मात्रा में APT जमा करेगा — यह न केवल Aptos पर आपकी यात्रा शुरू करने में मदद करेगा, बल्कि Bridge किए गए CAKE को रजिस्टर और क्लेम करने के लिए आपको APT गैस की भी आवश्यकता होगी।

इस विकल्प को बदलने से Bridging विफल हो सकती है।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Bridging ट्रांजैक्शन शुरू करने के लिए "Transfer" पर क्लिक करें और वॉलेट कन्फर्मेशन पॉपअप के माध्यम से पुष्टि करें।

कृपया ध्यान दें कि आपके BNB Smart Chain वॉलेट और Aptos वॉलेट की स्थिति के आधार पर, आपको **एकाधिक** वॉलेट कन्फर्मेशन की आवश्यकता हो सकती है। उदाहरण के लिए, यदि आप पहली बार Aptos पर CAKE Bridge कर रहे हैं, तो आपको:

* Bridging कॉन्ट्रैक्ट पर CAKE खर्च की अनुमति देनी होगी (आपके BNB Smart Chain वॉलेट से)
* CAKE रजिस्टर करना होगा (आपके Aptos वॉलेट से)

अधिक जानकारी के लिए कृपया [यह विवरण](aptos.md#bridging-cake-to-aptos-for-the-first-time) देखें।

8 - आराम से प्रतीक्षा करें। इसमें केवल कुछ मिनट लगने चाहिए। Bridging पूरी होने के बाद, CAKE आपके Aptos वॉलेट में जमा हो जाएगा। आप प्रोग्रेस बार से प्रगति ट्रैक कर सकते हैं।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## पहली बार Aptos पर CAKE Bridge करना

Aptos वॉलेट पर CAKE Bridge करने के लिए रजिस्ट्रेशन और क्लेम ट्रांजैक्शन की आवश्यकता होती है। यह उपयोगकर्ता सुरक्षा बढ़ाने के लिए किया जाता है और Aptos के लिए विशिष्ट है।

### **यदि आपके वॉलेट में पहले से APT (Aptos Coin) है:**

यदि आपके Aptos वॉलेट में CAKE अभी तक रजिस्टर नहीं है, तो आपसे उसे रजिस्टर करने के लिए कहा जाएगा। इस स्थिति में कोई अतिरिक्त क्लेम ट्रांजैक्शन की आवश्यकता नहीं है।

### **यदि आपके वॉलेट में APT (Aptos Coin) नहीं है:**

Bridge ट्रांजैक्शन पूरी होने के बाद, आपको अपना CAKE मैन्युअल रूप से क्लेम करना होगा। क्लेम करने के लिए गैस शुल्क को कवर करने हेतु, आपके स्रोत वॉलेट से आपके Aptos वॉलेट में APT टोकन भेजे जाएंगे।

ये रजिस्ट्रेशन और क्लेम चरण केवल पहली बार Aptos पर किसी टोकन के साथ इंटरैक्ट करने पर लागू होते हैं। उसी टोकन के बाद के ट्रांसफर में इन चरणों की आवश्यकता नहीं होगी।

पहली बार Aptos पर CAKE Bridge करने से पहले, सुनिश्चित करें कि आपके Aptos पते पर गैस शुल्क के लिए पर्याप्त APT हो। अधिक जानकारी के लिए, Aptos का यह विवरण देखें: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Aptos से BNB Smart Chain पर CAKE Bridge करें

1 - सुनिश्चित करें कि आपका वॉलेट BNB Smart Chain और Aptos Mainnet दोनों को सपोर्ट करता हो। या आपके ब्राउज़र में दोनों वॉलेट इंस्टॉल हों।

फिर [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/) खोलें।

2 - पहले, हमें अपना BNB Smart Chain वॉलेट कनेक्ट करना होगा।

"Connect" पर क्लिक करें और "EVM" सेक्शन के अंतर्गत अपना पसंदीदा वॉलेट चुनें। फिर अपने वॉलेट पॉपअप में पुष्टि करें और अनुमति दें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - फिर, हमें अपना Aptos वॉलेट कनेक्ट करना होगा।

वॉलेट कनेक्ट मोडल में, "Aptos" सेक्शन के अंतर्गत अपना पसंदीदा वॉलेट चुनें। फिर अपने वॉलेट पॉपअप में पुष्टि करें और अनुमति दें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - ऊपरी टोकन चयन फ़ील्ड में "v" पर क्लिक करें और "CAKE" चुनें। फिर Bridging की दिशा पलटने के लिए पृष्ठ के बीच में दोहरे तीर बटन पर क्लिक करें।

कृपया सुनिश्चित करें कि ऊपरी फ़ील्ड में "Aptos" नेटवर्क हो।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - वह CAKE की संख्या दर्ज करें जिसे आप BNB Smart Chain पर Bridge करना चाहते हैं।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - यदि आपका BNB Smart Chain वॉलेट नया बना है और उसमें कोई BNB (गैस टोकन) बैलेंस नहीं है। हम सुझाव देते हैं कि "gas on destination" विकल्प को उसके डिफ़ॉल्ट पर रखें। Bridge आपके वॉलेट में थोड़ी मात्रा में BNB जमा करेगा। यह BNB Smart Chain पर आपकी यात्रा शुरू करने और जीवंत PancakeSwap इकोसिस्टम को एक्सप्लोर करने में मदद करेगा।

7 - "Transfer" पर क्लिक करें और अपने वॉलेट पॉपअप से ट्रांजैक्शन को अनुमति दें।

8 - आराम से प्रतीक्षा करें। इसमें केवल कुछ मिनट लगने चाहिए। Bridging पूरी होने के बाद, CAKE आपके BNB Smart Chain वॉलेट में जमा हो जाएगा। आप प्रोग्रेस बार से प्रगति ट्रैक कर सकते हैं।
