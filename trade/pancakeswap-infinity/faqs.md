# FAQ

1. **Wie unterscheidet sich Infinity von PancakeSwap V3?**\
   Infinity fügt neue Funktionen wie programmierbare Hooks, mehr [Pool-Typen](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (wie LBAMM und CLAMM) und Gaseinsparungen hinzu. Die grundlegenden Swap- und Liquiditätsbereitstellungsmechanismen sind jedoch weitgehend ähnlich wie bei v3, mit Ausnahme einiger geringfügiger Unterschiede bei LBAMM-Pools für die Liquiditätsbereitstellung.\
   <br>
2.  **Was ist der Unterschied zwischen LBAMM und CLAMM?**

    1. **LBAMM (Liquidity Book AMM):** Verwendet Liquiditätsbins, die jeweils Liquidität auf unterschiedlichen Preisniveaus halten. LPs können Liquidität über verschiedene Bins hinweg bereitstellen, Swaps werden auf einem einzelnen Preisniveau innerhalb eines Bins ausgeführt.
    2. **CLAMM (Concentrated Liquidity AMM):** Ermöglicht es Nutzern, Liquidität innerhalb benutzerdefinierter Preisspannen bereitzustellen, ähnlich wie bei PancakeSwap V3.

    \
    Weitere Details finden Sie [hier](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **Wie kann ich meine Farm-Belohnungen einfordern, und warum ist dies auf alle 8 Stunden begrenzt?**\
   Sie können Farm-Belohnungen aus Ihren Liquiditätspositionen einfordern, indem Sie auf die Schaltfläche „Harvest" klicken. Infinity ermöglicht die gebündelte Einfoderung über alle aktiven Farm-Positionen hinweg, was Gaskosten spart. Belohnungen werden alle 8 Stunden berechnet und verarbeitet, um Gaskosten und Rechenaufwand zu optimieren. \
   \
   Weitere Details zum Farm-Mechanismus finden Sie [hier](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **Wie funktionieren die Infinity Hooks?**\
    Hooks sind anpassbare Smart-Contract-Erweiterungen, die einem Pool zusätzliche Funktionalität hinzufügen. Sie können während Swaps oder Liquiditätsereignissen zusätzliche Aktionen auslösen – zum Beispiel Gebühren anpassen, Rabatte anbieten oder andere Logiken anwenden.<br>

    Hooks werden beim Erstellen eines Pools angehängt. In den meisten Fällen **müssen Nutzer keine zusätzlichen Schritte unternehmen**. Solange Sie wie gewohnt swappen oder Liquidität bereitstellen, profitieren Sie automatisch von der Hook-Logik, sofern diese für diesen Pool gilt.<br>

    👉 **Sie können die aktiven Hooks und ihre Details auf der Seite jedes Pools im Abschnitt „Pool-Funktionen" einsehen.**\
    <br>
5.  **Warum habe ich beim Abziehen meiner Position aus einem LBAMM-Pool keine Gebühren erhalten?**\
    In LBAMM (Liquidity Book AMM)-Pools werden Gebühren automatisch zu Ihren aktiven Liquiditätsbins hinzugefügt. Das bedeutet:

    1. Wenn Sie Ihre Position abziehen, sind Ihre verdienten Gebühren in den gesamten Token-Beträgen enthalten, die Sie abziehen.
    2. Im Gegensatz zu traditionellen AMMs gibt es kein separates „einzuforderndes Gebührenguthaben" – alles ist in den Wert Ihrer Position integriert.

    \
    Falls Sie beim Abziehen keine zusätzlichen Token bemerkt haben, könnte das folgende Ursachen haben:

    1. Ihre Position hat möglicherweise aufgrund von Preisbewegungen während der Laufzeit mehr Impermanent Loss erlitten als die eingezogenen Gebühren.
    2. Ihre Liquidität befand sich nicht in aktiven Bins, in denen Trades stattfanden.
