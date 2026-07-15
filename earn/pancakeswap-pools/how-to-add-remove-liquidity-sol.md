# तरलता कैसे जोड़ें / हटाएं (SOL)

"तरलता" PancakeSwap के Exchange के कार्य करने का केंद्रीय आधार है। आप Liquidity पृष्ठ के माध्यम से दोनों टोकन Staking करके किसी भी टोकन जोड़े के लिए तरलता जोड़ सकते हैं।

तरलता जोड़ने के बदले में, आपको उस जोड़े के लिए ट्रेडिंग शुल्क और यील्ड फार्मिंग पुरस्कार (यदि लागू हो) प्राप्त होंगे।

PancakeSwap V3 आपको **केंद्रित तरलता** प्रदान करने देता है — अर्थात आप वह मूल्य सीमा चुनते हैं जहां आपकी तरलता सक्रिय रहे। यह आपको अपनी पूंजी के उपयोग पर अधिक नियंत्रण और दक्षता देता है।

{% hint style="warning" %}
**नोट:** इस गाइड में दिखाई गई छवियां केवल उदाहरण के उद्देश्य से हैं और वास्तविक समय के डेटा या वर्तमान pool आंकड़ों को नहीं दर्शाती हैं।
{% endhint %}

***

## तरलता जोड़ें

आप दो तरीकों से तरलता जोड़ सकते हैं:

* **विकल्प 1:** किसी मौजूदा pool में जोड़ें
* **विकल्प 2:** आपके द्वारा पहले से बनाई गई पोजीशन में और टोकन जोड़ें

***

### विकल्प 1: किसी मौजूदा Pool में जोड़ें

#### चरण 1: Pool सूची पृष्ठ पर जाएं

यहां आपको Solana पर सभी सक्रिय V3 pool दिखेंगे।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28386%29.png" alt=""><figcaption></figcaption></figure>

#### चरण 2: अपना Pool खोजने के लिए फ़िल्टर का उपयोग करें

आप पृष्ठ के शीर्ष पर फ़िल्टर का उपयोग करके:

*   किसी विशेष टोकन जोड़े के लिए **खोज** कर सकते हैं<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28387%29.png" alt=""><figcaption></figcaption></figure>
*   **लेआउट व्यू बदल** सकते हैं (ग्रिड/सूची)<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28388%29.png" alt=""><figcaption></figcaption></figure>
*   pool को TVL, Volume, Fees, या APR के आधार पर **सॉर्ट** कर सकते हैं<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28389%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
यदि आपका pool बनाने के तुरंत बाद दिखाई नहीं देता, तो कृपया 5 मिनट तक प्रतीक्षा करें। TVL, volume, fees और APR आंकड़े लगभग हर 15 मिनट में अपडेट होते हैं क्योंकि pool के माध्यम से Swap प्रवाहित होते हैं।
{% endhint %}

#### चरण 3: तरलता जोड़ने का तरीका चुनें

आप निम्न में से किसी एक तरीके से प्रक्रिया शुरू कर सकते हैं:

*   pool कार्ड पर **"Deposit"** पर क्लिक करें<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28390%29.png" alt=""><figcaption></figcaption></figure>
*   या "My Positions" के अंतर्गत **"Create New Position"** पर क्लिक करें<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28391%29.png" alt=""><figcaption></figcaption></figure>

#### चरण 4: अपनी मूल्य सीमा निर्धारित करें

चूंकि यह V3 pool है, आपको अपनी तरलता के लिए एक मूल्य सीमा चुननी होगी:

*   **त्वरित प्रीसेट सीमाओं** (जैसे +- 25%) का उपयोग करें या कस्टम सीमा निर्धारित करें<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28392%29.png" alt=""><figcaption></figcaption></figure>
*   बेस/कोट व्यू के बीच स्विच करने के लिए **मूल्य दिशा टॉगल** का उपयोग करें<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28393%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
निम्नलिखित स्थितियों में **अलर्ट** देखें:

* आपकी चुनी गई सीमा बाज़ार मूल्य से बहुत दूर हो
* Pool में कम तरलता हो
{% endhint %}

#### चरण 5: जमा राशि दर्ज करें

वह टोकन राशि दर्ज करें जो आप प्रदान करना चाहते हैं

\*\* APR तब तक नहीं दिखेगा जब तक आप दोनों टोकन के लिए राशि दर्ज नहीं करते

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28394%29.png" alt=""><figcaption></figcaption></figure>

#### चरण 6: पूर्वावलोकन और पुष्टि

*   **"Add Liquidity"** पर क्लिक करें

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28396%29.png" alt=""><figcaption></figcaption></figure>
*   पूर्वावलोकन मोडल में अपनी पोजीशन की समीक्षा करें<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28397%29.png" alt=""><figcaption></figcaption></figure>

पुष्टि होने के बाद, ट्रांजैक्शन सबमिट हो जाएगी और आपकी पोजीशन बन जाएगी!

***

### विकल्प 2: किसी मौजूदा पोजीशन में और तरलता जोड़ें

#### चरण 1: "My Positions" पर जाएं

यहां आपको अपनी सभी सक्रिय V3 तरलता पोजीशन दिखेंगी।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28398%29.png" alt=""><figcaption></figcaption></figure>

#### चरण 2: "+" बटन पर क्लिक करें

यह आपको अपनी वर्तमान मूल्य सीमा में और टोकन जोड़ने देता है।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28399%29.png" alt=""><figcaption></figcaption></figure>

#### चरण 3: जमा राशि दर्ज करें

वह टोकन राशि दर्ज करें जो आप जोड़ना चाहते हैं और **"Confirm"** पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28400%29.png" alt=""><figcaption></figcaption></figure>

पुष्टि होने पर आपको सफलता संदेश दिखाई देगा।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28401%29.png" alt=""><figcaption></figcaption></figure>

***

## तरलता हटाएं

आप **My Positions** टैब से अपनी किसी भी सक्रिय पोजीशन से सीधे तरलता हटा सकते हैं।

#### 1. **My Positions** पर जाएं

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28402%29.png" alt=""><figcaption></figcaption></figure>

#### 2. वह पोजीशन चुनें जिससे तरलता हटानी है

पोजीशन के बगल में **"−"** आइकन पर क्लिक करें।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28403%29.png" alt=""><figcaption></figcaption></figure>

#### 3. वह राशि दर्ज करें जो आप हटाना चाहते हैं

आप या तो:

* टोकन राशि मैन्युअल रूप से दर्ज करें
* **या** अपनी वर्तमान पोजीशन का प्रतिशत चुनने के लिए **स्लाइडर** का उपयोग करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28404%29.png" alt=""><figcaption></figcaption></figure>

#### 4. (वैकल्पिक) तरलता हटाने के बाद पोजीशन खुली रखें

यदि आप अपनी तरलता का **100%** हटाते समय **"Keep my position open"** चुनते हैं:

* आपके टोकन निकाल लिए जाएंगे
* लेकिन पोजीशन का इतिहास और आपकी मूल मूल्य सीमा **My Positions** के अंतर्गत **दिखती रहेगी**

यदि आप मूल्य सीमा प्रदर्शन सहित **पोजीशन पूरी तरह बंद** करना चाहते हैं:

* **"X"** आइकन पर क्लिक करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28408%29.png" alt=""><figcaption></figcaption></figure>

#### 5. उसी मूल्य सीमा का पुनः उपयोग करें

आप बाद में उसी मूल्य सीमा में **और तरलता जोड़** सकते हैं, पहली बार तरलता जोड़ते समय के समान चरणों का पालन करके।

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28409%29.png" alt=""><figcaption></figcaption></figure>
