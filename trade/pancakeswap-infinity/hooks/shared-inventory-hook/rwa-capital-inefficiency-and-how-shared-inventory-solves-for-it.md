---
description: '2026-09-04'
---

# L'inefficacité du capital des RWA — et comment le Shared Inventory la résout

Une étude de cas expérimentale PancakeSwap (Partie 1 : La mise en place)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Ceci est la première partie d'une étude de cas en deux volets. Dans cette partie, nous exposons le véritable problème d'efficacité du capital auquel sont confrontés les émetteurs d'actifs RWA, nous présentons la façon dont le Shared Inventory Hook (SIH) de PancakeSwap vise à le résoudre, et nous introduisons une étude de cas expérimentale en conditions réelles pour le tester avec des données onchain.

Au cours des prochaines semaines, nous publierons la Partie 2 : Les résultats.

***

### 🧩 Qu'est-ce que le problème d'efficacité du capital ?

L'industrie des RWA adore un chiffre : **le montant tokenisé.** C'est le titre de presque tous les rapports : une nouvelle classe d'actifs arrive, des milliards émis, des centaines de pour cent de croissance.

Il existe pourtant un second chiffre, souvent passé sous silence, qui est peut-être un signal plus important : **quelle part de ce montant peut réellement être échangée ?**

L'écart entre ces deux chiffres est là où tout se joue. Sur le tracker de référence, [rwa.xyz](http://rwa.xyz), la valeur _représentée_ onchain dépasse largement celle contre laquelle il est possible de _transacter_ à un instant donné — les données montrent que la valeur verrouillée, de référence et distribuée est **plus d'un ordre de grandeur supérieure à ce qui se trouve dans les carnets d'ordres échangeables.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Source : app.rwa.xyz/stocks_

Pour un émetteur de RWA, c'est le piège. Tokeniser une action, un ETF ou un titre du Trésor est la partie facile — le défi est de permettre un échange avec des prix serrés et fiable, et c'est là que l'efficacité du capital se gagne ou se perd. L'objectif ultime est de permettre aux traders d'_échanger réellement_ l'actif tokenisé facilement et à moindre coût — c'est en fin de compte de là que viennent le volume et les frais.

Et voici pourquoi il s'agit spécifiquement d'un problème d'_efficacité du capital_, et pas seulement de liquidité.

#### Chaque pool coté exige son propre stock exclusif d'USDT

Pour rendre une paire RWA échangeable dans un pool de liquidité concentrée (CLAMM) traditionnel, les émetteurs ont besoin d'un actif de cotation dédié — l'USDT — disponible pour que les acheteurs puissent y vendre. Si vous listez dix paires, le modèle CLAMM exige de financer **dix stocks d'USDT distincts**, un par paire, sans qu'aucun ne puisse aider les autres. Le capital de cotation est ainsi fragmenté en silos exclusifs.

Nous l'avons mesuré sur notre propre book. Nous avons pris **7 pools d'actions tokenisées actifs sur PancakeSwap** (chacun fonctionnant avec un pool CLAMM v3 traditionnel) et relevé l'USDT exclusif.

Instantané : **2 septembre 2026.**

<table data-search="false"><thead><tr><th>Paire</th><th>USDT exclusif dans le pool</th><th>TVL du pool</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Total</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Cela représente **\~745 k$ d'USDT alloués de façon exclusive.**

Et ce ne sont que les noms qui disposent d'un book.

SNXXB, KORUB, SOXSB et DJTB n'ont aucun book USDT CLAMM — tokenisés, mais difficiles à échanger.

***

### 🎯 Que doit optimiser un émetteur ?

Au-delà de la mécanique, un émetteur de RWA doit résoudre trois points essentiels :

1. **Que son actif soit réellement et efficacement échangeable** — des prix serrés sur chaque actif, pas seulement sur les tokens phares.
2. **Le moins de capital possible** immobilisé pour y parvenir — l'actif de cotation coûte cher ; financer dix stocks d'USDT de façon exclusive n'est pas très efficace.
3. **Ne pas avoir à gérer une table de trading —** Émettre des actifs sans avoir à exploiter chaque jour une infrastructure de liquidité.

La question est donc de savoir si la liquidité peut être structurée différemment — et c'est ce que le Shared Inventory Hook de PancakeSwap est conçu pour résoudre.

***

### 🥞 Shared Inventory Hook (SIH)

**Le SIH est un hook PancakeSwap Infinity qui permet à un émetteur de RWA de soutenir de nombreuses paires à partir d'une seule réserve partagée d'USDT, au lieu d'un stock exclusif par paire.**

Le SIH y parvient en fournissant la liquidité just-in-time, ce qui permet :

* Des prix plus profonds sur les paires
* Un price impact plus faible, en particulier sur les transactions de grande taille
* Du capital libéré pour les émetteurs de RWA, puisque moins de capital déployé cote davantage de paires

