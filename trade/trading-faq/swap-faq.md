# Swap FAQ

## Swap

### Exchange V3 में क्या नया है?

* Concentrated liquidity - तरलता सबसे सक्रिय रूप से व्यापार किए जाने वाले मूल्य सीमा पर केंद्रित होगी, जिसका अर्थ है:
  * ट्रेडर्स के लिए कम trading स्लिपेज
  * Liquidity providers के लिए संभावित रूप से अधिक LP fee पुरस्कार
* एक लचीली trading fee संरचना - Liquidity providers तरलता जोड़ियां बनाते समय या तरलता प्रदान करते समय कई trading fee tiers में से चुन सकते हैं
* अनुकूलन योग्य मूल्य सीमा - Liquidity providers यह भी चुन सकते हैं कि वे किस मूल्य सीमा पर तरलता प्रदान करना चाहते हैं
* Non-fungible liquidity positions - प्रत्येक liquidity position का अपना unique ID होगा जो इसकी configurations (जैसे मूल्य सीमा) के अनुरूप होगा। इसलिए, आप एक ही trading pair के साथ लेकिन अलग-अलग configurations और तरलता राशि के साथ कई positions बना और बनाए रख सकते हैं
* Backwards compatible - v3 Exchange legacy v2 और stable swap liquidity जोड़ियों का भी उपयोग करेगा ताकि हमेशा सर्वोत्तम trading route प्रदान किया जा सके
* Built-in limit order - Pro users liquidity provisioning में नई customizable मूल्य सीमा का उपयोग effectively एक limit order बनाने के लिए कर सकते हैं जो मूल्य लक्ष्य तक पहुंचने पर सभी टोकन को इच्छित एक में परिवर्तित करेगा



### क्या मैं Exchange V3 में अपने खुद के टोकन जोड़ सकता/सकती हूं?

हर कोई V3 पर तरलता जमा करके liquidity pools बना सकता है।

हालांकि, निम्नलिखित टोकन वर्तमान में **समर्थित नहीं** हैं:

* Fee-on-transfer tokens
* Rebase tokens

इन टोकन के लिए, कृपया Exchange V3 पर तरलता **न जोड़ें**। आपकी एसेट liquidity position में फंस सकती हैं।



### **मेरा लेनदेन क्यों नहीं हो रहा?**

PancakeSwap एक DeFi एप्लिकेशन है जो स्वैपिंग, LPs बनाने, farms और pools में स्टेकिंग आदि के लिए ऑन-चेन लेनदेन पूरा करने के लिए वॉलेट के साथ इंटरैक्ट करता है।

**Gas Fees**

