# Social Login FAQ

{% hint style="info" %}
Weitere Informationen finden Sie unter: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Allgemeine Übersicht

**1. Was ist der Social Login von PancakeSwap und warum sollte ich ihn nutzen?**

Social Login ermöglicht Ihnen den Zugriff auf PancakeSwap mit Ihrem **Google**-, **X-(Twitter)**-, **Discord**- oder **Telegram**-Konto – keine Wallet-Erweiterung oder Seed-Phrase erforderlich. Im Hintergrund wird eine selbst-verwaltete Wallet erstellt, sodass Sie DeFi sofort ausprobieren können, auch mit kleinen Beträgen. Dies senkt die Einstiegshürde, insbesondere in zeitkritischen Momenten.

**2. Welche Chains unterstützt der Social Login?**

Ihre Social-Login-Wallet funktioniert auf allen derzeit von PancakeSwap unterstützten Chains:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Alle Wallets sind **EVM-kompatibel** und können nativ über PancakeSwap in diesen Netzwerken verwendet werden. Wenn Sie Unterstützung für andere Chains wünschen (einschließlich Nicht-EVM), teilen Sie es uns mit!

**3. Wo kann ich die Social-Login-Wallet verwenden?**

Sie können sie direkt in jedem Desktop- oder mobilen **Browser** über die PancakeSwap-Web-App nutzen. Sie ist **nicht kompatibel** mit externen Wallet-Apps oder dApp-Browsern.



### 🛠️ Wallet-Einrichtung und Nutzung

**4. Wie wird die Wallet erstellt und gesichert?**

Ihre Wallet wird automatisch beim Login erstellt und mit einem **2-von-2-Schlüsselfreigabe-System** gesichert. Beide Freigaben sind erforderlich, um den Schlüssel zu rekonstruieren und eine Signatur zu generieren.

Weitere Informationen zur Freigabeverschlüsselung:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Wie viele Wallets kann ich erstellen?**

Sie erhalten **eine Wallet pro Social-Konto pro dApp**. Wenn Sie beispielsweise Ihren Google-Login in einer anderen App verwenden, die ebenfalls Privy nutzt, wird eine separate Wallet erstellt.



### 🔐 Sicherheit und Datenschutz

**6. Kann jemand auf meine Wallet zugreifen, wenn er mein Gerät stiehlt?**

Nein. Selbst wenn jemand Zugang zu Ihrem Gerät erhält, benötigt er zusätzlich Ihren **Social Login** und (falls festgelegt) Ihr **Wiederherstellungspasswort**.

**7. Welche Daten werden von PancakeSwap oder Privy gespeichert?**

* PancakeSwap **speichert keine** wallet-bezogenen Schlüsselfreigaben.
* Privy speichert die **verschlüsselte Auth-Freigabe und Wiederherstellungsfreigabe (falls kein Wiederherstellungsablauf eingerichtet ist)**.

> Wenn Sie das Wiederherstellungs-Setup nicht abgeschlossen haben, wird Ihre Wiederherstellungsfreigabe standardmäßig bei Privy gespeichert. Weitere Informationen: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Wiederherstellung und Sitzungsverwaltung

**8. Kann ich dieselbe Wallet auf einem anderen Gerät oder Browser verwenden?**

Ja! Melden Sie sich einfach mit demselben Social-Konto an. Bei einem neuen Gerät werden Sie durch den Wiederherstellungsprozess mit Ihrem Wiederherstellungspasswort (falls eingerichtet) geführt.

**9. Was passiert, wenn ich das Gerät wechsle?**

Sie werden aufgefordert, sich erneut mit Ihrem Social-Konto anzumelden und den Wiederherstellungsablauf zu durchlaufen (Passworteinrichtung). Wenn Sie kein Wiederherstellungspasswort eingerichtet haben, ist der Social-Konto-Login ausreichend.

**10. Was, wenn ich den Zugang zu meinem Social Login und meiner Wiederherstellungsmethode verliere?**

Wenn Sie den Zugang zu beiden verlieren – Ihrem Social-Konto und Ihrer Wiederherstellungsmethode – **kann Ihre Wallet nicht wiederhergestellt werden**. Es gibt keinen Fallback über eine Seed-Phrase, und der Export eines privaten Schlüssels wird derzeit nicht unterstützt.

> ⚠️ Denken Sie daran: Der Export Ihres privaten Schlüssels, falls in Zukunft aktiviert, würde jedem, der ihn besitzt, die vollständige Kontrolle über Ihre Wallet gewähren – behandeln Sie ihn mit äußerster Vorsicht.

**11. Wie lange dauern aktive Sitzungen?**

Sitzungen dauern 30 **Tage**. Danach werden Sie aufgefordert, sich **erneut anzumelden** und (falls erforderlich) Ihre Wiederherstellungsdaten erneut einzugeben. Während einer aktiven Sitzung können Sie Transaktionen durchführen, ohne jede Aktion manuell genehmigen zu müssen.



### ⚙️ Kompatibilität und Einschränkungen

**12. Kann ich Wallets exportieren oder importieren?**

* **Export**: Aus Sicherheitsgründen nicht standardmäßig unterstützt. Dies kann sich in zukünftigen Updates ändern.
* **Import**: Nicht unterstützt. Sie können keine externen Wallets wie MetaMask oder Phantom importieren.

**13. Kann ich diese Wallet über WalletConnect mit anderen dApps verbinden?**

Derzeit nicht. Die eingebettete Wallet ist **auf PancakeSwap beschränkt**. Wenn Sie daran interessiert sind, sie breiter zu nutzen, teilen Sie es uns mit – zukünftige Erweiterungen sind möglich.



### 🚀 Erweiterte Funktionen

**14. Unterstützt die Social-Login-Wallet Account Abstraction?**

Ja. Sie unterstützt **Account Abstraction-Funktionen** wie Transaktionsbündelung und **Gasfinanzierung** durch Integrationen wie Biconomy usw.

**15. Wie werden signaturfreie Transaktionen ermöglicht?**

* Nach dem Login ist Ihre Sitzung bis zu 30 **Tage** aktiv. Während dieser Zeit kann PancakeSwap Privy bitten, Transaktionen in Ihrem Namen mit Ihren Sitzungsanmeldeinformationen zu unterzeichnen.&#x20;
* Sie sehen für jede Aktion kein Wallet-Popup – alles wird im Hintergrund erledigt. Nach 30 Tagen müssen Sie sich erneut anmelden, um dieses signaturfreie Erlebnis weiter zu nutzen.
