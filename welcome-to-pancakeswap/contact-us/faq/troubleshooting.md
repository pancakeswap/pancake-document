---
description: सामान्य त्रुटि संदेश। जो त्रुटि आ रही है उस पर जाने के लिए साइडबार ➡️ का उपयोग करें।
---

# त्रुटि समाधान

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

कभी-कभी आपको ऐसी समस्या का सामना करना पड़ सकता है जिसका कोई स्पष्ट समाधान नहीं दिखता। ये समाधान सुझाव आपको आने वाली समस्याओं को सुलझाने में मदद कर सकते हैं।

## **एक्सचेंज पर समस्याएँ**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

आप टोकन स्वैप करने की कोशिश कर रहे हैं, लेकिन आपकी स्लिपेज सीमा बहुत कम है या तरलता बहुत कम है।

{% tabs %}
{% tab title="समाधान" %}
1. अपना पृष्ठ रिफ्रेश करें और बाद में पुनः प्रयास करें।
2. एक बार में कम मात्रा में व्यापार करने का प्रयास करें।
3. अपनी स्लिपेज सहिष्णुता बढ़ाएँ:
   1. तरलता पृष्ठ पर सेटिंग आइकन पर टैप करें।
   2. अपनी स्लिपेज सहिष्णुता थोड़ी बढ़ाएँ और पुनः प्रयास करें। ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. अंत में, कम दशमलव स्थानों वाली राशि दर्ज करने का प्रयास करें।
{% endtab %}

{% tab title="कारण" %}
**यह आमतौर पर कम तरलता वाले टोकनों के व्यापार के समय होता है।**

इसका अर्थ है कि तरलता पूल में उस टोकन की पर्याप्त मात्रा नहीं है जिसे आप स्वैप करना चाहते हैं: यह संभवतः एक छोटे बाज़ार पूंजीकरण वाला टोकन है जिसका बहुत कम व्यापार होता है।

हालाँकि, यह भी संभव है कि आप किसी स्कैम टोकन का व्यापार करने की कोशिश कर रहे हों जिसे बेचा नहीं जा सकता। ऐसे में PancakeSwap किसी टोकन को ब्लॉक करने या धनराशि वापस करने में असमर्थ है।
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

आप किसी तरलता पूल (LP) में तरलता जोड़ने/हटाने की कोशिश कर रहे हैं, लेकिन जोड़े में से एक टोकन की पर्याप्त मात्रा नहीं है।

{% tabs %}
{% tab title="समाधान" %}
**अपना पृष्ठ रिफ्रेश करें और पुनः प्रयास करें, या बाद में प्रयास करें।**

फिर भी काम नहीं कर रहा?

1. तरलता पृष्ठ पर सेटिंग आइकन पर टैप करें।
2. अपनी स्लिपेज सहिष्णुता थोड़ी बढ़ाएँ और पुनः प्रयास करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="कारण" %}
यह त्रुटि तब होती है जब आप किसी तरलता पूल (LP) में token A या token B (जोड़े में से एक टोकन) की अपर्याप्त मात्रा के साथ तरलता जोड़ने या हटाने का प्रयास करते हैं।

हो सकता है कि कीमतें बहुत तेज़ी से बदल रही हों और आपकी स्लिपेज सहिष्णुता बहुत कम हो।

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="तकनीकी समाधान" %}
ठीक है, तो आप इसे वाकई हल करने पर दृढ़ हैं। हम वास्तव में इसकी अनुशंसा नहीं करते जब तक आप जानते न हों कि आप क्या कर रहे हैं।

PancakeSwap वेबसाइट से इस समस्या को हल करने का अभी कोई सरल तरीका नहीं है: आपको कॉन्ट्रैक्ट के साथ सीधे इंटरैक्ट करना होगा। आप Router कॉन्ट्रैक्ट के माध्यम से सीधे तरलता जोड़ सकते हैं, amountAMin को एक छोटे मूल्य पर सेट करके, फिर सारी तरलता निकाल सकते हैं।

**LP कॉन्ट्रैक्ट को अनुमोदित करें**

