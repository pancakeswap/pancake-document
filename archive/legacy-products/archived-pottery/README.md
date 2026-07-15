# 🍯 \[Archived] Pottery

{% hint style="danger" %}
\[Archived] Pottery – 3 नवंबर 2023 से
{% endhint %}

Pottery, CAKE lock-staking को lottery elements के साथ combine करती है ताकि आपको अपने CAKE deposit पर बड़ा yield जीतने का मौका मिले! यह आसान और safe है क्योंकि आपको हमेशा कम से कम उतना CAKE वापस मिलेगा जितना आपने deposit किया था।

## विशेषताएं:

* Pottery page पर minimum 1 CAKE के साथ CAKE deposit करें&#x20;
* एक अलग Pottery cohort के लिए प्रत्येक महीने के पहले सोमवार को deposit बंद होती है (उस सोमवार को 23:59 UTC पर) और उससे पहले शुक्रवार को लगभग 10:00 UTC से खुलती है, जब तक कि कोई special arrangements न हों जो पहले से announce किए जाएंगे (पहली Pottery 8 अगस्त 2022 23:59 UTC पर बंद हो रही है)
* Product के beta stage के दौरान, प्रत्येक Pottery cohort के लिए total CAKE deposit पर cap है (maximum deposit cap 600,000 CAKE है)
* Deposit किया गया CAKE lock-staking pool की ओर directed होगा और दस (10) सप्ताह के लिए locked होगा; total staking rewards का 80% drawing के लिए Pottery pool को भेजा जाएगा, 20% आपकी withdrawal के लिए reserved रहेगा&#x20;
* प्रत्येक Pottery cohort (प्रति माह एक) के लिए, deposit पर प्रत्येक शुक्रवार (दोपहर UTC पर) दस (10) साप्ताहिक draws होंगे जिसमें प्रति सप्ताह आठ (8) winners होंगे, प्रत्येक address प्रति सप्ताह आठ winner slots में से एक से अधिक जीत सकता है \*
* Pool के सापेक्ष आपका deposit जितना बड़ा होगा, जीतने की संभावना उतनी ही अधिक होगी; winners प्रत्येक draw के तुरंत बाद अपना prize claim कर सकते हैं&#x20;
* प्रत्येक Pottery cohort draw अलग-अलग आयोजित करती है&#x20;
* Pottery cohort lock date से केवल 10 सप्ताह बाद ही आप अपना CAKE withdraw कर सकते हैं&#x20;
* Pottery सच्ची, secure randomness के लिए Chainlink के VRF implementation का उपयोग करती है

## Pottery Cohort&#x20;

प्रत्येक महीने के पहले सोमवार से पहले शुक्रवार को, अगले 10 सप्ताहों के लिए CAKE deposit करने और participate करने के लिए एक Pottery cohort खुलेगी। यह arrangement deposits को combine करके locked staking pool की ओर direct करती है, ताकि cohort का Pottery contract locked staking pool से deposit के staking rewards coordinate कर सके।

प्रत्येक deposit और lock date एक अलग cohort होगी – प्रति माह एक – उदाहरण के लिए 5 सितंबर 2022 की सभी deposits एक cohort में होंगी, 3 अक्टूबर 2022 की सभी deposits दूसरी cohort में होंगी।

जबकि different cohorts के लिए draws एक साथ हो सकते हैं, fairness के लिए प्रत्येक cohort के prize pools अलग-अलग रखे जाते हैं।

![(केवल illustration के उद्देश्य से, पहली Pottery के लिए actual cohort lock date 8 अगस्त 2022 निर्धारित की गई है)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

उदाहरण के लिए, 9 सितंबर 2022 को 2 अलग draws होते हैं, एक Aug 1 cohort के लिए छठे साप्ताहिक draw के रूप में और दूसरा Sep 5 cohort के लिए पहले साप्ताहिक draw के रूप में। यदि Aug 1 cohort में कुल 100,000 CAKE deposited हैं और Sep 5 cohort में कुल 300,000 CAKE deposited हैं, तो Aug 1 cohort का साप्ताहिक prize केवल उन 100,000 CAKE के staking rewards से आएगा, जबकि Sep 5 cohort का साप्ताहिक prize केवल उन 300,000 CAKE के staking rewards से आएगा। यदि आपने केवल Aug 1 cohort में CAKE deposit किया है, तो आपके पास 100,000 CAKE के staking rewards के आधार पर Sep 9 को साप्ताहिक prize जीतने का मौका है। यदि आपने Aug 1 और Sep 5 दोनों cohort में CAKE deposit किया है, तो आपके पास Sep 9 को दोनों साप्ताहिक prizes जीतने का मौका है।

#### Cohort system की आवश्यकता क्यों है? हम सबको एक साथ क्यों नहीं रख सकते?

चूँकि Pottery CAKE की fixed-term staking के साथ interact करती है, कोई भी deposit केवल lock duration के बाद ही withdraw की जा सकती है। यदि हम सभी deposits को एक साथ रखना चाहते हैं, तो जबकि हम initial lock के बाद अधिक deposit add कर सकते हैं और उन्हें भी 10 सप्ताहों के लिए lock कर सकते हैं, initial depositors समय पर withdraw नहीं कर पाएंगे।

## **Prize Funding और Staking Rewards Allocation**

Staking rewards के अधिक कुशल arrangement के लिए deposits को monthly cohorts में grouped किया जाता है जो प्रत्येक cohort के लिए एक साथ grouped होती हैं। Staking rewards का उपयोग prize pool को fund करने और Pottery में deposit करने के लिए staking rewards प्रदान करने के लिए किया जाता है।

Staking rewards का 80% 10 साप्ताहिक draws के लिए prize pool fund करने के लिए directed किया जाएगा और शेष 20% आपके 10 सप्ताह बाद CAKE deposit withdraw करने पर staking rewards के रूप में reserved रहेगा।

हालाँकि, चूँकि CAKE locked staking pool के staking rewards केवल lock duration के बाद distributed होती हैं – इस मामले में 10 सप्ताह – बेहतर product experience के लिए और deposit date के तुरंत बाद साप्ताहिक draws facilitate करने के लिए, contract locking के समय APR के आधार पर CAKE treasury से cohort के estimated total staking rewards का 80% borrow करता है। Borrowed CAKE का उपयोग प्रत्येक साप्ताहिक draw के payout के लिए किया जाता है।

10 सप्ताह के अंत में, जब staking pool से rewards distribute होती हैं, CAKE treasury को पहले repaid किया जाएगा, फिर बाकी vault में वापस directed होगा ताकि उपयोगकर्ता अपने initial deposit के साथ cohort में withdraw कर सकें।

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEF6IySHEmy1P1k5S3W_PvnFMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMKqAkTnNTfKRdU8s3UXO1n0Smnp8_6sAg)

