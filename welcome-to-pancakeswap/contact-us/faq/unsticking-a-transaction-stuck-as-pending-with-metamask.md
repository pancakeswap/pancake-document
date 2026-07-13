---
description: MetaMask में pending के रूप में अटके ट्रांजैक्शन को कैसे ठीक करें
---

# MetaMask पर अटके Pending ट्रांजैक्शन ठीक करना

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

यदि आपका ट्रांजैक्शन Metamask में pending पर अटका हुआ है और "Cancel" बटन काम नहीं कर रहा, तो आपको अपनी बैकलॉग साफ़ करने के लिए इस विधि का उपयोग करना पड़ सकता है।

यह विधि मूलतः अटके हुए ट्रांजैक्शन को एक और उच्च-प्राथमिकता ट्रांजैक्शन से अधिलेखित करके काम करती है।

### **1. कस्टमाइज़ ट्रांजैक्शन Nonce सक्षम करें**

1\. अपना MetaMask plugin खोलें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. ऊपर-दाईं ओर रंगीन वृत्त आइकन पर क्लिक करें और ड्रॉपडाउन मेनू से **Settings** पर क्लिक करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Settings मेनू में, **Advanced** चुनें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. नीचे स्क्रॉल करें जब तक **Advanced gas controls** दिखे। इसे ON करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Advanced settings में ही रहते हुए, नीचे स्क्रॉल करें जब तक **Customize transaction nonce** दिखे। इसे ON करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. अपना अटका हुआ ट्रांजैक्शन खोजें**

अब हम वह ट्रांजैक्शन खोजेंगे जो अटका हुआ है और "nonce" नोट करेंगे। यह एक प्रकार का पहचानकर्ता है, जिसे हम बाद में पुनः उपयोग करेंगे।

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. MetaMask के मुख्य पृष्ठ पर वापस जाएँ। "Assets" टैब में, अपने अटके हुए ट्रांजैक्शन का टोकन प्रकार खोजें (इस मामले में, CAKE)।

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. टोकन के मेनू में, Queue क्षेत्र में अपना **Pending** ट्रांजैक्शन खोजें। अधिक जानकारी के लिए अपने ट्रांजैक्शन पर क्लिक करें।

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. **Nonce** प्रविष्टि देखें और इस नंबर को नोट करें।

### **3. अटके हुए ट्रांजैक्शन को अधिलेखित करें**

अब हम अटके हुए ट्रांजैक्शन को बदलने के लिए एक नया ट्रांजैक्शन बनाएंगे। हम Nonce नंबर को कस्टमाइज़ करेंगे ताकि वह वही हो जो आपने अभी नोट किया।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. अपने अटके हुए ट्रांजैक्शन को बदलने के लिए एक नया ट्रांजैक्शन बनाएँ। इस बार **Transaction Fee** बढ़ाएँ। यहाँ हमने इसे 9 से 20 कर दिया है। इससे आपका ट्रांजैक्शन किसी block में जुड़ने की अधिक संभावना होगी।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. पुष्टि पृष्ठ पर, सुनिश्चित करें कि आपका Gas Price अब नई, अधिक राशि पर है।

10\. **CUSTOM NONCE** प्रविष्टि ढूँढें और nonce को वह नंबर बदलें जो आपने चरण 7 में नोट किया था। अब Confirm पर क्लिक करें।

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. आपका नया ट्रांजैक्शन अब किसी block में स्वीकार होना चाहिए। जाँचने के लिए, MetaMask खोलें और **Activity** टैब पर क्लिक करें।

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. आपका पूर्ण ट्रांजैक्शन आपकी Activity सूची के शीर्ष पर दिखना चाहिए। यदि अभी भी नारंगी रंग में "Pending" लिख रहा है तो थोड़ा और प्रतीक्षा करें, या और अधिक ट्रांजैक्शन शुल्क (gas price) के साथ प्रक्रिया पुनः आज़माएँ।

चूँकि कोई भी वॉलेट एक ही nonce के दो ट्रांजैक्शन नहीं बना सकता, यदि आपका प्रतिस्थापन ट्रांजैक्शन सफल होता है, तो आपका अटका हुआ ट्रांजैक्शन स्वतः रद्द हो जाएगा।<br>