उस LP टोकन के कॉन्ट्रैक्ट पर जाएँ जिसे आप अनुमोदित करना चाहते हैं।\
उदाहरण के लिए, यहाँ ETH/WBNB जोड़ा है: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. **Write Contract** चुनें, फिर **Connect to Web3** पर क्लिक करें और अपना वॉलेट कनेक्ट करें। ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. **"1. approve" अनुभाग में,** निम्न दर्ज करके Router के लिए LP टोकन को अनुमोदित करें:
   1. spender (address): उस LP टोकन का कॉन्ट्रैक्ट पता दर्ज करें जिसके साथ आप इंटरैक्ट करना चाहते हैं
   2. value (uint256): -1

**"balanceOf" क्वेरी करें**

1. **Read Contract** पर जाएँ।
2. **5. balanceOf** में, अपना वॉलेट पता दर्ज करें और **Query** पर क्लिक करें।
3. जो नंबर दिखे उसे नोट करें। यह uint256 प्रारूप में आपका LP बैलेंस दर्शाता है, जिसकी अगले चरण में आवश्यकता होगी।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**तरलता जोड़ें या हटाएँ**

Router कॉन्ट्रैक्ट पर जाएँ: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. ऊपर की तरह **Write Contract** और **Connect to Web3** चुनें।
2. **addLiquidity** या **removeLiquidity** ढूँढें (जो भी आप करना चाहते हैं)
3. LP में दोनों टोकनों के टोकन पते दर्ज करें।
4. **liquidity (uint256)** में, ऊपर "balanceOf" से मिला uint256 नंबर दर्ज करें।
5. **amountAMin** या **amountBMin** कम सेट करें: दोनों के लिए 1 आज़माएँ।
6. **to (address)** में अपना वॉलेट पता जोड़ें।
7. Deadline एक epoch time होनी चाहिए जो tx निष्पादन के समय से अधिक हो।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
इससे बहुत अधिक स्लिपेज हो सकती है, और यदि फ्रंटरनिंग हो तो उपयोगकर्ता को कुछ धनराशि का नुकसान हो सकता है
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

पुनः प्रयास करें, लेकिन ट्रांजैक्शन उत्पन्न होने के तुरंत बाद उसे कन्फर्म (साइन और ब्रॉडकास्ट) करें।

यह इसलिए हुआ क्योंकि आपने ट्रांजैक्शन शुरू किया, लेकिन समयसीमा पार होने तक इसे साइन और ब्रॉडकास्ट नहीं किया। अर्थात आपने पर्याप्त तेज़ी से "Confirm" नहीं दबाया।

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

"To" फ़ील्ड में राशि बदलने का प्रयास करें, जिससे "From" पर "(estimated)" प्रतीक आ जाए। फिर तुरंत स्वैप शुरू करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

यह आमतौर पर तब होता है जब आप अपनी स्वयं की शुल्क वाले टोकन को स्वैप करने की कोशिश कर रहे हों।

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

अपने वॉलेट में व्यापार करने की इच्छित राशि से 30% अधिक टोकन रखें, या कम मात्रा में व्यापार करने का प्रयास करें। यदि आप अधिकतम बेचना चाहते हैं, तो 100% के बजाय 70% या 69% आज़माएँ।\
यह tDoge या tBTC जैसे Restorative Rebase टोकनों के डिज़ाइन के कारण होता है।\
[रिस्टोरेटिव रीबेस टोकन कैसे काम करते हैं, यह समझें](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)।

इस समस्या का एक अन्य संभावित कारण यह हो सकता है कि दुर्भावनापूर्ण टोकन जारीकर्ता ने अपने टोकन का व्यापार निलंबित कर दिया हो। या उन्होंने केवल चुनिंदा वॉलेट पतों के लिए बिक्री संभव बनाई हो। किसी भी संभावित धोखे से बचने के लिए कृपया हमेशा अपना स्वयं का शोध करें। यदि आप जिस टोकन को स्वैप करने का प्रयास कर रहे हैं वह एयरड्रॉप से आया है और इस त्रुटि के साथ विफल हो रहा है, तो यह अधिकतर एक स्कैम है। कृपया कोई भी टोकन अनुमोदन न करें और किसी लिंक का अनुसरण न करें, ऐसा करने पर आपकी धनराशि जोखिम में पड़ सकती है।

