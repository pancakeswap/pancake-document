# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

CLAMM तरलता प्रदाताओं को अपनी पूँजी **विशिष्ट मूल्य सीमाओं** के भीतर आवंटित करने में सक्षम बनाता है। इससे होता है:

* **उच्च पूँजी दक्षता**: सक्रिय ट्रेडिंग मूल्यों पर अधिक तरलता।
* **गहरी तरलता**: Traders के लिए बेहतर निष्पादन।
* **सक्रिय LP प्रबंधन**: LPs को मूल्य बदलने पर पोजीशन समायोजित करनी होती है।
* out-of-range पोजीशन के लिए **अधिक impermanent loss** की संभावना।

{% hint style="info" %}
CLAMM constant product formula (X \* Y = K) पर काम करता है। प्रत्येक तरलता पोजीशन non-fungible है और NFT के रूप में प्रदर्शित होती है।
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM या "Bin Pool")

LBAMM **discrete price bins** लागू करता है, जिनमें से प्रत्येक एक विशिष्ट मूल्य स्तर पर तरलता रखता है। LBAMM **constant sum formula (X + Y = K)** का पालन करता है।



**प्रमुख विशेषताएँ:**

* एक bin के भीतर trades पर **0 मूल्य प्रभाव**।
* **Fungible तरलता** (प्रत्येक bin के भीतर तरलता एक ERC-20 token है)।
* LP पोजीशन समायोजित करने के लिए **कम गैस लागत**।
* **विभिन्न liquidity shapes का समर्थन** (जैसे skewed, uniform)।
* flat pricing curve per bin के कारण **कम अस्थिरता** वाली जोड़ियों के लिए अधिक उपयुक्त।

> 🥞 **PancakeSwap hooks के साथ LBAMM pools प्रदान करने वाला पहला प्रोटोकॉल है।**

{% hint style="success" %}
CLAMM और LBAMM दोनों pools **hooks** का समर्थन करते हैं, जो डेवलपर्स को pool व्यवहार अनुकूलित करने देते हैं। Pool types नए Pool Managers के माध्यम से extensible हैं, जिन्हें बिना प्रोटोकॉल पुनः-तैनाती के जोड़ा जा सकता है।
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>विशेषता</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Pricing Curve</strong></td><td>Constant Product (X * Y = K)</td><td>Constant Sum (X + Y = K)</td></tr><tr><td><strong>Liquidity Token</strong></td><td>Non-fungible (NFT)</td><td>Fungible (ERC-20 per bin)</td></tr><tr><td><strong>के लिए सर्वोत्तम</strong></td><td>उच्च/कम दोनों अस्थिरता वाली जोड़ियाँ</td><td>कम अस्थिरता वाली जोड़ियाँ</td></tr><tr><td><strong>लाभ</strong></td><td><ol><li>पूँजी दक्षता</li><li>wide/full range में गैस कुशल</li><li>व्यापक रूप से अपनाया गया</li></ol></td><td><ol><li>bin के भीतर 0 मूल्य प्रभाव</li><li>सस्ता LP प्रबंधन</li><li>लचीली liquidity shapes</li></ol></td></tr><tr><td><strong>Hook Support</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Fees

PancakeSwap Infinity Static और Dynamic शुल्क सेटिंग्स के माध्यम से एक लचीली और extensible शुल्क प्रणाली का समर्थन करता है। यह सेटअप pool creators और LPs दोनों को विभिन्न ट्रेडिंग रणनीतियों और जोखिम प्रोफाइल के लिए अनुकूलित करने के लिए शक्तिशाली उपकरण देता है।

#### 🔁 Dynamic Fees

* Dynamic Fees, hook contracts के माध्यम से रियल-टाइम में निर्धारित किए जाते हैं।
* ये शुल्क बाहरी कारकों जैसे अस्थिरता, ट्रेडिंग वॉल्यूम, उपयोगकर्ता की स्थिति (जैसे CAKE holdings), या hook में coded किसी भी कस्टम लॉजिक के आधार पर उतार-चढ़ाव कर सकते हैं।
* Dynamic fees वाले pools को pool creation के समय setting सक्षम करनी होती है और एक hook attach करना होता है जो `beforeSwap` के माध्यम से fees को संशोधित करने में सक्षम हो।
* एक बार pool initialize होने के बाद, शुल्क प्रकार (dynamic या static) अपरिवर्तनीय होता है।

Dynamic fees अधिकतम लचीलापन प्रदान करते हैं और बाजार की स्थितियों के आधार पर LPs और swappers दोनों के लिए शुल्क संरचनाओं को अनुकूलित करते हैं।

#### 📌 Static Fees

* Static Fee pools में pool creation के दौरान एक निश्चित शुल्क सेट किया जाता है।
* pool initialize होने के बाद ये शुल्क बदले नहीं जा सकते।
* सरल उपयोग-मामलों या जहाँ शुल्क संरचना की पूर्वानुमेयता महत्वपूर्ण हो, के लिए उपयुक्त।<br>

**🔒 अधिकतम शुल्क सीमाएँ:**

* CLAMM Pools: 100% तक (अधिकतर विशेष या प्रयोगात्मक उपयोग-मामलों के लिए)
* LBAMM Pools: 10% पर सीमित<br>

**🏛 Protocol Fee (static fee pools के लिए):**

* PancakeSwap, Infinity pools पर एक protocol fee लागू करता है
* LP fee का 33%, 0.4% पर सीमित

| **LP Fee**       | **Protocol Fee** |
| ---------------- | ---------------- |
| 1%               | 0.33%            |
| 2%               | 0.4% (सीमित)    |
| Dynamic Fee Pool | 0%               |

#### 🛠️ Pool Creators के लिए Setup Notes

* PoolManager के माध्यम से pool initialize करते समय, creator को चुनना होगा:
  * क्या pool static या dynamic fee का उपयोग करता है
  * क्या कोई hook contract attach है (dynamic fees के लिए आवश्यक)

ये settings स्थायी हैं और define करती हैं कि pool अपने पूरे जीवनकाल में कैसे व्यवहार करता है।
