---
description: Ethereum, BNB Chain, Aptos और कई अन्य चेन के बीच CAKE को Bridge करें
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
EVM के साथ Bridging (नई साइट): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Aptos के साथ Bridging (V1 Bridge): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## क्रिप्टो में Bridging क्या है?

* क्रिप्टो में Bridging का अर्थ है विभिन्न ब्लॉकचेन नेटवर्क के बीच संपत्ति (assets) स्थानांतरित करने की प्रक्रिया।
* यह इंटरऑपरेबिलिटी को बढ़ाता है, जिससे विभिन्न नेटवर्क के बीच डेटा और संपत्ति का स्थानांतरण संभव होता है।

\
Bridge करने के कुछ कारण निम्नलिखित हैं:

* विभिन्न क्रिप्टोकरेंसी टोकन खरीदना
* किसी विशेष नेटवर्क पर ही उपलब्ध NFT को मिंट करना
* सस्ते ट्रांजैक्शन से पैसे बचाना
* किसी अन्य नेटवर्क पर ही उपलब्ध dapp का उपयोग करना

***

## CAKE, एक मल्टीचेन टोकन

हमारे मल्टीचेन विस्तार और तैनाती के साथ, CAKE अब एक मल्टीचेन टोकन है जो BNB Chain का नेटिव टोकन है, लेकिन Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB और Aptos पर भी उपलब्ध है।

किसी भी अन्य चेन पर CAKE, BNB Smart Chain के CAKE के बराबर है। इसे इन चेन के बीच हमेशा 1:1 अनुपात में और CAKE में बिना किसी शुल्क के Bridge किया जा सकता है।

**कृपया ध्यान दें कि केवल एक ही CAKE है।** विभिन्न चेन पर CAKE के कोई अलग-अलग संस्करण नहीं हैं। सभी ब्लॉकचेन पर CAKE की कुल आपूर्ति 400M तक सीमित है, जैसा कि इस [vote proposal](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5) में उल्लिखित है।

***

## PancakeSwap Bridge क्या है?

PancakeSwap Bridge एक सुविधाजनक इन-ऐप टूल है जो आपको PancakeSwap इंटरफ़ेस के माध्यम से सीधे विभिन्न ब्लॉकचेन के बीच संपत्ति स्थानांतरित करने की सुविधा देता है। बाहरी Bridge साइटों पर जाने की बजाय, आप BNB Chain, Ethereum, Base, Arbitrum और अन्य चेन के बीच समर्थित टोकन को Bridge कर सकते हैं — सब एक ही स्थान से।

PancakeSwap Bridge विश्वसनीय तृतीय-पक्ष प्रदाताओं द्वारा संचालित है और एक **एग्रीगेटर** के रूप में कार्य करता है — जो मूल्य, गति और विश्वसनीयता के आधार पर सर्वोत्तम रूट का चयन करता है।

CAKE को Bridge करने का तरीका जानने के लिए, निम्नलिखित अनुभागों में ट्यूटोरियल और FAQ देखें।

***

## 🔗 यह कैसे काम करता है

### एग्रीगेटर के माध्यम से Bridging

PancakeSwap Bridge विश्वसनीय तृतीय-पक्ष Bridge प्रोटोकॉल के ऊपर एक स्मार्ट लेयर के रूप में कार्य करता है। जब आप Bridge ट्रांसफर शुरू करते हैं, तो PancakeSwap:

* इष्टतम रूट के लिए एकाधिक एकीकृत Bridge की जांच करता है
* आपके ट्रांजैक्शन को चयनित प्रदाता के पास भेजता है

Bridging नॉन-कस्टोडियल है — आपकी संपत्ति PancakeSwap की कस्टडी में नहीं जाती। ट्रांसफर सीधे Bridge प्रदाताओं द्वारा संभाले जाते हैं।

### समर्थित Bridge प्रदाता

