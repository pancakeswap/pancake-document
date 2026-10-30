---
description: '2026-08-21'
---

# Présentation du Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Coter cinq paires ne devrait pas coûter cinq fois le capital. Pourtant, onchain, c'est le marché que chaque émetteur d'actifs se voit imposer : la liquidité est liée à chaque paire, donc chaque nouvelle paire implique d'engager un nouveau bloc de capital — dont la majeure partie dort sans rien rapporter tant que cette paire précise n'est pas échangée dans cette fourchette de prix précise. Chaque fois que vous voulez coter une nouvelle paire, vous apportez du capital frais en liquidité — un capital alors verrouillé sur cette seule paire et inutilisable ailleurs.

Le Shared Inventory Hook (SIH) rompt ce lien. C'est le tout nouveau hook de PancakeSwap Infinity — et le premier conçu pour l'efficacité du capital.

_💡 Rappel : un hook est un smart contract (comme un module complémentaire) qui se branche sur un pool Infinity et exécute une logique personnalisée au cours d'un swap — sans avoir à créer un nouveau lieu d'échange._

Comment cela fonctionne-t-il ?

Au lieu de verrouiller une réserve distincte dans chaque pool, un émetteur d'actifs RWA alimente **un inventaire partagé unique**, et le shared inventory hook cote la profondeur à partir de celui-ci sur la paire qui est échangée — just-in-time, au moment même du swap. Imaginez une seule réserve alimentant tous les plats de la cuisine, plutôt qu'une réserve distincte pour chacun. Un seul solde fait le travail de plusieurs.

Ce simple changement est ce qui rend le SIH efficace en capital, et cela se manifeste de trois façons :

* **Un capital actif et productif.** La liquidité de l'inventaire du hook est injectée just-in-time lors d'un swap, elle travaille donc activement et vous rapporte des frais au lieu de rester inactive.
* **Opportunité de frais à partir d'un seul solde, sur plusieurs paires.** Un seul inventaire rapporte sur toutes les paires qu'il dessert, vous captez donc le flux de frais avec bien moins de capital déployé.
* **Price impact réduit.** Comme la liquidité cotée au moment du swap est plus profonde, les transactions de grande taille subissent un price impact plus faible chaque fois que le SIH cote le meilleur prix.
* **Efficacité du capital accrue.** Financez une fois ; le même capital soutient la profondeur sur chaque paire compatible SIH. De plus, vous pouvez activer le SIH pour une nouvelle paire sans ajouter de capital.

> \*\*Déjà convaincu ? Amenez vos actifs onchain de la manière la plus efficace en capital — remplissez ce formulaire → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**La preuve est onchain**

Le SIH a été lancé avec les bStocks en août, et le chiffre le plus important est l'intensité avec laquelle ce capital travaille. Sur le dernier instantané du hook (21 août 2026), 75 % de l'inventaire partagé est activement déployé sur les trois paires (inventaire du hook \~297 k$, actif \~224 k$). Sur les deux paires matures, CRCLB et MUB, l'utilisation est d'environ 99 % (98,96 % / 98,95 %). Le capital qui resterait inactif dans les pools CLAMM v3 traditionnels est ici dans la fourchette et en cotation.

Durant ses premières semaines (jusqu'au 21 août), les trois paires ont échangé \~710 k$ à travers 5 713 swaps — servis par un inventaire partagé d'environ 297 k$, générant des frais de LP avec un palier de 0,25 %.

_**Sources :** Tableau de bord Dune interne_ **Pools actifs :** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Où cela nous mène**

Le modèle est conçu pour passer à l'échelle — davantage de paires, un seul solde partagé s'étendant sur des milliers de marchés actifs 24h/24 et 7j/7. C'est le chemin le plus rapide que nous ayons vu pour mettre onchain toute la gamme de paires d'un token sans multiplier le capital qui la soutient.

Les pools SIH actifs se trouvent sur la [page Earn de PancakeSwap](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001) — ouvrez **Infinity** et cherchez **Shared Inventory** dans les caractéristiques des pools. Le SIH est actuellement activé sur CRCLB / USDT, MUB / USDT et GMEB / USDT.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Note : les LP particuliers peuvent déjà ajouter de la liquidité à ces pools depuis Earn — ce dépôt devient de la liquidité résidente du pool, détenue séparément de l'inventaire partagé._

_**Important :**_

_Le SIH est moins exposé à la dérive des prix qu'une position de LP standard, car l'inventaire n'est mis au travail qu'au moment d'un swap. Il n'est pas sans risque. L'opérateur détient toujours un inventaire qui évolue avec le marché. Comme pour toute stratégie onchain, les résultats dépendent du volume, de l'inventaire, de la couverture et des conditions de marché._

Prêt à maximiser l'efficacité du capital ? Faites activer le SIH sur vos paires de tokens dès maintenant → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, Les Chefs 🥞

***

_Avertissement : ce contenu est fourni à titre d'information générale et éducative uniquement. Il ne doit pas être interprété comme un conseil financier, juridique ou professionnel. Les prix des actifs numériques peuvent être volatils. La valeur de votre investissement peut baisser comme augmenter._
