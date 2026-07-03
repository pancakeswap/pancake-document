# Frais Dynamiques du Mode Degen

PancakeSwap Perpetuals Mode Degen utilise un modèle de frais dynamique. Ces frais sont conçus pour facturer des frais en fonction du PnL et protéger les utilisateurs contre les pertes.\
**Comment cela fonctionne-t-il ?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

où :

* Pnl est le profit ou la perte sur la position
* shareRate est le taux de partage, c'est-à-dire le pourcentage du notionnel payé en frais (15% par défaut)
* Notional est le montant utilisé pour ouvrir la position
* closeMinRate est le taux de frais de clôture minimum, soit le montant le plus bas que vous pouvez payer pour clôturer une position (0,03% par défaut)

\
**Exemple :**

Si vous avez une position avec un profit de 100 $, un taux de partage de 15% et un notionnel de 600 $, le taux de frais de clôture serait :

Taux de frais de clôture = Max(100 \* 15% / 600, 0,03%) = 0,03%

Dans ce cas, le taux de frais de clôture serait de 0,03%, soit le taux minimum.<br>

Remarque :

Les frais d'exécution ne sont facturés qu'à l'ouverture d'une position. Ils sont fixés à 0,3 USD (BNB Chain) / 0,2 USD (Arbitrum) / 0,01 USD (opBNB) / 0,3 USD (Base), similaires à ceux facturés lors du trading de paires perpétuelles classiques. Il n'y a pas de frais d'ouverture de position.

En cas de Liquidation, le taux de perte de Liquidation de 90% inclut les frais de clôture.
