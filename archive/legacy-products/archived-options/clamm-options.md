# CLAMM Options

{% hint style="danger" %}
\[ARCHIVÉ] Options – À partir du 11 mars 2025\
Si vous avez encore de la Liquidité à retirer, veuillez le faire immédiatement en visitant https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options présente une approche novatrice du trading d'options on-chain, offrant aux fournisseurs de Liquidité une plateforme pour capitaliser sur la Liquidité v3 de PancakeSwap. Cela leur permet d'utiliser la Liquidité à la fois pour les pools de Liquidité v3 et pour vendre des options, en gagnant des frais de trading AMM standard, des primes d'options et des récompenses supplémentaires, tandis que les traders peuvent utiliser cette Liquidité pour acheter des options de style américain sur divers tokens.

Conçu par l'équipe Stryke (anciennement Dopex), le protocole CLAMM options introduit un système efficace de double fourniture de Liquidité pour les traders d'options (acheteurs) et les pools PancakeSwap v3.

Voici une présentation structurée du fonctionnement de CLAMM Options :

1. Les LPs qui ajoutent de la Liquidité aux CLAMM options contribuent simultanément au pool PancakeSwap v3 désigné dans leur plage de prix choisie.
2. Lorsqu'un trader d'options (acheteur) initie une position, la Liquidité est extraite du pool v3 pour faciliter la vente d'options. Le LP concerné devient alors un vendeur d'options et reçoit une prime.
3. La Liquidité non utilisée par les acheteurs d'options reste dans le pool PancakeSwap v3, pouvant générer des frais de trading.
4. Le rendement de la vente d'options et de la fourniture de Liquidité dans un pool v3 reflète la même perte impermanente, garantissant que les utilisateurs ne font face à aucun risque accru par rapport à la méthode conventionnelle d'ajout de Liquidité aux pools v3.
5. Les LPs font face à certains risques, car la Liquidité pourrait rester inutilisée en raison d'une demande plus faible d'achats d'options. De plus, comme la Liquidité est ajoutée au pool dans une plage inactive, elle pourrait ne pas générer de frais.

Les CLAMM options de style américain de PancakeSwap feront leur débuts sur la chaîne Arbitrum, offrant de la flexibilité avec diverses durées d'expiration allant de 1 heure à 24 heures.

| **Marchés**             | ARB/USDC, ETH/USDC et wBTC/USDC    |
| ----------------------- | ---------------------------------- |
| **Types d'options**     | Call & Put                         |
| **Prix d'exercice**     | Basés sur les ticks du pool v3     |
| **Durées d'expiration** | 1H, 2H, 6H, 12H et 24H            |

**Conditions d'exercice :** Les utilisateurs peuvent exercer des positions avant la clôture pour éviter que les options dans la monnaie expirent sans valeur. L'exercice automatique peut être activé pour réaliser les bénéfices automatiquement à l'expiration, sans actions supplémentaires.

### Guide étape par étape

Voici le guide étape par étape sur l'utilisation des CLAMM Options de PancakeSwap.

**Pour les Traders :** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Pour les LPs :** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
