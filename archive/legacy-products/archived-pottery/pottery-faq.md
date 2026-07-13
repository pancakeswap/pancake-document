# Pottery FAQ

{% hint style="danger" %}
\[Archived] Pottery – 3 नवंबर 2023 से
{% endhint %}

## जब हमारे पास पहले से Lottery v2 है तो Pottery की आवश्यकता क्यों है?

Pottery, Lottery v2 की तुलना में एक बिल्कुल अलग product है। यह locked CAKE pool और lottery function का combination है जो true, secure randomness के लिए Chainlink के VRF implementation का उपयोग करता है। Pottery में participate करके, आप deposited CAKE में से कुछ भी नहीं खोएंगे, आप केवल deposited CAKE की staking rewards को risk कर रहे हैं। यह product उन CAKErs के लिए designed है जो अधिक risk-averse हैं लेकिन फिर भी इस प्रकार के product में participate करना चाहते हैं। यह CAKE जीतने का एक आसान, मजेदार और safe तरीका है। [Product structure के बारे में अधिक जानें यहाँ](https://docs.pancakeswap.finance/products/pottery)।

## क्या Pottery original Lottery v2 को replace कर रही है?

Pottery, original Lottery v2 को replace नहीं कर रही है। ये दोनों products अलग-अलग operate और run होती हैं। आप दोनों में participate कर सकते हैं!

## Pottery PancakeSwap और CAKE की कैसे मदद करती है?

प्रत्येक सप्ताह distributed prize pot का आठ प्रतिशत (8%) burning के लिए fees के रूप में charged किया जाएगा, जिससे CAKE में value accrued होती है। हम product के beta stage के बाद fee structure को review और adjust करने का लक्ष्य रखते हैं।

## Pottery का beta stage किसलिए है?

इस नए product के operations जैसे treasury से borrowing, cohort management और drawing के कारण। Product, beta stage में प्रत्येक Pottery के लिए capped total deposit के साथ शुरू होगा ताकि सुनिश्चित हो कि सब कुछ सुचारू रूप से चले। Beta stage pass होने के बाद, हम operations और community feedback के आधार पर fees, प्रत्येक cohort की frequency, lock period आदि जैसे different parameters review और adjust कर सकते हैं।

## मेरे CAKE को 10 सप्ताहों के लिए lock क्यों करना होगा?

यदि Pottery flexible staking pool का उपयोग कर सके, तो इसकी product structure बहुत सरल होगी - PoolTogether और Moonpot जैसे products के समान। हालाँकि, flexible staking pool से current yield एक meaningful prize pool for drawing के लिए पर्याप्त नहीं है। इसलिए, prize pool को fund करने के लिए उपयोग की जाने वाली rewards को balance करने के लिए CAKE को moderate duration के लिए lock करने का निर्णय लिया गया है। अधिक operations और community feedback के साथ, हम lock duration को आगे review और adjust कर सकते हैं।

## मैं withdraw क्यों नहीं कर सकता/सकती?

कृपया ध्यान दें कि withdrawal button lock date के 10 सप्ताह बाद ही lit up होगा और available होगा। Withdrawal की date lock date और time से 10 सप्ताह पर based है – प्रत्येक महीने के पहले सोमवार को 23:59 UTC।

## मैं अपना deposit क्यों नहीं देख सकता/सकती?

Subgraph reading के कारण कभी-कभी थोड़ी delay हो सकती है, delays होने पर signal मिलेगा – आमतौर पर 15 मिनट बाद फिर से check करने पर सही amount दिखाई देगी।

## मुझे कैसे पता चलेगा कि मैंने साप्ताहिक draw में जीता है?

दोपहर UTC के आसपास शुक्रवार को प्रत्येक draw के बाद, आप Finished Rounds panel में results और winners देख सकते हैं। किसी भी साप्ताहिक draw में जीतने की जाँच करने का दूसरा तरीका Claim panel में देखना है कि कोई prize claim करने के लिए है या नहीं। [यहाँ participate कैसे करें इस page को देखें](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery)!

## Prize का funding source क्या है?

Prize pools deposits की staking rewards द्वारा funded हैं। हालाँकि, चूँकि CAKE locked staking pool की staking rewards केवल lock duration के बाद distributed होती हैं – इस मामले में 10 सप्ताह – बेहतर product experience के लिए और deposit date के तुरंत बाद साप्ताहिक draws facilitate करने के लिए, contract locking के समय APR के आधार पर CAKE treasury से cohort के estimated total staking rewards का 80% borrow करता है। Borrowed CAKE का उपयोग प्रत्येक साप्ताहिक draw के payout के लिए किया जाता है। [Product structure के बारे में अधिक जानें यहाँ](https://docs.pancakeswap.finance/products/pottery)!

## यदि मैं जीतता/जीतती हूँ, तो क्या मुझे manually prize claim करना होगा?

हाँ, आपको Pottery page पर Claim panel के अंतर्गत Claim button पर click करना होगा।

## Pottery कितनी बार होती है?

प्रत्येक Pottery cohort लगभग 10:00 UTC पर शुक्रवार को deposit के लिए open होती है और प्रत्येक महीने के पहले सोमवार को 23:59 UTC पर बंद होती है, जब तक कि कोई special arrangement और prior notice न हो। प्रत्येक cohort के 10 subsequent Fridays पर दोपहर UTC पर 10 साप्ताहिक draws होंगे।

पहली Pottery 5 अगस्त 2022 को deposit के लिए open होगी और 8 अगस्त 2022 को 23:59 UTC पर lock होगी।

## Pottery deposit केवल महीने में एक बार क्यों open होती है?

यह arrangement deposits को combine करके locked staking pool की ओर direct करती है, ताकि cohort का Pottery contract locked staking pool से deposit के staking rewards coordinate कर सके। अधिक operations और community feedback के साथ, हम frequency को review और adjust कर सकते हैं।

## Deposit की limit क्या है?

Minimum deposit 1 CAKE है। Product के beta stage में, प्रत्येक cohort के लिए maximum deposit cap भी होगी जिसे आप deposit करते समय Deposit panel में देख सकते हैं। यह सुनिश्चित करने के लिए कि operations side पर treasury से borrowing, locked staking और drawing सुचारू रूप से चले। जबकि आप जितना maximum deposit कर सकते हैं वह उस cohort का maximum deposit cap है (यदि किसी और ने CAKE deposit नहीं किया है), आप सभी prizes जीतेंगे, हालाँकि इसका भी मतलब यह है कि आपको जो final return मिलेगा वह आपके CAKE को 10 सप्ताहों के लिए locked staking pool में रखने के समान होगा, लेकिन आप Pottery fees भी pay करेंगे।

## Cohort system की आवश्यकता क्यों है? हम सबको एक साथ क्यों नहीं रख सकते?

चूँकि Pottery CAKE की fixed-term staking के साथ interact करती है, कोई भी deposit केवल lock duration के बाद ही withdraw की जा सकती है। यदि हम सभी deposits को एक साथ रखना चाहते हैं, तो जबकि हम initial lock के बाद अधिक deposit add कर सकते हैं और उन्हें भी 10 सप्ताहों (नई deposit के समय से) के लिए lock कर सकते हैं, initial depositors समय पर withdraw नहीं कर पाएंगे।

## SHARE token क्या है?

SHARE tokens pottery में deposit करने पर generate और distribute किए जाते हैं। यह deposit pool के विरुद्ध आपके share की credential और representative के रूप में serve करता है।

Withdrawal पर, SHARE token pottery contract को वापस transfer किया जाएगा और burn हो जाएगा।

## मैं इस product के लिए feedback कहाँ दे सकता/सकती हूँ?

कृपया बेझिझक हमसे [Telegram](https://t.me/pancakeswap) या [Discord](https://discord.gg/pancakeswap) पर संपर्क करें यदि आप format के बारे में अनिश्चित हैं या यदि आपके पास हमारे लिए कोई feedback है!
