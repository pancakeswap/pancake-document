---
description: Trading Reward FAQ
---

# FAQ

{% hint style="danger" %}
\[Archived] Trading Reward – 23 अगस्त 2024 से
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## General

#### मेरा traded volume track क्यों नहीं हुआ?

* Volume numbers update होने में समय लगता है और SubGraph delays के अधीन हैं। कृपया बाद में फिर से check करें
* आपका trade **exactly** [Trading Reward page](https://pancakeswap.finance/trading-reward#rewards-breakdown) पर highlighted trading pair से, fee tier सहित, route होना चाहिए। Trading routes कैसे view करें इसके लिए [यह tutorial](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) देखें
* केवल V3 trading pairs इस program के लिए eligible हैं
* Ethereum और BNB Chain दोनों पर trading reward program के लिए eligible same wallet address उपयोग करें
* यदि किसी pair में आपका trading volume बहुत कम है, तो आप कोई rewards claim करने के लिए eligible नहीं हो सकते
* Third-party trading aggregators का उपयोग करने से trades अन्य liquidity providers के माध्यम से route हो सकती हैं और track नहीं होंगी

#### मैंने बहुत trade किया लेकिन बहुत कम rewards मिलीं, ऐसा क्यों?

Trading reward की राशि उन trades में paid trading fee पर आधारित होती है।

यदि आपकी trades कम fee tier वाले pairs, उदाहरण के लिए 0.01%, के माध्यम से route होती हैं, तो आप अपने trade के लिए बहुत कम fee pay कर रहे हैं। इसलिए rewards की संख्या उसी के अनुरूप कम हो जाएगी।

## Top Traders Campaign

#### क्या campaign जीतने के लिए मुझे पूरे समय required ranking के भीतर रहना होगा?

नहीं, आपको केवल **campaign के अंत में** required ranking से higher ranked होना चाहिए। लेकिन यह recommended है कि higher rank रखें और rank maintain करें। और यह सुनिश्चित करने के लिए अक्सर check back करें कि आप required ranking से बाहर नहीं जा रहे।

#### Ranking किस number पर based है?

Ranking उस rewards की संख्या पर based है जो प्रत्येक user trading करके accumulate करता है। Reward amount उनके trades में paid trading का एक fixed % के बराबर है।

## CAKE Stakers Campaign

#### मेरा address previous campaign के लिए eligible था। यह latest campaign के लिए eligible क्यों नहीं है?

प्रत्येक campaign की अपनी eligibility requirements होती हैं, जैसे snapshot time पर minimum threshold veCAKE amount।

साथ ही, snapshot time प्रत्येक campaign की end time होती है। veCAKE समय के साथ घटते रहने के कारण, आपका veCAKE balance future campaigns के लिए threshold से नीचे गिर सकता है।

आपको अपनी veCAKE बढ़ानी पड़ सकती है। बस page पर दिए गए instructions follow करें।

#### यह क्यों बता रहा है कि मेरे पास additional rewards हैं जो claim नहीं किए जा सकते?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

Snapshot time पर veCAKE की राशि campaign से अर्जित की जा सकने वाली rewards की maximum राशि निर्धारित करेगी। "Max Reward Cap" section से footnote check करें।

जबकि campaign active है, आप किसी भी समय अपनी veCAKE बढ़ा सकते हैं और यह cap raise कर सकते हैं।

#### "veCAKE at snapshot time" क्या है?

veCAKE धीरे-धीरे समय के साथ घटती है क्योंकि remaining lock time कम होती है। इसलिए, IFO iCAKE के समान, एक snapshot veCAKE balance - एक specific time पर veCAKE balance, जो static है - qualification metric के रूप में उपयोग करने के लिए बेहतर suited है।

Trading Reward में, snapshot time प्रत्येक campaign के अंत को refer करती है। इसलिए, आपका "veCAKE balance at snapshot time" का अर्थ है "campaign end time पर आपका veCAKE balance"।

#### "veCAKE at snapshot time" campaign से कैसे related है?

* Snapshot time पर आपका veCAKE balance number required threshold से अधिक है
* आप जो maximum rewards अर्जित कर सकते हैं वह snapshot time पर आपके veCAKE balance के y % से linked है

उदाहरण के लिए:

1. Alice ने day 1 पर 2 साल (104 सप्ताह) के लिए 300 CAKE lock किए। Day 1 पर, Alice का veCAKE balance `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` होगा।
2. Day 1 पर एक trading reward campaign launch किया जाता है, जिसमें threshold veCAKE 100 और 1% reward cap है। Campaign 30 दिनों में समाप्त हो रहा है।
3. 30 दिनों के बाद, Alice की position में लगभग 99.71 सप्ताहों का remaining lock time होगा, इसलिए veCAKE balance `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143` होगा।
4. इसलिए, इस campaign के लिए, Alice का snapshot time पर `143` veCAKE होगा।
5. 143, 100 से अधिक है इसलिए Alice campaign के लिए eligible है, वह trading rewards अर्जित करने के लिए eligible pairs trade करना शुरू कर सकती है।
6. 1% reward cap के साथ, Alice इस campaign से अर्जित कर सकने वाली maximum CAKE राशि `143 * 1% = 1.43` CAKE है।
7. Alice campaign समाप्त होने से पहले किसी भी समय अपनी veCAKE बढ़ा सकती है, या तो अधिक CAKE lock करके, या अपनी position extend करके।

#### Campaign के दौरान मैं snapshot time पर अपनी veCAKE कैसे check करूँ?

आप Trading Reward page पर check कर सकते हैं।

यदि snapshot time पर आपकी veCAKE threshold से कम है या आपकी rewards currently उससे capped हो रही हैं, तो page आपको alert करेगा।

उन cases में, आप page छोड़े बिना अपनी veCAKE बढ़ाने के लिए "Increase veCAKE" button पर click कर सकते हैं।

#### क्या मैं campaign के दौरान अपनी veCAKE बढ़ा सकता/सकती हूँ?

हाँ, आप campaign समाप्त होने से पहले किसी भी समय अपनी veCAKE बढ़ा सकते हैं। आपका "veCAKE at snapshot time" accordingly update होगा।
