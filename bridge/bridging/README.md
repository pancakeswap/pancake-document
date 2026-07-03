---
description: Bridge CAKE entre Ethereum, BNB Chain, Aptos et bien d'autres
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging vers/depuis des EVMs (Nouveau site) : [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging vers/depuis Aptos (V1 Bridge) : [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## Qu'est-ce que le Bridging en crypto ?

* Le Bridging en crypto désigne le processus de transfert d'actifs entre différents réseaux blockchain.
* Il renforce l'interopérabilité, en permettant le transfert de données et d'actifs entre divers réseaux.

\
Voici quelques raisons pour lesquelles vous pourriez souhaiter effectuer un Bridge :

* Acheter différents tokens de cryptomonnaie
* Créer un NFT disponible uniquement sur un réseau spécifique
* Économiser de l'argent grâce à des transactions moins coûteuses
* Utiliser une application décentralisée disponible uniquement sur un autre réseau

***

## CAKE, un token multichain

Grâce à notre expansion et déploiement multichain, CAKE est désormais un token multichain natif de BNB Chain, mais également disponible sur Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB et Aptos.

CAKE sur l'une ou l'autre de ces blockchains est équivalent au CAKE sur BNB Smart Chain. Il peut toujours être Bridgé entre ces chaînes selon un ratio 1:1 et sans frais en CAKE.

**Veuillez noter qu'il n'existe qu'un seul CAKE.** Il n'existe pas de versions différentes de CAKE sur différentes chaînes. L'offre totale de CAKE sur toutes les blockchains est plafonnée à 400 millions, comme indiqué dans cette [proposition de vote](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5).

***

## Qu'est-ce que le PancakeSwap Bridge ?

Le PancakeSwap Bridge est un outil intégré pratique qui vous permet de déplacer des actifs entre différentes blockchains directement depuis l'interface PancakeSwap. Au lieu de visiter des sites Bridge externes, vous pouvez Bridger des tokens pris en charge entre des chaînes telles que BNB Chain, Ethereum, Base, Arbitrum, et bien d'autres — le tout depuis un seul endroit.

Le PancakeSwap Bridge est alimenté par des fournisseurs tiers de confiance et fonctionne comme un **agrégateur** — sélectionnant le meilleur itinéraire en fonction du prix, de la vitesse et de la fiabilité.

Pour apprendre à Bridger des CAKE, consultez les tutoriels et la FAQ dans les sections suivantes.

***

## 🔗 Fonctionnement

### Bridging via des agrégateurs

Le PancakeSwap Bridge agit comme une couche intelligente au-dessus de protocoles Bridge tiers de confiance. Lorsque vous initiez un transfert Bridge, PancakeSwap :

* Vérifie plusieurs Bridges intégrés pour trouver les itinéraires optimaux
* Envoie votre transaction au fournisseur sélectionné

Le Bridging est non-custodial — vos actifs ne passent pas par la garde de PancakeSwap. Les transferts sont traités directement par les fournisseurs Bridge.

### Fournisseurs Bridge pris en charge

Nous intégrons actuellement :

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Remarque : Chaque fournisseur dispose de mécanismes de Bridging, de chaînes prises en charge, de frais et de limites différents.

***

### Chaînes et tokens pris en charge

#### Chaînes actuellement prises en charge

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (Site V1)

#### Tokens disponibles pour le Bridging

Les tokens disponibles varient selon la chaîne et l'itinéraire. Les tokens pris en charge couramment incluent (sans s'y limiter) :

* CAKE
* USDT
* USDC
* ETH

***

#### Limitations et exclusions

Certains tokens peuvent ne pas être pris en charge en raison des limitations du Bridge ou de contraintes de Liquidité. Ceux-ci ont été filtrés pour offrir la meilleure expérience utilisateur possible. Par exemple :

**Pour cBridge :**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Pour deBridge :**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Ce qui précède n'est qu'un exemple. Les tokens réellement disponibles par chaîne sont affichés directement dans l'interface Bridge._

***

### 💸 Frais et coûts

#### Frais Bridge

* Facturés par le fournisseur Bridge sous-jacent
* Comprend généralement un petit montant par transfert
* Clairement affichés avant que vous ne confirmiez votre Bridge

***

#### Frais de gas

* Vous payez les frais de gas sur la **chaîne source** pour initier la transaction
* Certains fournisseurs peuvent également exiger du gas sur la **chaîne de destination**
* **Conseil :** Conservez toujours des tokens natifs (par ex. ETH, BNB) des deux côtés du Bridge

***

#### Montants minimums et restrictions

Certains itinéraires Bridge imposent :

* **Des montants minimum/maximum de Bridge** (par ex. minimum de 10 USDC)
* **Des décimales ou formats de tokens spécifiques** (par ex. uniquement les tokens ERC-20)

L'interface détectera et affichera automatiquement les transferts non valides.

***

### ⏳ Délais de transaction et suivi

#### Combien de temps dure un Bridging ?

Les transferts Bridge se complètent généralement en quelques **minutes**, selon :

* Les chaînes source et de destination
* La congestion du réseau
* L'efficacité du fournisseur Bridge

#### Suivi de votre transfert

Une fois soumis, vous pouvez consulter le statut de la transaction via les explorateurs propres à chaque fournisseur :

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Si une transaction est bloquée pendant une longue période, vérifiez l'explorateur concerné ou contactez nos administrateurs via nos [canaux sociaux](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) pour obtenir de l'[aide](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Conseils avant d'effectuer un Bridge

* **Conservez des tokens de gas sur les deux chaînes** (par ex. ETH + BNB)
* **Commencez par de petits montants** si c'est votre première fois
* Évitez les Bridges pendant les périodes de forte activité sur les chaînes (cela peut entraîner des frais de gas plus élevés)
* Confirmez la compatibilité des tokens sur les deux chaînes
* Vérifiez toujours les réseaux source et de destination

***

### Complément d'information : Adresses CAKE Omni-chain Fungible Token (OFT)

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([lien](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([lien](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([lien](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([lien](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([lien](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([lien](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([lien](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([lien](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([lien](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
