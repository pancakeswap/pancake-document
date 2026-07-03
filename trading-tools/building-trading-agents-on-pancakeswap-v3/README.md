# 🤖 BNB AI Agent Studio

> Un guide pour les développeurs créant des agents autonomes — avec [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) ou tout autre framework — qui interagissent avec les pools de Liquidité et les Farm de PancakeSwap V3 sur BNB Smart Chain.
>
> Vous décrivez une stratégie ; votre agent l'exécute on-chain, sans intervention. Cette page couvre la partie PancakeSwap : les contrats à appeler, l'ordre sûr pour les appeler, et un exemple complet (un rééquilibreur de plage V3 automatisé). Pour savoir comment décrire, construire et déployer l'agent lui-même, consultez la documentation de BNB Agent Studio.

PancakeSwap ne nécessite **aucune intégration** pour que cela fonctionne. Les pools V3 et les Farm sont des contrats intelligents sans permission — votre agent les appelle directement, de la même manière que le frontend de PancakeSwap le fait. Tout ce qui est décrit ci-dessous est une surface on-chain publique.

***

### 1. Ce qu'un agent peut faire avec PancakeSwap

La Liquidité concentrée (V3) offre aux fournisseurs de Liquidité une bien meilleure efficacité du capital que V2, au prix d'une gestion active : une position ne génère des frais que lorsque le prix est dans sa plage de ticks, et les récompenses/rendements évoluent constamment. Cette charge opérationnelle est exactement ce qu'un agent supprime. Stratégies courantes :

* **Rééquilibreur de plage** — surveille une position LP ; lorsque le prix dérive vers le bord de la plage, retirer et réémettre autour du nouveau prix pour que la position continue à générer des frais. _(Exemple dans §6.)_
* **Routeur APR de Farm** — suit le rendement CAKE + frais sur les pools et déplace la Liquidité vers le rendement total le plus élevé.
* **Bots de Swap/cotation** — achemine les transactions via le Smart Router pour la meilleure exécution entre V2 + V3.

Tout cela est une composition des mêmes quelques appels de contrats ci-dessous.

***

### 2. Surface contractuelle (BNB Smart Chain, chainId 56)

| Contrat                               | Adresse                                      | Votre agent l'utilise pour                                                                                     |
| ------------------------------------- | -------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Créer/gérer des positions LP — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Exécuter des Swaps avec le meilleur routage V2+V3                                                              |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Staker un NFT de position pour générer du CAKE — `harvest`, `withdraw`                                          |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Obtenir une cotation de Swap avant de l'envoyer                                                                |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Résoudre une adresse de pool à partir de `(token0, token1, fee)`                                               |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Approbations de tokens sans gaz/groupées pour **les Swaps Smart Router** (voir §5.1)                           |

> ⚠️ **Vérifiez toujours les adresses** par rapport à la liste de déploiement canonique de PancakeSwap avant d'envoyer de la valeur réelle. Considérez le tableau ci-dessus comme un point de départ.

Un **pool** V3 est identifié par `(token0, token1, fee)`. Niveaux de frais et leur espacement de tick :

| Frais  | valeur `fee` | Espacement de tick | Utilisation typique            |
| ------ | ------------ | ------------------ | ------------------------------ |
| 0,01 % | `100`        | 1                  | Stable–stable                  |
| 0,05 % | `500`        | 10                 | Corrélé (ex. ETH/BTC)          |
| 0,25 % | `2500`       | 50                 | La plupart des paires          |
| 1,00 % | `10000`      | 200                | Exotique / volatil             |

Une **position** V3 est un NFT ERC-721 conservé dans le NonfungiblePositionManager. Il stocke `tickLower`, `tickUpper`, `liquidity` et les frais accumulés. Vous y faites référence par `tokenId`.

***

### 3. Outillage

