---
hidden: true
---

# Intégration des Teneurs de Marché

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Intégration des Teneurs de Marché sur Ethereum

PancakeSwap est intégré avec des teneurs de marché sur Ethereum et Binance Smart Chain pour aider les traders à exécuter leurs échanges à moindre coût.

En plus de l'AMM, les échanges sur PancakeSwap peuvent désormais être acheminés vers des teneurs de marché présélectionnés s'ils offrent une exécution meilleure que les prix actuels de l'AMM. Ce routage est effectué automatiquement par un [Smart Router](smart-router-v2/) afin que les échanges ne soient acheminés vers les teneurs de marché que lorsqu'ils proposent activement de meilleurs prix. Lorsque l'AMM est plus compétitif, les traders sont acheminés vers les AMMs pour l'exécution.

Il existe 2 scénarios dans lesquels les teneurs de marché opèrent sur PancakeSwap.

**Scénario 1 : Pools de Liquidité AMM existantes**

Si PancakeSwap dispose déjà d'une Liquidité pour un token donné (par ex. WETH/USDC) dans l'AMM, PancakeSwap demandera aux teneurs de marché un devis pour le même échange. Le Smart Router de PancakeSwap acheminera ensuite la demande d'échange vers l'AMM ou les teneurs de marché selon la source offrant le meilleur prix à tout moment.

**Scénario 2 : Aucune pool de Liquidité AMM existante**

Dans ce cas, le Smart Router acheminera automatiquement l'échange vers les teneurs de marché. Cela n'empêche toutefois pas les projets de créer ensuite leur propre pool de Liquidité AMM et de travailler avec nous pour maintenir une Liquidité DEX décentralisée.

### Frais

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap ne facture aucun frais aux traders pour les échanges exécutés par les teneurs de marché. Cependant, PancakeSwap perçoit **0,05% de frais de trading** auprès des teneurs de marché présélectionnés sur les volumes exécutés par ceux-ci. PancakeSwap perçoit des **frais de trading réduits à 0,01%** pour les échanges entre paires de stablecoins. Veuillez vous référer à la répartition des frais ci-dessous :<br>

<table><thead><tr><th width="178">Échanges</th><th width="138">Frais de Trading</th><th width="182">Frais PCS sur MM</th><th width="147">Burn de CAKE</th><th align="center">Trésorerie PancakeSwap</th></tr></thead><tbody><tr><td>Tokens bridgés depuis d'autres réseaux</td><td>N/A</td><td>0,25%</td><td>0,083%</td><td align="center">0,167%</td></tr><tr><td>Non-stablecoin sur Ethereum (ex. ETH/USDC)</td><td>N/A</td><td>0,05%</td><td>0,017%</td><td align="center">0,033%</td></tr><tr><td>Non-stablecoin sur BSC (ex. BNB/USDT)</td><td>N/A</td><td>0,05%</td><td>0,017% </td><td align="center">0,033%</td></tr><tr><td>Stablecoin vers Stablecoin sur Ethereum</td><td>N/A</td><td>0,01%</td><td>0,003%</td><td align="center">0,007%</td></tr></tbody></table>

#### Actifs actuellement pris en charge

Les actifs suivants sont actuellement pris en charge et peuvent varier selon le(s) teneur(s) de marché :

**Sur Ethereum**

* **Majeurs :** WETH, WBTC
* **Stablecoins :** USDT, USDC, DAI, BUSD
* **Autres actifs ERC-20 populaires :** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Sur Binance Smart Chain :**

* **Majeurs :** BNB, ETH, BTCB
* Tokens BNB non natifs : ARB, OP

Veuillez noter que, contrairement aux AMMs, les teneurs de marché ne pourront pas trader n'importe quel montant et les quantités qu'ils sont prêts à exécuter dépendent de leur propre Liquidité. Il n'est pas rare que de très grands ordres ne puissent être entièrement exécutés. Nous conseillons aux utilisateurs de bien vérifier les devis pour s'assurer que chaque échange correspond au prix et à la quantité souhaités.

**Interruptions des teneurs de marché**

Les teneurs de marché ne sont pas tenus de proposer des cotations 24h/24 et 7j/7. Il peut arriver (par ex. lors d'événements économiques majeurs ou de mises à jour système) que le teneur de marché soit temporairement indisponible. Pendant ces périodes, ces tokens ne pourront tout simplement pas être échangés, et nous conseillons aux utilisateurs d'attendre quelque temps avant que le teneur de marché revienne en ligne.

#### FAQ

**Q.** Les teneurs de marché seront-ils intégrés sur Aptos ?

**Rép. :** Éventuellement. Pour l'instant, nous lançons l'intégration des teneurs de marché uniquement sur Ethereum et Binance Smart Chain afin d'améliorer la Liquidité pour une meilleure expérience utilisateur. Nous continuerons à surveiller les autres chaînes.

**Q.** Comment PancakeSwap génère-t-il des revenus s'il ne facture pas de frais aux utilisateurs ?

**Rép. :** PancakeSwap ne facture aucun frais aux utilisateurs, mais perçoit une petite commission auprès des teneurs de marché, qu'il utilise pour financer le rachat et la destruction de CAKE.

**Q.** Les fournisseurs de Liquidité continueront-ils à percevoir des frais LP ?

**Rép. :** Oui, les fournisseurs de Liquidité continueront à percevoir 0,17% de frais de trading (frais LP) ainsi que des rendements sur les Farms CAKE.

**Q.** Les teneurs de marché ajouteront-ils de la Liquidité à l'AMM ? Cela fera-t-il baisser l'APR ?

**Rép. :** Les teneurs de marché maintiennent leur propre Liquidité séparée et ne percevront donc aucun APR sur les échanges réalisés via l'AMM. Seuls les LPs percevront des frais et des APRs en fournissant de la Liquidité aux pools AMM.

**Q.** Je fournis de la Liquidité sur PancakeSwap Ethereum. Dois-je faire quelque chose ?

**Rép. :** Non, vous n'avez rien à faire. Vous continuerez à percevoir les frais LP pour les échanges exécutés via l'AMM et à générer un rendement en CAKE.

**Q.** Comment devenir teneur de marché ?

**Rép. :** Nous évaluons et collaborons avec les teneurs de marché au cas par cas. Veuillez nous contacter directement ou passer par nos administrateurs si vous souhaitez travailler avec nous.
