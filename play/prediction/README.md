# 🔮 Prediction

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction est un marché de Prédiction décentralisé, amusant et simple.

> **Prédisez si le prix du BNB, du BTC ou de l'ETH va monter ou baisser — prédisez correctement pour gagner !**

### Plateformes

Vous pouvez jouer à PancakeSwap Prediction sur :

* **Bureau / dApp** : [Guide PancakeSwap Prediction](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Mini application Telegram (BNBUSD uniquement)** : [Bot de Prédiction](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Résumé : Comment ça fonctionne

1. **Choisissez un actif sur lequel parier** : Actuellement disponible sur **BNB Chain**, **zkSync Era** et **Arbitrum One**.
2. **Choisissez À LA HAUSSE ou À LA BAISSE** : Prédisez si le prix de l'actif sera plus élevé ou plus bas lorsque la phase « EN DIRECT » se termine (chaque tour = 5 minutes).
3. Placez votre montant de mise : Tout montant en BNB
4. **Verrouillez votre position** : Une fois placée, votre mise ne peut pas être modifiée.
5. **Victoire ou défaite** :
   * Si vous avez choisi **À LA HAUSSE**, vous gagnez si le _Prix de clôture_ > _Prix verrouillé_ à la fin du tour.
   * Si vous avez choisi **À LA BAISSE**, vous gagnez si le _Prix de clôture_ < _Prix verrouillé_ à la fin du tour.

### Mécanique et frais

* **Chaînes prises en charge : BNB Chain, zkSync Era, Arbitrum One**
* **Fréquence des tours** : Toutes les **5 minutes** (tours continus).
* **Frais de participation** : **3 %** du pot total de chaque tour, dont une partie est destinée aux **rachats de CAKE**.
* **Gains** : Réclamables à tout moment après la finalisation des résultats.
* **Les paiements** sont basés sur le ratio des mises dans chaque pool :
  * Ratio de paiement (Pool À LA HAUSSE) = _(Valeur totale des deux pools ÷ Valeur du pool À LA HAUSSE)_
  * Ratio de paiement (Pool À LA BAISSE) = _(Valeur totale des deux pools ÷ Valeur du pool À LA BAISSE)_
  * Voir la [FAQ](prediction-faq.md) pour un exemple détaillé

### Résultats possibles

* **Victoire :** Vous partagez le pot total avec les autres gagnants (moins 3 % de frais)
* **Défaite :** Vous perdez la totalité de votre mise

**Cas particuliers** :

* **Égalité** (Prix verrouillé = Prix de clôture) : La maison remporte toutes les mises.
* S'il n'y a pas de mises opposées :
  * Si vous gagnez : récupérez 97 % de votre mise initiale (3 % de frais s'appliquent).
  * Si vous perdez : votre mise complète revient à la maison.
* **Annulation :** par exemple en cas de défaillance de l'Oracle, les utilisateurs sont remboursés de leur mise initiale

### Flux de prix (Oracles)

| Chaîne    | Marchés                                  | Objectif                                                                | Oracle                     |
| --------- | ---------------------------------------- | ----------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (pausé) | Définit le _Prix verrouillé_ et le _Prix de clôture_ (mis à jour \~ toutes les 20 secondes). | **Chainlink**              |
| BNB Chain | Tous                                     | Alimente le graphique en temps réel dans l'interface (à titre indicatif uniquement). | Flux Binance / TradingView |

#### **Oracle ChainLink**

* Utilisé pour le prix de verrouillage et le prix de fin de chaque tour du marché de Prédiction. Mise à jour à intervalles de 20 secondes au maximum.
* Notre contrat de Prédiction utilise le flux de prix de l'Oracle ChainLink sur BNB Chain pour définir les prix qui déterminent si un utilisateur a gagné ou non.
* Utilisé pour le graphique « Chainlink » dans l'interface.

#### **Binance**

* Utilisé pour les mises à jour de prix en temps réel sur l'interface du marché de Prédiction de PancakeSwap.
* Utilisé pour le graphique « TradingView » dans l'interface.

Étant donné que nous utilisons deux flux de prix différents, les mises à jour de prix en temps réel de Binance et le prix de l'Oracle ChainLink peuvent différer légèrement. Toutefois, ils ne devraient pas varier de manière significative.

### Adresses des contrats

BNB Chain :

* **BNBUSD** : [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD** : [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD** : [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
