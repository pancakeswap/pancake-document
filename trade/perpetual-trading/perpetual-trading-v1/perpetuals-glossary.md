# Perpetuals V1 शब्दावली

**यहां आपको फ्यूचर्स ट्रेडिंग से संबंधित सभी शब्दों की परिभाषाएं मिलेंगी**

### **Perpetual Trading**

&#x20;Perpetuals, perpetual swaps, या perps एक विशेष प्रकार के फ्यूचर्स कॉन्ट्रैक्ट होते हैं जिनकी कोई समाप्ति तिथि नहीं होती।



### **लीवरेज**

लीवरेज एक ट्रेडिंग तंत्र है। ट्रेडर इसका उपयोग बाजार में अपने एक्सपोज़र को बढ़ाने के लिए कर सकते हैं, जिससे उन्हें निवेश की पूरी राशि से कम भुगतान करना पड़ता है। सरल शब्दों में, आप अपने निवेश को लीवरेज करने के लिए पैसे उधार लेते हैं।

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **मार्जिन**

यह वह गारंटी है जो आप अपनी लीवरेज्ड पोजीशन के लिए देते हैं। इसके उपयोग के दो मोड हैं:

* Cross Margin Mode: एक ही मार्जिन एसेट के अंतर्गत सभी cross पोजीशन एक ही एसेट cross मार्जिन शेष साझा करती हैं। लिक्विडेशन की स्थिति में, आपकी एसेट का पूर्ण मार्जिन शेष और एसेट के अंतर्गत कोई भी शेष खुली पोजीशन ज़ब्त की जा सकती है।
* Isolated Margin Mode: प्रत्येक को आवंटित मार्जिन की मात्रा को सीमित करके व्यक्तिगत पोजीशन पर अपने जोखिम का प्रबंधन करें। यदि किसी पोजीशन का मार्जिन अनुपात 100% तक पहुंच जाता है, तो पोजीशन का लिक्विडेशन हो जाएगा। इस मोड का उपयोग करके पोजीशन में मार्जिन जोड़ा या हटाया जा सकता है।

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**मार्जिन अनुपात**: मार्जिन अनुपात = Maintenance Margin / Margin Balance। एक बार मार्जिन अनुपात 100% तक पहुंचने पर आपकी पोजीशन का लिक्विडेशन हो जाएगा।

**Maintenance Ratio**: आपकी खुली पोजीशन को बनाए रखने के लिए आवश्यक न्यूनतम मार्जिन शेष।

**Margin Balance** = Wallet Balance + Unrealized PNL। एक बार Margin Balance <= Maintenance Margin होने पर आपकी पोजीशन का लिक्विडेशन हो जाएगा।

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### एसेट:

**Deposit**: अपने फंड अपने Futures खाते में जमा करें

**Withdraw**: अपने फंड अपने Futures खाते से अपने वॉलेट में निकालें

**Balance**: Wallet Balance = Total Net Transfer + Total Realized Profit + Total Net Funding Fee - Total Commission।

**Unrealized PNL**: Mark Price के आधार पर गणना की गई इस पोजीशन पर अप्राप्त लाभ और हानि, और इक्विटी प्रतिशत पर रिटर्न।

**मोड:**&#x20;

* Single Asset Mode: केवल प्रतीक की एकल मार्जिन एसेट का उपयोग करके USDⓈ-M Futures ट्रेडिंग का समर्थन करता है। एक ही मार्जिन एसेट पोजीशन का PNL ऑफसेट किया जा सकता है। Cross Margin Mode और Isolated Margin Mode दोनों का समर्थन करता है।
* Multi-Assets Mode: कई मार्जिन एसेट में USDⓈ-M Futures ट्रेडिंग। विभिन्न मार्जिन एसेट पोजीशन में PNL ऑफसेट किया जा सकता है। केवल Cross Margin Mode का समर्थन करता है।

{% hint style="info" %}
नोट: यदि USDⓈ-M Futures में खुली पोजीशन या खुले ऑर्डर हैं, तो Multi-Assets Mode सक्रिय नहीं किया जा सकता। Multi-Assets Mode केवल USDⓈ-M Futures पर लागू होता है। Multi-Assets Mode सक्रिय करने से पहले, कृपया Multi-Assets Mode का उपयोग करते समय USDⓈ-M Futures खाते के जोखिम को बेहतर ढंग से प्रबंधित करने के लिए विस्तार से गाइड पढ़ें।<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### ऑर्डर

