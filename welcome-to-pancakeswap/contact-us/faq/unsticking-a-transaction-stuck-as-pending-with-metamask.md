---
description: अपने MetaMask में अटके किसी भी पेंडिंग ट्रांज़ैक्शन को "अनस्टिक" कैसे करें
---

# MetaMask पर अटके पेंडिंग ट्रांज़ैक्शन ठीक करना

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

यदि आपका ट्रांज़ैक्शन Metamask में पेंडिंग पर अटका है, और “Cancel” बटन से कोई मदद नहीं मिल रही, तो अपना बैकलॉग साफ़ करने के लिए आपको इस तरीके का उपयोग करना पड़ सकता है।

यह तरीका मूल रूप से अटके हुए ट्रांज़ैक्शन को एक दूसरे, उच्च-प्राथमिकता वाले ट्रांज़ैक्शन से ओवरराइट करके काम करता है।

### **1. कस्टमाइज़्ड ट्रांज़ैक्शन नॉन्स सक्षम करें**

1\. अपना MetaMask प्लगइन खोलें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. ऊपर दाईं ओर रंगीन सर्कल आइकन पर क्लिक करें और ड्रॉपडाउन मेनू से **Settings** चुनें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Settings मेनू में, **Advanced** चुनें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. नीचे स्क्रॉल करें जब तक आपको **Advanced gas controls** न दिखे। इसे ON करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Advanced सेटिंग्स में ही, स्क्रॉल करते रहें जब तक आपको **Customize transaction nonce** न दिखे। इसे ON करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. अपना अटका हुआ ट्रांज़ैक्शन ढूँढें**

अब हम वह ट्रांज़ैक्शन ढूँढेंगे जो अटका हुआ है, और उसके “nonce” को नोट कर लेंगे। यह एक प्रकार का आइडेंटिफ़ायर है, जिसे हम बाद में दोबारा उपयोग करेंगे।

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMask के मुख्य पेज पर वापस जाएँ। “Assets” टैब में, अपने अटके हुए ट्रांज़ैक्शन का टोकन प्रकार ढूँढें (इस उदाहरण में, CAKE)।

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. टोकन के मेनू में, Queue क्षेत्र में अपना **Pending** ट्रांज़ैक्शन ढूँढें। अधिक विवरण के लिए अपने ट्रांज़ैक्शन पर क्लिक करें।

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. **Nonce** प्रविष्टि देखें, और इस संख्या को नोट कर लें।

### **3. अटके हुए ट्रांज़ैक्शन को ओवरराइट करें**

अब हम अटके हुए ट्रांज़ैक्शन को बदलने के लिए एक नया ट्रांज़ैक्शन बनाएँगे। हम Nonce संख्या को कस्टमाइज़ करेंगे, ताकि वह वही हो जो आपने अभी लिखी है।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. अपने अटके हुए ट्रांज़ैक्शन को बदलने के लिए एक नया ट्रांज़ैक्शन बनाएँ। इस बार, **Transaction Fee** बढ़ाएँ। यहाँ हमने इसे 9 से बढ़ाकर 20 कर दिया है। इससे आपके ट्रांज़ैक्शन के किसी ब्लॉक में जुड़ने की संभावना बढ़ जाएगी।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. कन्फ़र्मेशन पेज पर, सुनिश्चित करें कि आपका Gas Price अब आपकी नई, बढ़ी हुई राशि पर है।

11\. **CUSTOM NONCE** प्रविष्टि ढूँढें और nonce को चरण 8 में लिखी गई संख्या में बदलें। अब Confirm पर क्लिक करें।

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. आपका नया ट्रांज़ैक्शन अब किसी ब्लॉक में स्वीकार हो जाना चाहिए। जाँचने के लिए, MetaMask खोलें और **Activity** टैब पर क्लिक करें।

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. आपका पूरा हुआ ट्रांज़ैक्शन आपकी Activity सूची में सबसे ऊपर दिखना चाहिए। यदि वह अब भी नारंगी रंग में “Pending” दिखा रहा है, तो आपको थोड़ा और इंतज़ार करना होगा, या और अधिक ट्रांज़ैक्शन फीस (गैस प्राइस) के साथ यह प्रक्रिया दोबारा करनी होगी।

चूँकि कोई भी वॉलेट एक ही nonce के दो ट्रांज़ैक्शन नहीं बना सकता, इसलिए यदि आपका बनाया गया रिप्लेसमेंट ट्रांज़ैक्शन सफल हो जाता है, तो आपका अटका हुआ ट्रांज़ैक्शन रद्द हो जाएगा।<br>