Vous pouvez interagir avec ces contrats via des ABI bruts et n'importe quelle bibliothèque web3, mais les packages **`@pancakeswap/v3-sdk`** et **`@pancakeswap/smart-router`** effectuent les calculs complexes (tick ↔ prix, minimums ajustés au Glissement, encodage des données d'appel) pour vous. Les exemples ci-dessous les utilisent avec [viem](https://viem.sh/).

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

Votre agent n'est que ce portefeuille exécutant des transactions selon un calendrier ou un déclencheur. Le portefeuille est financé et géré par Agent Studio — voir la documentation BNB.

***

### 4. Lecture de l'état (à faire avant chaque action)

Un agent décide _s'il faut_ agir en lisant la chaîne. Les trois lectures qui pilotent la plupart des stratégies :

**Prix du pool et tick actuel** — construire une entité `Pool` à partir des données on-chain `slot0` + `liquidity` :

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress résolu depuis la factory ou computePoolAddress()
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

console.log('price token0→token1:', pool.token0Price.toSignificant(6))
console.log('current tick:', pool.tickCurrent)
```

**Une position que vous détenez** — la lire depuis le NonfungiblePositionManager par `tokenId` :

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**La position est-elle dans la plage ?** Ce simple booléen est le déclencheur d'un rééquilibreur. Vous pouvez le resserrer à « dans N ticks de la frontière » pour agir _avant_ qu'elle ne sorte de la plage.

***

### 5. Séquences de transactions sécurisées

C'est la partie à bien maîtriser. Un agent sans surveillance n'a pas d'humain pour corriger une mauvaise transaction, donc chaque appel modifiant l'état doit être protégé par les quatre garde-fous ci-dessous.

#### 5.1 Approbations

Avant qu'un contrat puisse déplacer vos tokens, il a besoin d'une allocation. Le mécanisme approprié dépend du contrat que vous appelez — les trois ci-dessous sont sans permission :

* **ERC-20 `approve`** — fonctionne à la fois pour le Smart Router et le NonfungiblePositionManager, avec n'importe quel token. Une transaction par token/dépenseur. Le plus simple, mais une approbation infinie permanente est un risque permanent.
* **`selfPermit` (EIP-2612)** — pour les opérations de Liquidité **NonfungiblePositionManager**. Si le token prend en charge EIP-2612, le SDK peut regrouper un permit signé, limité en montant, _inline_ avec `mint`/`increaseLiquidity` via multicall — pas de transaction d'approbation séparée. Revient à `approve` pour les tokens sans EIP-2612.
* **Permit2** — pour les Swaps **Smart Router**. Approuvez Permit2 une fois par token, puis accordez des allocations courtes, signées, limitées en montant par Swap.

Pour un agent autonome : limitez chaque permit au montant exact et avec une courte expiration. **N'accordez jamais une approbation illimitée depuis un portefeuille d'agent qui contient des soldes significatifs.**

#### 5.2 Glissement — n'envoyez jamais `amountMin = 0`

Chaque ajout/retrait/Swap doit spécifier un résultat minimal acceptable. Laissez le SDK le dériver à partir d'une tolérance plutôt que de le calculer manuellement :

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0,50%

// lors de l'émission / de l'ajout :
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// lors du retrait :
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Pour les Swaps, le Smart Router applique `slippageTolerance` et calcule `amountOutMinimum` pour vous (§6, étape 0). **Un minimum à zéro est une invitation ouverte aux bots sandwich** — sur un portefeuille sans surveillance, cela peut signifier des pertes répétées et silencieuses.

#### 5.3 Délais — définissez-en toujours un

Chaque appel prend un `deadline` (secondes unix). Si la transaction est encore en attente à ce moment, elle est annulée au lieu d'être exécutée à un prix périmé. Gardez-le court pour un agent :

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutes
```

#### 5.4 Multicall — rendez les actions en plusieurs étapes atomiques

Le NonfungiblePositionManager et le Smart Router prennent en charge `multicall` : plusieurs appels regroupés en **une seule transaction** qui réussissent tous ou échouent tous. Il ne s'agit pas seulement d'économies de gaz — c'est une propriété de sécurité. Un rééquilibrage qui effectue `decreaseLiquidity` puis `collect` ne doit jamais s'exécuter à moitié. Le SDK regroupe pour vous :

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Il n'existe pas de fonction « rééquilibrage » atomique.** Déplacer une plage est une _séquence composée_ (retrait → collecte → émission). Le retrait et la nouvelle émission se produisent dans des transactions séparées ; le prix peut évoluer entre les deux. Relisez l'état et recalculez les minimums pour l'émission après la confirmation du retrait — ne réutilisez pas les chiffres d'avant le retrait.

#### Liste de contrôle des garde-fous (à appliquer à chaque action de l'agent)

* \[ ] Allocation de tokens limitée au montant (Permit2), pas illimitée
* \[ ] `amount*Min` / `amountOutMinimum` dérivé d'une tolérance de Glissement explicite, jamais `0`
* \[ ] `deadline` court sur chaque appel
* \[ ] Actions en plusieurs étapes regroupées via `multicall`
* \[ ] Relecture de l'état entre les transactions séparées d'une séquence
* \[ ] Un plafond par exécution sur la valeur déplacée, et une vérification de cohérence que le prix du pool est dans les limites attendues avant d'agir (protection bon marché contre l'action dans un pool manipulé/illiquide)

