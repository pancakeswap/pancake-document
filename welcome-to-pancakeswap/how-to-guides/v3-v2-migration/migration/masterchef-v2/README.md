---
description: Zu MasterChef v2 migrieren
---

# MasterChef v2

PancakeSwap MasterChef v2 ist ein neuer Haupt-Staking-Vertrag für Farms und bietet mehr Flexibilität bei der Anpassung der $CAKE-Emissionen, einschließlich CAKE-Pool, Burning und anderer PancakeSwap-Produkte.

### Muss ich migrieren?

Wenn Sie derzeit PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)) verwenden, müssen Sie zum neuen Vertrag ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)) migrieren.

### Überblick

#### Einzahlung&#x20;

Wenn Sie derzeit `enterStaking(uint256 _amount)` auf dem aktuellen PancakeSwap MasterChef verwenden, müssen Sie zum neuen CAKE-Pool-Vertrag migrieren. Die entsprechende Dokumentation finden Sie [hier](../cake-syrup-pool.md).

Die Einzahlungsfunktion für die Farm-Pools ist unverändert. Sie müssen jedoch die MasterChef-Adresse und die `pid` aktualisieren. Die [Farm-Liste](list-of-farms.md) enthält die neuen `pids` für MasterChef v2.

#### Pool-Typen

MasterChef v2 hat 2 Pool-Typen: Reguläre Farm-Pools und Spezielle Farm-Pools. Mit `poolInfo(_pid).isRegular` können Sie den Pool-Typ abfragen. Sie haben unterschiedliche `totalAllocPoint`-Werte, wodurch sie zwei unabhängige Pool-Sets bilden.

Spezielle Farm-Pools: Nur whitegelistete Adressen können einzahlen. Sie werden in der Regel von internen PancakeSwap-Produkten für die Rewards-Verteilung genutzt.

Reguläre Farm-Pools: Die regulären LP-Token-Farms. Zum Beispiel CAKE-BNB, BNB-BUSD usw.

#### Abheben

Wenn Sie derzeit `leaveStaking(uint256 _amount)` auf dem aktuellen PancakeSwap MasterChef verwenden, müssen Sie zum neuen CAKE-Pool-Vertrag migrieren. Die entsprechende Dokumentation finden Sie [hier](../cake-syrup-pool.md).

Die Abhebungsfunktion für die Farm-Pools ist unverändert. Sie müssen jedoch die MasterChef-Adresse und die `pid` aktualisieren. Die [Farm-Liste](list-of-farms.md) enthält die neuen `pids` für MasterChef v2.

#### Staking-Guthaben

Verwenden Sie `userInfo[_pid][_user].amount`, um das Staking-Guthaben abzufragen.

#### Staking-Token&#x20;

Beachten Sie, dass die neue `PoolInfo`-Struktur das LP-Token-Adressfeld **nicht** enthält. Sie müssen `lpToken(_pid)` verwenden, um das Staking-Token eines bestimmten Pools abzufragen.&#x20;

#### Gesamte Staking-Anteile/Betrag

Verwenden Sie `lpToken.balanceOf(MasterChef.address)`, um den Gesamt-Staking-Betrag für einen beliebigen Farm-Pool abzufragen.

In MasterChef v2 kann der Anteil der Benutzer jedoch erhöht werden (demnächst verfügbar). Daher werden Rewards mit einem neuen `totalBoostedShare`-Feld in `PoolInfo` als Gesamtanteile jedes Pools berechnet. Wenn beispielsweise Pool 0 zwei Benutzer hat, Benutzer1 100 LPs stakt (ohne Boost) und Benutzer2 100 stakt (mit `boostMultiplier` von 1,05), wird `totalBoostedShare` zu 205. Dies führt dazu, dass Benutzer2 mehr Rewards erhält.

#### CakePerBlock

Sie können `cakePerBlock(bool _isRegular)` verwenden, um den CAKE-Reward pro Block abzufragen, der an alle PancakeSwap-Farms geht.

### Mainnet-Vertragsadresse

**Vertragsname:** MasterChef v2\
**Vertragsadresse:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Den PancakeSwap: Haupt-Staking-Vertrag v2 auf BscScan anzeigen.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Testnet-Umgebung

Sie können die folgende Testnet-Umgebung verwenden, um die Integration Ihres Projekts mit dem neuen PancakeSwap MasterChef v2 zu testen. Wenn Sie Fragen haben, wenden Sie sich bitte über die bestehenden Kanäle an unser Team oder kontaktieren Sie uns per E-Mail unter bun@pancakeswap.com.

**Dummy-Token:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (prägbar mit `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (prägbar mit `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory und Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP-Paare

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manuelles CAKE
  * pid4: Dummy-Pool für MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
