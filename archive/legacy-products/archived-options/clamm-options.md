# CLAMM Options

{% hint style="danger" %}
[ARCHIVIERT] Options – Stand 11. März 2025\
Wenn Sie noch Liquidität abzuheben haben, tun Sie dies bitte sofort unter https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options präsentiert einen neuartigen Ansatz für den On-Chain-Optionshandel und bietet Liquiditätsanbietern eine Plattform, um v3-Liquidität auf PancakeSwap zu nutzen. Dies ermöglicht es ihnen, Liquidität sowohl für die v3-Liquiditätspools als auch für den Verkauf von Optionen zu verwenden, dabei Standard-AMM-Handelsgebühren, Optionsprämien und zusätzliche Belohnungen zu verdienen, während Händler diese Liquidität nutzen können, um amerikanische Optionen auf verschiedene Token zu kaufen.

Das von Stryke (ehemals Dopex) entwickelte CLAMM-Options-Protokoll führt ein effizientes duales Liquiditätsbereitstellungssystem für Optionshändler (Käufer) und PancakeSwap-v3-Pools ein.

Hier ist eine strukturierte Übersicht über die Funktionsweise von CLAMM Options:

1. LPs, die Liquidität zu CLAMM Options hinzufügen, leisten gleichzeitig einen Beitrag zum entsprechenden PancakeSwap-v3-Pool innerhalb ihrer gewählten Preisspanne.
2. Wenn ein Optionshändler (Käufer) eine Position eröffnet, wird Liquidität aus dem v3-Pool entnommen, um den Optionsverkauf zu ermöglichen. Der jeweilige LP wird dadurch zum Optionsverkäufer und erhält eine Prämie.
3. Liquidität, die von Optionskäufern nicht genutzt wird, verbleibt im PancakeSwap-v3-Pool und kann potenziell Handelsgebühren verdienen.
4. Die Auszahlung aus dem Optionsverkauf und der Liquiditätsbereitstellung in einem v3-Pool spiegelt denselben Impermanent Loss wider, sodass Nutzer im Vergleich zur herkömmlichen Methode der Liquiditätsbereitstellung in v3-Pools kein erhöhtes Risiko eingehen.
5. LPs gehen einige Risiken ein, da Liquidität aufgrund geringerer Nachfrage nach Optionskäufen möglicherweise ungenutzt bleibt. Da die Liquidität außerdem dem Pool in einem inaktiven Bereich hinzugefügt wird, werden möglicherweise keine Gebühren verdient.

PancakeSwaps amerikanische CLAMM-Options werden auf der Arbitrum-Chain debütieren und bieten Flexibilität mit verschiedenen Ablaufzeiten von 1 Stunde bis 24 Stunden.

| **Märkte**           | ARB/USDC, ETH/USDC und wBTC/USDC |
| -------------------- | --------------------------------- |
| **Optionstypen**     | Call & Put                        |
| **Ausübungspreise**  | Basierend auf v3-Pool-Ticks       |
| **Ablaufzeiten**     | 1H, 2H, 6H, 12H und 24H          |

**Ausübungsbedingungen:** Nutzer können Positionen vor dem Schließen ausüben, um zu verhindern, dass im Geld liegende Optionen wertlos verfallen. Die automatische Ausübung kann aktiviert werden, um Gewinne bei Ablauf automatisch zu realisieren, ohne weitere Aktionen.

### Schritt-für-Schritt-Anleitung

Hier ist die Schritt-für-Schritt-Anleitung zur Nutzung von PancakeSwap CLAMM Options.

**Für Händler:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Für LPs:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
