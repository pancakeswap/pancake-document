---
hidden: true
---

# Degen Mode

Degen Trading Mode ट्रेडर्स को पारंपरिक ट्रेडिंग तरीकों की तुलना में व्यापार करने का एक वैकल्पिक तरीका प्रदान करता है। जो ट्रेडर बाजार का विश्लेषण करने में स्क्रीन समय कम करना पसंद करते हैं और अधिक hands-off दृष्टिकोण रखते हैं, वे इस ट्रेडिंग मोड को चुन सकते हैं। उच्च अस्थिरता की अवधि के दौरान, ट्रेडर 0 स्लिपेज, उच्च लीवरेज और अत्यंत कम शुल्क के साथ अपने लाभ को अधिकतम कर सकते हैं। कम अस्थिरता में, ट्रेडर मामूली मूल्य आंदोलनों पर अनुमान लगा सकते हैं।

प्रारंभ में, Degen Trading Mode BTCUSD के लिए उपलब्ध होगा, जो long और short market orders के लिए 1001x की अधिकतम लीवरेज का समर्थन करेगा। ट्रेडर्स को zero स्लिपेज के साथ पोजीशन खोलने से पहले principal (संपार्श्विक राशि) इनपुट करना होगा।

Degen mode Perpetuals V2 पर BNB Chain, Arbitrum, opBNB और Base chain दोनों पर उपलब्ध है।

### Degen Mode प्रारूप

Degen mode हमारे perpetual ट्रेडर्स को निम्नलिखित gameplay विशेषताएं और लाभ प्रदान करता है:

**उच्च लीवरेज, कम अग्रिम संपार्श्विक -** 1001x के उच्च लीवरेज के साथ, उपयोगकर्ता Degen Mode के माध्यम से भाग ले सकते हैं और अपनी ट्रेडिंग रणनीतियों को बढ़ा सकते हैं। उपयोगकर्ता अब महत्वपूर्ण अग्रिम संपार्श्विक के बिना उच्च upside का आनंद ले सकते हैं।

**कम शुल्क -** Zero-slippage ट्रेडिंग के साथ, उपयोगकर्ता बेहतर ट्रेडिंग अनुभव का आनंद ले सकते हैं। उपयोगकर्ताओं से open position fees नहीं लिया जाता। इससे उपयोगकर्ताओं का ट्रेडिंग upside बढ़ता है क्योंकि open position fees को अब संपार्श्विक के रूप में बचाया और उपयोग किया जा सकता है।

**Dynamic Fee Structure -** विशेष रूप से Degen Mode के लिए तैयार, closing positions के लिए Dynamic Fee Structure को Profit and Loss (PnL) के आधार पर शुल्क लेने के लिए सावधानीपूर्वक डिज़ाइन किया गया है। dynamic fee structure के बारे में अधिक जानकारी के लिए [यहां](degen-mode-dynamic-fee.md) देखें।

**जोड़ी प्रस्ताव -** Degen Mode BNB Chain, Arbitrum, opBNB और Base chain पर BTCUSD के लिए उपलब्ध है।

### यह कैसे काम करता है

1. [https://perp.pancakeswap.finance/en/futures/v2/](https://perp.pancakeswap.finance/en/futures/v2/) पर जाएं या हमारे होम पेज पर "Perpetuals" चुनें।
2. स्क्रीन के ऊपरी दाईं ओर, "Long" या "Short" पोजीशन चुनें और 1001x leverage चुनने के लिए leverage editor पर क्लिक करें।
3. मात्रा और उचित leverage चुनें।
4. take profit राशि (50% से 300% के बीच) चुनें और **open position** चुनें।
5. आपकी पोजीशन स्क्रीन के नीचे "positions" टैब में दिखाई देगी।
6. पोजीशन बंद करने के लिए, पोजीशन की साइड में "close" बटन दबाएं। अन्यथा, Degen Mode close take profit या लिक्विडेशन अवधि पर स्वचालित रूप से निष्पादित होगा। अधिक जानकारी के लिए, कृपया [perpetuals-glossary.md](../perpetuals-glossary.md "mention") और [perpetual-trading-faq](../perpetual-trading-faq/ "mention") देखें।
