# ❓ Bridging FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Bridge करने से पहले

1.  **क्या मैं CAKE Bridge करने के लिए मोबाइल वॉलेट या MetaMask के अलावा अन्य वॉलेट का उपयोग कर सकता/सकती हूं?**

    वर्तमान में, PancakeSwap CAKE Bridging Coinbase Wallet, MetaMask और MetaMask-संगत वॉलेट को सपोर्ट करता है। जल्द ही अधिक वॉलेट समर्थन आने वाला है।

    _सुझाव:_ प्राइवेट की या सीड फ्रेज़ को जोखिम भरे तरीके से कॉपी-पेस्ट करने से बचने के लिए, हम Bridging के लिए डेस्कटॉप वॉलेट एक्सटेंशन के माध्यम से नए वॉलेट बनाने की सलाह देते हैं।
2.  **कोई रूट या टोकन उपलब्ध क्यों नहीं है?**

    कुछ रूट Bridge क्षमता, टोकन समर्थन या तरलता पर निर्भर करते हैं। कृपया बाद में पुनः प्रयास करें या किसी अन्य प्रदाता को आज़माएं। प्रत्येक चेन के लिए उपलब्ध टोकन सीधे Bridge UI में दिखाए जाते हैं।
3.  **Bridging ट्रांजैक्शन सबमिट करते समय मुझे त्रुटि आती है।**

    "MAX" बटन का उपयोग करने की बजाय राशि मैन्युअल रूप से दर्ज करने का प्रयास करें, और यदि आवश्यक हो तो राशि से दशमलव हटा दें।
4.  **मेरे Bridging कोट में "Insufficient X to cover native fee" क्यों दिखता है?**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Bridging के लिए स्रोत चेन के नेटिव टोकन में गैस शुल्क देना होता है, उदाहरण के लिए:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    ट्रांजैक्शन पूरी करने के लिए सुनिश्चित करें कि आपके स्रोत वॉलेट में शुल्क को कवर करने के लिए पर्याप्त नेटिव टोकन हों।
5.  **बटन पर "X CAKE Exceeded" क्यों दिखता है?**

    BSC और Aptos के बीच CAKE Bridging के लिए सुरक्षा सुनिश्चित करने हेतु एक दैनिक क्षमता सीमा है। कम राशि का प्रयास करें या प्रतीक्षा करके बाद में पुनः प्रयास करें। सीमाएं Chefs द्वारा मांग के आधार पर गतिशील रूप से समायोजित की जाती हैं।
6.  **मुझे कोई विशेष टोकन क्यों नहीं मिल रहा?**

    हो सकता है कि टोकन आपके चुने हुए रूट पर समर्थित न हो या उसमें तरलता की कमी हो। कोई अन्य चेन या अलग राशि आज़माएं।
7.  **क्या मैं BNB Chain से Ethereum पर अलग पते पर Bridge कर सकता/सकती हूं?**

    नहीं, सुरक्षा कारणों से, EVM चेन पर Bridging केवल एक ही पते के बीच काम करती है।
8.  **मैं 0.00000001 CAKE से कम Bridge क्यों नहीं कर सकता/सकती?**

    Aptos टोकन, जिसमें Aptos पर CAKE भी शामिल है, में अधिकतम 8 दशमलव स्थान होते हैं। 0.00000001 से कम के ट्रांजैक्शन अस्वीकार या राउंड डाउन किए जाएंगे। यह Ethereum Bridging पर भी लागू होता है। कोई भी शेष राशि आपके स्रोत वॉलेट में बनी रहेगी।

***

## Bridge करने के बाद

1.  **क्या पुष्टि के बाद Bridge ट्रांसफर रद्द किया जा सकता है?**

    नहीं, एक बार शुरू होने के बाद, Bridge ट्रांजैक्शन प्रदाता द्वारा संभाली जाती है और रद्द नहीं की जा सकती। पलटाव के लिए, एक नए ट्रांजैक्शन के माध्यम से संपत्ति को वापस Bridge करें।
2.  **यदि मेरा ट्रांजैक्शन "pending" में अटका है तो क्या करें?**

    Bridging में 30 मिनट तक का समय लग सकता है। संबंधित Bridge प्रदाता के एक्सप्लोरर पर अपने ट्रांजैक्शन हैश से उसकी स्थिति जांचें:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    यदि 60 मिनट के बाद भी pending हो, तो कृपया [सोशल चैनलों](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) के माध्यम से हमारे एडमिन से संपर्क करें।
3. **मुझे अपना CAKE नहीं मिला। मुझे क्या करना चाहिए?**
   * पहली बार Aptos पर CAKE Bridge करते समय, आपको अपना CAKE **मैन्युअल रूप से क्लेम** करना पड़ सकता है। सुनिश्चित करें कि आपके Aptos वॉलेट में गैस के लिए पर्याप्त APT हो। [Aptos Bridging गाइड](https://docs.pancakeswap.finance/bridge/bridging/aptos) और [Aptos विवरण](https://theaptosbridge.com/faq#registering-claiming-assets) देखें।
   * BNB Chain या Ethereum पर Bridge करते समय, कुछ वॉलेट को अपना बैलेंस देखने के लिए आपसे CAKE का टोकन पता मैन्युअल रूप से जोड़ने की आवश्यकता होती है। उदाहरण के लिए, इस [MetaMask गाइड](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) का पालन करें — अन्य वॉलेट में भी इसी तरह की प्रक्रिया होनी चाहिए।
   * यदि 60 मिनट के बाद भी आपको CAKE नहीं दिखता, तो [सोशल चैनलों](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) के माध्यम से हमारे एडमिन से संपर्क करें।