**Buy/Long:** एक Long ऑर्डर खोलें। इस ऑर्डर में आप एक एसेट खरीदते हैं और कीमत बढ़ने पर बेचने का इंतजार करते हैं। "Buy" और "long" का परस्पर उपयोग किया जाता है।

**Sell/Short:** एक Short ऑर्डर खोलें। इस ऑर्डर में आप एक एसेट उधार लेते हैं, उसे बेचते हैं, और उम्मीद करते हैं कि कीमत कम होने पर उसे वापस खरीद सकेंगे। "Sell" और "short" का परस्पर उपयोग किया जाता है।

**Limit Order:** एक limit order एक विशिष्ट मूल्य या बेहतर पर खरीदने या बेचने का ऑर्डर है। Limit orders के निष्पादित होने की गारंटी नहीं होती।

**Market Order:** एक market order सर्वोत्तम उपलब्ध वर्तमान मूल्य पर खरीदने या बेचने का ऑर्डर है। यह ऑर्डर बुक पर पहले से रखे गए limit orders के विरुद्ध निष्पादित होता है। Market order देते समय, आप market taker के रूप में शुल्क देंगे।

**Stop Limit Order:** Stop-limit order को समझने का सबसे आसान तरीका इसे stop price और limit price में विभाजित करना है। Stop price केवल वह मूल्य है जो limit order को ट्रिगर करता है, और limit price उस limit order का मूल्य है जो ट्रिगर होता है। इसका मतलब है कि एक बार आपका stop price पहुंचने पर, आपका limit order तुरंत ऑर्डर बुक पर रखा जाएगा।

**Stop Market Order:** Stop-limit order की तरह, एक stop market order एक stop price को ट्रिगर के रूप में उपयोग करता है। हालांकि, जब stop price पहुंचता है, तो यह market order ट्रिगर करता है।

**Trailing Stop:** एक trailing stop एक ऑर्डर प्रकार है जो ट्रेड अनुकूल रूप से आगे बढ़ने पर लाभ लॉक करने या नुकसान सीमित करने के लिए डिज़ाइन किया गया है। Trailing stops केवल तभी आगे बढ़ते हैं जब कीमत अनुकूल रूप से आगे बढ़ती है। एक बार लाभ लॉक करने या नुकसान कम करने के लिए आगे बढ़ने के बाद, यह दूसरी दिशा में वापस नहीं जाता।

**Post Only:** Post-only Mode का मतलब है कि ट्रेडर केवल तभी ऑर्डर दे सकते हैं जब यह ऑर्डर बुक में Maker Order के रूप में पोस्ट होगा। एक ऑर्डर जो Taker Order के रूप में पोस्ट होगा उसे अस्वीकार कर दिया जाएगा। कोई Market Order नहीं दिए जा सकते और कोई ऑर्डर नहीं भरा जाएगा। Post-only मोड में Resting orders रद्द की जा सकती हैं।

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JsFdfrn7WFOjEcqfPaxerPjGSq1iIpxz6tcN_A839ASRF3B)

**Reduce Only:** Reduce-Only order केवल आपकी पोजीशन को कम करेगा, बढ़ाएगा नहीं।

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF निर्देश** आपको यह निर्दिष्ट करने की अनुमति देते हैं कि आपके ऑर्डर निष्पादित या समाप्त होने से पहले कितने समय तक सक्रिय रहेंगे। आप TIF निर्देशों के लिए इनमें से एक विकल्प चुन सकते हैं:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel): ऑर्डर तब तक सक्रिय रहेगा जब तक यह भरा या रद्द नहीं हो जाता।&#x20;
* **IOC** (Immediate Or Cancel): ऑर्डर तुरंत निष्पादित होगा (पूरी तरह या आंशिक रूप से)। यदि यह केवल आंशिक रूप से निष्पादित होता है, तो ऑर्डर का अधूरा हिस्सा रद्द कर दिया जाएगा।&#x20;
* **FOK** (Fill Or Kill): ऑर्डर तुरंत पूरी तरह भरा जाना चाहिए। यदि नहीं, तो यह बिल्कुल भी निष्पादित नहीं होगा।
