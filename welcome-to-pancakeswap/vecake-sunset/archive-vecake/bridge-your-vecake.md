# अपना veCAKE Bridge करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

अन्य chains पर veCAKE के लाभ जैसे bCAKE (Farm yield boosting) और iCAKE (IFO public sales allocation) का आनंद लेने के लिए, आपको BNB Chain पर एक सरल bridging request करनी होगी ताकि आपका veCAKE balance और PancakeProfile अन्य chains पर sync हो सके।

## Bridge कैसे करें? <a href="#id-734b8113-0e00-40ff-bccb-9c129460e2e2" id="id-734b8113-0e00-40ff-bccb-9c129460e2e2"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29.png" alt=""><figcaption></figcaption></figure>

[CAKE Staking](https://pancakeswap.finance/cake-staking) पेज पर जाएं और veCAKE benefits के अंतर्गत veCAKE Sync card खोजें। Sync modal खोलने के लिए "View Details" पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

Modal में, आप BNB Chain पर अपने veCAKE की संख्या देख सकते हैं। साथ ही destination chains की सूची भी है, जहाँ आप अपना veCAKE और Pancake Profile bridge कर सकते हैं और प्रत्येक chain पर अपनी veCAKE और Pancake Profile स्थिति देख सकते हैं।

Sync करने के लिए, chain चुनें और "Sync" पर क्लिक करें, फिर अपने वॉलेट popup में पुष्टि करें।

Bridging पूरी होने में 20 मिनट तक का समय लग सकता है। आप sync modal में bridging की प्रगति जाँच सकते हैं।&#x20;

नोट:

* आप एक बार में केवल एक chain bridge कर सकते हैं। अपने veCAKE को कई chains पर sync करने के लिए, उपरोक्त प्रक्रिया दोहराएं।
* Bridging request पर destination chain की gas cost को cover करने के लिए BNB चार्ज किया जाएगा। BNB की राशि destination chain पर निर्भर करती है। Ethereum mainnet जैसी chains पर उच्च gas cost के कारण sync काफी अधिक महंगी होगी।
* अनावश्यक gas खर्च से बचने के लिए, अपना veCAKE केवल उस chain पर sync करें जहाँ आप लाभ उठाना चाहते हैं।
* अधिक CAKE जोड़ने या अपनी veCAKE staking position बढ़ाने के बाद, destination chains पर veCAKE balance को अपडेट करने के लिए उपरोक्त प्रक्रिया दोहराएं ताकि आपके लाभ अद्यतित रहें।

## अक्सर पूछे जाने वाले सवाल (FAQ) <a href="#id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad" id="id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad"></a>

**प्रश्न: मुझे अपना veCAKE और Pancake Profile कितनी बार sync करने की आवश्यकता है?**

उत्तर: veCAKE के लिए, आपको तभी sync करना होगा जब आप अधिक CAKE जोड़ें, lock duration बढ़ाएं या relock करें। Destination chains पर आपका veCAKE balance BNB Chain के balance के साथ-साथ रैखिक रूप से घटता रहेगा।

Pancake Profile और उसके NFT के लिए, Private Sales में भाग लेने के लिए आपको दो बार sync करना होगा। पहली बार तब जब IFO प्रकाशित हो और UI पर दिखने लगे। दूसरी बार IFO sale समाप्त होने के बाद claiming सक्षम करने के लिए।

**प्रश्न: Bridging में कितना समय लगता है?**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

Destination chain पर निर्भर करता है। Bridge होने और पूरी तरह sync होने में आमतौर पर 2-5 मिनट लगते हैं। कुछ धीमी chains के लिए, 30 मिनट तक का समय लग सकता है। अपनी bridging request track करने के लिए, sync modal में LayerZero explorer link देखें। या [https://layerzeroscan.com/](https://layerzeroscan.com/) पर जाएं और BNB Chain tx id से खोजें।

**प्रश्न: BNB Chain पर bridging tx क्यों fail हो रही है?**

उत्तर:

* ऐसा हो सकता है क्योंकि destination chain का gas estimation पुराना हो गया है। कृपया पेज refresh करें और पुनः प्रयास करें।
* यह भी सुनिश्चित करें कि destination chain पर आवश्यक gas fee के लिए वॉलेट में पर्याप्त BNB हो।

**प्रश्न: मेरा veCAKE या Pancake Profile bridge क्यों नहीं हुआ?**

उत्तर:

* जिस veCAKE position में 1 दिन से कम remaining lock time हो, उसे bridge नहीं किया जाएगा। कृपया पहले lock बढ़ाएं और sync पुनः प्रयास करें।
* Sync पूरी होने में 30 मिनट तक का समय लग सकता है। कृपया https://layerzeroscan.com/ पर जाएं और BNB Chain tx ID से खोजकर पुष्टि करें कि bridging status "Delivered" है।
* यदि bridging status "Failed" या "Blocked" है, तो अधिक जानकारी के लिए public channel पर हमारे किसी ambassador से संपर्क करें।
