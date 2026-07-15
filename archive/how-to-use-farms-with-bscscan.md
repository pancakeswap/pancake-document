# BscScan के साथ Farms का उपयोग कैसे करें

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

PancakeSwap के साथ Farms का उपयोग करना पहली बार में कठिन लग सकता है क्योंकि इसमें कई चरण शामिल हैं। यह गाइड आपको सीधे BscScan के माध्यम से Farms contract का उपयोग करने के बारे में बताएगी।

{% hint style="warning" %}
कृपया समझें कि contracts के साथ interact करने के लिए BscScan का उपयोग करना शुरुआती लोगों के लिए अनुशंसित नहीं है। यदि आप confident नहीं हैं, तो हम सुझाव देते हैं कि इसके बजाय [How to Use Farms guide](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) उपयोग करें।
{% endhint %}

## Farm process identifier खोजना

Farming smart contract के साथ सही ढंग से interact करने के लिए, आपको अपने LP pair के लिए matching process identifier (PID) की आवश्यकता होगी। अभी के लिए, इसे locate करने का सबसे आसान तरीका GitHub जांचना है।

1\. [GitHub पर PancakeSwap website के Farms code](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts) खोलें।

2\. **Control**/**command** + **F** दबाएं और ticker से अपना pair खोजें (project name से नहीं)। उदाहरण के लिए, 'CAKE-BUSD'।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. PID number लिखें या copy करें — इस मामले में 389 — कहीं ऐसी जगह जहाँ आप आसानी से access कर सकें। आपको बाद में इसकी आवश्यकता होगी।

## BscScan के माध्यम से LP Tokens Deposit करना

BscScan का उपयोग करके LP Tokens deposit करने में कुछ चीजें शामिल हैं। हमने इसे चरणों में तोड़ा है ताकि follow करना आसान हो।

### Main Staking Contract address प्राप्त करना

Main staking contract का address है: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

लेकिन यह मानते हुए कि आप confirm करना चाहेंगे, [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) पर जाएं। आपको ऊपर बाईं ओर address दिखेगा। इसे clipboard पर copy करने के लिए **pages icon** पर क्लिक करें। आपको इसकी जल्द ही आवश्यकता होगी।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### अपने LP Token के लिए contract खोलें

Farm में commit करने से पहले आपको जिस LP Token को spend करना चाहते हैं उसके लिए smart contract को approve करना होगा।

### Source code से

1\. पहले, [GitHub पर farms.ts](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts) खोलें।

2\. **Control**/**command** + **F** दबाएं और ticker से अपना pair खोजें (project name से नहीं)। उदाहरण के लिए, 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. जब आपके पास जिस LP pair की तलाश में हैं उसका code हो, "56:" के बाद address ढूंढें। यह आपका contract address होगा।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### UI से

