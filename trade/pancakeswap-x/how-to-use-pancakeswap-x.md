# PancakeSwap X का उपयोग कैसे करें

PancakeSwap X सीधे परिचित "Swap" इंटरफ़ेस में बनाया गया है और सभी उपयोगकर्ताओं के लिए डिफ़ॉल्ट रूप से सक्षम है। PancakeSwap X का उपयोग करने के लिए, बस [Swap](https://pancakeswap.finance/swap) पेज पर जाएँ और ट्रेडिंग शुरू करें।

### PancakeSwap X सक्षम करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28470%29.png" alt="" width="375"><figcaption></figcaption></figure>

यदि X सक्षम नहीं है। settings modal खोलने के लिए "Route" में settings आइकन पर क्लिक करें, और फिर routing preference लाने के लिए "Customise Routing" पर क्लिक करें।

"Customize Routing" modal के भीतर, ट्रेड रूट के लिए PancakeSwap X को toggle करने के लिए एक नया switch होगा। इसे चालू करने के लिए बस क्लिक या टैप करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28471%29.png" alt="" width="375"><figcaption></figcaption></figure>

Toggle होने के बाद, आप मुख्य Swap पेज पर वापस जा सकते हैं। यदि वर्तमान Swap PancakeSwap X के लिए उपलब्ध है, तो "Route" सेक्शन में एक indicator दिखाई देगा। मूल्य प्रभाव और शुल्क दोनों 0 होंगे।

कृपया ध्यान दें कि PancakeSwap X सभी swaps के लिए उपलब्ध नहीं है। इसकी उपलब्धता input और output tokens के साथ-साथ trade size और नेटवर्क पर निर्भर करती है। यदि swap PancakeSwap X द्वारा संसाधित नहीं किया जा सकता, तो इसे AMM तरलता पूलों के माध्यम से रूट किया जाएगा।

जब कोई ट्रेड PancakeSwap X के माध्यम से जा रहा हो, तो यह "Route" सेक्शन में highlighted होगा।

### ऑर्डर सबमिट करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28472%29.png" alt="" width="375"><figcaption></figcaption></figure>

ऑर्डर सबमिट करने के लिए, "Swap" पर क्लिक करें, फिर "Confirm Swap" modal में सभी parameters सत्यापित करें। यदि सब कुछ ठीक दिखे, तो आगे बढ़ने के लिए "Confirm Swap" पर क्लिक करें।

यदि आपने input token approve नहीं किया है, तो आपका वॉलेट आपसे approve करने के लिए कहेगा। कृपया ध्यान दें कि PancakeSwap X के माध्यम से swapping के लिए किसी gas token की आवश्यकता नहीं है, लेकिन token spending के लिए approve करने में गैस की आवश्यकता होती है।

Token approval के बाद, ऑर्डर पर signing के लिए एक और wallet popup दिखाई देगा। आगे बढ़ने के लिए बस "Confirm" पर क्लिक करें। कोई गैस लागत या onchain लेनदेन शामिल नहीं होगा।

ऑर्डर सबमिट होने के बाद, एक progress bar के साथ एक modal दिखाई देगा। आप modal बंद कर सकते हैं, जबकि आपका ऑर्डर background में भरा जाता रहेगा।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28473%29.png" alt="" width="367"><figcaption></figcaption></figure>

ध्यान दें कि नियमित AMM DEX तरलता पूल swaps के विपरीत, एक बार PancakeSwap X ऑर्डर सबमिट होने के बाद, तरलता प्रदाताओं को जवाब देने और आपका ऑर्डर भरने में कुछ समय लगेगा। ऑर्डर सफलतापूर्वक भरे जाने तक 2 मिनट तक का समय लग सकता है।

### अपने ऑर्डर की स्थिति ट्रैक करें

अपने ऑर्डर की स्थिति ट्रैक करने के लिए, ऊपर दाएँ wallet dropdown से wallet modal खोलें। ऑर्डरों की सूची लाने के लिए "Transaction" बटन पर क्लिक करें। किसी विशिष्ट ऑर्डर का अधिक विवरण देखने के लिए, बस क्लिक करें और detail modal खोलें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28474%29.png" alt="" width="375"><figcaption></figcaption></figure>

एक बार ऑर्डर सफलतापूर्वक भर जाने पर, आपको ऑर्डर पर एक हरा चेक मार्क दिखाई देगा, जबकि खरीदे गए टोकन स्वतः आपके वॉलेट में भेज दिए जाएंगे।