इसलिए, पहली बात यह है कि **सुनिश्चित करें कि ऑन-चेन लेनदेन के लिए gas fee का भुगतान करने के लिए आपके पास पर्याप्त BNB है**। आमतौर पर, gas fee queue में लेनदेन की संख्या के आधार पर उतार-चढ़ाव करती है, यदि अधिक लेनदेन हैं, तो लेनदेन को push करने के लिए उच्च gas fee की आवश्यकता हो सकती है। BNB Smart Chain पर, gas fee आमतौर पर BNB में कुछ cents से एक dollar USD तक होती है। [gas fee के बारे में यहां अधिक जानें](https://academy.binance.com/en/glossary/gas)।

**Transaction Fees**

यदि आपकी स्वैपिंग क्रिया अभी भी नहीं हो रही और यह आपको स्लिपेज संशोधित करने के लिए एक error दिखा रही है -- आप यह जांचना चाहेंगे कि क्या आप जिन टोकन की swap करने की कोशिश कर रहे हैं उन पर **लेनदेन पर कोई fees और प्रतिबंध हैं**।

BNB Smart Chain पर टोकन के लिए अपने contracts में एक **transaction fee** शामिल करना असामान्य नहीं है, आमतौर पर ये fees एक fair launch project के treasury को fund करने, burn के लिए उपयोग की जा सकती हैं -- उदाहरण के लिए, इस [APX token में हर लेनदेन पर 1% tax](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) है जो burn address को भेजने के लिए है, ताकि अधिक लेनदेन से अधिक burning हो, APX token holders के लिए मूल्य अर्जित हो।

Transaction fee के साथ, चाहे वह inclusive हो (swap राशि का एक हिस्सा आपके address के अलावा कहीं भेजा जाता है इसलिए estimated input के लिए output अपेक्षित से कम है) या exclusive (आपके address से अतिरिक्त टोकन भेजने के लिए अतिरिक्त ट्रांसफर की आवश्यकता है इसलिए estimated output के लिए input अपेक्षित से अधिक है), यह input और output राशि को प्रभावित करता है जिसके लिए आप लेनदेन पर हस्ताक्षर करने के लिए सहमत होते हैं। कई मामलों में, tax के कारण लेनदेन input और output आवश्यकताओं को पूरा नहीं कर सकता।

**Transaction Fees के साथ Swapping**

किसी भी टोकन की swap करने से पहले, सुनिश्चित करें कि आपने यह समझने के लिए उनकी website देखी है कि क्या उनके पास transaction fee mechanism (या _tax_ जैसा कि कई projects इसे कहते हैं) है। यदि है, तो सुनिश्चित करें कि आपने transaction fee को accommodate करने के लिए पर्याप्त स्लिपेज सेट की है -- जैसे यदि 5% का transaction fee है, तो आपकी स्लिपेज कम से कम 5% plus आपकी trading राशि और टोकन की तरलता के आधार पर सामान्य trading स्लिपेज होनी चाहिए, कहें 5.5%-6%।

कुछ चरम मामलों में जिनमें कुछ scams शामिल हैं, कुछ टोकन के पास chain पर अधिकांश या सभी transfers पर block भी है, या केवल कुछ addresses को बेचने की अनुमति है, ऐसे मामले में टोकन की सफलतापूर्वक swap करना असंभव है। उस टोकन के बारे में जानें जिसे आप swap करने की कोशिश कर रहे हैं और किसी भी fees और प्रतिबंधों के बारे में जागरूक रहें!



### क्या नया Swap interface v2 या stable swap liquidity का उपयोग करता है?

हां। नया Swap v3 सर्वोत्तम trading route पाने के लिए PancakeSwap v3, v2 और stable swap से तरलता का उपयोग करता है।



### Split routing क्या है?

Swap v3 में, सर्वोत्तम दर के साथ आपके ट्रेड को निष्पादित करने के लिए आपका ट्रेड कई routes में विभाजित हो सकता है।

अपने ट्रेड के route के बारे में अधिक विवरण देखने के लिए, "Route" section पर "v" बटन टैप करें और विवरण देखने के लिए expand करें।

[यहां](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences) और अधिक जानें।



### मैं कुछ liquidity sources को कैसे customize या disable करूं?

नया Swap v3 सर्वोत्तम trading route पाने के लिए PancakeSwap v3, v2 और stable swap से तरलता का उपयोग करता है। हालांकि, यदि आप नहीं चाहते कि आपका ट्रेड उनके माध्यम से route हो तो आप कुछ liquidity sources को customize या disable कर सकते हैं।

एक trading route देखते समय, "Customize Routing" बटन पर क्लिक करें। या Swap interface के ऊपरी दाएं कोने में cog ⚙️ बटन पर क्लिक करें और "Customize Routing" चुनें।

"Customize Routing" pop up के भीतर, आप चुन सकते हैं कि आप किस liquidity source का उपयोग करना चाहते हैं। या multihops को पूरी तरह disable करें।

नोट: multihops को disable करने से specific trading pairs पर बढ़ी हुई स्लिपेज या खराब trading rate हो सकती है। सावधानी के साथ आगे बढ़ें।

[यहां](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources) और अधिक जानें।



## तरलता

### Fee tiers क्या हैं और सही कैसे चुनें?

Exchange v3 में, जब आप तरलता प्रदान कर रहे हों, तो आप उसी टोकन जोड़ी के लिए कई अलग-अलग trading fees (0.01%, 0.05%, 0.25%, और 1%) में से चुन सकते हैं।

उदाहरण के लिए, CAKE-BNB के लिए, एक 0.25% जोड़ी हो सकती है, जिसका अर्थ है कि हर ट्रेड के लिए 0.25% trading fee लागू है। हालांकि, कुछ liquidity providers 0.05% fee rate के साथ CAKE-BNB trading pair को तरलता प्रदान करना चुन सकते हैं, जो बेहतर quote प्रदान करती है और अधिक trading volume आकर्षित करती है।

कौन सी trading fee configuration चुनें इसका कोई "सही" जवाब नहीं है। यह trading pair के भीतर टोकन पर निर्भर करता है। आमतौर पर, अस्थिर टोकन में अस्थिरता से उत्पन्न impermanent loss की बेहतर भरपाई के लिए उच्च trading fee होनी चाहिए। दूसरी ओर, stable coins जैसे टोकन में छोटे मूल्य आंदोलन और कम impermanent losses होते हैं, इसलिए उनकी trading fee कम होनी चाहिए।

एक टोकन जोड़ी का चयन करते समय, "Add Liquidity" interface आपके लिए स्वचालित रूप से सबसे लोकप्रिय fee tier चुनेगा।



### मेरे दो जमा टोकन USD मूल्य में समान क्यों नहीं हैं?

Exchange V3 में, एक liquidity position में अंतर्निहित एसेट का USD में हमेशा समान मूल्य नहीं होगा। यह position की मूल्य सीमा settings और जोड़ी के वर्तमान मूल्य पर निर्भर करेगा।

वास्तव में, यदि आपकी position range से बाहर जाती है, तो सभी टोकन एक single एसेट में परिवर्तित हो जाएंगे। इसके अलावा, आप एक ऐसी मूल्य सीमा पर तरलता प्रदान कर सकते हैं जो वर्तमान मूल्य को कवर नहीं करती और केवल एक single एसेट जमा कर सकते हैं। और जानने के लिए पढ़ते रहें ⬇️



### यदि मेरी liquidity position range से बाहर चली जाए तो क्या होता है?

यदि वर्तमान मूल्य आपकी position में परिभाषित मूल्य सीमा से बाहर चला जाता है तो आप कोई trading fee पुरस्कार नहीं कमाएंगे।

इसके अलावा, सभी टोकन मूल्य की स्थिति की दिशा के आधार पर एक single एसेट में परिवर्तित हो जाएंगे।

उदाहरण के लिए, यदि CAKE/BUSD की एक position को 3 BUSD प्रति CAKE से 5 BUSD प्रति CAKE की मूल्य सीमा के साथ configured किया गया है। और यदि CAKE की कीमत 5 BUSD प्रति CAKE से अधिक या उसके बराबर है तो position में सभी एसेट BUSD में परिवर्तित हो जाएंगी, और इसके विपरीत।

कृपया ध्यान दें कि यदि मूल्य range में वापस आता है, तो आप फिर से trading fee पुरस्कार प्राप्त करना शुरू करेंगे। कोई अतिरिक्त कार्रवाई की आवश्यकता नहीं है।



### क्या हमेशा छोटी सीमा के साथ तरलता प्रदान करना बेहतर है?

एक छोटी मूल्य सीमा पर तरलता प्रदान करने से आपकी तरलता को एक specific मूल्य सीमा पर concentrate करने में मदद मिलेगी, जो मूल्य सीमा के भीतर कुल तरलता के विरुद्ध आपकी relative shares को बढ़ाती है, संभावित रूप से अधिक trading fee पुरस्कार अर्जित करती है।

हालांकि, कृपया ध्यान रखें कि केवल active liquidity positions ट्रेडों से trading fee पुरस्कार अर्जित करेंगी। इसका मतलब है कि आप केवल तभी पुरस्कार अर्जित करेंगे जब वर्तमान trading price liquidity position में परिभाषित मूल्य सीमा के भीतर हो।



### क्या मेरी position को हमेशा range में रखने और fee पुरस्कार अर्जित करने के लिए स्वचालित रूप से समायोजित करने के कोई तरीके हैं?

PancakeSwap v3 Zap के माध्यम से one-click liquidity depositing का समर्थन करता है, जो BNB Chain और Ethereum पर उपलब्ध है।



### v3 Exchange के लिए trading fee breakdown क्या होगा?

|                    | 0.01% | 0.05% | 0.25% | 1%  |
| ------------------ | ----- | ----- | ----- | --- |
| Liquidity Provider | 67%   | 66%   | 68%   | 68% |
| CAKE Burn          | 15%   | 15%   | 23%   | 23% |
| Treasury           | 18%   | 19%   | 9%    | 9%  |

### क्या LP fee पुरस्कार Exchange v2 की तरह स्वचालित रूप से compound होते हैं?

नहीं।

Exchange v3 में आपको trading fee पुरस्कार manually claim करने होंगे। आप position detail page पर ऐसा कर सकते हैं। आप liquidity page पर अपनी सभी v3 liquidity positions पा सकते हैं।



### LP APR को क्या प्रभावित करता है?

Exchange v3 में, LP fee reward APR liquidity positions के बीच भिन्न हो सकता है। यह निम्नलिखित कारकों पर आधारित है:

* Trading volume\
  \- अधिक volume अधिक fee पुरस्कार उत्पन्न करता है
* Liquidity pair fee tier\
  \- उच्च fee tier individual ट्रेडों से अधिक fee पुरस्कार उत्पन्न करता है
* जमा किए गए टोकन की संख्या\
  \- position में अधिक टोकन कुल active तरलता के विरुद्ध एक बड़े relative share में translate होता है, जो ट्रेडों से अधिक trading fee पुरस्कार प्राप्त करता है
* चुनी गई मूल्य सीमा\
  \- छोटी मूल्य सीमा एक ही टोकन राशि के लिए उच्च concentration की अनुमति देती है, जो कुल active तरलता के विरुद्ध एक बड़े relative share में translate होती है, और ट्रेडों से अधिक trading fee पुरस्कार प्राप्त करती है
* वर्तमान में active तरलता की मात्रा\
  \- यदि अधिक उपयोगकर्ता जमा करते हैं और आपके समान range के साथ अपनी तरलता concentrate करते हैं, तो आप कुल के विरुद्ध छोटे relative share के कारण कम trading fee अर्जित करेंगे
* क्या liquidity position active है\
  \- केवल active liquidity positions trading fee पुरस्कार अर्जित करेंगी



### क्या मैं v2 तरलता प्रदान कर सकता/सकती हूं?

v2 तरलता प्रदान करना अब उचित नहीं है। हम दक्षता में सुधार करने के लिए नई सुविधाओं का लाभ उठाने के लिए v3 तरलता का उपयोग करने की अनुशंसा करते हैं।

यदि आप v2 तरलता जोड़ना चाहते हैं:

* यदि टोकन जोड़ी का v3 pool नहीं है, या v3 के सबसे बड़े pool की तुलना में v2 में अधिक तरलता है। एक "Add V2 Liquidity" दिखाई देगा। v2 तरलता जोड़ने पर स्विच करने के लिए बस क्लिक करें
* वैकल्पिक रूप से, v2 liquidity provisioning हमेशा उपयोग करने के लिए URL में `/v2` का उपयोग करें



### मैं अभी-अभी बनाई गई जोड़ी में तरलता क्यों नहीं जोड़ सकता/सकती?

Legacy Exchange V2 (प्रत्येक UniSwap V2 fork में मौजूद) की एक bug के कारण, यदि जोड़ी इस प्रकार है तो आप सामान्य PancakeSwap liquidity UI और इसके contract calls का उपयोग करके जोड़ी में तरलता नहीं जोड़ सकेंगे:

* FactoryV2 पर `createPair` call करके initial liquidity जमा किए और initial LP tokens mint किए बिना बनाई गई
* फिर, जोड़ी में टोकन में से एक को `sync` call करते समय pool contract में manually transfer किया गया

{% hint style="info" %}
हाल ही में, BNB Chain पर PancakeSwap Exchange V2 पर ऐसे हमलों की बढ़ती मात्रा देखी गई।&#x20;

हम दृढ़ता से अनुशंसा करते हैं कि जोड़ी निर्माण के साथ प्रारंभिक तरलता जोड़कर अपने टोकन के लिए trading pair बनाने के लिए हमारे UI का उपयोग करें।
{% endhint %}

जबकि Chefs इस समस्या को हल करने के लिए कड़ी मेहनत कर रहे हैं, यहां BscScan का उपयोग करके इसे हल करने के लिए एक step-by-step गाइड है:

#### Pool address और इसके BscScan page का पता लगाएं

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

यदि आपकी जोड़ी प्रभावित है, तो आप error prompt में trading pair/pool के लिए BscScan page का लिंक देखेंगे।

वैकल्पिक रूप से, आप Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)) पर जा सकते हैं, "Read Contract", "6. getPair" पर जाएं, अपने trading pair के दो टोकन का address दर्ज करें, और "Query" पर क्लिक करें। आपको return field में pair address दिखाई देना चाहिए।