### ट्रांजैक्शन सफल नहीं हो सकता

कम मात्रा में व्यापार करने का प्रयास करें, या सेटिंग आइकन के माध्यम से स्लिपेज सहिष्णुता बढ़ाएँ और पुनः प्रयास करें। यह कम तरलता के कारण होता है।

### **Price Impact बहुत अधिक है**

कम मात्रा में व्यापार करने का प्रयास करें, या सेटिंग आइकन के माध्यम से स्लिपेज सहिष्णुता बढ़ाएँ और पुनः प्रयास करें। यह कम तरलता के कारण होता है।

### estimateGas विफल

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="समाधान" %}
**यदि BNB जोड़े से तरलता हटाते समय यह त्रुटि आई:**

कृपया "Receive WBNB" चुनें और पुनः प्रयास करें।

**यदि स्वैप करने की कोशिश में यह त्रुटि आई:**

कृपया उस टोकन की प्रोजेक्ट टीम से संपर्क करें जिसे आप स्वैप करने की कोशिश कर रहे हैं। \*\*\*\* इस समस्या को प्रोजेक्ट टीम द्वारा हल किया जाना आवश्यक है।
{% endtab %}

{% tab title="कारण" %}
**यह समस्या (स्वैप के दौरान) उन टोकनों के कारण होती है जिन्होंने अपने कॉन्ट्रैक्ट में V1 PancakeSwap router को हार्ड-कोड किया हुआ है।**

हालाँकि यह प्रथा अच्छी नहीं है, इन परियोजनाओं ने ऐसा अपने टोकनोमिक्स के कारण किया प्रतीत होता है, जिसमें प्रत्येक खरीदारी से टोकन का एक प्रतिशत LP को भेजा जाता है।

प्रभावित परियोजनाएँ संभवतः V2 router के साथ काम नहीं करेंगी: उन्हें नए router पते की ओर इशारा करते हुए अपने टोकनों के नए संस्करण बनाने होंगे, और मौजूदा टोकन धारकों को नए टोकन पर स्थानांतरित करना होगा।

हम अनुशंसा करते हैं कि ऐसे टोकन बनाने वाली परियोजनाएँ अपने उपयोगकर्ताओं को उन्हें V2 LP में जोड़ने से रोकने के प्रयास भी करें।

