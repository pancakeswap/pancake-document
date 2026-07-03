---
description: >-
  Nous comprenons que vous puissiez avoir des questions sur notre dernière mise à niveau. Nous avons compilé cette FAQ complète pour répondre à toutes vos interrogations. Plongeons-y :
---

# FAQ PancakeSwap Infinity

**Q1 En quoi PancakeSwap Infinity bénéficiera-t-il aux traders et aux fournisseurs de Liquidité ?**

**Rép. :** PancakeSwap Infinity apporte de nombreux avantages tant pour les traders que pour les fournisseurs de Liquidité :

**1. Opérations simplifiées et économies de gas :** Grâce à des fonctionnalités telles que le Singleton et la comptabilité Flash, PancakeSwap Infinity réduit considérablement les frais de gas. Le Singleton consolide tous les pools dans un seul contrat, réduisant les coûts de déploiement de 99%. La comptabilité Flash optimise les processus comptables en calculant les soldes nets des transactions, minimisant ainsi la consommation de gas.

**2. Avantages directs grâce aux fonctionnalités avancées :** L'intégration des Hooks permet d'implémenter des frais dynamiques, des types d'ordres personnalisés et des modules de gestion active de la Liquidité. Les fournisseurs de Liquidité peuvent bénéficier d'une réduction des pertes impermanentes (IL), d'une protection MEV et d'un accès à différents niveaux de frais, garantissant des expériences de trading plus rentables et sécurisées.

\
**3. Flexibilité dans les conceptions d'AMM :** PancakeSwap Infinity supporte plusieurs types de pools, notamment le CLAMM et le LBAMM, permettant aux traders et aux LP de choisir différents types de pools. Cette approche inclusive permet également de prendre en charge tout futur actif nécessitant de nouvelles courbes de tarification. Consultez ce blog pour [en savoir plus](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2016.16.56.png" alt=""><figcaption></figcaption></figure>

**Q2** En quoi PancakeSwap Infinity bénéficiera-t-il aux développeurs et aux protocoles DeFi ?

**Rép. :** PancakeSwap Infinity ouvre un monde de possibilités pour les développeurs et les protocoles DeFi.

