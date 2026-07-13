---
description: CAKE emission का वितरण तय करने के लिए अपने veCAKE से vote करें
hidden: true
---

# Gauges Voting

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Gauge क्या है?

Gauges voting को समझने के लिए, आप CAKE emissions की आवश्यकता वाले किसी भी उत्पाद को gauges की एक श्रृंखला के रूप में सोच सकते हैं। इसमें farms, CAKE weekly reward pool, position manager vaults आदि शामिल हैं।

veCAKE holders अब अपने veCAKE का उपयोग votes के रूप में यह तय करने के लिए कर सकते हैं कि CAKE का कितना % किस उत्पाद को जाता है। Gauges Voting के माध्यम से एक gauge जितना अधिक veCAKE जमा करता है, उतने अधिक CAKE emissions उस अंतर्निहित तरलता पूल / position manager vault को आवंटित किए जाएंगे।

{% hint style="info" %}
प्रत्येक epoch (E-0) के votes अगले epoch (E+1) के लिए CAKE emission निर्धारित करते हैं, और ये परिवर्तन केवल वर्तमान epoch समाप्त होने के बाद ही लागू होते हैं।
{% endhint %}

#### Gauge Types

दो प्रकार के gauges हैं - 'core' और 'non-core'। पहले प्रकार को CAKE emissions Kitchen द्वारा नियंत्रित की जाती हैं, जबकि community veCAKE के साथ vote करके 'non-core' pools को emissions को प्रभावित करती है।

1. 'Core' gauges में प्रमुख tokens और stablecoins (WBTC, ETH, BNB, USDC, USDT, आदि) के pairs शामिल हैं - Kitchen यह सुनिश्चित करेगा कि इन pairs को पर्याप्त CAKE rewards मिलें क्योंकि ये protocol की revenue में महत्वपूर्ण योगदान देते हैं।
2. 'Non-core' gauges वे सभी gauges हैं जो 'core' gauges के रूप में वर्गीकृत नहीं हैं।

## Vote कैसे करें?

### 1 - Voting schedule समझें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Gauges weight voting हर दो सप्ताह में आयोजित होती है। एक epoch की शुरुआत, revenue sharing की तरह, हर सम गुरुवार को 00:00 UTC पर होती है।

उपरोक्त उदाहरण में:

* Epoch 1 सप्ताह 1 में पहले गुरुवार, 00:00 UTC पर शुरू होती है।
* Epoch 1 दो सप्ताह बाद, सप्ताह 3 में 15वें गुरुवार को 00:00 UTC पर समाप्त होती है।
* उपयोगकर्ता 1 से 14 तारीख तक 00:00 UTC के दौरान vote कर सकते हैं।
* votes को समायोजित और गिना जाने के कारण 14 से 15 तारीख तक 00:00 UTC के दौरान **कोई** vote नहीं दिया जा सकता।
* Voting results का snapshot 15 तारीख को 00:00 UTC पर लिया जाएगा। Epoch 1 का अंत।
* Voting results epoch बंद होने के 72 घंटों के भीतर लागू किए जाएंगे।

### 2 - पात्र बनें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

चूँकि veCAKE remaining lock time के अनुसार धीरे-धीरे घटता है, voting results प्रत्येक epoch के अंत में snapshot के माध्यम से लिए जाते हैं। इसमें कुल veCAKE की संख्या और प्रत्येक उपयोगकर्ता का veCAKE शामिल है।

उपरोक्त उदाहरण में:

* Epoch 1 के results 15 तारीख को 00:00 UTC पर veCAKE balances पर आधारित होंगे।
* जिन उपयोगकर्ताओं की veCAKE position 15 तारीख से पहले या बराबर unlock होती है, उनका snapshot time पर veCAKE balance 0 होगा। इसलिए Epoch 1 के लिए उनके पास कोई voting power नहीं होगी।

इसलिए, पात्र बनने के लिए, आपके पास एक सक्रिय veCAKE position होनी चाहिए, जो वर्तमान epoch के end/snapshot time से **बाद** में unlock हो।

उपरोक्त उदाहरण में:

* यदि आप epoch 1 में vote करना चाहते हैं, तो आपके पास एक veCAKE position होनी चाहिए जो 21 तारीख या उससे बाद, या सप्ताह 3 के गुरुवार को unlock हो।

### 3 - वर्तमान voting results जाँचें

"CAKE staking" पर जाएं, नीचे scroll करें और "Gauges Voting" section खोजें, फिर "Check Gauges" पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

ऊपर-बाईं ओर, आप निम्नलिखित पा सकते हैं:

* आपका veCAKE।
* वर्तमान epoch का Snapshot time और voting end time।
* अगले epoch में वितरित होने वाले CAKE rewards की कुल संख्या, जो वर्तमान epoch के voting results पर आधारित है।
* Cast किए गए veCAKE votes की कुल राशि।

ऊपर-दाईं ओर, आपको प्रत्येक gauge को प्राप्त % का प्रतिनिधित्व करने वाला pie chart मिलेगा।

नीचे, प्रत्येक voting gauge की एक पूरी सूची है। उनके द्वारा प्राप्त votes की संख्या और वर्तमान epoch में उन्हें मिलने वाले expected % weight के साथ। "boost" और "caps" field भी है, जो दो महत्वपूर्ण gauge विशेषताओं का विवरण देता है। अधिक जानकारी के लिए पढ़ते रहें।

#### Gauge Boost और Emission Caps

