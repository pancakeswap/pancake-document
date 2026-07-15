# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Emission rate** <a href="#emission-rate" id="emission-rate"></a>

### **Per block**

| **Metric**                                                                   | **Emission/block (CAKE)** | **Emission/day (CAKE)** |
| ---------------------------------------------------------------------------- | ------------------------: | ----------------------: |
| Emission                                                                     |                        40 |               1,152,000 |
| Burned Weekly [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                    -25.75 |                -787,600 |
| **Effective Emission**                                                       |              **<14.25\*** |           **364,400\*** |

\*Effective Emission वास्तव में इस राशि से थोड़ी कम है: lottery को आवंटित राशि से अतिरिक्त 45,000 CAKE प्रति दिन diverted और burned होती है (PID 137 - नीचे Details)।

उपरोक्त के अतिरिक्त, एक dynamic amount of CAKE भी [Dev address पर minted](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) होती है 9.09% की rate पर। इसका मतलब है कि यदि 100 CAKE harvested होती है, तो additional 9.09 CAKE minted होकर Dev Address पर भेजी जाती है।

{% hint style="info" %}
Dev address पर minted सभी CAKE साप्ताहिक burn में burn हो जाती है और कभी circulation में नहीं आती।&#x20;

इस कारण, हमने इसे उपरोक्त emission rate में शामिल नहीं किया है।
{% endhint %}

## Distribution <a href="#distribution" id="distribution"></a>

| Distributed to                | Reward/block (% of emission) | Reward/block (total CAKE) |           Reward/day |
| ----------------------------- | ---------------------------: | ------------------------: | -------------------: |
| Farms and Lottery             |                       10.62% |                      4.25 |     122,400 (approx) |
| of which diverted and burned  |                              |                           |              -46,000 |
| Syrup Pools                   |                          25% |                        10 |     288,000 (approx) |
| **Total Daily CAKE Emission** |                              |                           | **364,400 (approx)** |

## **अन्य Deflationary Mechanics** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Burning process वर्तमान में manual है। [Burn transactions यहाँ देखें](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead)।
{% endhint %}

उपरोक्त के साथ-साथ, CAKE निम्नलिखित तरीकों से भी burn होती है:

* PancakeSwap V2 पर हर trade का **0.05%**
* Dev address पर भेजी गई **100%** CAKE
* IFOs से **100%** CAKE performance fees
* Profile Creation और NFT minting पर खर्च की गई **100%** CAKE
* Farm Auctions के दौरान bid की गई **100%** CAKE
* Lottery tickets पर खर्च की गई CAKE का **20%**
* प्रति दिन **45,000** CAKE (historically lottery को assigned) _(इसके लिए CAKE एक farm द्वारा generated होती है - PID 137)_
* Prediction markets के प्रत्येक round का **3%** CAKE burn के लिए खरीदने के लिए उपयोग किया जाता है
* Auto CAKE Pool में हर yield harvest का **2%**
* NFT Market पर हर NFT sale का **2%** CAKE burn के लिए खरीदने के लिए उपयोग किया जाता है

## CAKE burn manual क्यों है?

जमीन से शुरू करने के लिए, PancakeSwap ने MasterChef contract के साथ MVP (minimum viable product) के रूप में launch किया जो प्रति block 40 CAKE emit करता था। इस कारण, early team ने CAKE minting logic को customize करने की क्षमता जैसे additional functions add नहीं किए। नए MasterChef पर migrate करने में बहुत समय और प्रयास लगता, इसलिए team ने दो pools बनाकर manual burn process के माध्यम से CAKE emissions कम करना opted किया:

* Legacy Lottery Pool (PID - 137) - lottery से burned CAKE
* Burn Pool (PID - 138) - प्रति block burned CAKE

ये pools farms के समान काम करते हैं, जहाँ Chefs प्रत्येक CAKE emission reduction vote के बाद उन्हें allocated 40 CAKE per block का percentage adjust कर सकते हैं।

{% hint style="warning" %}
Burn के दिन, homepage पर दिखाई देने वाली supply अचानक कई million CAKE से jump कर सकती है।&#x20;

चिंता न करें - **यह CAKE कभी भी वास्तव में CIRCULATION में नहीं आती:**
{% endhint %}

यह apparent jump इसलिए है क्योंकि burn के लिए allocated सभी CAKE सप्ताह के दौरान कैसे stored होती है।&#x20;

PID-137 और PID-138 दोनों pools को भेजी गई CAKE को साप्ताहिक token burns पूरी करने से पहले harvested किया जाता है, और इससे site पर Total Supply दिखाई देने वाली लगभग 6M jump करती है। ऐसा इसलिए है क्योंकि pending CAKE burn day पर harvested होने तक Total Supply में registered नहीं होती। एक बार token burn ट्रांजेक्शन पूरी हो जाने पर, ~6M Burned to Date में दिखाई देता है।&#x20;

## CAKE Supply खुद confirm कैसे करें

यह confirm करने के लिए कि PancakeSwap homepage पर दिखाया गया circulating CAKE supply सही है,&#x20;

1. BscScan पर CAKE token contract पर जाएं और [देखें कि Burn Address कितना CAKE hold करता है।](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) यह burned CAKE की कुल राशि है (circulation से हमेशा के लिए हटाया गया, और कभी भी retrieve करना असंभव)।
2. फिर, इस burned amount को BscScan द्वारा दिखाई जाने वाली "Total Supply" से घटाएं।
3. इससे आपको actual CAKE supply मिलती है।



#### **अगले page पर CAKE के deflationary mechanics के बारे में अधिक पढ़ें।** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
