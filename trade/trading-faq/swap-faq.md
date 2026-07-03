# FAQ Swap

## Swap

### Quelles sont les nouveautés d'Exchange V3 ?

* Liquidité concentrée — la Liquidité sera concentrée sur la plage de prix la plus activement tradée, ce qui signifie :
  * Un Glissement de trading plus faible pour les traders
  * Des récompenses en frais LP potentiellement plus élevées pour les fournisseurs de Liquidité
* Une structure de frais de trading flexible — les fournisseurs de Liquidité peuvent choisir entre plusieurs niveaux de frais de trading lors de la création de paires de Liquidité ou de l'apport de Liquidité
* Plage de prix personnalisable — les fournisseurs de Liquidité peuvent également choisir les plages de prix sur lesquelles ils souhaitent fournir de la Liquidité
* Positions de Liquidité non fongibles — chaque position de Liquidité aura son propre identifiant unique correspondant à sa configuration (comme la plage de prix). Vous pouvez donc créer et maintenir plusieurs positions avec la même paire de trading mais avec des configurations et des montants de Liquidité différents
* Compatibilité ascendante — Exchange v3 utilisera également les paires de Liquidité legacy v2 et StableSwap pour toujours offrir le meilleur itinéraire de trading
* Ordre Limit intégré — les utilisateurs avancés peuvent utiliser la nouvelle plage de prix personnalisable dans l'apport de Liquidité pour créer efficacement un ordre Limit qui convertira tous les tokens en tokens souhaités lorsque le prix atteint la cible



### Puis-je ajouter mes propres tokens à Exchange V3 ?

N'importe qui peut créer des pools de Liquidité en déposant de la Liquidité sur V3.

Cependant, les tokens suivants ne sont actuellement **PAS** supportés :

* Tokens avec frais de transfert
* Tokens rebase

Pour ces tokens, veuillez **NE PAS** ajouter de Liquidité sur Exchange V3. Vos actifs pourraient être bloqués dans la position de Liquidité.



### **Pourquoi ma transaction ne passe-t-elle pas ?**

PancakeSwap est une application DeFi qui interagit avec le Portefeuille pour réaliser des transactions on-chain pour les Swaps, la création de LP, le Staking dans les Farms et Pools, etc.

**Frais de gas**

