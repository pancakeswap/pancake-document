# Syrup Pool FAQ & Fehlerbehebung

## Fehlerbehebung

### **Ich kann den Syrup Pool, in dem ich gestakt habe, nicht finden!**

Den Syrup Pool sollten Sie auf der Syrup-Pools-Seite unter dem Tab „Abgeschlossen" finden.

Durch Auswahl von „Nur gestakte" wird es einfacher, Ihre Vermögenswerte zu finden.

### **Warum kann ich meine Token nicht aus einem Syrup Pool unstaken?**

Wenn Sie nicht aus dem „CAKE staken, CAKE verdienen"-Pool unstaken können, überprüfen Sie bitte, ob Sie die SYRUP-Token in Ihrer Wallet noch besitzen. Dieser Token dient als `Eigentumsnachweis` über Ihr CAKE im Manual-CAKE-Pool.

### **Warum sind meine verdienten Token nach dem Staken/Unstaken auf null gegangen?**

Keine Sorge! Sie befinden sich bereits in Ihrer Wallet.

Wenn Sie in einem Syrup Pool oder einer Farm staken oder unstaken, werden Ihre verdienten Token gleichzeitig geerntet und an Ihre Wallet gesendet.

## **Allgemeine Fragen**

### Wie wird der APR für Syrup Pools berechnet?

> Syrup Pool APR = Annualisierte Rewards (USD) / In Syrup Pool gestakte Nutzermittel (USD) × 100

Als einfaches Beispiel nehmen wir einen 60-tägigen Pool mit Rewards im Wert von 300.000 USD und CAKE im Wert von 3.000.000 USD, der darin gestakt ist.

Der APR schwankt, wenn mehr CAKE von Nutzern gestakt wird und sich der Preis von CAKE sowie des Reward-Tokens ändert.

|                                                          | **Berechnung**                   | Betrag                                       |
| -------------------------------------------------------- | -------------------------------- | -------------------------------------------- |
| Gesamte zu verteilende Rewards (USD-Wert)                |                                  | 300.000 USD                                  |
| Ausschüttungszeitraum                                    |                                  | 60 Tage                                      |
| Tägliche Ausschüttung                                    | 300.000 / 60 =                   | 5.000 USD täglich                            |
| **Annualisierte Rewards (USD-Wert)**                     | 5.000 × 365 =                    | **1.825.000 USD**                            |
| **Wert der von Nutzern im Pool gestakten CAKE (USD-Wert)** |                                  | **3.000.000 USD**                            |
| **APR**                                                  | (1.825.000 / 3.000.000) × 100 =  | <p></p><p><strong>60,833 % APR</strong></p>  |

### **Was bedeutet die „Ende"-Zahl in meinem Syrup Pool?**

Diese zeigt die Anzahl der verbleibenden Blöcke, bis die Rewards für diesen Pool nicht mehr verteilt werden. Sobald der Pool diesen Block erreicht hat, sollten Sie Ihre Token unstaken, da Sie danach keine Rewards mehr erhalten.

### **Woher stammen die Rewards aus Syrup Pools?**

Es gibt drei Haupttypen von Syrup Pools.

1. CAKE staken, CAKE verdienen
2. CAKE staken, andere Token verdienen.&#x20;
3. Andere Token staken, CAKE verdienen

Die Rewards für die „CAKE staken, CAKE verdienen"-Syrup-Pools stammen aus den [CAKE-Emissionen](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Pro Block wird eine bestimmte Anzahl von CAKE-Token als Rewards für diese Pools zugeteilt.

Die Rewards für den Typ „CAKE staken, andere Token verdienen" werden von den Projekt-Teams bereitgestellt, die einen Syrup Pool sponsern.

Beim Typ „Andere Token staken, CAKE verdienen" kauft die PancakeSwap-Treasury CAKE vom Markt zurück, um es als Rewards zu verteilen. Diese Pools werden von PancakeSwap finanziert, nicht von den Projekten selbst.

### Was ist der SYRUP-Token?

PancakeSwap's SYRUP-Token wird in Ihrer Wallet hinterlegt, wenn Sie mit dem **manuellen** „CAKE staken, CAKE verdienen"-Syrup-Pool interagieren. Er wird nicht gestakt.

Er ist im Grunde ein Schuldschein, der anzeigt, wie viel CAKE Sie im Pool gestakt haben.

Er wird automatisch zurückgegeben, wenn Sie Ihr CAKE aus diesem Pool unstaken.

{% hint style="warning" %}
Verkaufen Sie Ihre SYRUP-Token nicht! Sie müssen Ihren SYRUP zurückgeben, um Ihr CAKE aus dem Manual-CAKE-Pool zu unstaken. Die Menge an SYRUP, die Sie zurückgeben, muss der Menge an CAKE entsprechen, die Sie unstaken.
{% endhint %}