अद्यतन router पता है: [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

टोकन स्वैप करने की कोशिश में ट्रांजैक्शन विफल हो जाता है और यह त्रुटि संदेश दिखता है। यह त्रुटि Trust Wallet का उपयोग करने वाले मोबाइल उपकरणों पर रिपोर्ट की गई है।

{% tabs %}
{% tab title="समाधान" %}
1. बढ़ी हुई स्लिपेज अनुमति के साथ पुनः ट्रांजैक्शन का प्रयास करें।
2. यदि 1. से समस्या हल न हो, तो अपने ट्रांजैक्शन के लिए SafePal जैसे किसी अन्य वॉलेट का उपयोग करने पर विचार करें।
{% endtab %}

{% tab title="कारण" %}
**यह आमतौर पर Trust Wallet पर अपर्याप्त स्लिपेज अनुमति के साथ टोकनों का व्यापार करते समय होता है।**

समस्या के सटीक विवरण की अभी भी जाँच की जा रही है।
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

टोकन स्वैप करने की कोशिश में ट्रांजैक्शन विफल हो जाता है और यह त्रुटि संदेश दिखता है। यह त्रुटि विभिन्न प्लेटफॉर्म पर रिपोर्ट की गई है।

{% tabs %}
{% tab title="समाधान" %}
1. सुनिश्चित करें कि आपके पास पर्याप्त धनराशि उपलब्ध है।
2. सुनिश्चित करें कि आपने कॉन्ट्रैक्ट को उतनी धनराशि खर्च करने की अनुमति दी है जितने से आप व्यापार करने का प्रयास कर रहे हैं।
{% endtab %}

{% tab title="कारण" %}
यह त्रुटि तब होती है जब अपर्याप्त allowance के साथ टोकनों का व्यापार किया जाता है, या जब वॉलेट में अपर्याप्त धनराशि हो।\
यदि आप tau assets जैसे tDoge या tBTC के साथ Restorative Rebase वाले टोकनों का व्यापार कर रहे हैं, तो पहले इस [रीबेस टोकन गाइड](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c) से समझें कि वे कैसे काम करते हैं।
{% endtab %}
{% endtabs %}

## **Farm से जुड़ी समस्याएँ**

### Fail with error 'ds-math-sub-underflow'

आपके MasterChef कॉन्ट्रैक्ट में LP टोकन allowance समाप्त हो गई है।

**Unrekt या BscScan जैसे टोकन approval manager का उपयोग करें**

## **Syrup Pools से जुड़ी समस्याएँ**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

CAKE-CAKE pool से unstake करने के लिए आपके वॉलेट में पर्याप्त SYRUP नहीं है।

**कम से कम उतनी मात्रा में SYRUP प्राप्त करें जितना CAKE आप unstake करना चाहते हैं।**

1. एक्सचेंज पर SYRUP खरीदें। यदि आप 100 CAKE unstake करना चाहते हैं, तो आपको कम से कम 100 SYRUP चाहिए।
2. पुनः unstake का प्रयास करें।

यदि वह भी विफल हो, तो आप अपने stake किए हुए टोकनों को unstake करने के लिए कॉन्ट्रैक्ट से सीधे "emergencyWithdraw" कर सकते हैं।

1. यहाँ जाएँ: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. **"Connect to Web3"** पर क्लिक करें और अपना वॉलेट कनेक्ट करें। ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. **"4. emergencyWithdraw"** अनुभाग में "0" दर्ज करें और "Write" पर क्लिक करें।

इससे आपके stake किए हुए टोकन unstake हो जाएंगे और कोई भी संग्रहीत न किया गया CAKE yield खो जाएगा।

{% hint style="warning" %}
**इससे वह yield खो जाएगी जो आपने अभी तक harvest नहीं की है।**
{% endhint %}

इसे फिर से होने से रोकने के लिए, **अपना SYRUP न बेचें।** "Stake CAKE Earn CAKE" pool से unstake करने के लिए आपको इसकी अभी भी ज़रूरत है।

यह त्रुटि इसलिए हुई क्योंकि आपने SYRUP टोकन बेचे या ट्रांसफर किए। CAKE-CAKE Syrup Pool में stake करने पर 1:1 अनुपात में SYRUP मिंट होता है। leaveStaking (pool से CAKE unstake करते समय) को call करते समय 1:1 अनुपात में SYRUP burn होना ज़रूरी है, इसलिए यदि पर्याप्त नहीं है तो आप pool से unstake नहीं कर सकते।

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### गैस समाप्त (Out of Gas) त्रुटि

> Warning! Error encountered during contract execution \[out of gas]

ट्रांजैक्शन करते समय आपने बहुत कम gas limit सेट की है।

{% tabs %}
{% tab title="समाधान" %}
ट्रांजैक्शन साइन करने से पहले अपने वॉलेट में **gas limit** (gas price नहीं!) को मैन्युअल रूप से बढ़ाने का प्रयास करें।

200000 की सीमा आमतौर पर पर्याप्त होती है।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

उपरोक्त उदाहरण Metamask से है; यदि आप gas limit समायोजित करने का तरीका नहीं जानते तो अपने वॉलेट के दस्तावेज़ देखें।
{% endtab %}

{% tab title="कारण" %}
मूल रूप से, आपका वॉलेट (Metamask, Trust Wallet, आदि) जो करने की कोशिश कर रहा है उसे पूरा नहीं कर पाता।

आपका वॉलेट अनुमान लगाता है कि gas limit बहुत कम है, इसलिए फ़ंक्शन कॉल पूरी होने से पहले ही गैस खत्म हो जाती है।
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="समाधान" %}
1. Unrekt.net का उपयोग करके उस स्मार्ट कॉन्ट्रैक्ट की approval रद्द करें जिसके साथ आप इंटरैक्ट करने की कोशिश कर रहे हैं
2. कॉन्ट्रैक्ट को पुनः अनुमोदित करें, लेकिन इस बार खर्च allowance पर कोई सीमा न लगाएँ
3. कॉन्ट्रैक्ट के साथ इंटरैक्ट करने का पुनः प्रयास करें।
{% endtab %}