यह सुनिश्चित करने के लिए कि CAKE rewards सबसे उत्पादक gauges को जाएं, प्रत्येक gauge पर boost और/या emission cap लागू की जा सकती है। दोनों विशेषताएं एक साथ मौजूद हो सकती हैं।

Gauge Boost वह multiplier है जो किसी gauge को प्राप्त votes की संख्या पर लागू होता है, जो 1x से 2.5x तक होता है (V3 pools के gauges के लिए 2x पर cap है)। यह महत्वपूर्ण trading pairs के लिए votes और तरलता को प्रोत्साहित करने के लिए है।

Emission cap किसी gauge को मिलने वाले % weight की अधिकतम सीमा है, जो 2% से 20% तक होती है। यह आवंटन में निष्पक्षता बढ़ावा देने और gauge system के दुरुपयोग को रोकने के लिए है।

उदाहरण के लिए:

* एक gauge में 10 votes, 2x boost और 15% cap है। कुल vote 100 है।
* Boost लागू करने के बाद, इस gauge के 20 votes होंगे, total (100) के विरुद्ध 20% weight।
* हालाँकि, 15% cap होने के कारण, अगले epoch में इस gauge को मिलने वाले CAKE rewards का अंतिम % 15% पर समायोजित किया जाएगा।

#### Gauge Boost और Emission Caps कैसे निर्धारित होते हैं?

Gauge application की प्रक्रिया के दौरान, हम आवेदकों से boost multiplier और emissions cap % के मूल्य प्रस्तावित करने के लिए कहते हैं जो वे gauge को assign करना चाहते हैं। पूरे gauge application के साथ-साथ veCAKE holders को इन पर vote करना होता है।

सभी gauges के लिए default option 1.00x multiplier और 5% emission cap है। इन्हें भविष्य के proposals के साथ बदला जा सकता है।

{% hint style="info" %}
कृपया ध्यान दें कि voting results साप्ताहिक रूप से अपडेट होते हैं। संख्याओं की गणना आने वाले गुरुवार 00:00 UTC पर veCAKE balances के आधार पर की जाती है।
{% endhint %}

### 4 - Vote करने के लिए gauges जोड़ें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Gauge पर vote करने के लिए, नीचे scroll करें और "My Votes" section खोजें। "Add Gauge" पर क्लिक करें।

Pop-up window में, आप नीले "+" icon पर क्लिक करके अपनी votes की सूची में gauges जोड़ सकते हैं। आप सूची में वर्तमान voting results, boost और caps के साथ पा सकते हैं।

Gauge जल्दी से खोजने के लिए, आप blockchains, fee tiers और liquidity types द्वारा gauges filter करने के लिए filtering का उपयोग कर सकते हैं। या search field में token ticker टाइप करें।

### 5 - प्रत्येक gauge पर कितना % veCAKE vote करना है, चुनें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Gauges जोड़ने के बाद, आप चुन सकते हैं कि आपका कितना % veCAKE प्रत्येक gauge को जाता है।

ऐसा इसलिए है क्योंकि:

* veCAKE remaining lock time के साथ धीरे-धीरे घटता है। यह अनुमान लगाना और गणना करना अव्यावहारिक है कि कितने exact veCAKE vote किए जाएं।
* हर आने वाले epoch में दोबारा vote करना झंझट भरा है। इसलिए, gauges voting को आपके voting decisions को सभी आने वाले epochs में carry करने के लिए डिज़ाइन किया गया है जब तक आप नया vote नहीं डालते।

उपरोक्त उदाहरण में:

* इस समय, मेरे पास 2.62 veCAKE है।
* मैंने CAKE-BNB को 80% आवंटित करने का निर्णय लिया, जो अभी 2.10 veCAKE है।
* USDC-ETH को 20%, जो अभी 0.52 veCAKE है।
* Remaining lock time के साथ मेरा कुल veCAKE धीरे-धीरे घटता जाएगा। Snapshot time पर, मेरे पास कम veCAKE हो सकता है, लेकिन मेरा 80% - 20% का निर्णय अंतिम results पर लागू होगा।
* इसके अतिरिक्त, यह 80% - 20% निर्णय हर आने वाले epoch पर तब तक लागू होगा जब तक मैं नया vote request cast करके इसे अपडेट नहीं करता। या जब तक unlock के कारण मेरा veCAKE 0 नहीं हो जाता।

अपना निर्णय confirm करने के बाद, "Submit vote" पर क्लिक करें और अपने वॉलेट में confirm करें।

### 6 - अपने votes अपडेट करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Vote submit होने के बाद, आप अपने votes "Current Votes" में अपडेट होते देख सकते हैं। और remaining veCAKE भी अपडेट होता है।

कृपया ध्यान दें कि प्रत्येक gauge के लिए voting decision केवल हर 10 दिन में एक बार अपडेट की जा सकती है। Vote request submit करने के बाद, सभी voted gauges पर 10-दिन का cooldown period लागू होगा इससे पहले कि आप updates के लिए दूसरा request submit कर सकें।

अपना vote decision अपडेट करने के लिए, % बदलें और फिर से submit करें।

{% hint style="info" %}
कृपया ध्यान दें कि CAKE जोड़कर या lock time बढ़ाकर अधिक veCAKE प्राप्त करने के बाद, आपको vote request फिर से submit करके हर gauge को manually अपडेट करना होगा।

10 दिन का cooldown period तब भी लागू होता है चाहे आपने अपने % decisions बदले हों या नहीं।
{% endhint %}
