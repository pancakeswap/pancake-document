# Agent de Référence — Agent de Settlement d'Ordres/Intents

> Un agent Provider ERC-8183 qui traite un seul Job swap-intent à la fois en le routant via l'agrégation PancakeSwap et en livrant directement le token cible au Client.

### 0. Correspondance avec ERC-8183

ERC-8183 (Agentic Commerce ; Virtuals + Ethereum Foundation) définit un **Job** avec trois rôles et les états Open → Funded → Submitted → Terminal. Le **BNBAgent SDK** de BNB est l'implémentation en production.

| Rôle                                                       | Dans cet agent                                                                                                                          |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **Client** (Agent-A)                                       | publie un swap intent : « swap X du token A → token B, me livrer ≥ `minOut` », séquestre l'input + un pourboire                        |
| **Provider** (Agent-B) — **c'est notre agent de référence** | obtient un devis via **l'agrégation PancakeSwap**, et s'il peut atteindre/dépasser `minOut`, exécute le swap et livre le token B au Client |
| **Evaluator**                                              | vérifie que le Client a reçu un montant de token-B ≥ `minOut` ; libère le pourboire (ou rembourse le Client)                           |

Le livrable est objectif (« le Client a-t-il reçu ≥ `minOut` ? »), ce qui explique précisément pourquoi ce cas s'adapte à ERC-8183 contrairement au rebalancer.

***

### 1. Objectif et périmètre en une ligne

> Un agent **Provider** qui traite un seul Job swap-intent à la fois en le routant via l'agrégation PancakeSwap et en livrant directement le token cible au Client — et rien d'autre.

***

### 2. Ce que l'agent est AUTORISÉ à faire (liste d'autorisation des capacités)

| # | Capacité                    | Surface                                                       | Notes                                                                           |
| - | --------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| A | Découvrir les Jobs ouverts  | BNBAgent SDK (registre ERC-8183)                              | Lecture seule ; filtrer les Jobs swap-intent qu'il peut traiter                 |
| B | Obtenir un devis de route   | **Agrégation PancakeSwap** (Aggregator API / Smart Router)    | Lecture seule ; meilleur prix sur V3                                            |
| C | Accepter un Job             | BNBAgent SDK (Funded → committed)                             | Uniquement si le devis récent ≥ `minOut` et le pourboire ≥ seuil minimal        |
| D | Exécuter le swap            | Router PancakeSwap                                            | Input tiré du séquestre du Job ; **destinataire de l'output = le Client**, en une tx |
| E | Soumettre le livrable       | BNBAgent SDK (→ Submitted)                                    | Le hash de la tx de settlement comme preuve                                     |
| F | Réclamer le pourboire       | Séquestre ERC-8183 / x402                                     | Uniquement après que l'Evaluator marque le Job Terminal                         |

**L'output de chaque settlement va directement au Client. Le seul revenu de l'agent est le pourboire du Job.**

***

### 3. Garde-fous stricts (condition pour être mis en avant)

| Garde-fou                                     | Règle                                                                                                                                                                   |
| --------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ne jamais accepter ce qu'il ne peut pas remplir** | Accepter un Job uniquement si un devis _récent_ dépasse `minOut`. Dans le cas contraire, laisser le Job Funded pour un autre Provider.                            |
| **Redevis à l'exécution**                     | Redevis immédiatement avant le settlement ; abandonner si la route ne dépasse plus `minOut` (pas de devis périmés).                                                    |
| **Settlement atomique**                       | Pull-from-escrow → swap → livraison au Client en **une seule transaction**, destinataire de l'output = Client. L'agent ne doit jamais détenir les fonds du Client entre des étapes échouées. |
| **Glissement**                                | Glissement d'exécution borné ; le montant livré doit rester ≥ `minOut` après glissement, ou la tx est annulée. Jamais `amountOutMin = 0`.                             |
| **Deadline**                                  | Deadline courte sur la tx de settlement (≤ 5 min) ; respecter la deadline propre du Job.                                                                              |
| **Pourboire minimum / valeur maximum**        | Ne pas accepter de Jobs sous un seuil de pourboire ou au-delà d'un plafond de valeur par Job.                                                                         |
| **Liste blanche de tokens**                   | Ne traiter que les Jobs dont les tokens figurent sur la liste de tokens PancakeSwap (anti-honeypot / faux tokens).                                                     |
| **Concurrence mono-Job (v1)**                 | Traiter un Job à la fois ; pas de sur-engagement.                                                                                                                      |
| **Précondition gaz**                          | Confirmer qu'il y a suffisamment de BNB pour le settlement complet avant d'accepter.                                                                                   |
| **Idempotence**                               | Ne jamais soumettre en double ou re-traiter un Job déjà Submitted/Terminal.                                                                                            |