**1. Personnalisation sans limites :** Avec PancakeSwap Infinity, les développeurs peuvent créer des Hooks pour introduire des fonctionnalités personnalisées : des frais dynamiques aux ordres Limit on-chain, en passant par des oracles personnalisés. PancakeSwap Infinity prend en charge le déploiement de nouveaux types de pools (CLAMM, LBAMM, et tout autre type de pool à l'avenir), améliorant l'efficacité du capital et la flexibilité du trading.

**2. Accès à une Liquidité robuste et à une large base d'utilisateurs :** Avec plus de 1,8 million d'utilisateurs actifs et 2,1 milliards de dollars de Liquidité, les développeurs et les protocoles DeFi ont une opportunité sans précédent de tirer parti d'une communauté vaste et active, favorisant le développement et l'adoption de produits.

**3. Opportunités de génération de revenus :** Les développeurs peuvent établir un flux de revenus constant grâce aux frais de hook, leur permettant de définir des frais pour l'utilisation de leurs Hooks. En monétisant leurs innovations avec des frais, les développeurs peuvent contribuer à la croissance et au développement de l'écosystème PancakeSwap. Consultez ce blog pour [en savoir plus](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2009.40.42.png" alt=""><figcaption></figcaption></figure>

**Q3** Quelles améliorations PancakeSwap Infinity apporte-t-il par rapport à v3 ?

**Rép. :** PancakeSwap Infinity introduit la capacité d'améliorer les fonctionnalités des pools de Liquidité avec des fonctionnalités personnalisées sans réimplémenter le protocole de base. Il prend également en charge l'implémentation de toute courbe de tarification à la volée et offre des économies de gas substantielles pour les utilisateurs.

**Q4** Y aura-t-il des changements dans l'interface utilisateur ou l'expérience utilisateur de PancakeSwap Infinity ?

**Rép. :** Les utilisateurs peuvent effectuer des Swaps sur Infinity via la page d'échange de PancakeSwap, tout comme d'habitude. Les traders et les fournisseurs de Liquidité disposent de plusieurs options pour ajouter de la Liquidité sur les types de pools supportés, notamment CLAMM et LBAMM.

**Q5** Comment la communauté peut-elle participer aux tests ou fournir des retours sur PancakeSwap Infinity ?

**Rép. :** Si vous êtes membre de la communauté, n'hésitez pas à partager vos retours via nos réseaux sociaux sur [Telegram](https://t.me/PancakeSwapAnn), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) et [Twitter](https://twitter.com/PancakeSwap). Si vous êtes développeur, rejoignez notre communauté Discord pour développeurs et partagez vos réflexions.

**Q6** Où les utilisateurs peuvent-ils trouver plus d'informations sur PancakeSwap Infinity et rester informés de son avancement ?

**Rép. :** Visitez notre [site officiel](https://pancakeswap.finance/v4?utm_source=v4announcementblog\&utm_medium=blog\&utm_campaign=v4announcementblog\&utm_id=v4announcementblog), lisez notre [livre blanc](https://github.com/pancakeswap/pancake-v4-core/blob/main/docs/whitepaper-en.pdf) et suivez-nous sur les réseaux sociaux pour les dernières mises à jour et développements. Si vous êtes développeur, rejoignez notre communauté Discord pour développeurs.\
\
**Q7** Quel est le mécanisme de licence de PancakeSwap Infinity ?

**Rép. :** PancakeSwap Infinity s'engage en faveur des principes open-source. Notre code sera publié sous une licence open-source, permettant aux développeurs d'innover librement. Cependant, dans le cadre de notre [initiative Affiliés](https://forum.pancakeswap.finance/t/discussion-on-pancakeswap-affiliates-a-multichain-expansion-strategy/395), les protocoles DeFi qui forkent PancakeSwap seront chaleureusement accueillis et officiellement reconnus par la Kitchen.\
\
**Q8** Comment PancakeSwap Infinity réduit-il les frais de gas ?

**Rép. :** PancakeSwap Infinity s'appuie sur les mécanismes Singleton et de comptabilité Flash pour réduire significativement les frais de gas. En consolidant tous les pools dans un seul contrat (singleton), les transactions multi-pools sont simplifiées, les rendant plus économiques. La comptabilité Flash remplace les transferts individuels par des soldes nets, calculés collectivement à la fin de chaque transaction, ce qui génère des économies de gas substantielles. L'ERC-6909 réduit davantage le gas pour les utilisateurs fréquents en leur permettant de conserver leurs fonds au sein du protocole et de les utiliser selon les besoins, éliminant ainsi les transferts vers/depuis leur Portefeuille.\
\
**Q9** Que sont les Hooks dans PancakeSwap Infinity, et comment permettent-ils l'innovation ?

**Rép. :** Les Hooks sont des extensions personnalisables qui améliorent les fonctionnalités des pools de Liquidité, permettant aux développeurs d'introduire des fonctionnalités personnalisées et des options de gestion des frais. Déployés en externe, les Hooks peuvent exécuter une logique prédéfinie lors des actions clés du pool, offrant des possibilités infinies, notamment des frais dynamiques, des types d'ordres, des oracles personnalisés et des stratégies de gestion active de la Liquidité. Consultez ce blog pour [en savoir plus](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)\
\
**Q10** Quelles opportunités PancakeSwap Infinity présente-t-il pour les développeurs ?

**Rép. :** Les développeurs peuvent créer des solutions innovantes, générer des revenus grâce aux frais de hook et tirer parti de la vaste base d'utilisateurs et de la Liquidité profonde de PancakeSwap. Lisez notre [article de blog](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks) dédié pour savoir pourquoi les développeurs devraient construire sur PancakeSwap.

**Q11** Comment PancakeSwap Infinity contribue-t-il à l'écosystème DeFi au sens large ?

**Rép. :** PancakeSwap Infinity vise à remédier aux lacunes des AMM actuels, à améliorer l'expérience des DEX et à évoluer vers la plateforme DeFi la plus fonctionnelle, soutenue par notre approche open-source. Lisez la [vision de Chef Mochi pour Infinity](https://blog.pancakeswap.finance/articles/chef-mochi-s-vision-for-pancake-swap-v4-a-leap-forward-in-de-fi-innovation) pour en savoir plus\
\
**Q12** Où peut-on trouver le référentiel de modèle de hook ?

**Rép. :** Le modèle de Hooks est disponible sur [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) et des exemples de Hooks sur [https://github.com/pancakeswap/infinity-hooks](https://github.com/pancakeswap/infinity-hooks)\
\
**Q13** Pouvez-vous expliquer les cycles de vie des Hooks et leurs exemples ?

**Rép. :** Les Hooks peuvent être implémentés avant / après 5 actions clés : initialize, swap, addLiquidity, removeLiquidity, donate. Par exemple, lorsqu'un utilisateur initie un Swap, le contrat PoolManager vérifie si un hook de rappel beforeSwap existe. Si c'est le cas, la logique de la méthode beforeSwap dans le contrat de hook est exécutée ; sinon, le Swap se déroule normalement. Une fois le Swap terminé, le même processus se produit pour le rappel afterSwap.\
\
**Q14 :** Devons-nous effectuer un address mining pour garantir que les Hooks soient déployés à une adresse spécifique ?\
**Rép. :** Les Hooks peuvent être déployés à n'importe quelle adresse comme les autres contrats. Les permissions de rappel sont définies au niveau du PoolKey. Pour plus d'informations, veuillez consulter la FAQ sur les Hooks ici

[https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook](https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook)\
\
**Q15 :** Comment vérifier un contrat de hook sur etherscan ?

**Rép. :** Si vous utilisez foundry, vous pouvez vous référer au guide foundry ici [https://book.getfoundry.sh/reference/forge/forge-verify-contract](https://book.getfoundry.sh/reference/forge/forge-verify-contract) \
Ou si vous utilisez hardhat, référez-vous au guide hardhat ici [https://hardhat.org/hardhat-runner/docs/guides/verifying](https://hardhat.org/hardhat-runner/docs/guides/verifying)\
\
**Q16 :** Devons-nous utiliser foundry ou hardhat pour le développement de Hooks ?

**Rép. :** Le modèle [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) est basé sur foundry ; nous conseillons donc d'utiliser foundry. Par ailleurs, foundry gagne en popularité !

**Q17 :** Que sont les pool keys (clés de pool) ?

**Rép. :** PoolKey est une structure qui décrit chaque pool. En savoir plus [ici](https://developer.pancakeswap.finance/contracts/infinity/overview/amm-layer-poolmanager).\
\
\
PancakeSwap Infinity représente une étape majeure dans l'espace DeFi, offrant des avantages incomparables aux traders, développeurs, fournisseurs de Liquidité et à l'ensemble de la communauté. Nous sommes ravis d'entreprendre ce voyage avec vous et espérons façonner ensemble l'avenir de la DeFi. Nous espérons que cette FAQ a répondu à vos questions sur PancakeSwap Infinity. Si vous avez d'autres questions, n'hésitez pas à nous contacter via ([Twitter](https://twitter.com/PancakeSwap), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) et [Telegram](https://t.me/PancakeSwap)) ou consultez notre [documentation](https://developer.pancakeswap.finance) pour développeurs.
