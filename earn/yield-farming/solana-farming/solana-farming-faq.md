# FAQ sur le Farming Solana

### 1. Comment fonctionne le Farming SOL ?

* Le Farming V3 est **basé sur des campagnes**, ce qui signifie que les Farms sont actives uniquement pendant une durée déterminée.
* Pendant la campagne :
  * Les jetons de récompense sont distribués **chaque seconde** aux **positions de Liquidité actives**.
  * L'APR de farming sera affiché sur la page de liste des pools et la page de mes positions
* Une fois la campagne terminée :
  1. **Plus aucune récompense** ne sera distribuée.
  2. **L'APR de farming ne sera plus affiché** sur la page de liste des pools et la page de mes positions
  3. La Farm devient **inactive**, mais peut être redémarrée par le créateur en ajoutant davantage de récompenses.

### 2. Dois-je staker mon NFT LP pour gagner des récompenses de farming ?

* **Aucun staking n'est requis**.
* Tant que votre position de Liquidité est **active (dans la plage)** dans un pool avec une Farm active, vous gagnerez des récompenses automatiquement.

### 3. Existe-t-il des amplificateurs de Farm ?

* **Non**, les Farms V3 ne **prennent pas en charge** de mécanismes d'amplification.
* Les récompenses sont uniquement basées sur votre part de Liquidité active dans le pool.

### 4. Peut-on créer plusieurs Farms pour le même pool ?

* **Non**, il ne peut exister qu'**une seule Farm par paire de jetons et palier de frais**.

### 5. Comment sont configurées les Farms SOL ?

#### A. Jetons de récompense

* Jusqu'à **3 jetons de récompense différents** peuvent être assignés par Farm.
* Une fois définis, les types de jetons de récompense **ne peuvent pas être modifiés**.
* Le créateur de la Farm peut :
  * **Recharger** les jetons de récompense alloués.
  * **Prolonger la durée de farming** après la fin de la campagne.

#### B. Durée de la campagne

* Les campagnes doivent durer au minimum **7 jours** et au maximum **90 jours**.

### 6. Une Farm peut-elle être modifiée après sa création ?

Les créateurs de Farm peuvent modifier les paramètres suivants **après la création de la Farm** :

1. Taux de distribution des récompenses (par seconde)
2. Date de fin de la campagne
3. Ajouter un jeton de récompense et le montant de récompense correspondant (uniquement si moins de 3 jetons ont été initialement assignés)
