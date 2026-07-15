---
description: veCAKE Staking और IFO Allocations
hidden: true
---

# iCAKE

### **नया iCAKE क्या है?**

veCAKE में transition के बाद, नया iCAKE veCAKE balance पर आधारित होगा।

* पुराने iCAKE की तरह, यह PancakeSwap IFO public sales में अधिकतम CAKE commit सीमा निर्धारित करता है। उदाहरण के लिए, यदि आपके पास 200 iCAKE है, तो आप IFO public sales में 200 CAKE commit कर सकते हैं।
* नया iCAKE number प्रत्येक IFO के अंत में veCAKE balance का उपयोग करके गणना किया जाता है। इसलिए, प्रत्येक IFO के लिए आपके अलग-अलग iCAKE numbers होंगे।
* चूँकि veCAKE balance आपके remaining lock time के साथ धीरे-धीरे घटता है, इसलिए भविष्य के IFOs में आपका iCAKE आपके veCAKE balance के साथ घटेगा। अपना iCAKE number बनाए रखने के लिए, stakings में अधिक CAKE जोड़ें, या अपना lock renew/extend करें।

**iCAKE कोई नया token नहीं है, यह PancakeSwap IFO प्रणाली द्वारा उपयोग की जाने वाली एक संख्यात्मक metric है।**

### iCAKE की गणना कैसे होती है?

आपके पास iCAKE की संख्या प्रत्येक IFO के अंत में veCAKE balance पर आधारित होती है, एक पूर्वनिर्धारित ratio से गुणा करके।

veCAKE एक dynamically calculated मूल्य है जो इस पर निर्भर करता है कि आप कितना CAKE lock करते हैं और lock में कितना समय बचा है। veCAKE की गणना कैसे होती है, इसके बारे में अधिक जानने के लिए, [यहाँ](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef) देखें।

veCAKE balance के ऊपर एक अतिरिक्त ratio लागू किया जाता है, जिसे Kitchen प्रत्येक IFO के लिए समायोजित करता है। उदाहरण के लिए, यदि ratio 2x है, और अगले IFO के अंत में आपके पास 1 veCAKE है, तो आप 2 CAKE तक commit कर सकते हैं।

उदाहरण:

* आपने 100 CAKE को 2 वर्षों के लिए lock किया।
  * आपका remaining lock time है: `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (सेकंड)
  * अधिकतम lock time है: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (सेकंड)
  * वर्तमान क्षण में, आपके पास है: `100 * (62899200 / 126403199) ~= 49.76` veCAKE
* अगला IFO scheduled है; इसकी end time ठीक 1 सप्ताह बाद है, जो वर्तमान क्षण से `604800` सेकंड बाद है।
  * उस समय, आपका remaining lock time होगा: `62899200 - 604800 = 62294400` (सेकंड)
  * उस समय, आपके पास होगा: `100 * (62294400 / 126403199) ~= 49.28` veCAKE
* इस IFO के लिए, ratio `3x` निर्धारित है।
* इसलिए, इस IFO के लिए, आपके पास है: `49.28 * 3 = 147.84` iCAKE, जिसका अर्थ है कि आप public sale में 147.84 CAKE तक commit कर सकते हैं।

### मेरे पास iCAKE की संख्या कैसे जाँचें?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

आप IFO पेज पर [यहाँ](https://pancakeswap.finance/ifo) अपने iCAKE की संख्या जाँच सकते हैं।

कृपया ध्यान रखें कि जब कोई upcoming IFO नहीं है, तो आपका iCAKE real-time veCAKE balance का उपयोग करके गणना किया जाएगा, जो प्रति सेकंड धीरे-धीरे घटता है।

जब कोई upcoming IFO हो, तो आपका iCAKE snapshot time पर veCAKE balance का उपयोग करके गणना किया जाएगा, जो IFO का अंत है। IFO समाप्त होने तक आपका iCAKE घटेगा या बदलेगा नहीं।

### **मैं अपने iCAKE की संख्या कैसे बढ़ाऊँ?**

आप कभी भी निम्नलिखित तरीकों से iCAKE की संख्या बढ़ा सकते हैं:

* अपनी veCAKE staking position में अधिक CAKE जोड़ें।
* अपनी veCAKE staking position extend करें।

[CAKE Staking Page](https://pancakeswap.finance/cake-staking) पर

### iCAKE गणना में "Ratio" क्या है?

Ratio iCAKE की गणना करते समय veCAKE balance के ऊपर लागू एक अतिरिक्त control factor है।

उदाहरण के लिए, यदि ratio 2x है, और अगले IFO के अंत में आपके पास 1 veCAKE है, तो आप 2 CAKE तक commit कर सकते हैं।

प्रत्येक IFO के बीच, kitchen विभिन्न metrics के आधार पर "Ratio" को अनुकूलित करेगा। यह समायोजन सभी social channels पर प्रकाशित किया जाएगा।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

आप [IFO page](https://pancakeswap.finance/ifo) पर जाकर iCAKE गणना के लिए वर्तमान "Ratio" number जाँच सकते हैं।
