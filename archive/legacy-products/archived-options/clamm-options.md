# CLAMM Options

{% hint style="danger" %}
\[ARCHIVED] Options – 11 मार्च 2025 से\
यदि आपके पास अभी भी withdraw करने के लिए liquidity है, तो कृपया तुरंत https://www.stryke.xyz/en/trade पर जाकर ऐसा करें।
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options, on-chain options trading के लिए एक नया दृष्टिकोण प्रस्तुत करता है, जो liquidity providers को PancakeSwap पर v3 liquidity का लाभ उठाने का platform प्रदान करता है। यह उन्हें v3 liquidity pools और options बेचने दोनों के लिए liquidity का उपयोग करने, standard AMM trading fees, options premiums और अतिरिक्त rewards अर्जित करने की सुविधा देता है, जबकि traders इस liquidity का उपयोग विभिन्न tokens पर American-style options खरीदने के लिए कर सकते हैं।

Stryke (पूर्व में Dopex) team द्वारा तैयार, CLAMM options protocol options traders (buyers) और PancakeSwap v3 pools के लिए एक कुशल dual liquidity provision system पेश करता है।

यहाँ बताया गया है कि CLAMM Options कैसे काम करता है:

1. CLAMM options में liquidity add करने वाले LPs एक साथ अपने chosen price range के भीतर designated PancakeSwap v3 pool में contribute करते हैं।
2. जब कोई options trader (buyer) position शुरू करता है, तो options selling को facilitate करने के लिए v3 pool से liquidity निकाली जाती है। संबंधित LP इस प्रकार options seller बन जाता है और premium प्राप्त करता है।
3. Options buyers द्वारा उपयोग न की गई liquidity PancakeSwap v3 pool में रहती है, जो संभावित रूप से trading fees अर्जित करती है।
4. Options बेचने और v3 pool में liquidity provide करने से payoff, impermanent loss के समान ही mirror करता है, यह सुनिश्चित करते हुए कि उपयोगकर्ताओं को v3 pools में liquidity add करने की conventional method की तुलना में अधिक जोखिम नहीं है।
5. LPs को कुछ जोखिमों का सामना करना पड़ता है, क्योंकि options buying demand कम होने के कारण liquidity unused रह सकती है। इसके अतिरिक्त, चूँकि liquidity को inactive range में pool में add किया जाता है, इसलिए इसे कोई fees नहीं मिल सकती।

PancakeSwap के American-style CLAMM options Arbitrum chain पर debut करेंगे, जिसमें 1 घंटे से 24 घंटे तक की विभिन्न expiry durations के साथ flexibility मिलेगी।

| **Markets**          | ARB/USDC, ETH/USDC, और wBTC/USDC |
| -------------------- | ---------------------------------- |
| **Options Types**    | Call & Put                         |
| **Strike Prices**    | v3 pool ticks पर आधारित            |
| **Expiry Durations** | 1H, 2H, 6H, 12H, और 24H           |

**Exercise Conditions:** उपयोगकर्ता closure से पहले positions exercise कर सकते हैं ताकि in-the-money options worthless expire न हों। Auto-exercise enable करके expiry पर automatically profits realize की जा सकती हैं, जिससे आगे कोई action नहीं लेना होगा।

### चरण-दर-चरण मार्गदर्शिका

PancakeSwap CLAMM Options का उपयोग कैसे करें, इसकी चरण-दर-चरण मार्गदर्शिका यहाँ दी गई है।

**Traders के लिए:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**LPs के लिए:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
