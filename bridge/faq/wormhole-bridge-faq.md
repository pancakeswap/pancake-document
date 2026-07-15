---
hidden: true
---

# Wormhole Bridge FAQ

### प्र: मैं अपना ट्रांजैक्शन कैसे देख सकता/सकती हूं? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole Explorer

Bridge स्थिति पृष्ठ पर, आप एक लिंक देख सकते हैं जो आपको Wormhole Explorer पर आपके ट्रांजैक्शन तक ले जाएगा। जब आपकी स्रोत चेन ट्रांजैक्शन पूरी हो गई हो लेकिन Wormhole द्वारा अभी तक सत्यापित न हुई हो, तो आपकी ट्रांजैक्शन स्थिति इस तरह दिखेगी:

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

"find redeem" विकल्प एक वैकल्पिक तरीका है जिसका उपयोग आप अपनी गंतव्य चेन ट्रांजैक्शन पूरी करने के लिए कर सकते हैं। इस तरीके का उपयोग उस स्थिति में किया जा सकता है जब Wormhole Bridge रुक जाए या आपके Bridge ट्रांजैक्शन की स्थिति अपडेट करने में विफल हो। अपना ट्रांजैक्शन रिडीम करने के लिए पहले redeem बटन पर क्लिक करें।

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

फिर यह आपका ट्रांजैक्शन रिज्यूम करने का विकल्प दिखाएगा। फोरम (अगले प्रश्न में लिंक) पर जाने के लिए इस पर क्लिक करें जहां आप अपना रिडेम्प्शन ट्रांजैक्शन पूरा कर सकते हैं। <br>

### प्र: मैंने \<chain> पर टोकन भेजे — मेरे टोकन मेरे लक्ष्य वॉलेट में नहीं पहुंचे, लेकिन मेरे मूल वॉलेट से चले गए। मुझे क्या करना चाहिए?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

आपको या तो a) उन्हें रिडीम करना होगा, या, यदि रिडेम्पशन पहले से सफल हो चुकी है, तो b) उन्हें अपने वॉलेट में जोड़ना होगा:

**a) रिडीम करना:**

* [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem) पर जाएं
* आपको अपनी स्रोत चेन और संबंधित ट्रांजैक्शन ID दर्ज करनी होगी (जो आप अपने वॉलेट में या ब्लॉकचेन एक्सप्लोरर में अपने पते से खोज सकते हैं)

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Recover पर क्लिक करें
* Redeem पर क्लिक करें और वॉलेट अनुमोदन स्वीकार करें

**b) उन्हें अपने वॉलेट में जोड़ें:**

**Metamask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* Metamask के assets टैब में, import tokens पर क्लिक करें
* कॉन्ट्रैक्ट पता संबंधित ब्लॉक एक्सप्लोरर ट्रांजैक्शन में और टोकन नाम पर क्लिक करके मिलेगा। जब आप टोकन नाम पर क्लिक करते हैं, तो एक नई विंडो खुलेगी और कॉन्ट्रैक्ट पता प्रोफाइल सारांश में दाईं ओर होगा।
* आपको एक सिंबल भी चाहिए — यह कुछ भी हो सकता है जिससे आप टोकन को पहचान सकें।
* add custom token पर क्लिक करें

वीडियो ट्यूटोरियल देखें - अपने Metamask वॉलेट में टोकन कैसे जोड़ें [यहां।](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### मैंने X टोकन Bridge किया लेकिन अब उसे Swap नहीं कर पा रहा/रही। कोई DEX पर तरल बाज़ार नहीं हैं,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

आपने एक ऐसा टोकन Bridge किया है जिसकी लक्ष्य चेन पर कोई तरलता नहीं है। आपको इसे वापस Bridge करने के लिए Portal bridge का उपयोग करना होगा। आप टोकन कॉन्ट्रैक्ट पता (जो आपके वॉलेट में या ब्लॉकचेन एक्सप्लोरर में अपने पते से मिलेगा) को Portal के "select a token" खोज फ़ील्ड में पेस्ट करके यह कर सकते हैं।

तरल बाज़ारों का व्यापक अवलोकन [यहां](https://portalbridge.com/docs/faqs/liquid-markets) मिलेगा।

#### मैं लक्ष्य चेन पर अपने टोकन कैसे रिडीम कर सकता/सकती हूं?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

यदि आपने ट्रांसफर प्रक्रिया के दौरान गलती से पृष्ठ रीफ्रेश कर दिया या अपने टोकन रिडीम नहीं किए, तो आप [यहां](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow) दिए गए ट्यूटोरियल का पालन कर सकते हैं।