Voyons ces affirmations en pratique.

Selon ce même instantané du **2 septembre 2026**, le SIH détient **635 028 $** d'inventaire dans un seul hook, cotant **11 paires** à partir de **180 467 $** d'USDT partagé, avec un taux d'utilisation de **87,7 %**. Avec cela, le SIH a traité **3,56 M$ à travers 17 299 transactions.**

Soit **un seul solde d'USDT partagé d'environ 700 k$ cotant environ 11 paires, contre environ 745 k$ ne cotant que 7 paires**.

Même mission, mais conçue pour cesser de dupliquer le capital.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Ce que cela donne au regard des priorités des émetteurs :

* N soldes d'USDT exclusifs traditionnellement → ✅ une seule réserve partagée avec le SIH
* Émis mais non échangeable → ✅ échangeable\
  L'inventaire partagé injecté just-in-time autour du prix en direct signifie que des tokens sans book USDT v3 peuvent tout de même être cotés, et pas seulement émis.
* Gérer une table de trading → ✅ un opérateur avec permissions\
  L'émetteur fournit l'inventaire ; le hook et son opérateur s'occupent de la cotation.

***

### 🔬 Essayez le simulateur Shared Inventory

Développez votre intuition du comportement du SIH grâce à notre outil de comparaison interactif **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Il s'agit d'une **comparaison de haut niveau, normalisée**, du SIH face à un book CLAMM traditionnel — un certain nombre de facteurs du monde réel sont maintenus constants des deux côtés afin d'isoler clairement le mécanisme d'efficacité du capital. C'est un modèle pour comprendre, pas un compte de résultat.

Trois onglets :

* **Onglet Simulator** - jouez avec l'inventaire, la largeur de la bande et le flux pour voir comment le SIH _se comporterait_ face à un pool CLAMM comparable dans différentes conditions.
* **Onglet Comparison** - le SIH comparé directement à un book **PancakeSwap v3 CLAMM** sur les mêmes pools, afin de voir côte à côte la différence entre réserve d'USDT partagée et USDT exclusif en termes de capital engagé et de couverture.
* **Onglet Live data** — mesurez la performance réelle du SIH à l'instant, à partir des requêtes onchain qui alimentent cette étude.

Le simulateur vise à aider à démontrer le fonctionnement du Shared Inventory Hook. Essayez-le, puis confrontez-le aux résultats réels que nous publierons dans les prochaines semaines.

***

### 🧪 L'expérience

Au cours des **prochaines semaines**, nous exploitons le SIH en conditions réelles et le mesurons par rapport aux affirmations d'efficacité du capital ci-dessus, à l'aide de sources onchain. Chaque semaine, nous publierons de nouveaux éclairages sur la performance et l'architecture du SIH.

**Paires RWA actives dans l'étude :** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Note : SNXXB, KORUB, SOXSB et DJTB n'ont aucun book CLAMM traditionnel._

**Nous publierons les résultats au cours des prochaines semaines sur le** [**Twitter**](https://x.com/PancakeSwap) **de PancakeSwap.**

Les résultats publiés couvriront :

* **L'ensemble complet des données de performance -** Toutes les données du SIH sur les prochaines semaines, réunies en un seul tableau.
* **La question de l'allocation du capital -** Combien de capital le SIH a réellement fait économiser à un émetteur de RWA.
* **Réussites / échecs -** Là où le SIH a dépassé les attentes, et là où il doit encore progresser.
* **Le verdict -** Une conclusion argumentée sur l'efficacité réelle du SIH pour l'efficacité du capital des RWA.

_Note sur les données : les chiffres présentés ici proviennent de requêtes onchain en direct et de données publiques sur les paires, citées au fil du texte. Certaines comparaisons utilisent des fenêtres de temps différentes et nous les avons signalées — l'étude est conçue pour mesurer des éléments comparables, alors que cette introduction ne pouvait que poser la question._

***

### Vous souhaitez activer le SIH sur vos actifs ?

Si vous êtes un émetteur de RWA et que vous en avez assez de financer un stock d'USDT distinct pour chaque pool que vous cotez, ceci est pour vous.

Nous intégrons dès maintenant des émetteurs de RWA. Remplissez ce formulaire Google et nous vous guiderons pour faire coter votre actif sur le SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Merci de votre lecture ! Suivez-nous sur [X](https://x.com/PancakeSwap) pour les dernières actualités, et rejoignez la conversation sur [Telegram](https://t.me/PancakeSwap) et [Discord](https://discord.gg/pancakeswap).

Construisons ensemble,\
Les Chefs 🥞

***

_Avertissement : ce contenu est fourni à titre d'information générale et éducative uniquement. Il ne doit pas être interprété comme un conseil financier, juridique ou professionnel. Les prix des actifs numériques peuvent être volatils. La valeur de votre investissement peut baisser comme augmenter._
