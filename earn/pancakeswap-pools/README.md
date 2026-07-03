# 🌊 Liquidity Pools

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

Im neuen Exchange V3 wird Liquidität in Form von nicht-fungiblen Positionen verwaltet. Sie erhalten weiterhin einen Anteil an den Gebühren, während Sie Liquidität bereitstellen.

Wenn Sie Ihren Token einem Liquiditätspool hinzufügen, erhalten Sie Liquidity Provider NFT-Token und teilen sich die Gebühren.

### **Nicht-fungible Liquiditätspositionen**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

In V3 haben Liquiditätsanbieter nun mehr Kontrolle darüber, in welcher Preisspanne sie ihre Liquidität einsetzen möchten. Wenn Sie Ihren Token in V3 einem Liquiditätspool hinzufügen, erstellen Sie eine neue nicht-fungible Liquiditätsposition mit ihren eigenen einzigartigen Einstellungen.

Daher sind Liquiditätspositionen in V3 NFTs. Bitte beachten Sie, dass diese NFTs übertragbar sind und das Eigentum an den zugrunde liegenden Assets sowie den damit verdienten Handelsgebühren repräsentieren.

In V3 werden Handelsgebühren nicht mehr automatisch in der Position aufgezinst. Sie können diese manuell auf jeder Positionsdetailseite abrufen.

Sie können Ihre Mittel jederzeit zurückerhalten, indem Sie Ihre Liquidität entfernen.

### **Aktive Liquidität und Preisspannen**

In V3 können Liquiditätsanbieter ihre Positionen so konfigurieren, dass sie nur dann Liquidität bereitstellen, wenn der Preis innerhalb einer bestimmten Spanne liegt. Wenn sich der Handelspreis aus der Spanne herausbewegt, besteht die Position nur noch aus einem Token-Typ des Paares und wird inaktiv.

Inaktive Liquiditätspositionen nehmen nicht am Handel teil und verdienen keine Handelsgebühren.

### **Konzentrierte Liquidität**

In V3 können Liquiditätsanbieter ihre Token-Einlagen auf eine bestimmte Preisspanne konzentrieren, um nur innerhalb dieser Spanne Liquidität bereitzustellen. Mit der gleichen Menge an zugrunde liegenden Assets kann V3 einen deutlich größeren Handel unterstützen.

Dies führt zu einem deutlich höheren relativen Liquiditätsniveau im Vergleich zu V2. Und Liquiditätsanbieter können mit dem gleichen Kapitaleinsatz mehr Handelsgebühren verdienen.

Hier ist ein Beispiel:

> Baller und Claire haben beide im CAKE/USDT Pool mit Token-Assets im Wert von 1.000 USD Liquidität bereitgestellt. Der aktuelle Preis von CAKE beträgt 5 USDT.
>
> Ähnlich wie bei PancakeSwap v2 hat Baller seine Liquidität über die gesamte Preisspanne bereitgestellt. Er hat daher sein gesamtes Kapital eingezahlt: 500 USDT und 100 CAKE.
>
> Claire nutzt die neue Funktion für konzentrierte Liquidität in PancakeSwap v3 und erstellt eine Position mit einer Preisspanne von 2 bis 12,5 USDT pro CAKE. Sie hat 185 USDT und 37 CAKE eingezahlt, mit einem Gesamtwert von 370 USD. Damit kann sie die verbleibenden 630 USD anderweitig einsetzen, zum Beispiel CAKE im Syrup Pool sperren, um hohe CAKE-Renditen zu erzielen und gleichzeitig von einer Reihe von PancakeSwap-Ökosystem-Vorteilen zu profitieren.
>
> Solange CAKE innerhalb der Preisspanne von 2 bis 12,5 bleibt, erhalten Baller und Claire die gleichen Handelsgebührenprämien, obwohl Claire deutlich weniger Kapital in den Liquiditätspool eingezahlt hat.

### **Handelsgebühren**&#x20;

Das Bereitstellen von Liquidität belohnt Sie mit Handelsgebühren, wenn andere Nutzer Ihren Liquiditätspool für Swaps verwenden.

Jedes Mal, wenn jemand auf PancakeSwap handelt, zahlt der Händler für jeden Hop (Swap) in jedem Exchange V3 Liquiditätspool – abhängig vom Gebührentier des Liquiditätspools – eine Gebühr zwischen 0,01 % und 1 %. Die Gebührensätze und Gebührenaufschlüsselungen sind wie folgt:

<details>

<summary>Handelsgebühren (EVM)</summary>

| Gebührenkomponente / Gebührentier | 0,01 % | 0,05 % | 0,25 % | 1 %  |
| ---------------------------------- | ------ | ------ | ------ | ---- |
| Liquidity Provider                 | 67 %   | 66 %   | 68 %   | 68 % |
| CAKE Burn                          | 15 %   | 15 %   | 23 %   | 23 % |
| Treasury                           | 18 %   | 19 %   | 9 %    | 9 %  |

