# Degen Mode Dynamic Fee

PancakeSwap Perpetuals Degen Mode एक dynamic fee मॉडल का उपयोग करता है। यह शुल्क PnL के आधार पर शुल्क लेने और उपयोगकर्ताओं को नुकसान से बचाने के लिए डिज़ाइन किया गया है।\
**यह कैसे काम करता है?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

जहां:

* Pnl पोजीशन पर लाभ या हानि है
* shareRate शेयर दर है, जो notional का वह प्रतिशत है जो शुल्क में भुगतान किया जाता है (डिफ़ॉल्ट रूप से 15%)
* Notional पोजीशन खोलने के लिए उपयोग की जाने वाली धनराशि है
* closeMinRate न्यूनतम closing fee दर है, जो पोजीशन बंद करने के लिए भुगतान की जाने वाली सबसे कम राशि है (डिफ़ॉल्ट रूप से 0.03%)

\
**उदाहरण:**

यदि आपके पास $100 के लाभ, 15% की share rate और $600 के notional के साथ एक पोजीशन है, तो closing fee rate होगी:

Closing fee rate = Max(100 \* 15% / 600, 0.03%) = 0.03%

इस स्थिति में, closing fee rate 0.03% होगी, जो न्यूनतम closing fee rate है।<br>

नोट:

execution fee केवल तभी लिया जाएगा जब पोजीशन खोली जाती है। यह 0.3 USD (BNB Chain)/ 0.2 USD (Arbitrum)/ 0.01 USD (opBNB)/ 0.3 USD (Base) पर सेट है, जो classic perpetual trading जोड़ियों का व्यापार करते समय लगाए जाने वाले शुल्क के समान है। कोई opening position fee नहीं है।

लिक्विडेशन की स्थिति में, 90% liquid lost rate में close fee शामिल है।