उदाहरण के लिए, यदि 1 अगस्त 2022 की Pottery cohort में कुल 100,000 CAKE deposits आकर्षित हुई हैं, तो 10 सप्ताहों की locked staking का estimated return लगभग 3,674 CAKE है। Contract इसका 80%, या लगभग 2,940 CAKE, 10 साप्ताहिक draws के लिए prize pool के रूप में borrow करेगा, यानी fees से पहले प्रत्येक साप्ताहिक draw के लिए कुल prizes में 294 CAKE।

यह ध्यान रखना महत्वपूर्ण है कि deposit से duration के अंत में rewards और APR locked CAKE pool में अन्य deposits और उनकी lock-periods के आधार पर 10-सप्ताह की duration में बदल सकते हैं, इसलिए specified percentages से थोड़ा deviance हो सकता है (+/- 10%)।

Fees net of सभी staking rewards depositors को prize pool या rewards के माध्यम से वापस की जाएंगी। यदि actual APR, locking के समय estimated APR से कम है, तो इसका मतलब है कि साप्ताहिक draws के दौरान depositors को अधिक rewards distribute की गई हैं, और staking rewards portion के लिए कम। यदि actual APR, locking के समय estimated APR से अधिक है, तो साप्ताहिक draws के माध्यम से कम rewards distributed होती हैं और withdrawal के लिए available staking rewards के लिए अधिक reserved होती हैं। अंततः, expected value समान है।

## **जीतने का तरीका – Odds Calculation**

Odds की गणना cohort के total deposit size के सापेक्ष deposit amount के share के आधार पर होती है। सरलतः, आपने जितना अधिक CAKE deposit किया होगा, प्रत्येक साप्ताहिक draw में जीतने की संभावना उतनी ही अधिक होगी। उदाहरण के लिए, यदि आपने 10,000 CAKE deposit किए हैं और cohort का total deposit 100,000 CAKE है, तो प्रत्येक साप्ताहिक draw में आपके जीतने की 10% संभावना है।

प्रत्येक address प्रति सप्ताह 8 winner slots में से 1 से अधिक जीत सकता है।

चरम मामले में, यदि cohort के 100,000 CAKE सभी आपके द्वारा deposited हैं, तो आप प्रत्येक साप्ताहिक draw के सभी prizes जीतेंगे। हालाँकि, इसका मतलब है कि आपको जो final return मिलेगा वह 100,000 CAKE को 10 सप्ताहों के लिए locked staking pool में रखने के समान होगा, लेकिन आप Pottery fees भी pay करेंगे।

## **Risks – महत्वपूर्ण!**

आपको 10 सप्ताहों में आपके deposited का 100% वापस मिलने की guarantee है। हालाँकि, आप अपना CAKE deposit केवल 10 सप्ताहों के locking के बाद ही withdraw कर सकते हैं, बिना किसी early withdrawal के।

Pottery में participate करके, आप staking rewards को, साथ ही iCAKE और vCAKE जैसी अन्य locked-CAKE utilities को risk कर रहे हैं। यदि आप 10 साप्ताहिक draws में से कुछ भी नहीं जीतते हैं, तो आपने उन staking rewards का 80% खो दिया होगा जो आपको 10 सप्ताहों के लिए staking pool में CAKE lock करने पर मिलती।

कृपया अपनी risk preference के आधार पर participate करें, एक बार CAKE deposit हो जाने के बाद, early withdraw करने में कोई भी आपकी मदद नहीं कर सकता।

## **Fees**

प्रत्येक सप्ताह distributed prize pot का आठ प्रतिशत (8%) burning के लिए fees के रूप में charged किया जाएगा। हम product के beta stage के बाद fee structure को review और adjust करने का लक्ष्य रखते हैं।

## **Participate करने के लिए तैयार हैं?**

यदि आप product structure, risks और fees के बारे में clear हैं – PancakeSwap web UI से [participate कैसे करें](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) और अन्य [Pottery FAQ](https://docs.pancakeswap.finance/products/pottery/pottery-faq) के लिए यह page देखें!