Zum Beispiel in einem Pool mit 0,25 % Gebührentier:

* Unter allen aktiven (im Bereich liegenden) Liquiditätspositionen gibt es insgesamt 10 CAKE und 10 BNB Token.
* Jemand tauscht 1 CAKE gegen 1 BNB.
* Jemand anderes tauscht 1 BNB gegen 1 CAKE.
* Die Liquiditätsanbieter, die sich im Bereich befinden und aktive Liquidität bereitstellen, haben insgesamt 0,0017 CAKE und 0,0017 BNB aus den Trades verdient.
* Positionen mit Preisspannen, die den aktuellen Preis nicht abdecken und daher inaktiv sind, tragen nicht zum Handel bei und verdienen keine Gebühren.

</details>

<details>

<summary><strong>Handelsgebühren (Solana)</strong></summary>

**Verfügbare V3 CLAMM Pool Gebührentiere:**\
0,01 %, 0,02 %, 0,03 %, 0,04 %, 0,05 %, 0,1 %, 0,15 %, 0,16 %, 0,18 %, 0,2 %, 0,25 %, 0,4 %, 0,6 %, 0,8 %, 1 %, 2 %, 3 %, 4 %

**Hinweis:** Die Gebühren**verteilung bleibt** über alle Gebührentiere hinweg **gleich**.

| Gebührenkomponente                    | % der Gesamt-Swap-Gebühr | Beschreibung                                                     |
| ------------------------------------- | ------------------------ | ---------------------------------------------------------------- |
| **LPs (Liquidity Providers)**         | 84 %                     | Verdient von LPs, die im aktiven Preisbereich Liquidität stellen |
| **Burn**                              | 8 %                      | Dauerhaft entfernt, um das CAKE-Angebot zu reduzieren            |
| **Treasury**                          | 8 %                      | Dem PancakeSwap-Protokoll-Treasury zugewiesen                    |

**Beispiel: Gebührenverteilung in einem 0,25 % CAKE/SOL Pool**

1. **Pool-Aufbau:** Gesamte aktive Liquidität: 10 CAKE und 10 SOL (im Bereich liegende Positionen).
2. **Swaps finden statt:**
   * Nutzer A tauscht 1 CAKE → 1 SOL.
   * Nutzer B tauscht 1 SOL → 1 CAKE.
3. **Gesamte erhobene Gebühren:**
   * 0,25 % pro Trade × 2 Trades = **0,005 CAKE + 0,005 SOL**.
4. **Gebührenverteilung:**
   * **84 % an LPs:** 0,0042 CAKE + 0,0042 SOL
   * **8 % für Burn:** 0,0004 CAKE + 0,0004 SOL
   * **8 % für Treasury:** 0,0004 CAKE + 0,0004 SOL
5. **LP-Verdienste:**
   * Nur **im Bereich liegende LPs** verdienen Gebühren. Gebühren werden proportional zum jeweiligen LP-Anteil verteilt.
   * **Außerhalb des Bereichs liegende LPs** verdienen **keine Gebühren**.

</details>

### **CAKE verdienen**

Um das Bereitstellen von Liquidität noch lohnenswerter zu machen, können Sie Ihre Liquiditätspositionen auch auf den [CAKE Farms](https://pancakeswap.finance/liquidity/pools) einsetzen, um frische Renditen zu erzielen, während Sie weiterhin Handelsgebührenprämien verdienen.

***

## Exchange V2

### LP-Token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Wenn Sie beispielsweise **CAKE** und **BNB** in einen Liquiditätspool einzahlen, erhalten Sie **CAKE-BNB LP**-Token.

Die Anzahl der LP-Token, die Sie erhalten, repräsentiert Ihren Anteil am CAKE-BNB Liquiditätspool.

Sie können Ihre Mittel auch jederzeit zurückerhalten, indem Sie Ihre Liquidität entfernen.

### **Handelsgebühren verdienen**

Jedes Mal, wenn jemand auf PancakeSwap handelt, zahlt der Händler für jeden Hop (Swap) in jedem Exchange V2 Liquiditätspool eine feste Gebühr von 0,25 %, **von denen 0,17 %** in Form von Handelsgebühren in den Liquiditätspool zurückfließen.

### **CAKE verdienen**

Der alte Exchange V2 wird parallel zum neuen Exchange V3 betrieben. Daher verbleiben einige Handelspaare auf PancakeSwap Exchange V2 und haben entsprechende V2 Farms. Bitte prüfen Sie die Tags, um die Exchange-Versionen zu identifizieren.



## Impermanent Loss

Das Bereitstellen von Liquidität ist nicht ohne Risiko, da Sie einem Impermanent Loss ausgesetzt sein können.

[„Einfach ausgedrückt ist Impermanent Loss die Differenz zwischen dem Halten von Token in einem AMM und dem Halten in Ihrer Wallet." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
