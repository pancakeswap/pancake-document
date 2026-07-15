# Infinity StableSwap

### अवलोकन

Infinity StableSwap [ PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) के भीतर एक pool प्रकार है जो उन एसेट की swap के लिए अनुकूलित है जो समान मूल्य के करीब व्यापार करते हैं — जैसे stablecoins (जैसे USDC/USDT) या तंग-pegged एसेट (जैसे wrapped token जोड़ियां, liquid staking tokens और liquid restaking tokens)।

यह Infinity आर्किटेक्चर पर चलने वाले StableSwap hook द्वारा संचालित है, जो Curve के StableSwap NG डिज़ाइन से प्रेरित है। यह वर्तमान में BNB Chain पर उपलब्ध है, भविष्य में अतिरिक्त चेन पर विस्तार की योजना के साथ।

***

### यह कैसे काम करता है

Infinity StableSwap एक stable invariant curve का उपयोग करता है — constant-sum और constant-product के बीच एक संकर:

* peg के पास → curve constant-sum के करीब व्यवहार करता है, जिसके परिणामस्वरूप 1:1 के करीब ट्रेडों के लिए बहुत कम स्लिपेज होती है।
* peg से दूर → curve धीरे-धीरे constant-product की ओर जाता है, जो बड़े असंतुलन या depeg घटनाओं के दौरान संतुलन बहाल करने और pool की रक्षा करने में मदद करता है।

यह इसे विशेष रूप से stable जोड़ियों के लिए प्रभावी बनाता है जहां तंग मूल्य निर्धारण और कम स्लिपेज सबसे महत्वपूर्ण हैं।

***

### प्रमुख विशेषताएं

Near-peg swaps के लिए अनुकूलित: उन एसेट के बीच ट्रेडों के लिए कम स्लिपेज जो लगभग समान मूल्य पर व्यापार करने की उम्मीद है।

सरल तरलता प्रावधान: Liquidity providers (LPs) बिना मूल्य सीमा का चयन या प्रबंधन किए बिना दोनों टोकन आनुपातिक रूप से जमा करते हैं — CLAMM pools के विपरीत।

ERC-20 LP tokens: आपकी LP पोजीशन एक मानक ERC-20 टोकन के रूप में प्रदर्शित होती है, जिससे yield कार्यक्रमों, points campaigns और अन्य DeFi प्रोटोकॉल के साथ उपयोग करना आसान हो जाता है।

Dynamic fees: Pool balance की स्थितियों के आधार पर शुल्क समायोजित हो सकते हैं, उन ट्रेडों को पुरस्कृत करते हुए जो pool को equilibrium की ओर बहाल करने में मदद करते हैं और उन लोगों को हतोत्साहित करते हैं जो असंतुलन को खराब करते हैं।

Infinity routing support: ट्रेड स्वचालित रूप से StableSwap pools के माध्यम से route होते हैं जब वे सर्वोत्तम मूल्य प्रदान करते हैं — ट्रेडर्स के लिए कोई अतिरिक्त कदम की आवश्यकता नहीं।

Adjustable Amplification (A) parameter: Pool operators समय के साथ A parameter को ऊपर या नीचे ramp कर सकते हैं जो बदलती बाजार स्थितियों के अनुकूल होते हैं, अचानक परिवर्तनों को रोकने के लिए सुरक्षा उपायों के साथ।

***

### Pool पैरामीटर

StableSwap pool का व्यवहार पैरामीटर के एक छोटे सेट द्वारा नियंत्रित होता है, जो आमतौर पर pool निर्माण के समय सेट किए जाते हैं।

#### Amplification Coefficient (A)

A parameter नियंत्रित करता है कि pool 1:1 मूल्य peg को कितनी तंगी से पकड़ता है।

| A मूल्य  | प्रभाव                                                                         |
| -------- | ------------------------------------------------------------------------------ |
| उच्च A | peg के चारों ओर तंग curve; 1:1 के पास कम स्लिपेज; असंतुलन के प्रति अधिक संवेदनशील |
| कम A  | ढीला curve; एक मानक constant-product pool की तरह अधिक व्यवहार करता है               |

अंगूठे का नियम: मजबूत, विश्वसनीय peg वाली एसेट के लिए उच्च A का उपयोग करें (जैसे USDC/USDT)। ढीले या अधिक अस्थिर pegs वाली एसेट के लिए कम A का उपयोग करें (जैसे कुछ LST जोड़ियां)।

