---
hidden: true
---

# veCAKE FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Was ist der Unterschied zwischen gesperrtem CAKE und veCAKE? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE ist eine neue Version des Festlaufzeit-CAKE-Stakings mit mehr Vorteilen und Möglichkeiten für Inhaber gesperrter CAKE. Dazu gehören Gauge-Weight-Abstimmung, zusätzliche Incentives, Yield-Boosting und vieles mehr.

#### Was passiert mit den CAKE-Pool-Rewards, wenn das neue veCAKE eingeführt wird? <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

CAKE-Pool-Reward-Emissionen werden umgeleitet, um alle veCAKE-Inhaber entsprechend ihrem veCAKE-Guthaben im Verhältnis zum Gesamtangebot zu belohnen.

CAKE-Rewards und die wöchentlichen Revenue-Sharing-Rewards können nun wöchentlich donnerstags beansprucht werden.

Bitte beachten Sie, dass Nutzer zum neuen veCAKE-Staking migrieren müssen, um weiterhin Rewards zu erhalten.

#### Wie lange kann ich mein CAKE maximal sperren? <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

Die maximale Dauer, für die Sie Ihr CAKE sperren können, wurde nun auf 4 Jahre verlängert.

#### Ist veCAKE ein neuer Token? Kann er übertragen werden? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE ist eine live berechnete Zahl, die auf der Menge des gesperrten CAKE und der verbleibenden Sperrdauer basiert. Es ist kein Standardtoken und kann nicht übertragen werden.

#### Warum hat sich mein veCAKE-Saldo verändert? Wie berechnet sich sein Saldo? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

Der veCAKE-Saldo sinkt linear auf 0, basierend auf der verbleibenden Sperrdauer. Wenn wir uns dem Entsperrzeitpunkt nähern, sinkt daher Ihr Saldo.

Der veCAKE-Saldo kann wie folgt berechnet werden:

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### Wie erhöhe ich mein veCAKE? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Sobald Sie eine aktive veCAKE-Position haben, können Sie entweder mehr CAKE hinzufügen oder Ihre Sperrdauer erneuern/verlängern, um Ihren veCAKE-Saldo zu erhöhen.

#### Was passiert, wenn die Position entsperrt wird? Kann ich sie sofort erneuern? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Wenn die veCAKE-Staking-Position entsperrt wird, können Sie das gesamte gestakte CAKE abheben.

Um Ihre Position zu erneuern, müssen Sie das gesamte CAKE abheben und eine neue Staking-Position einrichten, indem Sie den zu sperrenden Betrag und die Sperrdauer auswählen.

#### Ich habe für 1 Woche gesperrt, warum ist die verbleibende Sperrdauer weniger als 1 Woche? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Wenn Sie mit dem neuen veCAKE sperren, wird die Entsperrzeit auf den nächsten Donnerstag in UTC-Zeit aufgerundet. Wenn Sie beispielsweise für 1 Woche an einem Dienstag sperren, ist Ihre tatsächliche Entsperrzeit der kommende Donnerstag, also 2 Tage später.

Sie können Ihre tatsächliche Entsperrzeit unten in der Vorschau einsehen.

#### Kann ich mehr CAKE im CAKE-Pool sperren? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

Nein.

Nach der Einführung von veCAKE wird der CAKE-Staking-Pool eingestellt und akzeptiert keine weiteren CAKE-Verlängerungen oder -Einzahlungen mehr.

Um CAKE zu sperren und von den Vorteilen zu profitieren, gehen Sie zur veCAKE-Seite.

#### Warum kann ich nicht migrieren? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

Für die Migration vom CAKE-Pool zu veCAKE ist eine aktive Position erforderlich. Wenn Ihre CAKE-Pool-Staking-Position bereits entsperrt ist, heben Sie diese CAKE einfach ab und erstellen Sie eine native veCAKE-Staking-Position.