1\. पहले, [PancakeSwap Farms page](https://pancakeswap.finance/farms) पर जाएं और ऊपर दाईं ओर "SEARCH" field का उपयोग करके अपना chosen pair खोजें। हम इस उदाहरण के लिए CAKE-BUSD उपयोग कर रहे हैं।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. अधिक जानकारी दिखाने के लिए row expand करने के लिए **Details** पर क्लिक करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. BscScan पर smart contract खोलने के लिए **View Contract** पर क्लिक करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### LP Token contract को permission देना

अब जब BscScan पर आपका LP Token's contract खुला है, तो आप Farm में अपने LP Tokens spend करने को approve करने जा रहे हैं।

1\. LP Token के contract page पर, **Contract** पर जाएं, फिर **Write Contract** पर।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask connect करने के लिए **Connect to Web3** पर क्लिक करें।

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Connection confirm करें।

3\. Function 1, "approve" के अंतर्गत, आपको "spender:address" दिखेगा। पहले clipboard पर copy किया गया Main Staking Contract का contract address paste करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. आपको contract जो LP Tokens spend कर सकता है उसकी amount भी approve करनी होगी। value field में, आपको Wei में amount दर्ज करना होगा। आप अपनी amount को आसानी से Wei में बदलने के लिए [BscScan Unit Converter](https://www.bscscan.com/unitconverter) का उपयोग कर सकते हैं। यहाँ हम 5 CAKE-BUSD LP Tokens उपयोग करेंगे।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
आप unlimited spend approval देने के लिए value के रूप में `-1` भी उपयोग कर सकते हैं। इसका मतलब यह नहीं है कि आप default रूप से सब कुछ spend करेंगे, बल्कि केवल यह कि इस contract का उपयोग करके किसी भी size का ट्रांजेक्शन आपके wallet द्वारा allow किया जाएगा।
{% endhint %}

6\. **Write** पर क्लिक करें और अपने MetaMask wallet में action accept करें। अब आप जितना approve किया है उतने amount तक LP Tokens Farm में commit करने में सक्षम हैं।

### Main Staking Contract smart contract के साथ LP Tokens Deposit करें

अब जब Main Staking Contract को आपके LP Tokens spend करने की approval मिल गई है, तो deposit करने का समय आ गया है।

1\. वापस [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) पर, **Contract** पर जाएं, फिर **Write Contract** पर।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask connect करने के लिए **Connect to Web3** पर क्लिक करें।

3\. Function 2, "deposit" तक scroll करें, और "\_pid" field में अपना PID type करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

यदि आपने अपना PID पहले copy नहीं किया, तो आप इस page पर ऊपर **Finding Farm process identifier** section में जानकारी प्राप्त कर सकते हैं।

4\. \_pid के नीचे आपको "\_amount" दिखेगा। LP contract को spend करने के लिए वह amount दर्ज करें जो आपने पहले approve किया था।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. जानकारी जांचें और **Write** पर क्लिक करें। MetaMask में अपना action confirm करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. आप **View your transaction** पर क्लिक करके confirm कर सकते हैं कि आपका deposit काम किया।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Pool से Withdrawing

Pool से अपने LP Tokens withdraw करना deposit करने के समान है। अंतर यह है कि आप किस function के साथ interact करेंगे।

1\. वापस [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) पर, **Contract** पर जाएं, फिर **Write Contract** पर।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask connect करने के लिए **Connect to Web3** पर क्लिक करें।

3\. Function 15, "withdraw" तक scroll करें, और "\_pid" field में अपना PID type करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

यदि आपने अपना PID पहले copy नहीं किया, तो आप इस page पर ऊपर **Finding Farm process identifier** section में जानकारी प्राप्त कर सकते हैं।

4\. \_pid के नीचे आपको "\_amount" दिखेगा। Pool से withdraw करने के लिए LP की amount दर्ज करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. जानकारी जांचें और **Write** पर क्लिक करें। MetaMask में अपना action confirm करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. आप **View your transaction** पर क्लिक करके confirm कर सकते हैं कि आपका withdrawal काम किया।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Emergency withdrawal करना**

Emergency withdraw function का उपयोग करने से आप तब pool से अपने सभी funds निकाल सकते हैं जब कोई अन्य तरीका काम नहीं कर रहा हो।

{% hint style="danger" %}
**Emergency withdraw function का उपयोग करने से आपके CAKE rewards जब्त हो जाएंगे!**

PancakeSwap team दृढ़ता से सुझाव देती है कि इस function से तब तक बचें जब तक PancakeSwap team द्वारा आधिकारिक रूप से सलाह न दी जाए, या यदि आप smart contracts के साथ interact करने में बहुत comfortable हैं और underlying code समझते हैं।
{% endhint %}

1\. [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) पर, **Contract** पर जाएं, फिर **Write Contract** पर।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask connect करने के लिए **Connect to Web3** पर क्लिक करें।

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

3\. Function 4, "emergencyWithdraw" तक scroll करें, और "\_pid" field में अपना PID type करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

यदि आपने अपना PID पहले copy नहीं किया, तो आप इस page पर ऊपर **Finding Farm process identifier** section में जानकारी प्राप्त कर सकते हैं।

5\. जानकारी जांचें और **Write** पर क्लिक करें। MetaMask में अपना action confirm करें।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. आप **View your transaction** पर क्लिक करके confirm कर सकते हैं कि आपका withdrawal काम किया।

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
