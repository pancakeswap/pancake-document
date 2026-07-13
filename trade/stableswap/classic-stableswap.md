# Classic StableSwap

Classic StableSwap PancakeSwap पर Curve Finance के AMM का कार्यान्वयन है। यह constant product formula (x\*y=k) के ऊपर linear invariant constant sum curve (x+y=k) जोड़ता है ताकि जब तक तरलता पूल अत्यधिक असंतुलित न हो, कीमतें अधिक समान रहें। परिणामस्वरूप, चूंकि StableSwaps समान रूप से मूल्य वाली एसेट तक सीमित हैं, impermanent loss उतनी चिंता का विषय नहीं है (अत्यधिक depeg मामलों को छोड़कर) और स्लिपेज सामान्य AMM की तुलना में कम है जो केवल constant product formula का उपयोग करता है।

जब आप StableSwap पर एक Swap (व्यापार) करते हैं तो आप सामान्य PancakeSwap AMM के सामान्य 0.25% की तुलना में कम trading fees का भुगतान करेंगे। शुल्क वितरण इस प्रकार है:

* 50% LP को पुरस्कार के रूप में&#x20;
* 40% CAKE buyback और burn के लिए&#x20;
* 10% PancakeSwap Treasury को

## StableSwap शुल्क

जोड़ियों के शुल्क नीचे दी गई तालिका में विभाजित किए गए हैं:

<table><thead><tr><th width="150">Stablepair</th><th width="132">Trading Fees</th><th width="118.33333333333331">LP पुरस्कार</th><th width="124">CAKE Buyback</th><th>PancakeSwap Treasury</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-USDT</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>HAY-BUSD</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>HAY-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>axlUSDC-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>BNBx-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>stkBNB-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr></tbody></table>

Kitchen धीरे-धीरे StableSwap जोड़ियां लॉन्च करेगा और उत्पाद को आगे परीक्षण और बेहतर बनाने के लिए शुल्कों को संशोधित करेगा।

## मुझे सामान्य AMM Swap के बजाय StableSwap का उपयोग क्यों करना चाहिए?

* समान ट्रेड चरणों के साथ अपने stablecoins या समान एसेट मूल्यों वाली अन्य जोड़ियों को अधिक कुशलता से swap करें&#x20;
* StableSwap फ़ंक्शन के साथ, trading स्लिपेज सामान्य AMM की तुलना में कम है&#x20;
* StableSwap trading fees सामान्य AMM की तुलना में कम हैं
