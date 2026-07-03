# FAQs

1. **En quoi Infinity diffère-t-il de PancakeSwap V3 ?**\
   Infinity ajoute de nouvelles fonctionnalités telles que des hooks programmables, davantage de [types de pools](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (comme LBAMM et CLAMM), ainsi que des économies de gas. Cependant, les mécanismes fondamentaux de Swap et de fourniture de Liquidité sont globalement similaires à ceux de v3, à quelques différences mineures près dans les pools LBAMM pour la fourniture de Liquidité.\
   <br>
2.  **Quelle est la différence entre LBAMM et CLAMM ?**

    1. **LBAMM (Liquidity Book AMM) :** Utilise des bins de Liquidité, chacun contenant de la Liquidité à différents niveaux de prix. Les LPs peuvent fournir de la Liquidité sur plusieurs bins ; les Swaps sont exécutés à un seul niveau de prix au sein d'un bin.
    2. **CLAMM (Concentrated Liquidity AMM) :** Permet aux utilisateurs de fournir de la Liquidité dans des plages de prix personnalisées, comme dans PancakeSwap V3.

    \
    Pour plus de détails, rendez-vous [ici](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **Comment puis-je réclamer mes récompenses de Farm, et pourquoi est-ce limité à toutes les 8 heures ?**\
   Vous pouvez réclamer vos récompenses de Farm depuis vos positions de Liquidité en cliquant sur le bouton « Harvest ». Infinity permet une réclamation groupée sur toutes les positions de Farm actives, ce qui permet d'économiser des frais de gas. Les récompenses sont calculées et traitées toutes les 8 heures afin d'optimiser les coûts de gas et les calculs. \
   \
   Pour plus de détails sur le mécanisme de farming, rendez-vous [ici](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **Comment fonctionnent les hooks Infinity ?**\
    Les hooks sont des extensions de contrat intelligent personnalisables qui ajoutent des fonctionnalités supplémentaires à un pool. Ils peuvent déclencher des actions supplémentaires lors de Swaps ou d'événements de Liquidité — par exemple, ajuster les frais, offrir des réductions ou appliquer d'autres logiques.<br>

    Les hooks sont attachés à un pool lors de sa création. Dans la plupart des cas, **les utilisateurs n'ont pas besoin d'effectuer d'étapes supplémentaires**. Tant que vous effectuez des Swaps ou fournissez de la Liquidité comme d'habitude, vous bénéficierez automatiquement de la logique du hook si elle s'applique à ce pool.<br>

    👉 **Vous pouvez consulter les hooks actifs et leurs détails sur la page de chaque pool dans la section « Fonctionnalités du Pool ».**\
    <br>
5.  **Pourquoi n'ai-je reçu aucun frais lors du retrait de ma position d'un pool LBAMM ?**\
    Dans les pools LBAMM (Liquidity Book AMM), les frais sont automatiquement ajoutés à vos bins de Liquidité actifs. Cela signifie :

    1. Lorsque vous retirez votre position, vos frais gagnés sont inclus dans les montants totaux de tokens que vous retirez.
    2. Contrairement aux AMMs traditionnels, il n'existe pas de solde de « frais à collecter » séparé — tout est intégré dans la valeur de votre position.

    \
    Si vous n'avez pas constaté de tokens supplémentaires lors du retrait, cela pourrait être dû au fait que :

    1. Votre position a peut-être subi une perte impermanente supérieure aux frais collectés en raison des mouvements de prix pendant la durée de votre position.
    2. Votre Liquidité ne se trouvait pas dans des bins actifs où des échanges ont eu lieu.