{% tab title="कारण" %}
यह तब होता है जब आपने पहली बार कॉन्ट्रैक्ट को अनुमोदित करते समय खर्च allowance पर एक सीमा निर्धारित की थी, और अब उस सीमा से अधिक स्वैप करने की कोशिश कर रहे हैं।
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

आप संभवतः किसी ऐसे Syrup Pool से unstake करने की कोशिश कर रहे हैं जिसमें कम पुरस्कार बचे हैं। नीचे समाधान देखें।

यदि नहीं, तो हो सकता है कि आप ऐसे टोकन भेजने की कोशिश कर रहे हों जो आपके वॉलेट में नहीं हैं (उदाहरण के लिए, कोई टोकन जो पहले से किसी pending ट्रांजैक्शन में असाइन है)। ऐसे में बस सुनिश्चित करें कि आपके पास वे टोकन हैं जिनका आप उपयोग करना चाहते हैं।

{% tabs %}
{% tab title="समाधान" %}
पहले, [टीम को बताएँ](../social-accounts.md) कि आप किस pool से unstake करने की कोशिश कर रहे हैं, ताकि वे पुरस्कार फिर से भर सकें। यदि आप जल्दी unstake करना चाहते हैं और pending yield खोने से कोई आपत्ति नहीं है, तो emergencyWithdraw आज़माएँ:

आप अपने stake किए हुए टोकनों को unstake करने के लिए कॉन्ट्रैक्ट से सीधे "emergencyWithdraw" कर सकते हैं।

