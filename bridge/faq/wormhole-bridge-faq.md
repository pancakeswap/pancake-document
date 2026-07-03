---
hidden: true
---

# Wormhole Bridge FAQ

### F: Wie kann ich meine Transaktion überprüfen? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole Explorer

Auf der Bridge-Statusseite finden Sie einen Link, der Sie zu Ihrer Transaktion im Wormhole Explorer führt. Wenn Ihre Quell-Chain-Transaktion abgeschlossen, aber noch nicht von Wormhole verifiziert wurde, sieht Ihr Transaktionsstatus folgendermaßen aus:

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

Die Option „Find Redeem" ist eine alternative Methode, mit der Sie Ihre Ziel-Chain-Transaktion abschließen können. Sie können diese Methode verwenden, wenn die Wormhole Bridge ins Stocken gerät oder den Status Ihrer Bridge-Transaktion nicht aktualisiert. Um Ihre Transaktion einzulösen, klicken Sie zunächst auf den Redeem-Button.

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

Anschließend wird diese Option angezeigt, um Ihre Transaktion fortzusetzen. Klicken Sie darauf, um zum Forum weitergeleitet zu werden (Link in der nächsten Frage), wo Sie Ihre Einlösungstransaktion abschließen können. <br>

### F: Ich habe Token an \<Chain> gesendet – meine Token sind nicht in meiner Ziel-Wallet angekommen, aber meine Ursprungs-Wallet hat sie verlassen. Was soll ich tun?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

Sie müssen entweder a) die Token einlösen, oder, falls die Einlösung bereits erfolgreich war, b) sie zu Ihrer Wallet hinzufügen:

**a) Einlösen:**

* Öffnen Sie [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)
* Sie müssen Ihre Quell-Chain und die entsprechende Transaktions-ID eingeben (diese finden Sie in Ihrer Wallet oder mit Ihrer Adresse im Block-Explorer der Blockchain).

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIEaCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Klicken Sie auf „Recover"
* Klicken Sie auf „Redeem" und bestätigen Sie die Wallet-Genehmigung

**b) Zur Wallet hinzufügen:**

**MetaMask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* Klicken Sie im MetaMask-Assets-Tab auf „Import Tokens"
* Die Vertragsadresse finden Sie in der entsprechenden Block-Explorer-Transaktion, indem Sie auf den Token-Namen klicken. Wenn Sie auf den Token-Namen klicken, öffnet sich ein neues Fenster und die Vertragsadresse befindet sich auf der rechten Seite in der Profilübersicht.
* Sie benötigen außerdem ein Symbol – dieses kann beliebig sein, damit Sie den Token erkennen.
* Klicken Sie auf „Add Custom Token"

Sehen Sie sich das Video-Tutorial an – So fügen Sie einen Token zu Ihrer MetaMask Wallet hinzu [hier.](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### Ich habe Token X gebrückt, kann ihn aber jetzt nicht swappen. Kein DEX hat liquide Märkte,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

Sie haben einen Token gebrückt, der auf der Ziel-Chain keine Liquidität hat. Sie müssen die Portal Bridge verwenden, um diesen Token zurückzubridgen. Sie können dies tun, indem Sie die Token-Vertragsadresse (die Sie in Ihrer Wallet oder mit Ihrer Adresse im Block-Explorer der Blockchain finden) in das Suchfeld „Token auswählen" von Portal einfügen.

Eine umfassende Übersicht der liquiden Märkte finden Sie [hier](https://portalbridge.com/docs/faqs/liquid-markets).

#### Wie kann ich meine Token auf der Ziel-Chain einlösen?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

Falls Sie die Seite während des Übertragungsprozesses versehentlich aktualisiert haben oder Ihre Token nicht eingelöst haben, können Sie dem Tutorial [hier](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow) folgen.
