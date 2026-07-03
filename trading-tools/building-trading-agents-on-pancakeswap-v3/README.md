# 🤖 BNB AI Agent Studio

> Eine Anleitung für Entwickler, die autonome Agenten – mit [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) oder einem beliebigen Framework – erstellen, die mit PancakeSwap V3-Liquiditätspools und Farms auf BNB Smart Chain interagieren.
>
> Sie beschreiben eine Strategie; Ihr Agent führt sie on-chain aus, ohne Aufsicht. Diese Seite behandelt den PancakeSwap-Anteil: die aufzurufenden Verträge, die sichere Reihenfolge der Aufrufe und ein vollständiges Praxisbeispiel (ein automatisierter V3-Range-Rebalancer). Informationen zur Beschreibung, Erstellung und Bereitstellung des Agenten selbst finden Sie in der BNB Agent Studio-Dokumentation.

PancakeSwap benötigt **keine Integration** dafür. V3-Pools und Farms sind permissionless Smart Contracts – Ihr Agent ruft sie direkt auf, genauso wie es das PancakeSwap-Frontend tut. Alles unten ist öffentliche On-Chain-Oberfläche.

***

### 1. Was ein Agent gegenüber PancakeSwap tun kann

Concentrated Liquidity (V3) bietet LPs eine weitaus bessere Kapitaleffizienz als V2, allerdings auf Kosten des aktiven Managements: Eine Position verdient nur dann Gebühren, wenn der Preis innerhalb ihres Tick-Bereichs liegt, und Belohnungen/Erträge verschieben sich ständig. Genau dieser operative Aufwand ist es, den ein Agent beseitigt. Häufige Strategien:

* **Range-Rebalancer** – beobachtet eine LP-Position; wenn der Preis sich dem Rand des Bereichs nähert, zieht er sie zurück und prägt um den neuen Preis herum neu, sodass die Position weiterhin Gebühren verdient. _(Praxisbeispiel in §6.)_
* **Farm APR-Router** – verfolgt CAKE + Gebührenertrag über Pools hinweg und verschiebt Liquidität in den höchsten Gesamtertrag.
* **Swap/Quote-Bots** – leiten Trades über den Smart Router für beste Ausführung über V2 + V3.

All dies sind Zusammensetzungen derselben Handvoll von Vertragsaufrufen unten.

***

### 2. Vertragsoberfläche (BNB Smart Chain, chainId 56)

| Vertrag                               | Adresse                                      | Ihr Agent verwendet ihn für                                                                               |
| ------------------------------------- | -------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | LP-Positionen erstellen/verwalten – `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn`   |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Swaps mit bester V2+V3-Routing ausführen                                                                  |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Positions-NFT zum Farm von CAKE einsetzen – `harvest`, `withdraw`                                         |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Einen Swap vor dem Senden quotieren                                                                        |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Eine Pool-Adresse aus `(token0, token1, fee)` auflösen                                                    |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Gasfreie/gebündelte Token-Genehmigungen für **Smart Router Swaps** (siehe §5.1)                           |

> ⚠️ **Überprüfen Sie Adressen immer** anhand der kanonischen PancakeSwap-Deployment-Liste, bevor Sie echte Werte senden. Behandeln Sie die obige Tabelle als Ausgangspunkt.

Ein V3-**Pool** wird durch `(token0, token1, fee)` identifiziert. Gebührenstufen und ihre Tick-Abstände:

| Gebühr | `fee`-Wert | Tick-Abstand | Typische Verwendung           |
| ------ | ----------- | ------------ | ----------------------------- |
| 0,01 % | `100`       | 1            | Stable–Stable                 |
| 0,05 % | `500`       | 10           | Korreliert (z. B. ETH/BTC)    |
| 0,25 % | `2500`      | 50           | Die meisten Paare             |
| 1,00 % | `10000`     | 200          | Exotisch / volatil            |

Eine V3-**Position** ist ein ERC-721-NFT, der im NonfungiblePositionManager gehalten wird. Er speichert `tickLower`, `tickUpper`, `liquidity` und aufgelaufene Gebühren. Sie referenzieren ihn über `tokenId`.

***

### 3. Werkzeuge