1. जिस Syrup Pool से आप unstake करने की कोशिश कर रहे हैं उसका कॉन्ट्रैक्ट पता खोजें। यह आपके वॉलेट के ट्रांजैक्शन लॉग में मिलेगा।
2. [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) पर जाएँ और खोज बार में कॉन्ट्रैक्ट पता दर्ज करें।
3. **Write Contract** चुनें।
4. **"Connect to Web3"** पर क्लिक करें और अपना वॉलेट कनेक्ट करें।![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. **"3. emergencyWithdraw"** अनुभाग में, "Write" पर क्लिक करें।

इससे आपके stake किए हुए टोकन unstake हो जाएंगे और कोई भी संग्रहीत न की गई yield खो जाएगी।

{% hint style="warning" %}
**इससे वह yield खो जाएगी जो आपने अभी तक harvest नहीं की है।**
{% endhint %}
{% endtab %}

{% tab title="कारण" %}
यह त्रुटि आमतौर पर तब आती है जब आप किसी पुराने Syrup Pool से unstake करने की कोशिश करते हैं, लेकिन निकासी के समय harvest के लिए pool में पर्याप्त पुरस्कार नहीं बचे होते। इससे ट्रांजैक्शन विफल हो जाती है।
{% endtab %}
{% endtabs %}

## **प्रेडिक्शन से जुड़ी समस्याएँ**

[Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention") देखें

## **अन्य समस्याएँ**

### Provider Error

> Provider Error\
> No provider was found

यह तब होता है जब आप MetaMask या Binance Chain Wallet जैसे ब्राउज़र एक्सटेंशन के माध्यम से कनेक्ट करने की कोशिश करते हैं, लेकिन आपने एक्सटेंशन इंस्टॉल नहीं किया है।

{% tabs %}
{% tab title="समाधान" %}
कनेक्ट करने के लिए आधिकारिक ब्राउज़र एक्सटेंशन इंस्टॉल करें, या [PancakeSwap से वॉलेट कैसे कनेक्ट करें](https://docs.pancakeswap.finance/get-started/connection-guide) पर हमारी गाइड पढ़ें।
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

अपनी chain को BNB Smart Chain पर स्विच करें। यदि आपको सहायता की आवश्यकता हो तो अपने वॉलेट के दस्तावेज़ में गाइड देखें।

### Already processing eth\_requestAccounts. Please wait.

सुनिश्चित करें कि आप अपने वॉलेट ऐप में साइन इन हैं और वह BNB Smart Chain से कनेक्ट है।

### SAFEMOON और इसी प्रकार के टोकन खरीदने में समस्याएँ

SAFEMOON का व्यापार करने के लिए, आपको सेटिंग आइकन पर क्लिक करके **अपनी स्लिपेज सहिष्णुता 12% या अधिक सेट करनी होगी।**\
यह इसलिए है क्योंकि **SafeMoon प्रत्येक ट्रांजैक्शन पर 10% शुल्क लगाता है**:

* 5% शुल्क = सभी मौजूदा धारकों में पुनर्वितरित
* 5% शुल्क = तरलता जोड़ने के लिए उपयोग

यही कारण है कि खरीदारी पर आपको उतने टोकन नहीं मिलते जितनी आप उम्मीद करते हैं।\
[How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742) पर अधिक पढ़ें।

### Internal JSON-RPC त्रुटियाँ

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

यह कुछ टोकनों पर Metamask के माध्यम से तरलता हटाने की कोशिश करते समय होता है। मूल कारण अभी अज्ञात है। किसी वैकल्पिक वॉलेट का उपयोग करने का प्रयास करें।

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

ट्रांजैक्शन शुल्क का भुगतान करने के लिए आपके पास पर्याप्त BNB नहीं है। आपको अपने वॉलेट में अधिक BEP-20 नेटवर्क BNB की आवश्यकता है।

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

अपने वॉलेट में ट्रांजैक्शन के लिए gas limit बढ़ाएँ। gas limit बढ़ाने का तरीका जानने के लिए अपने वॉलेट के दस्तावेज़ देखें।

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

कारण अस्पष्ट है। पुनः प्रयास करने से पहले ये चरण आज़माएँ:

1. gas limit बढ़ाएँ
2. स्लिपेज बढ़ाएँ
3. कैश साफ़ करें

## **Profile से जुड़ी समस्याएँ**

### अरे! आपके वॉलेट में कोई Pancake Collectibles नहीं मिले।

हम इस समस्या के पीछे के तर्क की जाँच कर रहे हैं। इस बीच कृपया नीचे दिया गया वैकल्पिक उपाय आज़माएँ।

{% tabs %}
{% tab title="वैकल्पिक उपाय 1" %}
1. "Collectible" पृष्ठ पर जाएँ, फिर वापस profile पृष्ठ पर आएँ।\
   यदि लिंक नहीं मिल रहा, तो [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) पर सीधे जाएँ।
2. Profile बनाने का पुनः प्रयास करें।
{% endtab %}

{% tab title="वैकल्पिक उपाय 2" %}
परिवेश बदलें।

* कैश साफ़ करें और पुनः प्रयास करें।
* किसी अन्य ब्राउज़र पर पुनः प्रयास करें।
* किसी अन्य वॉलेट ऐप पर पुनः प्रयास करें।
* किसी भिन्न नेटवर्क पर पुनः प्रयास करें (Wi-Fi और मोबाइल डेटा के बीच स्विच करें)
{% endtab %}
{% endtabs %}

### Username जाँचना लगातार चलता रहता है

दो संभावित कारण हो सकते हैं।

1. आपके ब्राउज़र में एकाधिक वॉलेट इंस्टॉल हैं।
2. नेटवर्क समस्या।

{% tabs %}
{% tab title="समाधान 1" %}
मूल कारण: आपके ब्राउज़र में एकाधिक वॉलेट इंस्टॉल हैं।\
\
इससे वॉलेटों के बीच संघर्ष हो सकता है। यह PancakeSwap के नियंत्रण से बाहर है और हम कुछ नहीं कर सकते।

1. ब्राउज़र में केवल एक ही वॉलेट रखें, बाकी हटा दें।
2. वॉलेट को फिर से कनेक्ट करें और username सेट करने का पुनः प्रयास करें।
{% endtab %}

{% tab title="समाधान 2" %}
मूल कारण: नेटवर्क अस्थिर है।

आपको पुनः प्रयास करना होगा।

1. टेक्स्ट फ़ील्ड में जो कुछ भी दर्ज है उसे पूरी तरह हटा दें।
2. Username फिर से टाइप करें, फिर कुछ सेकंड प्रतीक्षा करें।
3. यदि काम न करे, तो पृष्ठ पुनः लोड करें और पुनः प्रयास करें।
{% endtab %}
{% endtabs %}