हम वर्तमान में इनके साथ एकीकृत हैं:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> नोट: प्रत्येक प्रदाता की अलग-अलग Bridging प्रणाली, समर्थित चेन, शुल्क और सीमाएं हैं।

***

### समर्थित चेन और टोकन

#### वर्तमान में समर्थित चेन

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (V1 साइट)

#### Bridging के लिए उपलब्ध टोकन

उपलब्ध टोकन चेन और रूट के अनुसार भिन्न होते हैं। सामान्यतः समर्थित टोकन में शामिल हैं (लेकिन इन्हीं तक सीमित नहीं):

* CAKE
* USDT
* USDC
* ETH

***

#### सीमाएं और अपवाद

कुछ टोकन Bridge की सीमाओं या तरलता की बाधाओं के कारण समर्थित नहीं हो सकते। सर्वोत्तम उपयोगकर्ता अनुभव के लिए इन्हें फ़िल्टर किया गया है। उदाहरण के लिए:

**cBridge के लिए:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**deBridge के लिए:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_उपरोक्त उदाहरण हैं। प्रत्येक चेन के लिए वास्तविक उपलब्ध टोकन सीधे Bridge UI में दिखाए जाते हैं।_

***

### 💸 शुल्क और लागत

#### Bridge शुल्क

* अंतर्निहित Bridge प्रदाता द्वारा लिया जाता है
* आमतौर पर प्रति ट्रांसफर एक छोटा शुल्क शामिल होता है
* Bridge की पुष्टि करने से पहले स्पष्ट रूप से दिखाया जाता है

***

#### गैस शुल्क

* ट्रांजैक्शन शुरू करने के लिए आप **स्रोत चेन** पर गैस शुल्क देते हैं
* कुछ प्रदाताओं को **गंतव्य चेन** पर भी गैस की आवश्यकता हो सकती है
* **सुझाव:** Bridge के दोनों तरफ हमेशा नेटिव टोकन (जैसे ETH, BNB) रखें

***

#### न्यूनतम राशि और प्रतिबंध

कुछ Bridge रूट लागू करते हैं:

* **न्यूनतम/अधिकतम Bridge राशि** (जैसे न्यूनतम 10 USDC)
* **समर्थित टोकन दशमलव या प्रारूप** (जैसे केवल ERC-20 टोकन)

UI स्वचालित रूप से अमान्य ट्रांसफर का पता लगाएगा और दिखाएगा।

***

### ⏳ ट्रांजैक्शन समय और ट्रैकिंग

#### Bridging में कितना समय लगता है?

Bridge ट्रांसफर आमतौर पर कुछ **मिनटों** में पूरे हो जाते हैं, जो इन पर निर्भर करता है:

* स्रोत और गंतव्य चेन
* नेटवर्क की व्यस्तता
* Bridge प्रदाता की दक्षता

#### अपना ट्रांसफर ट्रैक करें

सबमिट करने के बाद, आप प्रदाता-विशिष्ट एक्सप्लोरर के माध्यम से ट्रांजैक्शन की स्थिति देख सकते हैं:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

यदि कोई ट्रांजैक्शन लंबे समय से अटका हुआ है, तो संबंधित एक्सप्लोरर देखें या [सहायता](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help) के लिए [सोशल चैनलों](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) के माध्यम से हमारे एडमिन से संपर्क करें।

***

### 🧠 Bridge करने से पहले सुझाव

* **दोनों चेन पर गैस टोकन रखें** (जैसे ETH + BNB)
* यदि आप पहली बार Bridge कर रहे हैं तो **छोटी राशि से शुरुआत करें**
* उच्च चेन गतिविधि के दौरान Bridge करने से बचें (इससे गैस शुल्क अधिक हो सकता है)
* दोनों चेन पर टोकन संगतता की पुष्टि करें
* स्रोत और गंतव्य नेटवर्क को हमेशा दोबारा जांचें

***

### अतिरिक्त: CAKE Omni-chain Fungible Token (OFT) पते

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
