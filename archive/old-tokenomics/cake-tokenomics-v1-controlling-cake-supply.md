# CAKE supply v1 को नियंत्रित करना

## CAKE का कोई hard cap क्यों नहीं है

CAKE token की supply पर वर्तमान में कोई hard cap नहीं है, जिससे यह एक inflationary token बनता है।

Community members अक्सर इसे चिंता के कारण के रूप में point out करते हैं, और जबकि chefs निश्चित रूप से hard cap की इच्छा को समझते हैं, एक बड़ा कारण है कि हम निकट भविष्य में एक set करने की उम्मीद नहीं करते:

> CAKE का primary function exchange को liquidity provide करने के लिए incentivize करना है। _बिना block rewards के, liquidity provide करने के लिए बहुत कम incentive होगा (LP fees आदि रहेंगे)।_

**तो CAKE की supply को limit करने के अन्य तरीके क्या हैं, inflation को counter करने के लिए?**

## Hard cap के बिना CAKE supply कैसे कम की जाती है

Chefs का लक्ष्य PancakeSwap के products में deflationary mechanisms build करके **deflation को emission से अधिक बनाना** है। लक्ष्य यह है कि circulation से जितना CAKE निकले उससे अधिक CAKE produced होने की तुलना में कम हो।

### Block emissions को कम करना

प्रति block बनाई गई CAKE की राशि कम करके, हम inflation को धीमा करते हैं। यह पहले ही एक बार किया जा चुका है: [block emissions में पहली कमी](https://voting.pancakeswap.finance/#/pancake/proposal/QmWSQZsqakCMQ1bmcoEsKzStdtdFHL6cohSjnMV9ira1EC) के बाद से, हमने effectively circulation में enter होने वाली CAKE की संख्या 40 CAKE per block से घटाकर 14.5 कर दी है। लेकिन हम इसे बहुत जल्दी, बहुत शुरुआत में नहीं करना चाहते, उसी कारण से जो hard cap नहीं चाहते: हमें अभी भी लोगों को liquidity provide करने के लिए incentivize करना है।

### Deflationary mechanisms

नियमित token burns ([burn address देखें](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead)) PancakeSwap के कई products में built-in हैं (जैसे lottery tickets पर खर्च की गई CAKE का 10% burn), और अधिक आने वाले हैं। वर्तमान और upcoming deflationary mechanisms के details के लिए [**CAKE Tokenomics page**](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics) देखें।
