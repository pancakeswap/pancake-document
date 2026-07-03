# Perpetuals V1 Glossar

**Hier finden Sie alle Begriffe, die im Futures Trading relevant sind, mit ihren Definitionen.**

### **Perpetual Trading**

&#x20;Perpetuals, Perpetual Swaps oder Perps sind eine besondere Art von Terminkontrakten ohne Ablaufdatum.



### **Hebel**

Der Hebel ist ein Handelsmechanismus. Händler können ihn nutzen, um ihr Marktengagement zu erhöhen, indem sie weniger als den vollen Investitionsbetrag zahlen. Einfach ausgedrückt: Sie leihen sich Geld, um Ihre Investition zu hebeln.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Margin**

Die Margin ist die Sicherheitsleistung für Ihre gehebelten Positionen. Sie können in zwei Modi verwendet werden:

* Cross Margin-Modus: Alle Cross-Positionen unter demselben Margin-Asset teilen sich dieselbe Cross-Margin-Bilanz des Assets. Im Falle einer Liquidierung können die vollständige Margin-Bilanz des Assets sowie alle verbleibenden offenen Positionen unter dem Asset eingezogen werden.
* Isolated Margin-Modus: Verwalten Sie Ihr Risiko bei einzelnen Positionen, indem Sie die für jede Position zugewiesene Margin einschränken. Wenn die Margin-Quote einer Position 100 % erreicht, wird die Position liquidiert. Im Isolated-Modus kann die Margin zu Positionen hinzugefügt oder davon abgezogen werden.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Margin-Quote**: Margin-Quote = Wartungsmargin / Margin-Bilanz. Ihre Positionen werden liquidiert, sobald die Margin-Quote 100 % erreicht.

**Wartungsquote**: Der Mindestbetrag der Margin-Bilanz, der erforderlich ist, um Ihre offenen Positionen aufrechtzuerhalten.

**Margin-Bilanz** = Wallet-Bilanz + nicht realisierter PNL. Ihre Positionen werden liquidiert, sobald die Margin-Bilanz ≤ der Wartungsmargin ist.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Assets:

**Einzahlen**: Guthaben in Ihr Futures-Konto einzahlen

**Abheben**: Guthaben von Ihrem Futures-Konto in Ihre Wallet abheben

**Bilanz**: Wallet-Bilanz = Gesamtnettotransfer + Gesamter realisierter Gewinn + Gesamte Netto-Finanzierungsgebühr – Gesamte Provision.

**Nicht realisierter PNL**: Nicht realisierter Gewinn und Verlust dieser Position, berechnet anhand des Mark-Preises, sowie die prozentuale Eigenkapitalrendite.

**Modi:**&#x20;

* Single Asset-Modus: Unterstützt USDⓈ-M Futures Trading ausschließlich mit dem einzelnen Margin-Asset des Symbols. PNL von Positionen desselben Margin-Assets können verrechnet werden. Unterstützt Cross Margin-Modus und Isolated Margin-Modus.
* Multi-Assets-Modus: USDⓈ-M Futures Trading über mehrere Margin-Assets hinweg. PNL kann zwischen verschiedenen Margin-Asset-Positionen verrechnet werden. Unterstützt nur den Cross Margin-Modus.

{% hint style="info" %}
Hinweis: Wenn offene Positionen oder offene Orders in USDⓈ-M Futures vorhanden sind, kann der Multi-Assets-Modus nicht aktiviert werden. Der Multi-Assets-Modus gilt nur für USDⓈ-M Futures. Vor der Aktivierung des Multi-Assets-Modus lesen Sie bitte den Leitfaden im Detail, um das Risiko des USDⓈ-M Futures-Kontos bei der Verwendung des Multi-Assets-Modus besser zu verwalten.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Orders

**Kaufen/Long:** Eine Long-Order eröffnen. Bei dieser Order kaufen Sie ein Asset und warten darauf, es zu verkaufen, wenn der Preis steigt. „Kaufen" und „Long" werden synonym verwendet.

**Verkaufen/Short:** Eine Short-Order eröffnen. Bei dieser Order leihen Sie sich ein Asset, verkaufen es und hoffen, es zurückzukaufen, wenn der Preis fällt. „Verkaufen" und „Short" werden synonym verwendet.

**Limit Order:** Eine Limit Order ist eine Order zum Kauf oder Verkauf zu einem bestimmten Preis oder besser. Limit Orders sind nicht garantiert ausführbar.

**Market Order:** Eine Market Order ist eine Order zum Kauf oder Verkauf zum besten verfügbaren aktuellen Preis. Sie wird gegen die Limit Orders ausgeführt, die zuvor im Orderbuch platziert wurden. Bei der Platzierung einer Market Order zahlen Sie Gebühren als Market Taker.

**Stop-Limit Order:** Am einfachsten lässt sich eine Stop-Limit Order verstehen, wenn man sie in Stop-Preis und Limit-Preis aufteilt. Der Stop-Preis ist einfach der Preis, der die Limit Order auslöst, und der Limit-Preis ist der Preis der ausgelösten Limit Order. Das bedeutet, dass Ihre Limit Order sofort ins Orderbuch aufgenommen wird, sobald Ihr Stop-Preis erreicht ist.

**Stop-Market Order:** Ähnlich wie eine Stop-Limit Order verwendet eine Stop-Market Order einen Stop-Preis als Auslöser. Wenn der Stop-Preis jedoch erreicht wird, wird stattdessen eine Market Order ausgelöst.

**Trailing Stop:** Ein Trailing Stop ist ein Ordertyp, der darauf ausgelegt ist, Gewinne zu sichern oder Verluste zu begrenzen, wenn sich ein Trade günstig entwickelt. Trailing Stops bewegen sich nur, wenn sich der Preis günstig entwickelt. Sobald sie sich zur Gewinnabsicherung oder Verlustbegrenzung bewegt haben, kehren sie nicht mehr in die andere Richtung zurück.

**Post Only:** Der Post-Only-Modus bedeutet, dass Händler eine Order nur dann platzieren können, wenn sie als Maker-Order ins Orderbuch aufgenommen würde. Eine Order, die als Taker-Order aufgenommen würde, wird abgelehnt. Es können keine Market Orders platziert und keine Orders ausgeführt werden. Ruhende Orders können im Post-Only-Modus storniert werden.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QPVj03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Reduce Only:** Eine Reduce-Only-Order reduziert Ihre Position nur, erhöht sie aber nicht.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF-Anweisungen** ermöglichen es Ihnen, die Gültigkeitsdauer Ihrer Orders festzulegen, bevor sie ausgeführt oder verfallen. Sie können eine der folgenden Optionen für TIF-Anweisungen auswählen:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel): Die Order bleibt aktiv, bis sie entweder ausgeführt oder storniert wird.&#x20;
* **IOC** (Immediate Or Cancel): Die Order wird sofort ausgeführt (entweder vollständig oder teilweise). Wenn sie nur teilweise ausgeführt wird, wird der nicht ausgeführte Teil der Order storniert.&#x20;
* **FOK** (Fill Or Kill): Die Order muss sofort vollständig ausgeführt werden. Andernfalls wird sie gar nicht ausgeführt.
