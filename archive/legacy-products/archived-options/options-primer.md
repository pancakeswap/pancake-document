# Options Primer



{% hint style="danger" %}
\[ARCHIVED] Options – 11 मार्च 2025 से\
यदि आपके पास अभी भी withdraw करने के लिए liquidity है, तो कृपया तुरंत https://www.stryke.xyz/en/trade पर जाकर ऐसा करें।
{% endhint %}



## Options क्या हैं?

Options derivative contracts हैं जो buyer को एक निर्धारित अवधि (expiration date) के भीतर एक पूर्व-निर्धारित मूल्य (strike price) पर underlying asset खरीदने (call option) या बेचने (put option) का अधिकार प्रदान करते हैं, लेकिन यह बाध्यकारी नहीं होता।

## Options के प्रकार?

### Call Options

Call option holder को agreed-upon strike price पर या उससे पहले expiration date तक underlying asset खरीदने का अधिकार देता है। Traders call options तब खरीदते हैं जब उन्हें underlying asset की price बढ़ने की उम्मीद होती है। यह उन्हें underlying asset को पूरी तरह से खरीदे बिना संभावित price appreciation से लाभ उठाने की अनुमति देता है।

> एक trader $50,000 की strike price के साथ Bitcoin पर call option खरीदता है जो एक महीने में expire होता है। यदि उस महीने में Bitcoin की price $50,000 से ऊपर जाती है, तो investor $50,000 पर Bitcoin खरीदने के लिए option exercise कर सकता है, जिससे संभावित रूप से price difference से लाभ होगा।

### Put Options

Put option holder को agreed-upon strike price पर या उससे पहले expiration date तक underlying asset बेचने का अधिकार देता है। Traders put options तब खरीदते हैं जब उन्हें underlying asset की price गिरने की उम्मीद होती है। यह उन्हें underlying asset को short sell किए बिना संभावित price declines से लाभ उठाने की अनुमति देता है। Put options का उपयोग आमतौर पर investment portfolios में किसी भी downside risks के विरुद्ध hedge करने के लिए भी किया जाता है।

> एक trader $3,000 की strike price के साथ Ethereum पर put option खरीदता है जो दो सप्ताह में expire होता है। यदि उस समय सीमा के भीतर Ethereum की price $3,000 से नीचे जाती है, तो trader $3,000 पर Ethereum बेचने के लिए option exercise कर सकता है, जिससे संभावित losses कम होंगी।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Options Positions

प्रत्येक प्रकार के option के लिए, दो संभावित positions होती हैं:

### **Long Option (Option Buyer)**&#x20;

इस position में option प्राप्त करने के लिए upfront premium का भुगतान करना होता है। यदि option profit में समाप्त होता है, तो holder को settlement प्राप्त होता है।

### **Short Option (Option Writer/Seller)**

इस position में, seller option जारी करने के लिए upfront premium प्राप्त करता है। हालाँकि, यदि option profit में समाप्त होता है (buyer के लिए; underlying price, strike price, और option के प्रकार के आधार पर), तो seller settlement का भुगतान करने के लिए बाध्य होता है।

## American बनाम European Options

* **American Options:** Expiration date से पहले किसी भी समय exercise किए जा सकते हैं। यह लचीलापन उन्हें European options की तुलना में अधिक मूल्यवान बनाता है।
* **European Options:** केवल expiration date पर ही exercise किए जा सकते हैं। लचीलेपन की कमी के कारण ये आमतौर पर American options की तुलना में कम महंगे होते हैं।

## Options का उपयोग कब करें?

यहाँ कुछ example use cases दिए गए हैं:

1. **Speculation:** एक investor को विश्वास है कि Bitcoin की price अगले महीने बढ़ेगी। वे anticipated price rise से लाभ उठाने के लिए Bitcoin पर call options खरीदते हैं।
2. **Hedging:** एक cryptocurrency validator Ethereum में संभावित price decreases के विरुद्ध hedge करना चाहता है। वे price एक निश्चित level से नीचे जाने पर losses से बचाने के लिए Ethereum पर put options खरीदते हैं।
3. **Income Generation:** एक crypto investor जो बड़ी मात्रा में Ether रखता है, वह अपनी holdings पर call options लिखने का निर्णय लेता है, जिससे potential upside price movements में भाग लेते हुए premiums अर्जित होती हैं।

## Options Pricing

Options pricing जटिल है और इसमें विभिन्न कारक शामिल होते हैं, जिसमें Black-Scholes model सबसे अधिक उपयोग किया जाने वाला है।&#x20;

