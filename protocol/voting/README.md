# 📔 Gouvernance

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Dans le cadre de la [mise à jour Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), cette page a été mise à jour le 15 mai 2025
{% endhint %}

Le Vote donne une voix à la communauté PancakeSwap, lui permettant d'avoir son mot à dire sur l'avenir de PancakeSwap.

Consultez le [portail de vote natif de PancakeSwap](https://pancakeswap.finance/voting) et notre page [Forum](https://forum.pancakeswap.finance/).

## Mécanismes de Vote

:notebook\_with\_decorative\_cover:Résumé - Ce qui a changé (après la [mise à jour Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Composant de Gouvernance</th><th width="218.01953125">Avant Tokenomics 3.0</th><th width="205.1796875">Après Tokenomics 3.0</th><th>Statut<select><option value="q1dVFsCri7zA" label="✅ Changed" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Unchanged" color="blue"></option></select></th></tr></thead><tbody><tr><td>Pouvoir de vote</td><td>1 veCAKE = 1 pouvoir de vote</td><td>1 CAKE = 1 pouvoir de vote</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Délégation</td><td>Autorisée (via la mécanique veCAKE)</td><td>La délégation n'est pas autorisée</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Seuil de soumission de proposition</td><td>Snapshot : 100 K veCAKE requis</td><td>Snapshot : 100 K CAKE requis</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Propositions Core vs Community</td><td>Rôles et objectifs définis pour chaque type de proposition</td><td>Aucun changement</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Période de vote</td><td>Community : fixe<br>Core : variable</td><td>Aucun changement</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Timing du snapshot</td><td>Au bloc de publication de la proposition</td><td>Aucun changement</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Quorum</td><td>Aucun quorum minimum</td><td>Aucun changement</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr></tbody></table>

### 1. **Pouvoir de vote (Modifié)**

* **Tous les détenteurs de CAKE disposent de droits de vote directs.**
* **Le pouvoir de vote correspond directement au nombre de CAKE détenus dans l'adresse du portefeuille lors du snapshot**
  * **1 CAKE = 1 pouvoir de vote**
  * **Le CAKE staké dans les Syrup Pools ne compte pas** dans votre pouvoir de vote, car il ne fait pas partie de votre solde de portefeuille au moment du snapshot
  * Solde snapshot = Même bloc que la publication de la proposition
* **La délégation n'est plus prise en charge.** Chaque détenteur de CAKE doit voter individuellement.

### 2. **Soumission de proposition (Inchangé)**

* **Comment soumettre une proposition**
  * Soumettre sur [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Doit inclure :
    * Titre
    * Contenu
    * Description
    * Action(s) on-chain (si nécessaire)
    * Durée du vote
* Types de propositions
  1.  Propositions Core

      * Ne peuvent être proposées que par l'**équipe Core de PancakeSwap**.
      * Nécessitent un vote des détenteurs de CAKE.
      * Si adoptées, seront mises en œuvre par l'équipe PancakeSwap.

      Exemples

      1. Ajustements du protocole (modifications de produits, modifications de frais)
      2. Utilisations significatives des fonds de croissance de l'écosystème non couvertes par des propositions précédentes
  2. Propositions Community
     * Les propositions **Community** sont publiées par la communauté PancakeSwap. Elles servent à proposer des idées et à exprimer le point de vue de la communauté. Ce sont des **suggestions non contraignantes** de la communauté.
     * Toute personne disposant de **100 000 CAKE (solde snapshot)** peut soumettre une proposition.
     * L'équipe PancakeSwap peut intégrer des propositions solides dans de futures propositions Core
     * Les membres de la communauté peuvent également utiliser notre [Forum](https://forum.pancakeswap.finance/) pour fournir des retours et faire des suggestions au protocole.

### **3. Durée du vote (Inchangé)**

* Tous les détenteurs de CAKE peuvent voter **pendant la fenêtre de vote** de chaque proposition.
  * Proposition Community : fixée à 3 jours
  * Proposition Core : variable, définie par PancakeSwap
* Votre pouvoir de vote est déterminé par un **snapshot de votre solde CAKE au bloc où la proposition est publiée**.
* **Ajouter plus de CAKE après la publication de la proposition n'augmentera pas votre pouvoir de vote** pour ce vote spécifique.

Pour tous les détails, consultez le [Guide de vote](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Résultat du vote (Inchangé)**

* Le résultat est basé sur le **total des votes exprimés** (total de CAKE utilisé pour voter)
* **Il n'y a actuellement aucun quorum minimum requis** pour qu'une proposition soit adoptée.

## Note : Droits de veto

Pour protéger le protocole, l'**équipe Core de PancakeSwap se réserve le droit d'intervenir dans des situations critiques** — telles que des menaces de sécurité ou des problèmes affectant le fonctionnement stable de la plateforme — **sans nécessiter un vote communautaire ou un sondage Snapshot**.

Dans tout cas où une action de veto est prise, l'équipe Core **partagera publiquement une explication claire** de la décision.

**Les actions de veto possibles peuvent inclure :**

1. **Mettre temporairement en pause les smart contracts** pour corriger des bugs urgents ou des vulnérabilités.
