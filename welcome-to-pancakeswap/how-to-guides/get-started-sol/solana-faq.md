# FAQ Solana

### Pools V3 – Foire Aux Questions (FAQ)

#### 1. Quels paliers de frais sont disponibles ?

**Paliers de frais pris en charge :**\
Les paliers de frais suivants sont disponibles pour les pools V3 (liquidité concentrée) :

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Répartition des frais (applicable à tous les paliers) :**

* 84 % pour les fournisseurs de Liquidité (LPs)
* 16 % pour le protocole
  * 8 % sont brûlés
  * 8 % vont à la trésorerie du protocole

#### 2. N'importe qui peut-il créer un Pool ?

Oui. La création de pools est libre et sans permission, avec quelques exceptions :

* Un seul pool peut exister pour une **combinaison de paire de tokens + palier de frais** donnée (par ex. un seul pool SOL <> USDC à 0,1 % peut exister à la fois)
* Seuls les **tokens SPL** et certains **tokens Token-2022** sont pris en charge pour le moment.

#### 3. Combien de temps faut-il pour qu'un nouveau pool apparaisse ?

* Les pools apparaissent généralement dans la liste environ **5 minutes** après leur création.
* S'il n'apparaît pas :
  * Utilisez la **barre de recherche** pour le localiser manuellement.
  * Les pools peuvent être filtrés de la liste en raison d'une **TVL faible**.

#### 4. Pourquoi l'APR ou la TVL de mon pool affiche-t-il toujours zéro ?

C'est normal juste après la création d'un nouveau pool :

* Les données APR et TVL ne s'afficheront qu'une fois **qu'au moins un Swap** aura eu lieu dans le pool.
* Après un Swap, ces métriques commenceront à s'afficher dans environ **15 minutes**.

#### 5. Comment ajouter un token personnalisé pour créer un Pool ?

Pour ajouter un nouveau token :

* Dans l'interface de création de pool, ouvrez le sélecteur de tokens.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Collez l'adresse du token dans la barre de recherche.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* Cliquez sur **« Ajouter le Token »**.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* Le token sera désormais recherchable dans la liste.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* Pour gérer les tokens :
  * Cliquez sur **« Voir la liste de tokens »**.
  *   Activez ou désactivez différentes listes, y compris la **Liste de tokens ajoutés par l'utilisateur**, qui inclut tous les tokens ajoutés manuellement.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Pourquoi ma première transaction sur Solana semble-t-elle plus coûteuse ?

Solana utilise des **Comptes de Tokens Associés (ATAs)** pour gérer les soldes de tokens de chaque portefeuille. Lorsque vous interagissez avec un token pour la première fois, votre portefeuille doit créer un ATA, ce qui entraîne un coût initial unique (payé en SOL).

* Ces frais de création d'ATA sont requis par le protocole Solana et ne sont pas spécifiques à PancakeSwap.
* Si l'ATA est ultérieurement fermé, **le SOL utilisé peut être remboursé** dans votre portefeuille.
