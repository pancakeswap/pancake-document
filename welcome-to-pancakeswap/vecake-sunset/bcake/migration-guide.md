---
description: >-
  bCAKE boosting का आनंद लेने के लिए अपनी V2, StableSwap या Position Manager तरलता Migrate करें
---

# Migration Guide

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-guide.png" alt=""><figcaption></figcaption></figure>

bCAKE के माध्यम से अपनी V2, StableSwap या Position Manager तरलता को boost करना शुरू करने के लिए, आपको पुराने contract से अपना LP unstake करके और नए में restake करके migration करनी होगी।

### Migration wizard पर जाएं

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Group%201410076909.png" alt="" width="189"><figcaption></figcaption></figure>

Farm या Position Manager पेज के शीर्ष पर banner खोजें, migration process शुरू करने के लिए "Proceed" पर क्लिक करें।

[Farm पर जाएं](https://pancakeswap.finance/farms)

[Position Manager पर जाएं](https://pancakeswap.finance/position-managers)

### पुराने contracts से अपने LP tokens Unstake करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/step1.png" alt=""><figcaption></figcaption></figure>

पहले चरण में, आपको V2, StableSwap farms और position managers की पूरी सूची दिखेगी जिन्हें bCAKE boosting का आनंद लेने के लिए migration की आवश्यकता है।

दाईं ओर "Unstake All" बटन पर क्लिक करें, और पुराने contracts से सभी LP tokens unstake करने के लिए अपने wallet app में tx confirm करें।

आपको उनमें से प्रत्येक को अलग-अलग unstake करना होगा।

सभी LPs unstake करने के बाद, अगले चरण पर जाने के लिए "Go to Stake" पर क्लिक करें।

### नए contracts में अपने LP tokens Restake करें

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/step2.png" alt=""><figcaption></figcaption></figure>

दूसरे चरण में, आपको V2, StableSwap farms और position managers की पूरी सूची दिखेगी जो restake के लिए उपलब्ध हैं।

पहले, deposits enable करने के लिए "Enable" बटन पर क्लिक करें।

फिर, नए contract में LP tokens restake करने के लिए "Restake" बटन पर क्लिक करें।

*   V2 और StableSwap farms के लिए, आपको नए pop-up modal में restake करने के लिए LP tokens की संख्या निर्धारित करनी होगी।<br>

    हम सभी LP tokens restake करने की सलाह देते हैं ताकि आप अधिकतम yield प्राप्त कर सकें।
*   Position Managers के लिए, बस अपने wallet में tx confirm करें, आपके सभी Position Managers LPs नए contracts में restake हो जाएंगे।<br>

    चूँकि Position Manager LPs को अलग-अलग process नहीं किया जा सकता, हम दृढ़ता से सलाह देते हैं कि सभी position managers LP को नए contracts में restake करें।

Restake होने के बाद, बटन "Staked" में बदल जाएंगे।

आपको उनमें से प्रत्येक को अलग-अलग restake करना होगा।

सभी LPs restake करने के बाद, Farm पेज पर वापस जाने के लिए "Finish" पर क्लिक करें।