#### जांचें कि कौन सा टोकन जमा किया गया है और दूसरे टोकन को manually जोड़ी में transfer करें

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

BscScan पर token balance field से, आप जांच सकते हैं कि कौन सा टोकन pool में जमा किया गया है। आमतौर पर, यह paired token होना चाहिए। (जैसे WBNB, USDT, आदि...)

एक बार पुष्टि होने के बाद, आपको दूसरी एसेट को pool contract में manually transfer करना होगा। आप अपने पसंदीदा wallet app में pool address को receiver के रूप में दर्ज करके ऐसा कर सकते हैं।

आप कोई भी राशि transfer कर सकते हैं लेकिन चूंकि यह effectively एक pool को एसेट "दान" करना है। आप liquidity tokens mint किए बिना एक liquidity में अपनी एसेट transfer करेंगे। इसलिए हम इस राशि को न्यूनतम रखने की सलाह देते हैं।

{% hint style="warning" %}
महत्वपूर्ण: एक बार टोकन transfer करने के बाद, आपको तुरंत pool पर `sync()` call करना होगा।
{% endhint %}

आप BscScan page पर trading pair के लिए जाकर, "Write Contract", "8. Sync" पर जाकर और "Write" बटन पर क्लिक करके ऐसा कर सकते हैं। लेनदेन करने से पहले आपको अपना वॉलेट connect करना होगा।