Si une règle ne peut être respectée, **passer le Job** — ne jamais forcer un settlement.

***

### 4. Hors périmètre — l'agent NE DOIT PAS

1. **Utiliser les fonds du Client à d'autres fins que le swap spécifié.** Le destinataire de l'output est toujours le Client.
2. **Avancer son propre inventaire / prendre un risque de capital.** La v1 est **uniquement escrow-pull** — elle route l'input séquestré du Client ; elle ne remplit pas depuis son propre solde.
3. **Router via des contrats non-PancakeSwap ou non vérifiés**, ou régler en dehors de l'agrégation PancakeSwap.
4. **Traiter des Jobs avec des tokens non présents sur la liste blanche**, ou (v1) tout token à UI graduée / RWA (§5).
5. **Utiliser le levier, les perps, la marge ou le lending.**
6. **Soumettre un livrable qu'il n'a pas réellement rempli** (pas de fausse attestation) ou **évaluer ses propres Jobs** (conflit d'intérêts).
7. **Appeler toute fonction owner/admin** sur PancakeSwap ou les contrats ERC-8183.
8. **Conserver des autorisations de tokens permanentes** au-delà d'un settlement unique ; limiter les autorisations au montant du Job.

***

### 5. Logique spécifique à PancakeSwap (exactitude applicative)

* **Router via l'agrégation PancakeSwap**, pas un seul pool — la meilleure exécution sur V2 / V3 / Stable est toute la proposition de valeur (« le meilleur prix remporte le pourboire »).
* **Livrer atomiquement au Client** en définissant le `recipient` du router sur l'adresse du Client ; jamais un « swap vers soi-même, puis transfert » en deux étapes.
* **Fraîcheur du devis** — le prix on-chain évolue entre la découverte et le settlement ; redevis à l'exécution (garde-fou §3).
* **`minOut` est en unités brutes.** Pour les **tokens à UI graduée / ERC-8056** (Binance Stock Tokens / RWA equities), brut ≠ affiché ; une mauvaise gestion livre silencieusement un montant incorrect. **Exclure les tokens à UI graduée de v1** jusqu'à ce que l'ingénierie confirme la gestion des unités brutes de bout en bout.
* **Le glissement minimum** sur le swap de settlement doit être calculé de sorte que le montant _livré_ ≥ `minOut`, en tenant compte de la répartition pourboire/frais.

***

### 6. Comportement en cas d'échec et de récupération

* **Le devis échoue à `minOut` lors de l'exécution** → abandonner avant/atomiquement avec le pull du séquestre ; le Job reste Funded pour un autre Provider. Pas d'état partiel.
* **Déjà Submitted/Terminal** → passer (idempotence).
* **La tx de settlement est annulée** → le Job reste réclamable par d'autres ; l'agent enregistre l'échec et continue.
* **Échecs répétés sur un Job** → mettre ce Job en liste noire localement et alerter, plutôt que de boucler sur les tentatives.

***

### 7. Points d'intégration (la partie BNB / ERC-8183)

Ces éléments sont fournis par BNB Agent Studio / BNBAgent SDK, non construits par PancakeSwap — mais la spécification en dépend :

* **Cycle de vie du Job** (découvrir Open → accepter Funded → Submitted → réclamer) via BNBAgent SDK.
* **Identité du Provider** via ERC-8004.
* **Séquestre + paiement** via le séquestre ERC-8183 / x402.
* **Evaluator** — le prédicat doit être « le solde token-B du Client a augmenté de ≥ `minOut` ». Confirmer avec BNB **qui gère l'Evaluator** (neutre/protocole vs. Client) et que le prédicat est applicable on-chain.

***

### 8. Posture recommandée v1 et décisions ouvertes

1. **Escrow-pull uniquement, un seul Job à la fois, uniquement tokens liste blanche, pas de tokens à UI graduée.** Surface la plus petite et la plus sûre pour être mis en avant au lancement.
2. **Confirmer l'interface de swap PancakeSwap** — l'**API HTTP Aggregator (`aggr`)** vs le **Smart Router SDK**. La note de Jerry indique « utiliser pcs aggr api » ; il faut confirmer ce que l'agent appelle, car cela change l'intégration (et si le guide nécessite une section d'agrégation).
3. **Confirmer le mécanisme de séquestre** avec BNB — le Provider peut-il tirer l'input séquestré du Client pour router le swap, et la livraison au Client est-elle applicable comme livrable ?
4. **Confirmer le propriétaire de l'Evaluator et le prédicat** (§7).

> Validation ingénierie avant mise en avant : routing escrow-pull → swap → livraison au Client atomique ; redevis à l'exécution ; calcul `minOut`-après-glissement ; application de la liste blanche ; gestion idempotente des Jobs.
