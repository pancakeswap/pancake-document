# Comment utiliser le TWAP

## Qu'est-ce que le TWAP ?

Le TWAP (Time-weighted Average Price, ou Prix Moyen Pondéré dans le Temps) est un type d'ordre courant utilisé en CeFi qui décompose un ordre en trades de plus petite taille et les exécute à intervalles réguliers. L'objectif principal d'un ordre TWAP est de réduire l'impact sur le prix de l'ordre. Il peut également être utile si un utilisateur souhaite mettre en place une stratégie de Dollar Cost Averaging (DCA) et acheter un certain token de manière régulière (par exemple une fois par mois).

Par conséquent, le TWAP est plus efficace lorsque la taille de l'ordre est importante par rapport à la Liquidité disponible, ou lorsqu'un utilisateur anticipe une période de forte volatilité des prix sans tendance haussière ou baissière claire.

## Comment configurer un ordre TWAP ?

1. Rendez-vous sur la page Swap et sélectionnez l'option d'ordre TWAP en cliquant sur TWAP.
2. Sélectionnez les tokens "De" et "Vers" et saisissez le montant que vous souhaitez échanger.
3. L'interface permet à la fois des ordres dTWAP-market, qui exécutent tous les trades au prix du marché disponible, et des ordres dTWAP-limit, qui n'exécutent les trades individuels que s'ils se situent dans la limite de prix définie par l'utilisateur. \
   Dans cet exemple, nous avons choisi d'exécuter les ordres TWAP au prix du marché.
4. Ensuite, nous spécifions les paramètres TWAP. Il existe 3 paramètres principaux qui contrôlent l'efficacité de l'ordre dTWAP :
   1. Total des trades : Permet à l'utilisateur de spécifier le nombre de trades individuels en lesquels son ordre sera décomposé. Le curseur de l'interface commence à 1 trade et permet d'augmenter le nombre de trades individuels, ou l'utilisateur peut saisir manuellement le total dans le champ de saisie.\
      Les utilisateurs doivent noter qu'il existe un certain compromis dans la définition de ce paramètre : plus de trades signifie une taille de trade individuelle plus petite, ce qui signifie un impact plus faible sur le prix. Cependant, plus de trades signifie également plus de transactions et des frais de gas globaux plus élevés.&#x20;
   2. Intervalle de trade : Définit l'intervalle de temps entre chaque trade individuel. L'interface commence par le minimum autorisé (2 minutes), ce qui laisse un minimum de temps pour la guerre d'enchères des takers et le règlement des blocs entre chaque partie. L'utilisateur peut le définir sur n'importe quelle durée souhaitée. Un trade ne s'exécutera jamais avant que ce délai ne soit écoulé après le trade précédent.\
      Les utilisateurs doivent également faire preuve de prudence lors de la définition de ce paramètre : des intervalles plus longs permettraient aux arbitrageurs de disposer d'une fenêtre plus longue pour corriger les écarts de prix sur les pools concernés et ramener les réserves à l'équilibre (au niveau du prix spot). Cependant, cela prendrait plus de temps pour que l'ordre soit exécuté et ajouterait de l'incertitude au prix d'exécution final, surtout en période de forte volatilité.
   3. Durée maximale : La durée maximale pendant laquelle l'ensemble des trades individuels constituant l'ordre dTWAP complet peuvent être exécutés. Passé ce délai, le trade expire, quel que soit le montant réellement échangé.\
      Notez que toutes les parties peuvent ne pas s'exécuter dans les ordres Limit, selon que le prix reste dans les paramètres définis. \
      La durée recommandée par défaut est calculée en multipliant le nombre d'intervalles par l'intervalle de trade, puis en doublant ce montant afin de servir de marge de sécurité pour permettre suffisamment de temps pour l'activité on-chain (notez que définir une durée inférieure à la valeur par défaut peut entraîner un ordre partiellement exécuté).

Comme on peut le voir, ces paramètres offrent une grande flexibilité pour personnaliser chaque ordre, en tenant compte de facteurs tels que les conditions du marché, les frais de gas actuels, etc.

8. Cliquez sur "Place order". Vérifiez les détails de votre ordre, acceptez l'avertissement et cliquez sur "Confirm order".
9. Une fois la transaction traitée, vous pourrez consulter le statut de votre ordre dans la section d'historique des ordres, sous "Open orders".
10. Les ordres ouverts peuvent être annulés à tout moment en développant l'ordre et en cliquant sur le bouton "Cancel Order".

Points à prendre en compte :

* Les ordres sont exécutés en trades plus petits sur une période de temps déterminée et sont soumis aux conditions du marché et à d'autres risques.
* Votre trade peut être exécuté à un prix significativement différent du prix actuel du marché (même si celui-ci ne sera pas inférieur à votre prix Limit, si vous en avez défini un), ce qui pourrait entraîner des pertes significatives. Si le prix du marché disponible est inférieur au prix Limit que vous avez défini, certains trades de votre ordre pourraient ne pas être exécutés, ce qui entraînerait un ordre partiellement exécuté.
* Les trades sont basés sur un protocole décentralisé qui utilise des takers off-chain qui se font concurrence pour exécuter les ordres. Ces takers sont autorisés à demander des frais, que le protocole déduit des tokens de sortie pour le taker gagnant.&#x20;
* Les takers peuvent prendre en compte les frais de gas pour vos transactions lors de la définition de leurs frais, ce qui peut entraîner des fluctuations dans les montants de frais.

<br>
