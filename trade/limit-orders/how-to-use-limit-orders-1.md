# Comment utiliser les Ordres Limit

Les ordres Limit générateurs de frais sur PancakeSwap fonctionnent différemment des ordres Limit traditionnels. Lorsqu'un utilisateur place un ordre Limit, il fournit en réalité une **Liquidité unilatérale** à un pool PancakeSwap Infinity.

À mesure que le prix du marché évolue, les Swaps dans le pool peuvent utiliser la Liquidité de l'utilisateur. Lorsque cela se produit, les tokens déposés sont entièrement convertis en tokens de sortie, et l'utilisateur reçoit :

* Les tokens de sortie, et
* Les frais de trading gagnés grâce aux Swaps exécutés contre sa Liquidité.

***

**Exemple : Vendre des BNB contre des USDT**

* **Prix actuel dans le pool BNB/USDT :** 600 USDT par BNB
* **Prix cible / Limit de l'utilisateur :** 700 USDT par BNB

Déroulement :

1. L'utilisateur définit un ordre Limit pour vendre des BNB à 700 USDT.
2. Ses BNB sont déposés dans le tick le plus proche du prix 700 USDT par BNB dans le pool.
3. Lorsque le prix du marché externe atteint 700 USDT, le prix du pool s'ajuste pour correspondre (grâce aux opportunités d'arbitrage / meilleure tarification).
4. À ce moment, les BNB de l'utilisateur sont échangés contre des USDT.
5. Durant ce processus, l'utilisateur gagne des frais sur chaque Swap qui consomme sa Liquidité.
6. Une fois la Liquidité entièrement consommée, les USDT convertis (plus les frais) sont automatiquement retirés et envoyés dans le Portefeuille de l'utilisateur.

***

### Guide étape par étape

Choisissez une paire de tokens (ex. BNB/CAKE) et le montant que vous souhaitez vendre / acheter.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Définissez votre prix cible / Limit.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Placez l'ordre Limit et confirmez. La Liquidité est placée en votre nom au tick le plus proche du prix Limit.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Lorsque le prix du pool atteint votre cible, votre ordre s'exécute. Les tokens de sortie souhaités + les frais sont automatiquement retirés et envoyés dans votre Portefeuille.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Statut de l'ordre

Vous pouvez consulter le statut de votre ordre en cliquant ici.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Votre ordre peut se trouver dans l'un des états suivants :**

| Statut           | Description                                                                              |
| ---------------- | ---------------------------------------------------------------------------------------- |
| En attente       | En attente que le prix atteigne votre cible                                              |
| Exécuté          | Ordre exécuté et fonds envoyés dans votre Portefeuille                                   |
| Partiellement exécuté | Seule une partie de votre ordre a été exécutée. Vous détenez les deux tokens (ex. une partie en BNB, une partie en USDT) |
| Annulé           | Vous avez annulé l'ordre. Tous vos fonds vous sont restitués.                            |

### FAQ

**Q : Dois-je payer des frais pour placer un ordre Limit ?**

R : Non. Au contraire, vous gagnez 0,1% de frais de trading lorsque votre ordre s'exécute.

**Q : Puis-je placer des ordres pour n'importe quelle paire ?**

R : Au lancement, seules certaines paires sélectionnées sont supportées. D'autres paires seront ajoutées ultérieurement.

**Q : Quelle est la taille minimale d'un ordre ?**

R : 50 $. Cela évite les ordres trop petits qui pourraient engendrer des frais de gas excessifs.&#x20;

**Q : Que se passe-t-il si seulement une partie de mon ordre est exécutée ?**

R : Vous détenez les deux tokens. Vous pouvez annuler à tout moment et retirer les deux tokens ainsi que les frais gagnés.

**Q : Mon ordre est exécuté mais je n'ai pas encore reçu les fonds dans mon Portefeuille ?**

R : Dans de très rares cas, cela peut arriver, mais vos fonds sont toujours en sécurité. Utilisez simplement le bouton "Withdraw" dans l'interface des détails de l'ordre pour réclamer les fonds manuellement.
