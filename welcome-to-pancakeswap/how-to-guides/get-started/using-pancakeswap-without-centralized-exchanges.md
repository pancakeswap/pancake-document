---
description: >-
  PancakeSwap का उपयोग शुरू करने के लिए आपको Binance, Coinbase, Kraken, Huobi, OKEx या
  किसी अन्य केंद्रीकृत एक्सचेंज पर अकाउंट की आवश्यकता नहीं है!
hidden: true
---

# केंद्रीकृत एक्सचेंज के बिना PancakeSwap का उपयोग

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-pancakeswap-without-cex-header.png)

PancakeSwap एक विकेंद्रीकृत एप्लिकेशन है। इसका मतलब है कि Binance या अन्य केंद्रीकृत प्लेटफ़ॉर्म के विपरीत, इसका उपयोग करने के लिए आपको अकाउंट रजिस्टर करने की आवश्यकता नहीं है... आपको बस एक क्रिप्टो वॉलेट चाहिए। तो केंद्रीकृत एक्सचेंज का उपयोग किए बिना PancakeSwap पर क्रिप्टो कैसे प्राप्त करें?

इस ट्यूटोरियल में, हम आपको "क्रॉस-चेन ब्रिज" का उपयोग करके अपनी एसेट को अपने BNB Smart Chain वॉलेट में ट्रांसफर करने और PancakeSwap का उपयोग शुरू करने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे।

### **अन्य ब्लॉकचेन से अपनी एसेट को BNB Smart Chain पर स्थानांतरित करें**

आप Ethereum या अन्य नेटवर्क से टोकन को BNB Smart Chain पर ट्रांसफर करने के लिए विभिन्न क्रॉस-चेन ब्रिज का उपयोग कर सकते हैं।

निम्नलिखित ट्यूटोरियल में, हम तीन अलग-अलग क्रॉस-चेन ब्रिज का उपयोग करके विभिन्न ब्लॉकचेन से USDT को BNB Smart Chain पर स्थानांतरित करने का प्रदर्शन करेंगे।

{% tabs %}
{% tab title="🥞🌉 Pancake Bridge (अनुशंसित)" %}
![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28168%29.png)

[**PancakeSwap Bridge**](http://bridge.pancakeswap.finance) — एक नेटिव एसेट क्रॉस-चेन ब्रिज, Stargate द्वारा संचालित।

यह ब्रिज आपको अपने स्टेबलकॉइन को BNB Chain पर आसानी से स्थानांतरित करने और जीवंत PancakeSwap समुदाय तथा व्यापक BNB इकोसिस्टम में भाग लेने की सुविधा देता है!

📖 [उपयोग करना सीखें](https://medium.com/pancakeswap/launching-pancakeswap-bridge-a-partnership-with-stargate-21c1c9f491a8)
{% endtab %}

{% tab title="AnySwap" %}
चलिए AnySwap का उपयोग करके Polygon (MATIC) ब्लॉकचेन से BSC पर USDT स्थानांतरित करने का प्रयास करते हैं।

1. अपने Polygon (MATIC) वॉलेट को USDT और गैस के लिए कुछ MATIC के साथ तैयार करें।
2. चूंकि AnySwap केवल MetaMask, OKEx Wallet और Coin98 Wallet को सपोर्ट करता है। यदि आप अन्य वॉलेट ऐप का उपयोग कर रहे हैं, तो हम अनुशंसा करते हैं कि आप अपना वॉलेट MetaMask में इम्पोर्ट करें।
3. [https://anyswap.exchange/#/router](https://anyswap.exchange/#/router) पर जाएं
4. अपना वॉलेट कनेक्ट करें और अपना नेटवर्क Polygon (MATIC) Mainnet पर स्विच करें।
5.  "From" के रूप में MATIC mainnet पर USDT और "To" के रूप में BSC mainnet पर USDT चुनें। फिर वह USDT राशि टाइप करें जो आप ट्रांसफर करना चाहते हैं।

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-055554AM-Google%20Chrome_AnySwap%20-%20Cross%20Chain%20Protocol.png" alt="" data-size="original">
6. अपने USDT को अनुमोदित करने के लिए "Approve USDT" पर क्लिक करें।
7. इसके अलावा यदि आप चाहते हैं कि AnySwap आपके USDT को किसी अन्य BSC पते पर जमा करे, तो कृपया "+ Send To" बटन का उपयोग करें।
8. "Swap" पर क्लिक करें और अपना अंतिम क्रॉस-चेन ट्रांजेक्शन पूरा करें।
9. नेटवर्क कितना व्यस्त है, इसके आधार पर पूरी प्रक्रिया में लगभग 10-30 मिनट लगेंगे।
10. पूरा होने के बाद। आपको अपने BSC वॉलेट में फंड मिल जाना चाहिए। अब आप BNB Smart Chain पर कुछ टोकन स्वैप करने के लिए PancakeSwap का उपयोग शुरू कर सकते हैं!
{% endtab %}

{% tab title="O3 Hub" %}
⚠️ **O3 Swap बीटा में है। कृपया अपने जोखिम पर व्यापार करें।**

चलिए ERC-20 ब्लॉकचेन से BNB Smart Chain पर USDT स्थानांतरित करने के लिए O3 Hub का उपयोग करने का प्रयास करते हैं।

1. अपने ERC-20 (Ethereum Mainnet) वॉलेट को USDT और गैस के लिए कुछ ETH के साथ तैयार करें।
2. चूंकि O3 Hub केवल MetaMask और O3 Wallet को सपोर्ट करता है। यदि आप अन्य वॉलेट ऐप का उपयोग कर रहे हैं, तो हम अनुशंसा करते हैं कि आप अपना वॉलेट MetaMask में इम्पोर्ट करें।
3. [https://o3swap.com/hub](https://o3swap.com/hub) पर जाएं
4.  ETH और BSC दोनों के लिए अपना MetaMask या O3 वॉलेट कनेक्ट करें। और MetaMask में अपना नेटवर्क Ethereum Mainnet पर स्विच करें।

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054852AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
5.  "You pay" के रूप में ERC-20 USDT और "You will receive" के रूप में BEP-20 USDT चुनें। फिर वह USDT राशि टाइप करें जो आप ट्रांसफर करना चाहते हैं।

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053358AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
6.  दोबारा जांचें कि "To" फ़ील्ड सही BNB Smart Chain वॉलेट पता दिखा रही है जो आपने कनेक्ट किया है।

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053441AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
7. सुनिश्चित करें कि सब कुछ सही है। "Swap" पर क्लिक करें।
8. अपने USDT को अनुमोदित करने और अंतिम क्रॉस-चेन ट्रांजेक्शन पूरा करने के लिए स्क्रीन पर दिए गए निर्देशों का पालन करें।
9.  नेटवर्क कितना व्यस्त है, इसके आधार पर पूरी प्रक्रिया में लगभग 10-30 मिनट लगेंगे। आप history टैब पर प्रगति को ट्रैक कर सकते हैं।

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054520AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
10. पूरा होने के बाद। आपको अपने BSC वॉलेट में फंड मिल जाना चाहिए। अब आप BNB Smart Chain पर कुछ टोकन स्वैप करने के लिए PancakeSwap का उपयोग शुरू कर सकते हैं!

इसके अलावा, आप O3 Swap की [यह उपयोगकर्ता गाइड](https://docs.o3swap.com/o3-swap-user-guide/hub#2.-hub-swap) देख सकते हैं।
{% endtab %}
{% endtabs %}
