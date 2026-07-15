# Social Login FAQ

{% hint style="info" %}
अधिक जानकारी के लिए देखें: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 सामान्य अवलोकन

**1. PancakeSwap का social login क्या है और मुझे इसे क्यों उपयोग करना चाहिए?**

Social login आपको अपने **Google**, **X (Twitter)**, **Discord**, या **Telegram** खाते का उपयोग करके PancakeSwap एक्सेस करने देता है — कोई वॉलेट एक्सटेंशन या seed phrase आवश्यक नहीं। पर्दे के पीछे एक self-custodial वॉलेट बनाया जाता है, इसलिए आप तुरंत DeFi आज़मा सकते हैं, यहाँ तक कि छोटी राशियों के साथ भी। यह प्रवेश की बाधा को कम करता है, विशेष रूप से समय-संवेदनशील क्षणों में।

**2. Social login किन चेन का समर्थन करता है?**

आपका social login वॉलेट PancakeSwap द्वारा वर्तमान में समर्थित सभी चेन पर काम करता है:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

सभी वॉलेट **EVM-compatible** हैं और PancakeSwap के माध्यम से इन नेटवर्क पर स्वाभाविक रूप से उपयोग किए जा सकते हैं। यदि आप अन्य चेन (non-EVM सहित) के लिए समर्थन देखना चाहते हैं, तो हमें बताएं!

**3. मैं social login वॉलेट कहाँ उपयोग कर सकता/सकती हूँ?**

आप इसे PancakeSwap web app के माध्यम से किसी भी desktop या mobile **ब्राउज़र** में सीधे उपयोग कर सकते हैं। यह बाहरी वॉलेट ऐप या dApp ब्राउज़र के साथ **compatible नहीं** है।



### 🛠️ वॉलेट सेटअप और उपयोग

**4. वॉलेट कैसे बनाया और सुरक्षित किया जाता है?**

आपका वॉलेट लॉगिन पर स्वचालित रूप से बनाया जाता है और **2-of-2 key share system** का उपयोग करके सुरक्षित किया जाता है। key को पुनर्निर्मित करने और signature उत्पन्न करने के लिए दोनों shares आवश्यक हैं।

share encryption के बारे में अधिक जानकारी के लिए देखें:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. मैं कितने वॉलेट बना सकता/सकती हूँ?**

आपको **प्रति social खाते प्रति dApp एक वॉलेट** मिलता है। उदाहरण के लिए, यदि आप किसी अन्य ऐप पर भी अपना Google login उपयोग करते हैं जो Privy का उपयोग करता है, तो वह एक अलग वॉलेट बनाएगा।



### 🔐 सुरक्षा और गोपनीयता

**6. यदि कोई मेरे डिवाइस को चुरा लेता है तो क्या वे मेरे वॉलेट तक पहुँच सकते हैं?**

नहीं। भले ही कोई आपके डिवाइस तक पहुँच प्राप्त कर ले, उन्हें फिर भी आपके **social login** और (यदि सेट हो) आपके **recovery password** दोनों की आवश्यकता होगी।

**7. PancakeSwap या Privy द्वारा कौन सा डेटा संग्रहीत किया जाता है?**

* PancakeSwap कोई भी wallet-related key shares **संग्रहीत नहीं करता**।
* Privy **encrypted Auth Share और Recovery Share (यदि recovery flow सेट नहीं है)** संग्रहीत करता है।

> यदि आपने recovery सेटअप पूरी नहीं की है, तो आपका Recovery Share डिफ़ॉल्ट रूप से Privy के पास संग्रहीत रहता है। अधिक जानकारी के लिए यहाँ जाएं: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)

### 🔄 Recovery और Session Management

**8. क्या मैं किसी अलग डिवाइस या ब्राउज़र पर एक ही वॉलेट उपयोग कर सकता/सकती हूँ?**

हाँ! बस उसी social खाते से लॉगिन करें। यदि यह एक नया डिवाइस है, तो आप अपने recovery password (यदि सेट किया गया हो) का उपयोग करके recovery प्रक्रिया से गुजरेंगे।

**9. यदि मैं डिवाइस बदलूं तो क्या होता है?**

आपको अपने social खाते से पुनः लॉगिन करने और recovery flow (password सेटअप) से गुजरने के लिए कहा जाएगा। यदि आपने recovery password सेट नहीं किया है, तो social खाते का login पर्याप्त है।

**10. यदि मैं अपना social login और recovery दोनों खो दूं तो क्या होगा?**

यदि आप अपने social खाते और recovery method दोनों तक पहुँच खो देते हैं, तो **आपका वॉलेट recover नहीं किया जा सकता**। कोई seed phrase fallback नहीं है, और private key export वर्तमान में समर्थित नहीं है।

> ⚠️ याद रखें: private key export, यदि भविष्य में सक्षम किया जाए, तो जिस किसी के पास भी है उसे आपके वॉलेट का पूर्ण नियंत्रण देगा — इसे अत्यंत सावधानी के साथ संभालें।

**11. सक्रिय sessions कितने समय तक चलती हैं?**

Sessions 30 **दिनों** तक चलती हैं। उसके बाद, आपको **पुनः लॉगिन** करने और (यदि आवश्यक हो) अपनी recovery credentials फिर से दर्ज करने के लिए कहा जाएगा। एक सक्रिय session के दौरान, आप प्रत्येक action के लिए मैन्युअल अनुमोदन की आवश्यकता के बिना ट्रांजेक्शन कर सकते हैं।



### ⚙️ Compatibility और सीमाएं

**12. क्या मैं वॉलेट export या import कर सकता/सकती हूँ?**

* **Export**: सुरक्षा कारणों से डिफ़ॉल्ट रूप से समर्थित नहीं। यह भविष्य के अपडेट में बदल सकता है।
* **Import**: समर्थित नहीं। आप MetaMask या Phantom जैसे बाहरी वॉलेट import नहीं कर सकते।

**13. क्या मैं इस वॉलेट को WalletConnect का उपयोग करके अन्य dApps से जोड़ सकता/सकती हूँ?**

इस समय नहीं। embedded वॉलेट **केवल PancakeSwap तक सीमित** है। यदि आप इसे अधिक व्यापक रूप से उपयोग करने में रुचि रखते हैं, तो हमें बताएं — भविष्य में विस्तार संभव है।



### 🚀 उन्नत सुविधाएं

**14. क्या social login वॉलेट Account Abstraction का समर्थन करता है?**

हाँ। यह Biconomy आदि जैसे integrations के माध्यम से transaction batching और **gas sponsorship** जैसी **Account Abstraction सुविधाओं** का समर्थन करता है।

**15. Signless ट्रांजेक्शन कैसे सक्षम होते हैं?**

* लॉगिन के बाद, आपकी session 30 **दिनों** तक सक्रिय रहती है। इस दौरान, PancakeSwap आपकी session credentials का उपयोग करके आपकी ओर से ट्रांजेक्शन sign करने के लिए Privy से अनुरोध कर सकता है।
* आपको प्रत्येक action के लिए wallet popup नहीं दिखेगा — सब कुछ पृष्ठभूमि में संभाला जाता है। 30 दिनों के बाद, इस signless अनुभव को जारी रखने के लिए आपको पुनः लॉगिन करना होगा।
