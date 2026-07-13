# अक्सर पूछे जाने वाले सवाल (FAQ)

### मैंने अपना CAKE lock किया या CAKE pool position migrate की। फिर भी मेरे 0 shares क्यों हैं? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Shares हर गुरुवार को 00:00 UTC पर साप्ताहिक वितरण के दौरान अपडेट होते हैं।

Rewards तब जमा होते हैं जब आप एक पूरे epoch के लिए staking पूरी कर चुके होते हैं।&#x20;

Epochs 7-दिवसीय अवधि होती हैं, जो प्रत्येक गुरुवार UTC 00:00 से शुरू होती हैं। उदाहरण के लिए, यदि आप मंगलवार को stake करते हैं, तो आपका पहला epoch गुरुवार से शुरू होगा। एक बार जब आप अगले गुरुवार तक staking पूरी कर लेते हैं, तो आप इस गुरुवार से अगले गुरुवार तक के rewards claim कर सकते हैं, यानी epoch 1।

अपडेट किए गए reward numbers के लिए हर गुरुवार वापस जाँचें।

### सक्रिय staking position होने के बावजूद मेरे shares/rewards 0 क्यों हैं? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Rewards की गणना करते समय, remaining lock duration को सप्ताहों में घटाकर round किया जाता है। इसलिए, shares प्राप्त करने के लिए, आपको सुनिश्चित करना होगा कि आपकी staking position अगले गुरुवार 00:00 UTC से पहले unlock न हो।

उदाहरण के लिए, सप्ताह 1 गुरुवार, 1 जनवरी 00:00 UTC से शुरू होता है। सप्ताह 1 वितरण के लिए rewards प्राप्त करने हेतु, आपको:

* 1 जनवरी, 00:00 UTC से पहले शामिल होना होगा।
* एक सक्रिय veCAKE staking position रखनी होगी, जो 15 जनवरी (सप्ताह 3 का गुरुवार) 00:00 UTC के बराबर या उससे बाद unlock हो।

कृपया ध्यान दें कि यदि आपकी staking position 8 जनवरी (सप्ताह 2 का गुरुवार) 00:00 UTC को unlock होती है, तो आपको सप्ताह 1 के लिए 0 rewards मिलेंगे क्योंकि आपका veCAKE balance 8 जनवरी 00:00 UTC पर शून्य हो जाएगा।

### क्या मैं सप्ताह के बीच में किसी वितरण अवधि में शामिल हो सकता हूँ? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

नहीं, जैसा उल्लेख किया गया है, rewards तभी जमा होना शुरू हो सकते हैं जब आप epoch की शुरुआत में पहले से staking कर रहे हों। यह हर सप्ताह गुरुवार को 00:00 UTC है।&#x20;

### मुझे अधिक rewards कैसे मिलेंगे? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

चूँकि pools में आपके shares वितरण के समय veCAKE balance के आधार पर गणना किए जाते हैं, जो अगले आने वाले गुरुवार 00:00 UTC पर होता है, अधिक rewards प्राप्त करने के लिए, बस अपना veCAKE balance बढ़ाएं:

* veCAKE staking position में अधिक CAKE lock करके
* अपनी staking position नवीनीकृत करके

कृपया ध्यान दें कि CAKE जोड़ने या extend करने के बाद, आपके shares केवल अगले epoch की शुरुआत, यानी आने वाले गुरुवार 00:00 UTC पर ही अपडेट होंगे।

### साप्ताहिक इंजेक्ट किए गए rewards विभिन्न trackers (जैसे Info page) पर दिखाए गए volume से 100% मेल क्यों नहीं खाते? साप्ताहिक CAKE pool rewards gauges voting results से 100% मेल क्यों नहीं खाते?

साप्ताहिक इंजेक्ट किए गए CAKE rewards की संख्या विभिन्न trackers पर दिखाए गए volume से गणना की गई संख्याओं से 100% मेल नहीं खा सकती। कई बाहरी कारक CAKE rewards की उस संख्या को प्रभावित कर सकते हैं जिसे convert किया जा सकता है:

* Trading fee convert और process होते समय CAKE token की कीमत
* Trading fee convert और process होते समय अंतर्निहित asset की कीमतें
* Gas और operational cost बचाने के लिए, BNB Chain के अलावा अन्य blockchains से revenue मासिक रूप से process की जाती है। इन्हें साप्ताहिक औसत के साथ एक महीने की देरी से इंजेक्ट किया जाएगा।
* Trading fee process करते समय कुछ trading pairs में अपर्याप्त तरलता हो सकती है।
* कुछ trading pairs में ऐसे tokens हो सकते हैं जिनमें custom logic है जो उनकी fee को process होने से रोकती है।
* Infrastructure और supportive system performance के कारण transaction में देरी।

अधिक trading fees को process करके CAKE में convert किया जा सके, इसके लिए Chefs tools और practices लागू करने पर कड़ी मेहनत कर रहे हैं।
