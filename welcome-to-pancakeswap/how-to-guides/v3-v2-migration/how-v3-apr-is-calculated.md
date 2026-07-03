# Comment l'APR v3 est calculé

{% hint style="info" %}
Dans les Farms et la Liquidité v3, grâce à la Liquidité non fongible et à la possibilité de personnaliser la plage de prix, chaque position LP dispose de son propre APR de frais LP et d'APR de Yield Farming CAKE.
{% endhint %}

L'APR total est la combinaison de l'APR des frais LP et de l'APR de récompense CAKE.

### Frais LP

En théorie, pour une plage de prix et une Liquidité données que l'utilisateur s'apprête à ajouter, on peut estimer les frais attendus sur les 7 prochains jours de la manière suivante :

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Montant des frais accumulés dans la plage de prix spécifiée par l'utilisateur au cours des 7 derniers jours
* $$L_{in}$$ : Liquidité actuelle dans la plage de prix spécifiée par l'utilisateur
* $$\Delta{L}$$ : Liquidité que l'utilisateur souhaite ajouter à la plage de prix

#### Frais dans la plage

Pour $$fee_{in}$$, nous utilisons les données historiques de volume de trading, le palier de frais et les données historiques de prix pour estimer le prix dans la plage :

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$ : Palier de frais
* $$V_{7d}$$ : Volume total de trading des 7 derniers jours
* $$T_{in}$$ : Durée, en secondes, pendant laquelle les prix sont restés dans la plage de prix au cours des 7 derniers jours
* $$T_{7d}$$ : 7 jours exprimés en secondes

### APR CAKE

#### Allocation du Pool

La récompense CAKE totale par seconde dans MC v3 utilise un mécanisme de mise à jour (upkeep) et peut être dérivée via `latestPeriodCakePerSecond` :

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

Pour chaque Pool, on peut utiliser `poolInfo` pour obtenir le `poolWeight` en divisant `poolInfo.allocPoint / totalAllocPoint`.

#### APR CAKE global

L'APR global est calculé en utilisant le montant total de Liquidité active et stakée du Pool avec les émissions de récompenses CAKE du Pool.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` représente la Liquidité active et stakée actuelle du Pool en USD, composée par tous les ticks de position dans la plage stakés dans MasterChef v3.

#### APR CAKE par position

Les APR des positions individuelles peuvent varier en fonction de leurs paramètres de plage de prix.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$ : Récompenses CAKE gagnées en USD par an dans le Pool
* $$USD_p$$ : Valeur totale en USD de la position
* $$L_{p}$$ : Liquidité de la position
* $$L_{lm}$$ : Liquidité totale de Staking suivie par le LMPool
