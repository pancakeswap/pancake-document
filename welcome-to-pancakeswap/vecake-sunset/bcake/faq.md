# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### Wie werden die bCAKE-Multiplikatoren berechnet?

Sie werden möglicherweise feststellen, dass Sie beim Staking in verschiedenen Farms unterschiedliche bCAKE-Boost-Multiplikatoren erhalten.

Das liegt daran, dass die bCAKE – Farm Booster-Multiplikatoren bei der Aktivierung oder Aktualisierung anhand folgender Kennzahlen berechnet werden:

* `userLpBalanceInFarm` : Die Menge an Liquidität, die Sie in der Farm staken.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : Die Gesamtmenge an Liquidität, die in der Farm gestakt wird, oder die aktuelle aktive Liquiditätsmenge im V3 LP-Pool. bCAKE wählt die kleinere der beiden Zahlen.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : Die Echtzeit-veCAKE-Menge, die Sie haben.
* `veCAKE.totalSupply` : Das Echtzeit-Gesamtangebot an veCAKE.

Der Multiplikator wird nach folgender Methode berechnet:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` und `constantB` werden von der Kitchen festgelegt und können basierend auf Community-Feedback und Marktbedingungen zukünftig angepasst werden. `constantB` variiert zwischen verschiedenen Farms, um die Unterschiede im LP-Preis auszugleichen.

`constantA` und `constantB` können wie folgt abgerufen werden:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Aber:

{% hint style="info" %}
**Kurzfassung**

Je mehr LP (Liquidität) Sie boosten möchten,

desto mehr CAKE müssen Sie für längere Zeiträume sperren.
{% endhint %}

### Warum ändern sich meine Multiplikatoren auch nach der Aktivierung?

Bitte beachten Sie, dass **jede Nutzeraktion an der Farming-Position oder am CAKE Staking-Pool Ihren Boost-Multiplikator automatisch** basierend auf den neuesten Daten und Statistiken aus Farms und dem CAKE Staking-Pool aktualisiert. Dazu gehören unter anderem:

* Staken/Entstaken einer Position in/aus der Farm.
* CAKE-Belohnungen aus der Farm harvesten.
* Ihre CAKE Staking-Dauer verlängern.
* Mehr CAKE zu Ihrer Staking-Position mit fester Laufzeit hinzufügen.
* Ihre CAKE Staking-Position in flexible umwandeln.

{% hint style="warning" %}
Bitte beachten Sie:&#x20;

Um Fairness zu gewährleisten und potenziellem Missbrauch mit veralteten Daten vorzubeugen, ist der Farm Booster so konzipiert, dass er genehmigungslos und durch Community-Governance gesteuert wird. Daher kann **jeder** die Funktion `updateLiquidity(address _tokenId)` am MasterChef V3-Vertrag aufrufen, um die Boost-Multiplikatoren anderer Nutzer mit den neuesten Daten zu aktualisieren.

Darüber hinaus wird die Kitchen alle bCAKE-aktivierten Farming-Positionen überwachen und jede Position mit einem veralteten Multiplikator aktualisieren.
{% endhint %}

### Warum kann ich eine Position nicht boosten?

1. Farm Booster ist nur für ausgewählte Farms verfügbar. In Zukunft werden weitere Farms hinzugefügt. Achten Sie jetzt auf **die grüne APR-Zahl mit einem grünen Raketensymbol.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. Aufgrund der Beteiligung mehrerer Verträge erfordern einige Vertragsinteraktionen etwas mehr Gas-Token (BNB). Stellen Sie daher sicher, dass Sie genug BNB in Ihrer Wallet haben. Wenn der Fehler weiterhin auftritt, versuchen Sie, das Gaslimit der Transaktion manuell zu erhöhen.

### Was ist der maximale bCAKE Boost-Multiplikator?

Derzeit beträgt der maximale Boost für einen Farm Booster 2,5x, was dem Nutzer 2,5x der ursprünglichen APR bietet.

Bitte beachten Sie, dass der maximale Boost je nach Art der Liquidität, die Sie staken möchten, variiert:

* V3: maximal 2x
* V2, StableSwap: maximal 2,5x
* Positionsmanager: maximal 2,5x

### Wie kann ich meine bCAKE Boost-Multiplikatoren erhöhen?

* Mehr CAKE zur veCAKE Staking-Position hinzufügen.
* Die Dauer Ihrer veCAKE Staking-Position verlängern oder erneuern.

Kurz gesagt:

**Mehr CAKE staken, länger staken.**

[Erfahren Sie mehr darüber, wie bCAKE Boost-Multiplikatoren berechnet werden](faq.md#how-are-the-bcake-multipliers-calculated).

### Woher stammen die zusätzlichen geboosteten CAKE-Belohnungen?

**Keine Sorge, für bCAKE werden keine zusätzlichen Emissionen zugeteilt.**

Ähnlich wie beim veCAKE CAKE Staking steigert bCAKE den individuellen Anteil eines Nutzers gegenüber anderen.

Auch wenn die Basis-APR nach der Einführung von bCAKE sinken kann, sind die Chefs der Meinung, dass dies ein guter Kompromiss ist, da es treue CAKE-Liebhaber begünstigt, indem es ihre Farming-Erträge steigert, mehr Nachfrage nach CAKE erzeugt und als starker Anreiz für das CAKE Staking dient.

### Warum ist der erhaltene Multiplikator niedrig?&#x20;

bCAKE – Farm Booster funktioniert so, dass sowohl Ihre veCAKE Staking-Position als auch Ihre Liquiditäts-Farming-Position im Vergleich zu anderen Nutzern bewertet wird. Kurz gesagt:

> Wenn Nutzer mehr Liquidität in der Farm boosten möchten, müssen sie mehr CAKE für längere Zeiträume im Pool sperren.

Dieses Design stellt sicher, dass die Vorteile nicht nur Großinhabern angeboten werden, sondern jedem Nutzer, der eine beachtliche CAKE Staking-Position im Vergleich zur Farming-Position hat.

Erfahren Sie mehr über die Berechnung des Multiplikators [hier](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Warum gibt es nur x Farms mit verfügbarem Booster?

Da bCAKE eines der Kernprodukte von PancakeSwap – das Liquiditäts-Farming – betrifft, möchten die Chefs bei der Einführung einen langsameren und beständigeren Ansatz verfolgen.

Daher sind viele Parameter in der anfänglichen Produktveröffentlichungsphase sehr konservativ. Dazu gehören die Anzahl der Farms, die Nutzer boosten können, welche Farms Nutzer boosten können sowie der Schwierigkeitsparameter beim Erhalt des Boost-Multiplikators.

**Die Chefs werden die Parameter basierend auf dem Community-Feedback anpassen.**

### **Wurde bCAKE V3 geprüft?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE wurde sowohl von internen als auch von externen Prüfern geprüft.

Prüfberichte finden Sie hier: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