In einigen Fällen kann die Migration nicht durchgeführt werden, wenn Ihre verbleibende CAKE-Pool-Sperrdauer weniger als 7 Tage beträgt. Warten Sie in diesem Fall die Entsperrung ab, heben Sie die CAKE ab und erstellen Sie eine native veCAKE-Staking-Position.

#### Kann ich mein gesperrtes CAKE vorzeitig abheben? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

Nein.

Nach der Sperrung wird CAKE im veCAKE-Contract bis zum Entsperrzeitpunkt gestakt.

#### Kann ich mein CAKE teilweise migrieren? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

Nein.

Sie können nur Ihre gesamte CAKE-Pool-Position auf einmal migrieren.

#### Was passiert mit iCAKE, bCAKE, vCAKE und rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Für iCAKE:**

IFO iCAKE wurde nun aktualisiert, um veCAKE zu unterstützen. Mehr erfahren:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Für bCAKE:**

Farm-Boosting bCAKE wurde nun aktualisiert, um veCAKE zu unterstützen. Mehr erfahren:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Für vCAKE:**

Abstimmungs-vCAKE wurde nun aktualisiert, um veCAKE zu unterstützen. Mehr erfahren:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Für rCAKE:**

Alle veCAKE-Inhaber (nativ oder migriert) werden automatisch in den neuen Revenue-Sharing-Pool aufgenommen. Umsatzbeteiligungen werden gemäß dem bestehenden Plan verteilt. Der alte Revenue-Sharing-Pool wird eingestellt; Nutzer können ihre ausstehenden Rewards über die Benefit-Card beanspruchen. Mehr erfahren:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### Können Multisig-Wallets für die Interaktion mit veCAKE verwendet werden?

Ja

Allerdings wurde im veCAKE-Staking-Contract ein `noContract`-Modifier für nicht auf der Whitelist stehende Adressen implementiert. Um Staking oder Migration vom Festlaufzeit-CAKE-Staking-Pool zu ermöglichen, müssen alle Contract-basierten Multisig-Wallets eine einmalige Selbst-Whitelisting-Aktion durchführen.

Zur Whitelist-Aufnahme besuchen Sie eine der folgenden Seiten:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Es sollte eine Aufforderung erscheinen. Klicken Sie auf „Whitelist" und führen Sie die Transaktion in Ihrer Multisig-Wallet durch.

Es wird eine Transaktion an den Eigentümer des veCAKE gesendet, bei dem es sich um einen Contract mit einer erlaubnisfreien Write-Funktion handelt, die es jedem Contract ermöglicht, sich selbst auf die Whitelist zu setzen.

Wenn die Aufforderung nicht erscheint, folgen Sie dieser Anleitung, um die Transaktion von [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11) aus auszuführen:

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Warum gibt es mehrere APRs?

Das Sperren von CAKE zur Erlangung von veCAKE bietet eine Reihe großartiger Vorteile im gesamten Produktportfolio von PancakeSwap. Vorteile und Incentives kommen in verschiedenen Formen und aus unterschiedlichen Quellen. Daher gibt es mehrere APRs.

Sie können alle gleichzeitig verdienen, sodass der kombinierte APR die Summe aller APRs ergibt.

Bitte beachten Sie, dass viele weitere Vorteile von veCAKE nicht im APR-Format quantifiziert werden können, wie z. B. der [Farm-Yield-Booster bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) oder [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). Schauen Sie sich diese unbedingt an.

#### Was ist der veCAKE-Pool-APR?

Dies ist der Incentive aus CAKE-Emissionen, dessen Rate durch den veCAKE-Pool-Voting-Gauge gesteuert wird.

Um die Emissionen an diesen Gauge zu erhöhen, lesen Sie mehr zu [Gauge Voting](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### Was ist der Revenue-Sharing-APR?

Dies ist der Incentive aus dem Protokoll-Revenue-Sharing, der aus Swap-Gebühren stammt, die in DEX-Produkten anfallen.

Mehr zum [Revenue Sharing](/broken/pages/wQegezs7c6A2HzQjPEjh) erfahren.
