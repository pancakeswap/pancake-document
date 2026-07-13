---
hidden: true
---

# Limit Orders का उपयोग कैसे करें

## Limit Orders क्या है

एक limit order उपयोगकर्ताओं को निष्पादन के समय बाजार मूल्य पर निर्भर रहने के बजाय एक निर्दिष्ट मूल्य या बेहतर पर एसेट खरीदने या बेचने में सक्षम करने वाला एक टूल है। एक limit order में, जबकि मूल्य की गारंटी होती है, ऑर्डर का निष्पादित होना नहीं — limit orders केवल तभी निष्पादित होंगे जब मूल्य ऑर्डर की योग्यताओं को पूरा करता है।

## Limit order कैसे सेट करें

1. Swap पेज पर जाएं और "LIMIT" पर क्लिक करके limit order विकल्प चुनें, या इस लिंक का उपयोग करें: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. वे "From" और "To" टोकन चुनें जिनका आप व्यापार करना चाहते हैं। इस उदाहरण में हमने क्रमशः USDC और ETH चुना, जिसका अर्थ है कि हम USDC के साथ ETH खरीदना चाहते हैं।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. वह राशि दर्ज करें जिसका आप व्यापार करना चाहते हैं। ध्यान दें कि limit price वर्तमान बाजार मूल्य दिखाएगी जो फिर destination टोकन (ETH) की अनुमानित output राशि का अनुमान लगाएगी।
2. इच्छित limit price सेट करें। ट्रेड केवल तभी निष्पादित होंगे जब उपलब्ध बाजार मूल्य limit price से बेहतर या उसके बराबर होगी। destination token output राशि उसी के अनुसार अपडेट होगी।

नीचे दिए गए उदाहरण में, हम ETH खरीदना चाहते हैं जब कीमत $1,900 या बेहतर हो। प्राप्त ETH की मात्रा 0.037 ETH के बराबर या उससे अधिक होगी। इस राशि के बराबर या बेहतर bids ही ऑर्डर भरने के लिए योग्य होंगी। यह राशि gas costs और fees को ध्यान में रखती है।&#x20;

{% hint style="info" %}
महत्वपूर्ण नोट: चूंकि शुल्क output token राशि से भुगतान किए जाते हैं, limit price में gas और trading fees शामिल हैं और इसलिए उपयोगकर्ताओं को मूल्य सेट करते समय इसे ध्यान में रखना चाहिए। उदाहरण के लिए, एक बहुत छोटे ऑर्डर की gas fees ऑर्डर output का बहुत बड़ा प्रतिशत हो सकती है, जो एक वास्तविक limit price दर्शाती है जो spot market price के साथ प्रतिस्पर्धात्मक नहीं है।
{% endhint %}

3.  "Place order" दबाएं। अपने ऑर्डर विवरण दोबारा जांचें, अस्वीकरण स्वीकार करें और "Confirm order" दबाएं।

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. एक बार लेनदेन पूर्ण होने के बाद, आप ऑर्डर इतिहास अनुभाग में "Open orders" के अंतर्गत अपना ऑर्डर देख सकेंगे। \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. खुले ऑर्डर को ऑर्डर विस्तार करके और "Cancel Order" बटन पर क्लिक करके किसी भी समय रद्द किया जा सकता है।

ध्यान देने योग्य बातें:

* आपका ऑर्डर निष्पादित नहीं हो सकता यदि उपलब्ध बाजार मूल्य आपके द्वारा निर्धारित limit price से खराब हो।
* ट्रेड एक decentralized protocol पर आधारित हैं जो off-chain takers का उपयोग करता है जो ऑर्डर भरने के लिए प्रतिस्पर्धा करते हैं। ये takers एक शुल्क का अनुरोध करने के हकदार हैं, जिसे protocol winning taker के लिए output tokens से हटाता है।&#x20;
* Takers अपनी fees सेट करते समय आपके लेनदेन के लिए gas fees को ध्यान में रख सकते हैं, जिसके परिणामस्वरूप fee राशि में उतार-चढ़ाव हो सकता है।
* एक limit price निर्दिष्ट करते समय, उपयोगकर्ता UI में destination tokens की वह न्यूनतम मात्रा देखेंगे जो वे ऑर्डर भरने पर प्राप्त करेंगे। इस राशि के बराबर या बेहतर bids करने वाले takers ही ऑर्डर भरने के लिए योग्य होंगे। यह राशि gas costs और trading fees को ध्यान में रखती है।