एक बार लेनदेन की पुष्टि हो जाने के बाद, आप PancakeSwap UI पर बाद की तरलता जोड़ सकते हैं।

#### यदि मैं launch price define करना चाहूं तो?

आपको टोकन transfer करते समय और pool को fix करते समय pool को launch price पर समायोजित करना होगा।

Transfer की जाने वाली राशि की गणना इनका उपयोग करके की जा सकती है:

* `tokenInside`: वह टोकन जो पहले से pool में transfer किया गया है। आमतौर पर यह paired token होना चाहिए। (जैसे WBNB, USDT, आदि...)
* `tokenToSend`: वह टोकन जो pool को भेजा जाने वाला है। आमतौर पर यह आपका project token होना चाहिए
* `tokenInside.price`: tokenInside का USD price
* `tokenToSend.price`: tokenToSend का USD price (launch price)
* `pool`: V2 pool

निम्नलिखित सूत्र के साथ:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

यदि परिणाम 0 से छोटा है (आमतौर पर तब होता है जब launch price बहुत बड़ी हो। आपको पहले pool में अधिक `tokenInside` जमा करने की आवश्यकता हो सकती है)



### Stable LP और legacy v2 LP को कैसे प्रबंधित करें?

आप उन्हें हमेशा की तरह [Liquidity](https://pancakeswap.finance/liquidity) page पर जाकर प्रबंधित कर सकते हैं।



### Ethereum mainnet पर USDT को enable/approve करने से पहले approval reset क्यों करना होगा?

Ethereum mainnet पर काम करते समय, USDT token approvals और token allowance के प्रबंधन के लिए एक अलग logic का पालन करता है।&#x20;

इसलिए, जब spending allowances बहुत कम हों। नया approval सेट करने से पहले approval reset करना आवश्यक है।