***

### 6. Exemple complet — rééquilibreur de plage V3 automatisé

L'agent de référence. Il surveille une position ; lorsque le prix approche de la frontière de la plage, il retire la Liquidité et réémet une nouvelle plage centrée sur le prix actuel. Cinq étapes.

**Déclencheur :** `pool.tickCurrent` est dans un tampon de `tickLower`/`tickUpper` (depuis §4).

#### Étape 0 — (optionnel) rééquilibrer le ratio de tokens

Après le retrait, vous détiendrez token0 et token1 dans le ratio produit par l'ancienne plage. Une nouvelle plage recentrée nécessite généralement un ratio différent, alors échangez l'excédent via le Smart Router :

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

#### Étapes 1–3 — retirer la Liquidité, collecter, brûler (une seule transaction)

`removeCallParameters` construit l'ensemble du bundle : il effectue `decreaseLiquidity` à zéro, `collect`e à la fois le principal retiré et les frais accumulés, et `burn`e le NFT désormais vide — sous la forme d'un unique `multicall` atomique.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — sortie complète
  slippageTolerance: new Percent(50, 10_000),     // 0,50% — définit amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // attendre — la prochaine émission dépend de ces tokens
```

> Si la position est **stakée dans MasterChefV3**, vous ne retirez pas depuis le NFPM. Appelez d'abord `MasterChefV3.withdraw(tokenId, to)` pour dé-staker (cela récolte également le CAKE en attente), ce qui retourne le NFT dans votre portefeuille — puis exécutez le retrait ci-dessus. Voir §7.

#### Étape 4 — émettre la nouvelle plage

Recalculez les ticks autour du prix _actuel_ (relisez le pool — voir §5.4), ajustez-les à l'espacement du niveau de frais, construisez une `Position` à partir des tokens que vous détenez maintenant, et émettez.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* relire slot0 + liquidity → nouveau Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // largeur de plage définie par la stratégie

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
  slippageTolerance: new Percent(50, 10_000), // définit amount0Min/amount1Min pour l'émission
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

L'agent détient maintenant un nouveau NFT dans la plage. S'il faisait du Farming, restakez-le (§7). Repassez à la lecture §4 au prochain tick.

***

### 7. Interactions avec les Farm (MasterChefV3)

Staker un NFT de position V3 dans MasterChefV3 génère du CAKE en plus des frais de Swap.

> **Seules les positions des pools avec un Farm actif génèrent du CAKE.** La Gouvernance de PancakeSwap enregistre quels pools sont éligibles au Farming (chacun obtient un `pid`). Staker une position dont le pool n'est pas enregistré génère une erreur avec `InvalidPid`. C'est le seul endroit où l'activité de l'agent dépend d'une liste côté PancakeSwap — et c'est au niveau du pool, pas au niveau de l'agent : n'importe quel portefeuille peut staker dans n'importe quel Farm actif. (Gérer une position via le NonfungiblePositionManager — émission/collecte/rééquilibrage — ne nécessite pas de Farm et fonctionne pour tous les pools.)

> **Seules les positions des pools avec un Farm actif génèrent du CAKE.** La Gouvernance de PancakeSwap enregistre quels pools sont éligibles au Farming (chacun obtient un `pid`). Staker une position dont le pool n'est pas enregistré génère une erreur avec `InvalidPid`. C'est le _seul_ endroit où l'activité de l'agent dépend d'une liste côté PancakeSwap — et c'est au niveau du pool, pas au niveau de l'agent : n'importe quel portefeuille peut staker dans n'importe quel Farm _actif_. Vérifiez que le pool dispose d'un Farm actif avant de construire une stratégie de Farming autour de lui. (Gérer une position via le NonfungiblePositionManager — émission/collecte/rééquilibrage — ne nécessite pas de Farm et fonctionne pour tous les pools.)

* **Staker** — transférer le NFT de position vers MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). Le Farm garde maintenant le NFT en dépôt.
* **Récolter** — `harvest(tokenId, to)` réclame le CAKE en attente sans dé-staker. Utilisez `batchHarvest` pour réclamer sur plusieurs positions en une seule transaction.
* **Retrait / sortie** — `withdraw(tokenId, to)` dé-stake, récolte le CAKE en attente et retourne le NFT dans votre portefeuille. Vous devez retirer avant de pouvoir effectuer `decreaseLiquidity`/`burn` (les appels NFPM dans §6 ne fonctionnent que sur un NFT que votre portefeuille détient).

Un rééquilibreur pour une position **en Farm** s'exécute donc ainsi : `withdraw` → retrait/collecte/brûlage → émission → `safeTransferFrom` vers MasterChefV3.

***

### 8. Sécurité, limites et avertissements

Lisez ceci avant de déployer un agent qui déplace des fonds réels.

* **L'autonomie est irréversible.** Un agent déployé signe et envoie des transactions sans confirmation humaine. Un bug, un mauvais déclencheur, ou un flux de prix manipulé s'exécute pour de vrai. Testez sur le testnet BSC, puis plafonnez l'exposition sur le mainnet (limites par transaction et par jour) avant de passer à l'échelle.
* **Le Glissement et les délais sont obligatoires**, pas optionnels (§5). Un agent qui les omet finira par être attaqué par un sandwich.
* **Défense contre la manipulation de prix.** Avant d'agir, vérifiez le prix du pool par rapport à une référence indépendante et ignorez l'exécution si elle diverge — une assurance bon marché contre le trading dans un pool manipulé ou peu liquide.
* **Gaz et financement.** Maintenez le portefeuille de l'agent financé en BNB pour le gaz ; un agent à court de gaz peut laisser une position à mi-rééquilibrage (retirée mais pas réémise). Relire l'état à chaque exécution (§4) lui permet de récupérer au prochain tick.
* **Tokens à UI mise à l'échelle / RWA.** Certains tokens BSC (ex. Binance Stock Tokens) utilisent des multiplicateurs d'UI on-chain (ERC-8056). Les montants bruts on-chain diffèrent des montants affichés. Si votre agent trade ces tokens, effectuez tous les calculs contractuels en unités brutes et n'appliquez le multiplicateur que pour l'affichage orienté utilisateur.
* **Vous êtes responsable de votre agent.** Les pools PancakeSwap sont des contrats sans permission ; déployer un agent autonome contre eux est votre décision et votre risque. Ce guide est une référence technique, pas un conseil financier, et PancakeSwap ne garantit pas les résultats.

***

### 9. Référence

* **`@pancakeswap/smart-router`** — routage + données d'appel de Swap (les meilleurs exemples dans le dépôt se trouvent dans son README)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, mathématiques tick/prix
* **BNB Agent Studio** — description, construction et déploiement de l'agent (documentation BNB)
* **Adresses de déploiement PancakeSwap** — liste canonique des contrats (vérifier avant utilisation)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
