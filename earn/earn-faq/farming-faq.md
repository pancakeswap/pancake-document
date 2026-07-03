---
hidden: true
---

# Farming FAQ

### Warum gibt es mehrere APRs?

In V3 können Sie Ihre Vermögenswerte konzentrieren, während Sie Liquidität bereitstellen, um Ihren Anteil an der gesamten verfügbaren Liquidität zu erhöhen und so einen höheren Prozentsatz der Rewards zu verdienen.

Abhängig von den Preisspanneneinstellungen der Position wird daher jede Liquiditätsposition ihren eigenen LP-Gebühren-APR und ihren eigenen Farming-APR haben.

Der globale APR wird berechnet aus der Gesamtmenge der CAKE-Rewards in USD, geteilt durch die Gesamtmenge der Vermögenswerte in den aktiven Positionen, die derzeit in der Farm gestakt sind. Der globale Farming-APR ist daher nur ein allgemeiner Richtwert und repräsentiert nicht die individuellen APRs der einzelnen Positionen.

Um Ihren Farming-APR anzuzeigen, schauen Sie sich Ihre Positionen unter den jeweiligen Farms an.

###

### Was passiert, wenn meine Liquiditätsposition außerhalb der Preisspanne gerät, während ich in der Farm stake?

In V3 verdienen nur aktive (im Bereich befindliche) Liquiditätspositionen CAKE aus Farms.

Die Position hört auf, CAKE-Rewards zu erhalten, wenn der Preis außerhalb der Spanne gerät.

Wenn der Preis wieder in die Spanne zurückkehrt, beginnt die Position erneut, CAKE-Rewards zu erhalten. Von Stakern sind keine weiteren Maßnahmen erforderlich.



### Gibt es Möglichkeiten, meine Position automatisch anzupassen, damit sie immer in der Spanne ist und Gebühren-Rewards verdient?

PancakeSwap v3 unterstützt One-Click-Liquiditätseinzahlung via Zap, verfügbar auf BNB Chain und Ethereum.



### Ist es immer besser, mit einer Liquiditätsposition mit kleinerer Spanne zu farmen?

Das Bereitstellen von Liquidität in einer kleineren Preisspanne konzentriert Ihre Liquidität, was Ihren relativen Anteil an der gesamten Liquidität innerhalb der Preisspanne erhöht und potenziell mehr CAKE-Rewards generiert.

Bitte beachten Sie jedoch, dass nur aktive Liquiditätspositionen CAKE-Rewards verdienen. Das bedeutet, dass Sie nur Rewards verdienen, wenn der aktuelle Handelspreis innerhalb der in der Liquiditätsposition definierten Preisspanne liegt.

Wenn Sie die Preisspanne Ihrer Position anpassen müssen, müssen Sie unstaken, Liquidität entfernen und eine neue Position mit der aktualisierten Preisspanne erstellen. Beachten Sie bitte, dass häufige Anpassungen nicht immer die optimalste Strategie sind, da dadurch der Impermanent Loss realisiert wird und für mehrere Transaktionen Gaskosten anfallen.



### Wie viele Positionen kann ich in einer einzigen Farm staken?

Es gibt keine maximale Anzahl von Positionen, die Sie in einer Farm staken können.

Bitte beachten Sie jedoch, dass Sie für jede Position Gas aufwenden müssen, um manuell zu ernten. Berücksichtigen Sie bei Yield-Operationen stets die Gaskosten.



### Wie oft sollte ich meine Rewards ernten?

Wie oft Sie Ihre Rewards ernten, liegt bei Ihnen – es ist jedoch hilfreich zu beachten, dass beim Ernten eine kleine Gebühr anfällt. Diese Gebühr ist in Ihrer Wallet sichtbar, wenn Sie nach dem Klicken auf „Ernten" bestätigen.

Dies zeigt die Erntegebühr, wie sie in der MetaMask-Wallet erscheint. Verschiedene Wallets stellen die Informationen etwas unterschiedlich dar. Überlegen Sie, Ihre Rewards eine Weile anwachsen zu lassen, damit Sie weniger häufig Gebühren zahlen.



### Was, wenn ich meine Position anpassen möchte, während ich in der Farm stake?