La première chose à vérifier est de **s'assurer d'avoir suffisamment de BNB pour payer les frais de gas** des transactions on-chain. En règle générale, les frais de gas fluctuent en fonction du nombre de transactions en attente — plus il y en a, plus les frais de gas requis peuvent être élevés pour faire passer la transaction. Sur BNB Smart Chain, les frais de gas varient généralement de quelques centimes à environ un dollar en BNB. En savoir plus sur les [frais de gas](https://academy.binance.com/en/glossary/gas).

**Frais de transaction**

Si votre action de Swap ne passe toujours pas et qu'une erreur vous demande de réviser le Glissement, il peut être utile de vérifier si les tokens que vous essayez d'échanger comportent **des frais et des restrictions sur les transactions**.

Il n'est pas rare que les tokens sur BNB Smart Chain incluent des **frais de transaction** dans leurs contrats. Ces frais sont généralement utilisés pour le burn, le financement d'une trésorerie d'un projet, ou d'autres mécanismes — par exemple, [ce token APX applique une taxe de 1% sur chaque transaction](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) envoyée à une adresse de burn, de sorte que davantage de transactions entraînent davantage de burns, créant de la valeur pour les détenteurs de tokens APX.

Avec les frais de transaction, qu'ils soient inclusifs (une partie du montant du Swap est envoyée ailleurs que votre adresse, de sorte que le montant de sortie est inférieur à celui estimé pour l'entrée) ou exclusifs (nécessitant un transfert supplémentaire depuis votre adresse pour envoyer des tokens supplémentaires, de sorte que l'entrée est supérieure à celle estimée pour la sortie), ils affectent les montants d'entrée et de sortie que vous acceptez en signant la transaction. Dans de nombreux cas, la transaction ne peut pas satisfaire aux exigences d'entrée et de sortie en raison de la taxe.

**Effectuer des Swaps avec des frais de transaction**

Avant d'échanger des tokens, assurez-vous d'avoir consulté leur site web pour comprendre s'ils appliquent un mécanisme de frais de transaction (souvent appelé _taxe_ par de nombreux projets). Si c'est le cas, veillez à définir un Glissement suffisant pour accommoder les frais de transaction — par exemple, s'il y a des frais de transaction de 5%, votre Glissement devra être d'au moins 5% plus le Glissement de trading normal selon le montant et la Liquidité du token, soit environ 5,5%-6%.

Dans certains cas extrêmes, notamment certaines arnaques, des tokens peuvent avoir un blocage sur la plupart ou la totalité des transferts on-chain, ou n'autoriser que certaines adresses à vendre. Dans ce cas, il est impossible de réaliser le Swap avec succès. Renseignez-vous sur le token que vous essayez d'échanger et restez vigilant face aux frais et restrictions !



### La nouvelle interface Swap utilise-t-elle la Liquidité v2 ou StableSwap ?

Oui. Le nouveau Swap v3 utilise la Liquidité de PancakeSwap v3, v2 et StableSwap pour obtenir le meilleur itinéraire de trading.



### Qu'est-ce que le routage fractionné ?

Dans Swap v3, votre trade peut être divisé en plusieurs itinéraires pour s'exécuter au meilleur taux.

Pour voir les détails de l'itinéraire de votre trade, appuyez sur le bouton "v" dans la section "Route" pour développer et afficher les détails.

En savoir plus [ici](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Comment personnaliser ou désactiver certaines sources de Liquidité ?

Le nouveau Swap v3 utilise la Liquidité de PancakeSwap v3, v2 et StableSwap pour obtenir le meilleur itinéraire de trading. Vous pouvez cependant personnaliser ou désactiver certaines sources de Liquidité si vous ne souhaitez pas que votre trade y soit routé.

Lors de la visualisation d'un itinéraire de trading, cliquez sur le bouton "Personnaliser le routage". Vous pouvez également cliquer sur le bouton ⚙️ en haut à droite de l'interface Swap et choisir "Personnaliser le routage".

Dans la fenêtre contextuelle "Personnaliser le routage", vous pouvez choisir les sources de Liquidité que vous souhaitez utiliser, ou désactiver complètement les routes multi-étapes.

Remarque : désactiver les routes multi-étapes peut entraîner un Glissement accru ou un taux de trading moins favorable sur certaines paires. Procédez avec prudence.

En savoir plus [ici](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Liquidité

### Que sont les niveaux de frais et comment choisir le bon ?

Dans Exchange v3, lorsque vous fournissez de la Liquidité, vous pouvez choisir entre plusieurs frais de trading différents (0,01%, 0,05%, 0,25% et 1%) pour la même paire de tokens.

Par exemple, pour CAKE-BNB, il peut exister une paire à 0,25%, ce qui signifie que des frais de trading de 0,25% s'appliquent à chaque trade. Cependant, certains fournisseurs de Liquidité pourraient choisir de fournir de la Liquidité à une paire de trading CAKE-BNB avec un taux de 0,05%, offrant une meilleure cotation et attirant plus de volume de trading.

Il n'y a pas de réponse "correcte" pour choisir la configuration des frais de trading. Cela dépend des tokens de la paire de trading. En général, les tokens volatils devraient avoir des frais de trading plus élevés pour mieux compenser la perte impermanente causée par la volatilité. En revanche, les tokens comme les stablecoins ont des mouvements de prix plus faibles et des pertes impermanentes plus faibles, donc leurs frais de trading devraient être plus bas.

Lors de la sélection d'une paire de tokens, l'interface "Ajouter de la Liquidité" choisira automatiquement le niveau de frais le plus populaire pour vous.



### Pourquoi mes deux tokens de dépôt ne sont-ils pas d'une valeur équivalente en USD ?

Dans Exchange V3, les actifs sous-jacents d'une position de Liquidité n'auront pas toujours une valeur équivalente en USD. Cela dépend des paramètres de plage de prix d'une position et du prix actuel de la paire.

En fait, si votre position sort de la plage, tous les tokens seront convertis en un seul actif. De plus, vous pouvez fournir de la Liquidité à une plage de prix qui ne couvre pas le prix actuel et déposer un seul actif uniquement. Continuez à lire pour en savoir plus ⬇️



### Que se passe-t-il si ma position de Liquidité sort de la plage ?

Vous ne gagnerez aucune récompense de frais de trading si le prix actuel sort de la plage de prix définie dans votre position.

De plus, tous les tokens seront convertis en un seul actif en fonction de la direction de la condition de prix.

Par exemple, si une position CAKE/BUSD est configurée avec une plage de prix de 3 BUSD par CAKE à 5 BUSD par CAKE. Tous les actifs de la position seront convertis en BUSD si le prix du CAKE est supérieur ou égal à 5 BUSD par CAKE, et vice versa.

Veuillez noter que si le prix revient dans la plage, vous commencerez à nouveau à recevoir des récompenses de frais de trading. Aucune action supplémentaire n'est requise.



### Est-il toujours préférable de fournir de la Liquidité sur une plage plus étroite ?

Fournir de la Liquidité sur une plage de prix plus étroite permet de concentrer votre Liquidité sur une plage de prix spécifique, augmentant votre part relative par rapport à la Liquidité totale dans la plage de prix, et potentiellement générer plus de récompenses de frais de trading.

Cependant, veuillez garder à l'esprit que seules les positions de Liquidité actives gagneront des récompenses de frais de trading. Cela signifie que vous ne gagnerez des récompenses que lorsque le prix de trading actuel est dans la plage de prix définie dans la position de Liquidité.



### Existe-t-il des moyens d'ajuster automatiquement ma position pour qu'elle soit toujours dans la plage et génère des récompenses en frais ?

PancakeSwap v3 prend en charge le dépôt de Liquidité en un clic via Zap, disponible sur BNB Chain et Ethereum.



### Quelle sera la répartition des frais de trading pour Exchange v3 ?

|                          | 0,01% | 0,05% | 0,25% | 1%  |
| ------------------------ | ----- | ----- | ----- | --- |
| Fournisseur de Liquidité | 67%   | 66%   | 68%   | 68% |
| Burn de CAKE             | 15%   | 15%   | 23%   | 23% |
| Trésorerie               | 18%   | 19%   | 9%    | 9%  |

### Les récompenses en frais LP sont-elles automatiquement composées comme dans Exchange v2 ?

Non.

Dans Exchange v3, vous devrez réclamer les récompenses de frais de trading manuellement. Vous pouvez le faire sur la page de détail de la position. Vous pouvez trouver toutes vos positions de Liquidité v3 sur la page de Liquidité.



### Quels facteurs influencent l'APR des LP ?

Dans Exchange v3, l'APR des récompenses en frais LP peut varier entre les positions de Liquidité. Il est basé sur les facteurs suivants :

* Volume de trading\
  \- un volume plus élevé génère plus de récompenses en frais
* Niveau de frais de la paire de Liquidité\
  \- un niveau de frais plus élevé génère plus de récompenses en frais par trade individuel
* Le nombre de tokens déposés\
  \- plus de tokens dans la position correspond à une part relative plus grande par rapport à la Liquidité active totale, ce qui génère plus de récompenses en frais de trading
* La plage de prix sélectionnée\
  \- une plage de prix plus petite permet une concentration plus élevée pour le même montant de tokens déposés, ce qui correspond à une part relative plus grande par rapport à la Liquidité active totale, et génère plus de récompenses en frais de trading
* La quantité de Liquidité actuellement active\
  \- si davantage d'utilisateurs déposent et concentrent leur Liquidité dans la même plage que vous, vous gagnerez moins en frais de trading en raison d'une part relative plus faible par rapport au total
* Si la position de Liquidité est active\
  \- seules les positions de Liquidité actives gagneront des récompenses en frais de trading



### Puis-je fournir de la Liquidité v2 ?

Fournir de la Liquidité v2 n'est plus conseillé. Nous recommandons d'utiliser la Liquidité v3 pour profiter des nouvelles fonctionnalités améliorant l'efficacité.

Si vous souhaitez tout de même ajouter de la Liquidité v2 :

* Si la paire de tokens n'a pas de pool v3, ou si elle a plus de Liquidité en v2 qu'en v3. Un bouton "Ajouter de la Liquidité V2" apparaîtra. Cliquez simplement dessus pour passer à l'ajout de Liquidité v2
* Vous pouvez également utiliser `/v2` dans l'URL pour toujours utiliser l'apport de Liquidité v2



### Pourquoi ne puis-je pas ajouter de Liquidité à une paire que je viens de créer ?

En raison d'un bug provenant de l'Exchange V2 legacy (présent dans tous les forks UniSwap V2), vous ne pourrez pas ajouter de Liquidité à une paire en utilisant l'interface de Liquidité PancakeSwap normale et ses appels de contrat si une paire est :

* Créée en appelant `createPair` sur FactoryV2 sans déposer de Liquidité initiale et minter les tokens LP initiaux
* Puis, l'un des tokens de la paire a été transféré manuellement dans le contrat de pool tout en appelant `sync`

{% hint style="info" %}
Récemment, une augmentation de ce type d'attaques a été observée sur PancakeSwap Exchange V2 sur BNB Chain.

Nous recommandons fortement d'utiliser notre interface pour créer la paire de trading de votre token en ajoutant la Liquidité initiale lors de la création de la paire.
{% endhint %}

Pendant que les Chefs travaillent sur une solution pour résoudre ce problème, voici un guide étape par étape pour le résoudre en utilisant BscScan :

#### Localiser l'adresse du pool et sa page BscScan

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Si votre paire est affectée, vous verrez le lien vers la page BscScan de la paire de trading/du pool dans le message d'erreur.

Vous pouvez également accéder à Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), aller dans "Read Contract", "6. getPair", entrer les adresses des deux tokens de votre paire de trading, et cliquer sur "Query". Vous devriez voir l'adresse de la paire dans le champ de retour.

#### Vérifier quel token a été déposé et transférer l'autre token dans la paire manuellement

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

À partir du champ de solde de tokens sur BscScan, vous pouvez vérifier quel token a été déposé dans le pool. Généralement, il devrait s'agir du token apparié (comme WBNB, USDT, etc.)

Une fois confirmé, vous devez transférer manuellement l'autre actif dans le contrat de pool. Vous pouvez le faire dans l'application de Portefeuille de votre choix en entrant l'adresse du pool comme destinataire.

Vous pouvez transférer n'importe quel montant, mais étant donné qu'il s'agit effectivement d'un "don" d'actifs à un pool, vous transférerez vos actifs dans une Liquidité sans minter de tokens de Liquidité. Nous recommandons donc de maintenir ce montant minimal.

{% hint style="warning" %}
IMPORTANT : Une fois que vous avez transféré le token, vous devez appeler `sync()` immédiatement sur le pool.
{% endhint %}

Vous pouvez le faire en accédant à la page BscScan de la paire de trading, en allant dans "Write Contract", "8. Sync", et en cliquant sur le bouton "Write". Vous devrez connecter votre Portefeuille avant d'effectuer la transaction.

Une fois la transaction confirmée, vous pouvez ajouter la Liquidité suivante sur l'interface PancakeSwap.

#### Que faire si je veux définir le prix de lancement ?

Vous devez ajuster le pool au prix de lancement lors du transfert du token et de la correction du pool.

Le montant à transférer peut être calculé en utilisant :

* `tokenInside` : le token déjà transféré dans le pool. Généralement, il s'agit du token apparié (comme WBNB, USDT, etc.)
* `tokenToSend` : le token sur le point d'être envoyé au pool. Généralement, il s'agit de votre token de projet
* `tokenInside.price` : le prix en USD de tokenInside
* `tokenToSend.price` : le prix en USD de tokenToSend (le prix de lancement)
* `pool` : le pool V2

Avec la formule suivante :

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Si le résultat est inférieur à 0 (cela arrive généralement lorsque le prix de lancement est très élevé. Vous devrez peut-être d'abord déposer davantage de `tokenInside` dans le pool)



### Comment gérer les LP StableSwap et les LP v2 legacy ?

Vous pouvez les gérer comme d'habitude en accédant à la page [Liquidité](https://pancakeswap.finance/liquidity).



### Pourquoi dois-je réinitialiser l'approbation de l'USDT avant d'activer/approuver ?

Lors d'opérations sur le réseau principal Ethereum, le token USDT suit une logique différente pour la gestion des approbations et des autorisations de tokens.

Par conséquent, lorsque les autorisations de dépenses sont trop faibles, il vous est demandé de réinitialiser l'approbation avant d'en définir une nouvelle.
