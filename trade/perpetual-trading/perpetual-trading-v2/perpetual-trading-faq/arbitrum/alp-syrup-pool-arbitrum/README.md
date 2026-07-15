# ALP Syrup Pool (Arbitrum)

ALP एक ऐसा टोकन है जो PancakeSwap Perpetuals V2 पर तरलता को संचालित करता है। उपयोगकर्ता USDC, USDT, DAI, ETH और BTC जैसे संपार्श्विक टोकन का उपयोग करके ALP मिंट/खरीद करते हैं। ये टोकन ApolloX द्वारा संचालित PancakeSwap Perpetuals ट्रेड इंजन को तरलता प्रदान करते हैं। ALP टोकन **वॉलेट के बीच ट्रांसफर नहीं किए जा सकते** और केवल **ALP contract के माध्यम से मिंट/बेचे जा सकते हैं और ALP pool में स्टेक किए जा सकते हैं**।

### चरण-दर-चरण गाइड

#### ALP खरीदना/मिंट करना

1. [PancakeSwap ALP Pool (V2)](https://perp.pancakeswap.finance/en/ALP) पेज तक पहुंचने के लिए क्लिक करें और अपना वॉलेट कनेक्ट करें
2. अपना वॉलेट कनेक्ट करने के बाद, **Buy ALP** पर क्लिक करें। आप ALP खरीदने के लिए किसी भी ALP pool एसेट का उपयोग कर सकते हैं।
3. जानकारी की पुष्टि करने के बाद, लेनदेन पूर्ण करने के लिए **Buy ALP** पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Buy%20ALP%20Module.png" alt=""><figcaption></figcaption></figure>

**ALP Staking (Arbitrum)**

1. Pancake ALP Dashboard Page पर **Stake Now** पर क्लिक करें, या [यहां](https://pancakeswap.finance/pools?chain=arb) क्लिक करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/png%20%284%29.png" alt=""><figcaption></figcaption></figure>

2. CAKE-ALP syrup pool चुनें
3. ALP **Enable** करें और **Stake** पर क्लिक करें
4. स्टेक करने के लिए ALP की मात्रा चुनें और **confirm** पर क्लिक करें

**ALP बेचना**

1. &#x20;ALP Pool (V2) पेज तक पहुंचने के लिए क्लिक करें और अपना वॉलेट कनेक्ट करें
2. अपना वॉलेट कनेक्ट करने के बाद, **Sell ALP** पर क्लिक करें।

ALP बेचने की शर्तें:

* &#x20;उपयोगकर्ता खरीद के समय से 48 घंटे बाद ALP बेच सकते हैं
* &#x20;बेचे जा सकने वाले ALP टोकन की मात्रा: min\[(तरलता पूल का मूल्य - उपयोगकर्ता की पोजीशनों का मूल्य)\*50%]/ALP Market Price। उदाहरण के लिए, तरलता पूल का मूल्य 10,000,000 USDT है, उपयोगकर्ता की पोजीशन का मूल्य 5,000,000 USDT है और ALP Market Price 2 USDT है, ALP उपयोगकर्ता द्वारा बेची जा सकने वाली अधिकतम मात्रा 1,250,000 है।&#x20;
* साथ ही, उपयोगकर्ताओं द्वारा अपने ALP टोकन बेचने के बाद प्राप्त होने वाली एसेट की मात्रा ALP तरलता पूल से अधिक नहीं हो सकती। उदाहरण के लिए, यदि तरलता पूल में केवल 1000 USDT है, तो उपयोगकर्ताओं को प्राप्त USDT की अधिकतम मात्रा 1000 USDT होगी और शेष ALP को अन्य क्रिप्टोकरेंसी के लिए बेचा जा सकता है।
