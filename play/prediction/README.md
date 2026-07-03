# 🔮 Prognose

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction ist ein spaßiger und einfacher dezentraler Prognosemarkt.

> **Sagen Sie vorher, ob der BNB-, BTC- oder ETH-Preis steigen oder fallen wird – tippen Sie richtig und gewinnen Sie!**

### Plattformen

Sie können PancakeSwap Prediction spielen auf:

* **Desktop/dApp**: [PancakeSwap Prediction-Anleitung](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini App (nur BNBUSD)**: [Prediction Bot](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Zusammenfassung: So funktioniert es

1. **Wählen Sie einen Vermögenswert aus**: Derzeit verfügbar auf **BNB Chain**, **zkSync Era** und **Arbitrum One**.
2. **Wählen Sie HOCH oder NIEDRIG**: Prognostizieren Sie, ob der Vermögenswertpreis höher oder niedriger liegt, wenn die „LIVE"-Phase endet (jede Runde = 5 Minuten).
3. Setzen Sie Ihren Einsatzbetrag: Beliebiger BNB-Betrag
4. **Sperren Sie Ihre Position**: Nach der Platzierung kann Ihr Einsatz nicht mehr geändert werden.
5. **Gewinn oder Verlust**:
   * Wenn Sie **HOCH** gewählt haben, gewinnen Sie, wenn der _Schlusskurs_ > _gesperrter Kurs_ am Ende der Runde ist.
   * Wenn Sie **NIEDRIG** gewählt haben, gewinnen Sie, wenn der _Schlusskurs_ < _gesperrter Kurs_ am Ende der Runde ist.

### Mechanismen und Gebühren

* **Unterstützte Chains: BNB Chain, zkSync Era, Arbitrum One**
* **Rundenfrequenz**: Alle **5 Minuten** (rollende Runden).
* **Teilnahmegebühr**: **3 %** des gesamten Preispools jeder Runde, ein Teil davon fließt in **CAKE-Rückkäufe**.
* **Gewinne**: Jederzeit einlösbar, nachdem die Ergebnisse finalisiert sind.
* **Auszahlungen** basieren auf dem Verhältnis der Einsätze in jedem Pool:
  * Auszahlungsquote (HOCH-Pool) = _(Gesamtwert beider Pools ÷ Wert des HOCH-Pools)_
  * Auszahlungsquote (NIEDRIG-Pool) = _(Gesamtwert beider Pools ÷ Wert des NIEDRIG-Pools)_
  * Siehe: [FAQ](prediction-faq.md) für ein ausgearbeitetes Beispiel

### Ergebnisse

* **Gewinn:** Sie teilen sich den Gesamttopf mit anderen Gewinnern (abzüglich 3 % Gebühr)
* **Verlust:** Sie verlieren Ihren gesamten Einsatzbetrag

**Sonderfälle**:

* **Unentschieden** (gesperrter Kurs = Schlusskurs): Das Haus gewinnt alle Einsätze.
* Wenn es keine gegnerischen Einsätze gibt:
  * Wenn Sie gewinnen: Sie erhalten 97 % Ihres ursprünglichen Einsatzes zurück (3 % Gebühr fällt an).
  * Wenn Sie verlieren: Ihr gesamter Einsatz fällt an das Haus.
* **Abgebrochen:** z. B. Oracle-Ausfall; Nutzer erhalten ihren ursprünglichen Einsatz zurück

### Preisfeeds (Oracles)

| Chain     | Märkte                                    | Zweck                                                                          | Oracle                     |
| --------- | ----------------------------------------- | ------------------------------------------------------------------------------ | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (pausiert) | Legt den _gesperrten Kurs_ und den _Schlusskurs_ fest (aktualisiert \~alle 20 Sekunden). | **Chainlink**              |
| BNB Chain | Alle                                      | Betreibt das Live-Chart in der Benutzeroberfläche (nur zur Referenz).           | Binance / TradingView Feed |

#### **ChainLink Oracle**

* Wird für den Sperrkurs und den Endkurs jeder Prognosemarkt-Runde verwendet. Diese Aktualisierung erfolgt in Intervallen von bis zu 20 Sekunden.
* Unser Prognosevertrag verwendet den ChainLink Oracle-Preisfeed auf BNB Chain, um die Preise festzulegen, die bestimmen, ob ein Nutzer gewonnen hat.
* Wird für das „Chainlink"-Chart in der Benutzeroberfläche verwendet.

#### **Binance**

* Wird für Echtzeit-Preisaktualisierungen auf der PancakeSwap Prediction-Marktoberfläche verwendet.
* Wird für das „TradingView"-Chart in der Benutzeroberfläche verwendet.

Da wir zwei verschiedene Preisfeeds verwenden, können die Echtzeit-Preisaktualisierungen von Binance und der ChainLink Oracle-Preis geringfügig abweichen. Sie sollten jedoch nicht wesentlich voneinander abweichen.

### Vertragsadressen

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
