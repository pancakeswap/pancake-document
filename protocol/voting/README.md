# 📔 Governance

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
[Tokenomics 3.0 upgrade](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) के हिस्से के रूप में, यह पेज 15 मई 2025 को अपडेट किया गया है
{% endhint %}

Voting PancakeSwap समुदाय को एक आवाज़ देता है, जिससे समुदाय को यह कहने का अधिकार मिलता है कि PancakeSwap भविष्य में कैसे विकसित होगा।

[PancakeSwap के native voting portal](https://pancakeswap.finance/voting) और हमारे [Forum](https://forum.pancakeswap.finance/) पेज देखें।

## Voting Mechanics

:notebook\_with\_decorative\_cover:सारांश - क्या बदला ([Tokenomics 3.0 Update](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) के बाद)

<table><thead><tr><th width="200.6015625">Governance Component</th><th width="218.01953125">Tokenomics 3.0 से पहले</th><th width="205.1796875">Tokenomics 3.0 के बाद</th><th>स्थिति<select><option value="q1dVFsCri7zA" label="✅ बदला" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 अपरिवर्तित" color="blue"></option></select></th></tr></thead><tbody><tr><td>Voting Power</td><td>1 veCAKE = 1 voting power</td><td>1 CAKE = 1 voting power</td><td><span data-option="q1dVFsCri7zA">✅ बदला</span></td></tr><tr><td>Delegation</td><td>Allowed (veCAKE mechanics के माध्यम से)</td><td>Delegation allowed नहीं है</td><td><span data-option="q1dVFsCri7zA">✅ बदला</span></td></tr><tr><td>Proposal Submission Threshold</td><td>Snapshot 100K veCAKE required</td><td>Snapshot 100K CAKE required</td><td><span data-option="q1dVFsCri7zA">✅ बदला</span></td></tr><tr><td>Core vs Community Proposals</td><td>प्रत्येक proposal type के लिए defined roles और purposes</td><td>कोई परिवर्तन नहीं</td><td><span data-option="4AGl26rwjYcI">🔁 अपरिवर्तित</span></td></tr><tr><td>Voting Period</td><td>Community: Fixed<br>Core: Variable</td><td>कोई परिवर्तन नहीं</td><td><span data-option="4AGl26rwjYcI">🔁 अपरिवर्तित</span></td></tr><tr><td>Snapshot Timing</td><td>Proposal posted block पर</td><td>कोई परिवर्तन नहीं</td><td><span data-option="4AGl26rwjYcI">🔁 अपरिवर्तित</span></td></tr><tr><td>Quorum</td><td>कोई minimum quorum नहीं</td><td>कोई परिवर्तन नहीं</td><td><span data-option="4AGl26rwjYcI">🔁 अपरिवर्तित</span></td></tr></tbody></table>

### 1. **Voting Power (बदला)**

* **सभी CAKE holders के पास direct voting rights हैं।**
* **Voting power snapshot के दौरान wallet address में held CAKE की संख्या के सीधे अनुरूप है**
  * **1 CAKE = 1 voting power**
  * **Syrup Pools में staked CAKE आपकी voting power में नहीं गिनती**, क्योंकि यह snapshot के समय आपकी wallet balance का हिस्सा नहीं है
  * Snapshot balance = Same block proposal posted
* **Delegation अब समर्थित नहीं है।** हर CAKE holder को individually vote करना होगा।

### 2. **Proposal Submission (अपरिवर्तित)**

* **Proposal कैसे Submit करें**
  * [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create) पर Submit करें
  * इसमें शामिल होना चाहिए:
    * Title
    * Content
    * Description
    * On-chain action(s) (यदि आवश्यक हो)
    * Voting Duration
* Proposals के प्रकार
  1.  Core Proposals

      * केवल **PancakeSwap Core Team** द्वारा propose किए जा सकते हैं।
      * CAKE holders द्वारा vote की आवश्यकता है।
      * Pass होने पर, PancakeSwap team द्वारा implement किए जाएंगे।

      उदाहरण

      1. Protocol adjustments (product changes, fee changes)
      2. Ecosystem Growth funds के significant uses जो पिछले proposals में शामिल नहीं हैं
  2. Community Proposals
     * **Community** proposals PancakeSwap community द्वारा post किए जाते हैं। इनका उपयोग ideas propose करने और community का point of view व्यक्त करने के लिए किया जाता है। ये community की **non-binding suggestions** हैं।
     * **100,000 CAKE (snapshot balance)** वाला कोई भी submit कर सकता है।
     * PancakeSwap team मजबूत proposals को भविष्य के Core Proposals में adopt कर सकती है
     * Community members protocol को feedback और suggestions देने के लिए हमारे [Forum](https://forum.pancakeswap.finance/) का भी उपयोग कर सकते हैं।

### **3. Voting Duration (अपरिवर्तित)**

* सभी CAKE holders प्रत्येक proposal के लिए **voting window के दौरान** vote कर सकते हैं।
  * Community proposal: 3 दिनों पर Fixed
  * Core Proposal: Variable, PancakeSwap द्वारा निर्धारित
* आपकी voting power **proposal post होने पर block में आपके CAKE balance के snapshot** से निर्धारित होती है।
* **Proposal post होने के बाद अधिक CAKE जोड़ने से उस specific vote के लिए आपकी voting power नहीं बढ़ेगी।**

पूरी जानकारी के लिए, [Voting Guide](https://docs.pancakeswap.finance/protocol/voting/voting-guide) देखें।

### **4. Voting Outcome (अपरिवर्तित)**

* परिणाम **कुल votes cast** (voting के लिए उपयोग किए गए total CAKE) पर आधारित है
* **वर्तमान में proposal pass होने के लिए कोई minimum quorum आवश्यक नहीं है।**

## नोट: Veto Rights

Protocol की सुरक्षा के लिए, **PancakeSwap Core Team critical situations में हस्तक्षेप करने का अधिकार सुरक्षित रखती है** — जैसे security threats या platform के स्थिर संचालन को प्रभावित करने वाले मुद्दे — **community vote या Snapshot poll की आवश्यकता के बिना**।

किसी भी मामले में जहाँ veto action लिया जाता है, Core Team **निर्णय की एक स्पष्ट व्याख्या सार्वजनिक रूप से share करेगी**।

**Possible veto actions में शामिल हो सकते हैं:**

1. **Smart contracts को अस्थायी रूप से pause करना** urgent bugs या vulnerabilities ठीक करने के लिए।