Sie können mit rohen ABIs und jeder Web3-Bibliothek mit diesen Verträgen kommunizieren, aber die Pakete **`@pancakeswap/v3-sdk`** und **`@pancakeswap/smart-router`** erledigen die komplexe Mathematik (Tick ↔ Preis, Kursabweichungs-angepasste Minima, Calldata-Codierung) für Sie. Die folgenden Beispiele verwenden sie mit [viem](https://viem.sh/).

```bash
pnpm add @pancakeswap/v3-sdk @pancakeswap/smart-router @pancakeswap/sdk viem
```

```tsx
import { createPublicClient, createWalletClient, http } from 'viem'
import { bsc } from 'viem/chains'
import { privateKeyToAccount } from 'viem/accounts'

const account = privateKeyToAccount(process.env.AGENT_PRIVATE_KEY as `0x${string}`)

const publicClient = createPublicClient({ chain: bsc, transport: http() })
const walletClient = createWalletClient({ chain: bsc, account, transport: http() })
```

Ihr Agent ist genau diese Wallet, die planmäßig oder ausgelöst Transaktionen ausführt. Die Wallet wird von Agent Studio finanziert und verwaltet – siehe BNB-Dokumentation.

***

### 4. Zustand lesen (vor jeder Aktion)

Ein Agent entscheidet, _ob_ er handelt, indem er die Chain liest. Die drei Lesevorgänge, die die meisten Strategien antreiben:

**Pool-Preis und aktueller Tick** – eine `Pool`-Entität aus On-Chain-`slot0` + `liquidity` aufbauen:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress aus der Factory oder computePoolAddress() aufgelöst
const [slot0, liquidity] = await Promise.all([
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'slot0' }),
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'liquidity' }),
])

const pool = new Pool(
  token0, token1, FeeAmount.MEDIUM,
  slot0[0],      // sqrtPriceX96
  liquidity,
  slot0[1],      // tick
)

console.log('Preis token0→token1:', pool.token0Price.toSignificant(6))
console.log('aktueller Tick:', pool.tickCurrent)
```

**Eine Position, die Sie besitzen** – aus dem NonfungiblePositionManager über `tokenId` lesen:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**Liegt die Position im Bereich?** Dieses einzelne Boolean ist der Auslöser für einen Rebalancer. Sie können es auf „innerhalb von N Ticks der Grenze" verfeinern, um _bevor_ er außerhalb des Bereichs liegt zu handeln.

***

### 5. Sichere Transaktionssequenzen

Dies ist der Teil, den Sie genau richtig hinbekommen müssen. Ein autonomer Agent hat keinen Menschen, der eine fehlerhafte Transaktion abfängt, daher muss jeder zustandsändernde Aufruf mit den vier unten stehenden Sicherheitsvorkehrungen abgesichert werden.

#### 5.1 Genehmigungen

Bevor ein Vertrag Ihre Token verschieben kann, benötigt er eine Erlaubnis. Der richtige Mechanismus hängt davon ab, welchen Vertrag Sie aufrufen – alle drei unten sind permissionless:

* **ERC-20 `approve`** – funktioniert sowohl für den Smart Router als auch den NonfungiblePositionManager, mit beliebigem Token. Eine Transaktion pro Token/Ausgeber. Am einfachsten, aber eine dauerhafte unbegrenzte Genehmigung ist ein dauerhaftes Risiko.
* **`selfPermit` (EIP-2612)** – für **NonfungiblePositionManager**-Liquiditätsoperationen. Wenn der Token EIP-2612 unterstützt, kann das SDK eine signierte, betragsgebundene Erlaubnis _inline_ mit `mint`/`increaseLiquidity` via Multicall bündeln – kein separater Approve-Vorgang. Fällt bei Token ohne EIP-2612 auf `approve` zurück.
* **Permit2** – für **Smart Router**-Swaps. Einmalig Permit2 pro Token genehmigen, dann kurzlebige, signierte, betragsgebundene Erlaubnisse pro Swap gewähren.

Für einen autonomen Agenten: Beschränken Sie jede Erlaubnis auf den genauen Betrag und eine kurze Ablaufzeit. **Gewähren Sie niemals eine unbegrenzte Genehmigung von einer Agent-Wallet, die nennenswerte Salden hält.**

#### 5.2 Kursabweichung – senden Sie nie `amountMin = 0`

Jedes Hinzufügen/Entfernen/Tauschen muss einen minimal akzeptablen Output angeben. Lassen Sie das SDK ihn von einer Toleranz ableiten, statt ihn manuell zu berechnen:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0,50%

// beim Prägen / Hinzufügen:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// beim Entfernen:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Für Swaps wendet der Smart Router `slippageTolerance` an und berechnet `amountOutMinimum` für Sie (§6, Schritt 0). **Ein Null-Minimum ist eine offene Einladung für Sandwich-Bots** – bei einer unbeaufsichtigten Wallet können das wiederholte, stille Verluste bedeuten.

#### 5.3 Deadlines – immer eine festlegen

Jeder Aufruf nimmt eine `deadline` (Unix-Sekunden). Wenn die Transaktion zu diesem Zeitpunkt noch aussteht, wird sie rückgängig gemacht, anstatt zu einem veralteten Preis ausgeführt zu werden. Halten Sie sie für einen Agenten kurz:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 Minuten
```