Options pricing को प्रभावित करने वाले प्रमुख कारक:

* **Underlying Asset Price:** Underlying asset की वर्तमान market price।
* **Strike Price:** वह price जिस पर option holder underlying asset खरीद या बेच सकता है।
* **Volatility:** Underlying asset में price fluctuations की degree।&#x20;
* **Time to Expiration:** Option expire होने तक शेष समय।
* **Interest Rates:** Risk-free rate of return।

Options pricing यह निर्धारित करती है कि option trader द्वारा option खरीदने पर writer को कितना premium/fee मिलता है। Option writers को settlement भुगतान का जोखिम होता है यदि उनके options In-The-Money या ITM (buyer के लिए profitable) expire होते हैं। इसलिए, purchasers से अर्जित premiums को ITM event की probability को उचित रूप से reflect करना चाहिए।

PancakeSwap CLAMM options premiums निम्नलिखित assumptions के साथ Black-Scholes model से derived हैं:

* Risk-free rate को शून्य माना गया है।
* Volatility underlying asset की 30-day historical volatility पर आधारित है [implied volatility (IV) के proxy के रूप में उपयोग की जाती है]।

कुछ exceptions में शामिल हैं:

* $ETH और $BTC IV सीधे Deribit से ली जाती हैं यदि strike prices match होती हैं। यदि strike prices match नहीं होती हैं, तो Deribit के closest upper और lower strikes को IV set करने के लिए offset की degree के आधार पर weighted किया जाता है।
* $ARB, $ETH के विरुद्ध base asset की effective strike price की गणना करके IV extrapolate करने के लिए 30-day beta-based historical volatility का उपयोग करता है, जिसे $ETH के विरुद्ध base asset के beta से गुणा किया जाता है।

उच्च volatility वाली assets में कम volatility वाली assets की तुलना में अधिक महंगा premium होगा क्योंकि option के ITM expire होने का writers को अधिक जोखिम होता है।

## Options Settlement

### Settlement Conditions

* Settlement, expiration पर option की moneyness के आधार पर निर्धारित किया जाता है।
* Settlement तभी calculated होता है जब option exercise के समय In-The-Money (ITM) हो।

### ITM Conditions

* **Call Option:** यदि Settlement पर Spot Price > Strike Price
* **Put Option:** यदि Settlement पर Spot Price < Strike Price

### Settlement Calculation

* **Call Option:** #Options \* (Spot Price at Settlement - Strike Price)
* **Put Option:** #Options \* (Strike Price - Spot Price at Settlement)

### Moneyness

Moneyness किसी option के intrinsic value को refer करती है, जो execution के समय उसकी strike price की उसकी spot price से तुलना करके निर्धारित होती है।

### Classification

1. Out-of-The-Money (OTM):
   1. यदि settlement के समय spot price, strike price से अलग है और settlement तत्काल होने पर कोई value exchange नहीं होगी, तो option OTM है।
   2. Conditions:
      1. Call Option: Spot Price < Strike Price
      2. Put Option: Spot Price > Strike Price

{% hint style="info" %}
$2,000 की strike price वाला $ETH call option OTM होगा यदि spot price $1,800 है ($1,800 < $2,000 यानी OTM)।
{% endhint %}

2. At-The-Money (ATM):
   1. यदि settlement के समय spot price, strike price के बराबर है और settlement तत्काल होने पर कोई value exchange नहीं होगी, तो option ATM है।
   2. Conditions: Call और Put दोनों Options के लिए: Spot Price = Strike Price

{% hint style="info" %}
$1,800 की strike price वाले $ETH call option और put option दोनों ATM होंगे यदि spot price भी $1,800 है ($1,800 = $1,800 यानी ATM)।
{% endhint %}

3. In-The-Money (ITM):
   1. यदि settlement के समय spot price, strike price से अलग है और settlement तत्काल होने पर value exchange होगी, तो option ITM है।
   2. Conditions:
      1. Call Option: Spot Price > Strike Price
      2. Put Option: Spot Price < Strike Price

{% hint style="info" %}
$1,600 की strike price वाला $ETH call option ITM होगा यदि spot price $1,800 है ($1,800 > $1,600 यानी ITM)।
{% endhint %}

Option buyer द्वारा अर्जित settlement, option writer द्वारा खोई गई collateral के बराबर होता है। Settlement में भुगतान किया गया options premium शामिल नहीं है, जिसे option buyers और writers के लिए profits या losses की गणना करते समय शामिल किया जाता है।