A parameter को pool operator द्वारा एक निर्धारित समय अवधि में धीरे-धीरे ऊपर या नीचे ramped किया जा सकता है। परिवर्तन धीरे-धीरे लागू होते हैं जिसमें हेरफेर या अचानक मूल्य बदलावों को रोकने के लिए सुरक्षा उपाय होते हैं।

#### Off-Peg Fee Multiplier

एक अतिरिक्त पैरामीटर जो equilibrium से दूर जाने पर प्रभावी शुल्क को समायोजित करता है। यह उन ट्रेडों को हतोत्साहित करने में मदद करता है जो pool को और असंतुलित करेंगे और बाजार के तनाव या depeg घटनाओं के दौरान pool को अधिक मजबूत बनाता है।

#### Dynamic Fees

प्रत्येक swap पर लिया जाने वाला शुल्क, liquidity providers को भुगतान किया जाता है। Infinity StableSwap dynamic fees का समर्थन करता है — जिसका अर्थ है कि किसी दिए गए ट्रेड पर प्रभावी शुल्क pool की वर्तमान स्थिति (जैसे ट्रेड balance में सुधार या बिगाड़ता है) के आधार पर भिन्न हो सकता है।

***

### Infinity StableSwap बनाम Classic StableSwap

यदि आपने पहले PancakeSwap के मौजूदा StableSwap का उपयोग किया है, तो यहां क्या बदलता है — और क्या समान रहता है।

| <p><br></p>                 | Classic StableSwap                                        | Infinity StableSwap                                                |
| --------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ |
| मूल्य निर्धारण curve               | Stable invariant (hybrid constant-sum / constant-product) | वही stable invariant curve, peg के पास वही कम स्लिपेज            |
| ERC-20 LP tokens            | ✅ हां                                                     | ✅ हां                                                              |
| Pool निर्माण               | Ops-heavy; team द्वारा manual setup की आवश्यकता              | Permissionless — कोई भी pool बना सकता है                          |
| Swap fees                   | प्रति जोड़ी निश्चित (जैसे USDC/USDT के लिए 0.01%)                 | Dynamic fees — ट्रेड pool balance को कैसे प्रभावित करता है इसके आधार पर समायोजित होता है |
| Amplification (A) parameter | Static — एक बार सेट, बदला नहीं जा सकता                      | Adjustable — समय के साथ धीरे-धीरे ऊपर या नीचे ramped किया जा सकता है          |
| Off-peg fee multiplier      | ❌ समर्थित नहीं                                           | ✅ समर्थित — depeg घटनाओं के दौरान pool की रक्षा करने में मदद करता है           |
| Gas efficiency              | मानक                                                  | बेहतर — Infinity के Singleton और Flash Accounting से लाभ |

#### क्या समान रहता है

* मूल मूल्य निर्धारण curve और near-peg कम स्लिपेज व्यवहार अपरिवर्तित है।

#### क्या नया और बेहतर है

* Permissionless Pool Creation: Pool को manual team setup की आवश्यकता के बिना permissionlessly बनाया जा सकता है।
* Dynamic fees LPs की रक्षा करती हैं: एकल निश्चित शुल्क के बजाय, शुल्क प्रति ट्रेड समायोजित हो सकता है इस आधार पर कि ट्रेड pool balance में मदद करता है या नुकसान पहुंचाता है — अस्थिर परिस्थितियों के दौरान pool को अधिक लचीला बनाता है।
* Adaptable A parameter: amplification coefficient को समय के साथ बाजार की स्थितियों के अनुसार tuned किया जा सकता है, बजाय हमेशा के लिए deployment पर locked होने के।

***

### अक्सर पूछे जाने वाले सवाल (FAQ)

Infinity StableSwap के लिए कौन सी एसेट उपयुक्त हैं?

वे एसेट जो समान मूल्य के करीब व्यापार करने की उम्मीद है: stablecoins (USDC, USDT, BUSD, आदि), एक ही एसेट के wrapped equivalents (जैसे WBTC/cbBTC), और चुनिंदा liquid staking tokens / liquid restaking tokens (LST/LRT) जोड़ियां जहां peg अस्थिरता कम हो।

<br>

Infinity StableSwap पुराने PancakeSwap StableSwap से कैसे अलग है?

Infinity StableSwap को PancakeSwap Infinity पर एक hook के रूप में लागू किया गया है, जिसका अर्थ है कि यह Infinity के सभी infrastructure लाभों को प्राप्त करता है, जिसमें Singleton और Flash Accounting के माध्यम से कम gas costs, और एक अधिक लचीली शुल्क प्रणाली शामिल है। यह dynamic fees और adjustable amplification जैसी नई क्षमताओं का भी समर्थन करता है जो legacy StableSwap में नहीं थीं।

