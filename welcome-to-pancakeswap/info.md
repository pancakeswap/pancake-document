# 📈 Analytics (Info पृष्ठ)

## Info पृष्ठ&#x20;

PancakeSwap की मूल analytics साइट यहाँ देखें: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

सभी core metrics डेटा PCS आंतरिक Indexer से प्राप्त होते हैं, जो कॉन्ट्रैक्ट call होने पर triggered events से डेटा एकत्र करता है।&#x20;

PancakeSwap के आंतरिक indexer में दिनांक आयाम के लिए, हम दैनिक आँकड़ों के लिए अंतर्राष्ट्रीय मानक समय (UTC) का उपयोग करते हैं। इसलिए, जब Dashboard पर क्षैतिज अक्ष कोई तिथि दर्शाता है, तो वह अंतर्राष्ट्रीय मानक समय (UTC) में तिथि को दर्शाता है।<br>

## Core Metrics

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume (ट्रेडिंग वॉल्यूम):** हम प्रत्येक ट्रेडिंग जोड़े के दैनिक डेटा और प्रत्येक टोकन के दैनिक ट्रेडिंग डेटा की निगरानी करते हैं। दैनिक ट्रेडिंग वॉल्यूम की गणना दिन के प्रत्येक टोकन के ट्रेडिंग वॉल्यूम को उसकी कीमत से गुणा करके की जाती है।

**Total Value Locked:** आंतरिक Indexer से सभी pools प्राप्त करें और प्रत्येक pool से reserve\_usd या total\_value\_locked\_usd पढ़ें।&#x20;

**Price:** PCS आंतरिक Indexer में, हम USD-संबंधित कीमतों की गणना के लिए कई base pools का उपयोग करते हैं। प्राथमिक pool stablecoin ट्रेडिंग pool है, जहाँ हम सबसे अधिक वॉल्यूम वाले ट्रेडिंग pool को base pool के रूप में उपयोग करते हैं और ट्रेडिंग वॉल्यूम भार के आधार पर stablecoin की USD कीमत की गणना करते हैं। इसके अलावा, chain के stablecoin के साथ base token का ट्रेडिंग pool भी USD कीमत प्रदान करने के लिए base pool माना जाता है।

_जो टोकन whitelist में नहीं हैं या whitelisted टोकनों के साथ जोड़े नहीं हैं, उन्हें इन गणनाओं से बाहर रखा जाता है।_

<br>