#### 5.4 Multicall – mehrstufige Aktionen atomar machen

Der NonfungiblePositionManager und Smart Router unterstützen `multicall`: mehrere Aufrufe in **einer Transaktion** gebündelt, die alle erfolgreich sind oder alle rückgängig gemacht werden. Das ist nicht nur eine Gasersparnis – es ist eine Sicherheitseigenschaft. Ein Rebalancing, das `decreaseLiquidity` dann `collect` ausführt, darf niemals halb ausgeführt werden. Das SDK bündelt für Sie:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Es gibt keine atomare „Rebalance"-Funktion.** Das Verschieben eines Bereichs ist eine _zusammengesetzte_ Sequenz (entfernen → sammeln → prägen). Das Entfernen und das neue Prägen finden in separaten Transaktionen statt; der Preis kann sich dazwischen bewegen. Lesen Sie den Zustand neu und berechnen Sie Minima für das Prägen nach dem Entfernen – verwenden Sie keine vor-Entfernung-Zahlen erneut.

#### Sicherheitsvorkehrungs-Checkliste (auf jede Agent-Aktion anwenden)

* \[ ] Token-Erlaubnis auf den Betrag beschränkt (Permit2), nicht unbegrenzt
* \[ ] `amount*Min` / `amountOutMinimum` von einer expliziten Kursabweichungstoleranz abgeleitet, niemals `0`
* \[ ] Kurze `deadline` für jeden Aufruf
* \[ ] Mehrstufige Aktionen über `multicall` gebündelt
* \[ ] Zustand zwischen separaten Transaktionen einer Sequenz neu gelesen
* \[ ] Eine Obergrenze pro Lauf für bewegte Werte und eine Plausibilitätsprüfung, dass der Pool-Preis innerhalb erwarteter Grenzen liegt, bevor gehandelt wird (billige Absicherung gegen das Handeln in einen manipulierten/illiquiden Pool)

***

### 6. Praxisbeispiel – automatisierter V3-Range-Rebalancer

Der Referenzagent. Er beobachtet eine Position; wenn der Preis sich der Bereichsgrenze nähert, zieht er Liquidität heraus und prägt einen neuen Bereich um den aktuellen Preis herum. Fünf Schritte.

**Auslöser:** `pool.tickCurrent` liegt innerhalb eines Puffers von `tickLower`/`tickUpper` (aus §4).

#### Schritt 0 – (optional) das Token-Verhältnis neu ausbalancieren

Nach dem Rückzug halten Sie token0 und token1 in dem Verhältnis, das der alte Bereich ergab. Ein neuer, neu zentrierter Bereich benötigt normalerweise ein anderes Verhältnis, also tauschen Sie den Überschuss über den Smart Router:

```tsx
import { SmartRouter, SwapRouter } from '@pancakeswap/smart-router'
import { TradeType } from '@pancakeswap/swap-sdk-core' 

const quoteProvider = SmartRouter.createQuoteProvider({ onChainProvider: () => publicClient })                                                                                                     
const trade = await SmartRouter.getBestTrade(amountIn, tokenOut, TradeType.EXACT_INPUT, {
  gasPriceWei: () => publicClient.getGasPrice(),
  maxHops: 2,
  poolProvider: SmartRouter.createStaticPoolProvider(candidatePools),
  quoteProvider,
})

const { calldata, value } = SwapRouter.swapCallParameters(trade, {
  slippageTolerance: new Percent(50, 10_000),
  deadlineOrPreviousBlockhash: deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: SMART_ROUTER_ADDRESS, data: calldata, value: BigInt(value) })
```

#### Schritte 1–3 – Liquidität entfernen, sammeln, verbrennen (eine Transaktion)

`removeCallParameters` erstellt das gesamte Bundle: Es verringert `decreaseLiquidity` auf null, `collect`s sowohl das zurückgezogene Kapital als auch aufgelaufene Gebühren und `burn`s den nun leeren NFT – als einzelnen atomaren `multicall`.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% – vollständiger Ausstieg
  slippageTolerance: new Percent(50, 10_000),     // 0,50% – legt amount0Min/amount1Min fest
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // warten – das nächste Prägen hängt von diesen Token ab
```

> Wenn die Position **in MasterChefV3 eingesetzt** ist, entfernen Sie sie nicht aus dem NFPM. Rufen Sie zuerst `MasterChefV3.withdraw(tokenId, to)` auf, um sie auszusetzen (dies erntet auch ausstehende CAKE) und gibt den NFT an Ihre Wallet zurück – dann führen Sie das obige Entfernen aus. Siehe §7.

#### Schritt 4 – den neuen Bereich prägen

Berechnen Sie Ticks um den _aktuellen_ Preis herum neu (lesen Sie den Pool neu – siehe §5.4), richten Sie sie am Tick-Abstand der Gebührenstufe aus, erstellen Sie eine `Position` aus den Token, die Sie jetzt halten, und prägen Sie.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* Pool neu lesen slot0 + liquidity → neuer Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // strategiedefinierte Bereichsbreite

const tickLower = nearestUsableTick(freshPool.tickCurrent - halfWidth, spacing)
const tickUpper = nearestUsableTick(freshPool.tickCurrent + halfWidth, spacing)

const newPosition = Position.fromAmounts({
  pool: freshPool,
  tickLower,
  tickUpper,
  amount0: balance0,
  amount1: balance1,
  useFullPrecision: true,
})

const { calldata, value } = NonfungiblePositionManager.addCallParameters(newPosition, {
  slippageTolerance: new Percent(50, 10_000), // legt amount0Min/amount1Min für das Prägen fest
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

Der Agent hält nun einen frischen, im Bereich liegenden NFT. Wenn er farmt, setzen Sie ihn erneut ein (§7). Kehren Sie beim nächsten Tick zum §4-Lesen zurück.

***

### 7. Farm-Interaktionen (MasterChefV3)

Das Einsetzen eines V3-Positions-NFTs in MasterChefV3 verdient CAKE zusätzlich zu den Swap-Gebühren.

> **Nur Positionen aus Pools mit einer aktiven Farm verdienen CAKE.** Die PancakeSwap Governance registriert, welche Pools farmbar sind (jeder erhält eine `pid`). Das Einsetzen einer Position, deren Pool nicht registriert ist, schlägt mit `InvalidPid` fehl. Dies ist der einzige Ort, an dem die Agent-Aktivität von einer PancakeSwap-seitigen Liste abhängt – und es ist auf Pool-Ebene, nicht auf Agent-Ebene: jede Wallet kann in jede aktive Farm einsetzen. (Das Verwalten einer Position über den NonfungiblePositionManager – mint/collect/rebalance – benötigt keine Farm und funktioniert für jeden Pool.)

> **Nur Positionen aus Pools mit einer aktiven Farm verdienen CAKE.** Die PancakeSwap Governance registriert, welche Pools farmbar sind (jeder erhält eine `pid`). Das Einsetzen einer Position, deren Pool nicht registriert ist, schlägt mit `InvalidPid` fehl. Dies ist der _einzige_ Ort, an dem die Agent-Aktivität von einer PancakeSwap-seitigen Liste abhängt – und es ist auf Pool-Ebene, nicht auf Agent-Ebene: jede Wallet kann in jede _aktive_ Farm einsetzen. Überprüfen Sie vor dem Aufbau einer Farming-Strategie, ob der Pool eine aktive Farm hat. (Das Verwalten einer Position über den NonfungiblePositionManager – mint/collect/rebalance – benötigt keine Farm und funktioniert für jeden Pool.)

* **Einsetzen** – Übertragen Sie den Positions-NFT an MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). Die Farm verwahrt nun den NFT.
* **Ernten** – `harvest(tokenId, to)` beansprucht ausstehende CAKE ohne Auszahlung. Verwenden Sie `batchHarvest`, um über mehrere Positionen in einer Transaktion zu ernten.
* **Abheben / Beenden** – `withdraw(tokenId, to)` setzt aus, erntet ausstehende CAKE und gibt den NFT an Ihre Wallet zurück. Sie müssen abheben, bevor Sie `decreaseLiquidity`/`burn` aufrufen können (die NFPM-Aufrufe in §6 funktionieren nur auf einem NFT, den Ihre Wallet hält).

Ein Rebalancer für eine **gefernte** Position läuft daher: `withdraw` → entfernen/sammeln/verbrennen → prägen → `safeTransferFrom` zurück in MasterChefV3.

***

### 8. Sicherheit, Grenzen und Haftungsausschlüsse

Lesen Sie dies, bevor Sie einen Agenten einsetzen, der echte Gelder bewegt.

* **Autonomie ist unumkehrbar.** Ein eingesetzter Agent signiert und sendet Transaktionen ohne menschliche Bestätigung. Ein Fehler, ein falscher Auslöser oder ein manipulierter Preisfeed wird real ausgeführt. Testen Sie im BSC-Testnetz, begrenzen Sie dann das Mainnet-Risiko (pro Trade und pro Tag), bevor Sie skalieren.
* **Kursabweichung und Deadlines sind Pflicht**, nicht optional (§5). Ein Agent, der sie weglässt, wird irgendwann per Sandwich-Angriff angegriffen.
* **Preismanipulations-Abwehr.** Vor dem Handeln den Pool-Preis gegen eine unabhängige Referenz prüfen und den Lauf überspringen, wenn sie abweichen – billige Absicherung gegen das Handeln in einen manipulierten oder dünnen Pool.
* **Gas und Finanzierung.** Halten Sie die Agent-Wallet mit BNB für Gas finanziert; ein ausgehungerter Agent kann eine Position mitten im Rebalancing zurücklassen (entfernt, aber nicht neu geprägt). Das erneute Lesen des Zustands bei jedem Lauf (§4) ermöglicht die Wiederherstellung beim nächsten Tick.
* **Skalierte-UI / RWA-Token.** Einige BSC-Token (z. B. Binance Stock Tokens) verwenden On-Chain-UI-Multiplikatoren (ERC-8056). On-Chain-Rohmengen unterscheiden sich von angezeigten Mengen. Wenn Ihr Agent diese handelt, führen Sie alle Vertragsberechnungen in Roheinheiten durch und wenden Sie den Multiplikator nur für die menschenlesbare Anzeige an.
* **Sie sind für Ihren Agenten verantwortlich.** PancakeSwap-Pools sind permissionless Contracts; einen autonomen Agenten gegen sie einzusetzen ist Ihre Entscheidung und Ihr Risiko. Diese Anleitung ist eine technische Referenz, keine Finanzberatung, und PancakeSwap übernimmt keine Garantie für Ergebnisse.

***

### 9. Referenz

* **`@pancakeswap/smart-router`** – Routing + Swap-Calldata (beste Beispiele im Repo sind in seiner README)
* **`@pancakeswap/v3-sdk`** – `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, Tick/Preis-Mathematik
* **BNB Agent Studio** – Beschreibung, Erstellung und Bereitstellung des Agenten (BNB-Dokumentation)
* **PancakeSwap-Deployment-Adressen** – kanonische Vertragsliste (vor Verwendung verifizieren)
* **ERC-8056 (Scaled UI Amount)** – [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