Während Sie in der Farm staken, können Sie Liquidität hinzufügen oder entfernen, ohne zu unstaken. Suchen Sie einfach die Liquiditätsposition, die Sie anpassen möchten, und klicken Sie auf deren Titel/ID. Sie gelangen dann zur Positionsdetailseite, wo Sie die Schaltflächen „Hinzufügen" und „Entfernen" verwenden können.

Wenn Sie die Preisspannenkonfiguration einer Liquiditätsposition anpassen möchten, müssen Sie diese aus der Farm unstaken, die gesamte Liquidität entfernen und eine neue Position durch Hinzufügen von Liquidität neu erstellen.



### Was beeinflusst den Farming-APR?

In Farm v3 kann der CAKE-Reward-APR zwischen Liquiditätspositionen variieren. Er basiert auf folgenden Faktoren:

* CAKE-Emissionsrate an Farms\
  \- Mehr CAKE erzeugt einen höheren Ertrag für alle Farms. Lesen Sie mehr auf [unserer Tokenomics-Seite](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics).
* Farm-Multiplikator\
  \- Farms mit einem höheren Multiplikator erhalten mehr CAKE im Verhältnis zu allen anderen Farms. Bitte beachten Sie, dass v3- und v2- + StableSwap-Farms zwei separate Multiplikatoren-Sätze verwenden. Auch Farms auf Ethereum und BNB Chain verwenden zwei separate Multiplikatoren-Sätze.
* Die Anzahl der in der Position hinterlegten Token\
  \- Mehr Token in der Position bedeuten einen größeren relativen Anteil an der gesamten aktiven Liquidität im Farm-Pool und führen zu mehr CAKE-Rewards.
* Die ausgewählte Preisspanne\
  \- Eine kleinere Preisspanne ermöglicht eine höhere Konzentration bei gleicher Tokenmenge, was zu einem größeren relativen Anteil an der gesamten aktiven Liquidität im Farm-Pool führt und mehr CAKE-Rewards einbringt.
* Die Menge der aktuell aktiven Liquidität\
  \- Wenn mehr Nutzer Liquidität in derselben Spanne wie Sie einzahlen und konzentrieren, erhalten Sie aufgrund eines kleineren relativen Anteils weniger CAKE-Rewards.
* Ob die Liquiditätsposition aktiv ist\
  \- Nur aktive Liquiditätspositionen verdienen CAKE-Rewards aus der Farm.



### Warum sehe ich ein „Positionen aktualisieren"-Popup?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Kurz nach dem V3-Launch haben die Chefs ein Update der Farms implementiert, um die Reward-Berechnungen präziser und zuverlässiger zu machen. Wenn Sie dieses Popup sehen, bedeutet das, dass einige Ihrer Positionen aktualisiert werden müssen.

Klicken Sie einfach auf „Alle aktualisieren" und bestätigen Sie im Wallet-Popup.

Bitte beachten Sie, dass die Chefs dieses Update auch auf die historischen Staking-Daten zwischen dem Launch von Farm V3 und der Implementierung dieses Updates anwenden. Falls zusätzliche CAKE-Rewards vorhanden sind, werden diese vor dem 1. Mai 2023 als Airdrop an Ihre Wallet gesendet.



### Warum hat eine 2x-Farm in V3 einen geringeren APR als eine 1x-Farm in V2?

Zunächst müssen Sie beim Vergleich von APRs sicherstellen, dass die Gesamtmenge der gestakten Liquidität zwischen den beiden Farms gleich ist.

Darüber hinaus gibt es nun mehrere Farm-Gruppen mit jeweils eigenem CAKE-Emissionsstrom. Jede Farm-Gruppe verfügt über separate Multiplikatoren-Sätze.

Eine einzelne Farm erhält CAKE-Emissionen basierend auf:

* A = Gesamt-CAKE pro Sekunde/Block für die Farm-Gruppe, zu der sie gehört
* B = Gesamtzahl der Multiplikatoren innerhalb der Gruppe, zu der sie gehört
* C = Der Multiplikator, den die Farm hat

`CAKE pro Block/Sekunde = C / B × A`

Die oben genannten Zahlen finden Sie in den jeweiligen [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I)-Contracts.



### Kann ich bCAKE in v3-Farms verwenden?

Ja

bCAKE für V3-Farms kommt sehr bald nach der Bereitstellung von PancakeSwap Farm V3. Bleiben Sie dran.
