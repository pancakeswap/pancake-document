# Glossaire des Perpétuels V2

**Vous trouverez ici la définition de tous les termes propres au trading à terme.**

### **Trading Perpétuel**

&#x20;Les perpétuels, swaps perpétuels ou perps sont un type particulier de contrat à terme sans date d'expiration.

### **Levier**

Le Levier est un mécanisme de trading. Les traders peuvent l'utiliser pour accroître leur exposition au marché en n'ayant à payer qu'une fraction du montant total de l'investissement. En termes simples, vous empruntez des fonds pour démultiplier votre investissement.

### Ordres

**Long :** Ouvrir un ordre Long. Dans cet ordre, vous achetez un actif et attendez de le vendre lorsque le prix monte. "Acheter" et "long" sont utilisés de manière interchangeable.

**Short :** Ouvrir un ordre Short. Dans cet ordre, vous empruntez un actif, le vendez, et espérez le racheter lorsque le prix baisse. "Vendre" et "short" sont utilisés de manière interchangeable.

**Ordre Limit :** Un ordre Limit consiste à acheter ou vendre à un prix précis ou plus avantageux. Les ordres Limit ne sont pas garantis d'être exécutés.

**Ordre Market :** Un ordre Market est un ordre d'achat ou de vente au meilleur prix disponible actuellement.

#### Gestion des Positions

Les utilisateurs peuvent consulter les détails de leurs positions ouvertes, comme le prix d'ouverture, en cliquant sur "Position" en bas de la page de trading. Ils peuvent y voir des informations telles que le prix d'ouverture, le nombre de positions, le dernier prix et le prix de Liquidation forcée.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Perp5.png" alt=""><figcaption></figcaption></figure>

**Mode de position**

PancakeSwap utilise un mode de Levier isolé pour chaque paire de trading v2. Les paires fonctionnent indépendamment :&#x20;

* Chaque paire de trading est une position isolée ; les utilisateurs peuvent ouvrir plusieurs positions isolées.
* Chaque position (paire de trading) fonctionne indépendamment. Si les utilisateurs doivent compléter leur marge, ils devront le faire manuellement même s'ils disposent d'actifs disponibles dans d'autres positions séparées (ApolloX prévoit de proposer une recharge automatique à l'avenir).
* Chaque position de trading isolée aura son propre taux de risque et son propre prix de Liquidation, et sera réglée individuellement.
* Le risque de Liquidation est isolé pour chaque paire de trading. Si une position est liquidée, cela n'affecte pas les autres positions.

**Clôturer une position**

Les utilisateurs peuvent clôturer leurs positions en cliquant sur "Close Position".

#### Frais et Glissement

Veuillez consulter la [page d'Aster](https://docs.asterdex.com/product/asterex-simple/fees-and-slippage) pour plus d'informations sur les frais.