<br>

क्या मुझे समय के साथ अपनी पोजीशन प्रबंधित करनी होगी?

नहीं। CLAMM के विपरीत, आपको मूल्य सीमा सेट या समायोजित करने की आवश्यकता नहीं है। आपकी तरलता हमेशा पूरे curve में सक्रिय रहती है, इसलिए आपकी पोजीशन के "out of range" जाने का कोई जोखिम नहीं है।

<br>

क्या मैं केवल एक टोकन के साथ तरलता प्रदान कर सकता/सकती हूं?

हां, single-token deposits समर्थित हैं।

<br>

Dynamic fees कैसे काम करती हैं?

Infinity StableSwap में, swap fee प्रति ट्रेड इस आधार पर भिन्न हो सकती है कि ट्रेड pool के balance को कैसे प्रभावित करता है। जो ट्रेड pool को equilibrium की ओर वापस लाने में मदद करते हैं वे कम प्रभावी fees दे सकते हैं, जबकि जो ट्रेड असंतुलन को बिगाड़ते हैं वे उच्च fees दे सकते हैं। यह LPs की रक्षा करने और स्वस्थ pool की स्थितियों को बनाए रखने के लिए डिज़ाइन किया गया है।



***



## Infinity StableSwap Pool बनाना



Infinity StableSwap pools permissionless हैं — कोई भी PancakeSwap team से अनुमोदन की आवश्यकता के बिना एक बना सकता है।

<br>

### चरण-दर-चरण

1\. Farm/Liquidity पेज पर जाएं और Create Pool पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Pool type options से StableSwap Pool चुनें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. अपने pool के लिए टोकन जोड़ी चुनें (जैसे USDC / USDT)।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Pool पैरामीटर

| पैरामीटर             | यह क्या करता है                                                                                                    |
| --------------------- | --------------------------------------------------------------------------------------------------------------- |
| Swap Fee              | प्रत्येक swap पर लिया जाने वाला शुल्क, LPs को भुगतान किया जाता है। तंग stable जोड़ियों के लिए डिफ़ॉल्ट 0.01% है।                                 |
| A (Amplification)     | नियंत्रित करता है कि curve peg को कितनी तंगी से पकड़ता है। उच्च = 1:1 के पास कम स्लिपेज, लेकिन असंतुलन के प्रति अधिक संवेदनशील। |
| Offpeg Fee Multiplier | जब pool balance से दूर जाता है तो fees बढ़ाता है, उन ट्रेडों को हतोत्साहित करता है जो असंतुलन को खराब करते हैं।                |
| Moving Average Time   | dynamic fee adjustments के लिए moving average price की गणना के लिए उपयोग की जाने वाली समय विंडो।                             |

⚠️ पैरामीटर सावधानी से सेट करें। गलत पैरामीटर — विशेष रूप से ढीले-pegged एसेट पर बहुत उच्च A — LPs के लिए जोखिम बढ़ा सकते हैं। यदि आप अनिश्चित हैं, तो अपने एसेट प्रकार के लिए preset का उपयोग करें और Advanced settings बदलने से बचें।

<br>

एक Pool Parameter Preset चुनें — यह आपके एसेट प्रकार के लिए अनुशंसित पैरामीटर स्वचालित रूप से सेट करता है। आप फिर भी Advanced toggle के माध्यम से उन्हें manually समायोजित कर सकते हैं।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                            | A    | Offpeg Fee Multiplier | Moving Average Time (seconds) |
| --------------------------------- | ---- | --------------------- | ----------------------------- |
| Fiat Redeemable Stablecoins       | 1000 | 10                    | 600                           |
| Crypto Collateralized Stablecoins | 100  | 12.5                  | 600                           |
| Liquid Restaking Tokens           | 500  | 10                    | 600                           |

<br>

&#x20; कौन सा चुनना है, इसके बारे में अनिश्चित हैं?&#x20;

* USDC/USDT जैसी जोड़ियों के लिए Fiat Redeemable Stablecoins का उपयोग करें
* algo या crypto-backed stablecoins के लिए Crypto Collateralized Stablecoins का उपयोग करें
* stkBNB/WBNB जैसी LRT जोड़ियों के लिए Liquid Restaking Tokens का उपयोग करें।

<br>

5\. प्रारंभिक तरलता seed करने के लिए जमा राशि दर्ज करें। दोनों टोकन की राशि समान होनी चाहिए (जैसे 1 USDC और 1 USDT)।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Preview Pool पर क्लिक करें, अपनी settings की समीक्षा करें, confirmation box चेक करें, फिर Create Pool पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
