# FAQ Monad

#### 1. Quels paliers de frais sont disponibles sur les pools de Liquidité PancakeSwap ?

**Paliers de frais pris en charge :**

* Les paliers de frais suivants sont disponibles pour les pools V3 (liquidité concentrée) : `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Pour les pools V2, seuls les pools à 0,25 % de frais sont pris en charge

#### 2. N'importe qui peut-il créer un Pool ?

Oui. La création de pools est libre et sans permission, avec quelques exceptions :

* Un seul pool peut exister pour une **combinaison de paire de tokens + palier de frais** donnée (par ex. un seul pool WMON <> USDC à 0,05 % peut exister à la fois)

#### 3. Combien de temps faut-il pour qu'un nouveau pool apparaisse ?

* Les pools apparaissent généralement dans la liste environ **5 minutes** après leur création.
* S'il n'apparaît pas :
  * Utilisez la **barre de recherche** pour le localiser manuellement.
  * Les pools peuvent être filtrés de la liste en raison d'une **TVL faible**.

#### 4. Pourquoi l'APR ou la TVL de mon pool affiche-t-il toujours zéro ?

C'est normal juste après la création d'un nouveau pool :

* Les données APR et TVL ne s'afficheront qu'une fois **qu'au moins un Swap** aura eu lieu dans le pool.
* Après un Swap, ces métriques commenceront à s'afficher dans environ **15 minutes**.

#### **5. Pourquoi mes transactions échouent-elles parfois si mon portefeuille contient moins de 10 MON ?**

Monad exige que chaque compte maintienne un **solde de sécurité minimum de 10 MON**. Si votre solde est faible et que vous envoyez trop de transactions trop rapidement, le réseau peut **cesser d'en accepter de nouvelles**.

#### **6. Pourquoi les 1 ou 2 premières transactions réussissent-elles, mais pas les suivantes ?**

Monad traite les blocs en utilisant une vue légèrement « décalée » de votre solde. Ainsi :

* Votre **première** transaction se déroule généralement bien.
* La **deuxième** peut également passer.
* Mais si vous envoyez **plusieurs transactions en peu de temps**, le réseau considère que vous n'avez peut-être pas suffisamment de MON pour couvrir tous les frais de gas.

Il **bloque** alors la transaction suivante. C'est un comportement normal qui fait partie du système de sécurité.

#### **7. Pourquoi les règles sont-elles plus strictes pour les comptes intelligents (contract wallets) ?**

Les comptes intelligents suivent des **règles plus strictes** :

* Ils doivent **toujours** conserver au moins **10 MON** pendant l'exécution du code de contrat.
* Si votre compte intelligent passe sous 10 MON, la transaction peut **échouer immédiatement**, même si les EOA fonctionnent encore pour quelques transactions.

C'est pourquoi les utilisateurs de comptes intelligents constatent des échecs plus tôt.

#### **8. Cela signifie-t-il que je ne peux pas utiliser Monad avec moins de 10 MON ?**

Vous _pouvez_ quand même l'utiliser, notamment avec un EOA classique — mais :

* N'envoyez pas plusieurs transactions les unes après les autres.
* Attendez quelques blocs entre les transactions.
* Conservez un peu de MON dans votre portefeuille pour éviter tout problème.

#### **9. Comment éviter ces échecs ?**

Conseils simples :

* Conservez **10 MON ou plus** dans votre portefeuille si possible.
* Si vous manquez de MON, **espacez vos transactions** (ne les envoyez pas en rafale).
* Les utilisateurs de comptes intelligents devraient conserver **un peu plus de 10 MON**, car les appels de contrat consomment davantage de gas.
