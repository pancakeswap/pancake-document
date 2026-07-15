# 🔀 Crosschain Swaps

Crosschain Swaps उपयोगकर्ताओं को एक ही सुव्यवस्थित लेनदेन में चेन के बीच टोकन को सहजता से स्वैप करने की सुविधा देते हैं।

Crosschain swaps निम्नलिखित चेनों के बीच समर्थित हैं:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**लेनदेन बिजली की गति से होते हैं — आमतौर पर कुछ सेकंड से लेकर एक मिनट से कम समय में पूरे हो जाते हैं।**
{% endhint %}

***

### 🔍 यह कैसे काम करता है

1. उपयोगकर्ता From / To चेन और From / To टोकन चुनता है
2. PancakeSwap राउटर सबसे कुशल रूट की गणना करता है
3. स्रोत और गंतव्य चेनों पर PancakeSwap के तरलता पूलों (v2, v3, Infinity, StableSwaps) का उपयोग करके स्वैप निष्पादित किए जाते हैं
4. ब्रिजिंग हमारे भागीदार प्रोटोकॉल के माध्यम से संभाली जाती है: [Across](https://across.to/) (EVM <> EVM के लिए), [Relay](https://relay.link/bridge) (SOL <> EVM के लिए)

{% hint style="success" %}
**Crosschain swaps उन सभी टोकनों के लिए उपलब्ध हैं जिनके पास स्रोत और गंतव्य दोनों चेनों पर पर्याप्त तरलता है।**
{% endhint %}

***

### 💸 शुल्क

* **PancakeSwap Crosschain लेनदेन के लिए कोई शुल्क नहीं लेता।**
* शुल्क निम्नलिखित से बना होता है:
  1. **ट्रेडिंग शुल्क:** स्रोत और गंतव्य चेनों पर तरलता पूलों के भीतर स्वैप के लिए लागू होता है
  2. **Bridge Fee:** संपत्तियों की ब्रिजिंग के लिए relayers को भुगतान किया जाता है

***

### 🎯 Intents क्या हैं?

Intents उपयोगकर्ताओं को यह चिंता किए बिना अपना वांछित परिणाम परिभाषित करने देते हैं कि यह कैसे हासिल होगा।

Intent के उदाहरण:

* "Base पर 1 ETH को Arbitrum पर कम से कम 3000 USDC के लिए स्वैप करें"

Intents के बिना, उपयोगकर्ता को मैन्युअल रूप से:

* ETH को Arbitrum पर ब्रिज करना होगा
* सबसे अच्छे ETH → USDC मूल्य वाला DEX ढूँढना होगा

{% hint style="success" %}
**Intents के साथ — सिस्टम सब कुछ स्वतः संभाल लेता है।**
{% endhint %}

**इंटेंट-आधारित डिज़ाइन के लाभ:**

* सहज उपयोगकर्ता अनुभव
* तेज़ लेनदेन समय
* एक क्लिक में, एकल लेनदेन

***

### 🔐 ऑडिट

हमने क्रॉस-चेन सुरक्षा क्षेत्र के सम्मानित नामों के साथ कई ऑडिट राउंड किए हैं:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
