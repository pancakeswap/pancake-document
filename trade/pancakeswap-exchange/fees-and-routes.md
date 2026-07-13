# Fees and Routes

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

Exchange V3 में, डिफ़ॉल्ट रूप से, PancakeSwap Smart Router, V3, V2, StableSwap (BNB Chain), और AMM तथा मार्केट मेकर्स (BNB Chain और Ethereum) से तरलता का उपयोग करके ट्रेड निष्पादित करता है और ट्रेडर्स के लिए सर्वोत्तम मूल्य खोजता है।

हालाँकि, उपयोगकर्ता हमेशा यह चुनकर अपना व्यापार अनुकूलित कर सकते हैं कि राउटर किन तरलता स्रोतों का उपयोग करे, और multihops तथा split routing को सक्षम या अक्षम कर सकते हैं।

### **वर्तमान में लागू शुल्क दर और शुल्क राशि जाँचें**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

आपके वर्तमान स्वैप पर कितना ट्रेडिंग शुल्क लगेगा यह जाँचने के लिए, swap detail सेक्शन में "Fee" सेक्शन देखें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

यह जाँचने के लिए कि आपका व्यापार किस प्रकार के पूल और शुल्क स्तर से रूट किया जा रहा है, "Route" सेक्शन देखें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

अधिक विवरण जानने के लिए, पूर्ण ट्रेडिंग रूट प्रदर्शन देखने के लिए आवर्धक आइकन पर क्लिक करें।



### **तरलता स्रोत अनुकूलित करें**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

"Customize Routing" इंटरफ़ेस के शीर्ष पर, आप चुन सकते हैं कि आपके व्यापार को रूट करते समय राउटर किस तरलता स्रोत का उपयोग करे। इस इंटरफ़ेस को खोलने के लिए आप:

* ट्रेडिंग रूट प्रदर्शन के नीचे "Customize Routing" पर क्लिक कर सकते हैं।
* swap इंटरफ़ेस में cog आइकन पर क्लिक करें, और फिर नीचे "Customize Routing" पर क्लिक करें।

डिफ़ॉल्ट रूप से, सभी तरलता स्रोत सक्षम होते हैं और Smart Router PancakeSwap के भीतर उपलब्ध सभी तरलता का पूरा लाभ उठाता है।

कृपया ध्यान दें कि राउटर AMM तरलता पूलों और MM मार्केट मेकर्स के बीच ट्रेड रूट नहीं करेगा। जब आपका व्यापार MM मार्केट मेकर्स द्वारा निष्पादित किया जाता है, तो वह किसी भी AMM तरलता पूल से नहीं गुजरेगा।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

ऊपरी दाएँ कोने में "Reset" बटन पर क्लिक करके आप कॉन्फ़िगरेशन को डिफ़ॉल्ट पर रीसेट कर सकते हैं।



### **रूटिंग प्राथमिकताएँ अनुकूलित करें**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

"Customize Routing" इंटरफ़ेस के नीचे, आप multihops और split routing को सक्षम या अक्षम करके अपनी रूटिंग प्राथमिकताएँ अनुकूलित कर सकते हैं।

Multihops टोकनों को सर्वोत्तम मूल्य प्राप्त करने के लिए कई तरलता पूलों के बीच कई hops के माध्यम से स्वैप करने की अनुमति देता है। इसे बंद करने पर ट्रेड सीधे स्वैप तक सीमित हो जाएंगे, जिससे अधिक स्लिपेज या यहाँ तक कि धन की हानि भी हो सकती है।

Split routing टोकन स्वैप को सर्वोत्तम मूल्य प्राप्त करने के लिए कई रूटों में विभाजित करने में सक्षम बनाता है। इसे बंद करने पर ट्रेड एकल रूट से निष्पादित होने तक सीमित हो जाएंगे, जिससे कम दक्षता या अधिक स्लिपेज हो सकती है।

{% hint style="warning" %}
जब अनुकूलित ट्रेडिंग कॉन्फ़िगरेशन के कारण आपका व्यापार निष्पादित नहीं हो पाता, तो एक चेतावनी दिखाई देगी। आप "Check your settings" पर क्लिक करके जल्दी से "Customize Routing" इंटरफ़ेस खोल सकते हैं। या अपने कॉन्फ़िगरेशन को तुरंत डिफ़ॉल्ट पर वापस लाने के लिए "Reset to default" चुनें।
{% endhint %}
