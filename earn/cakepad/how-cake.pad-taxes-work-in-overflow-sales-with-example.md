# Fonctionnement des taxes CAKE.PAD dans les ventes en sursouscription – Avec exemple

1. Les taxes ne sont prélevées **que si** l'événement CAKE.PAD **est sursouscrit**
   1. Sursouscription = Total des dépôts de tous les utilisateurs > Montant de l'objectif de levée de fonds.
   * La taxe n'est prélevée que sur les fonds excédentaires engagés par les participants. Aucuns frais ne sont payés par le projet partenaire CAKE.PAD.
   * Le projet partenaire CAKE.PAD reçoit 100 % de son montant cible de levée de fonds.
   * Les taxes CAKE.PAD sont collectées en CAKE, et 100 % en seront brûlés.
   * Les frais sont basés sur le **taux de souscription total du pool** (% de l'objectif de levée de fonds) :

**Taux de sursouscription <> Palier de frais**&#x20;

<table data-full-width="false"><thead><tr><th>Taux de sursouscription</th><th>Palier de frais</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1,00 %</td></tr><tr><td>≥ 50x</td><td>0,80 %</td></tr><tr><td>≥ 100x</td><td>0,60 %</td></tr><tr><td>≥ 150x</td><td>0,50 %</td></tr><tr><td>≥ 200x</td><td>0,40 %</td></tr><tr><td>≥ 250x</td><td>0,30 %</td></tr><tr><td>≥ 300x</td><td>0,25 %</td></tr><tr><td>≥ 400x</td><td>0,20 %</td></tr><tr><td>≥ 500x</td><td>0,15 %</td></tr><tr><td>≥ 650x</td><td>0,12 %</td></tr><tr><td>≥ 800x</td><td>0,10 %</td></tr><tr><td>≥ 1500x</td><td>0,05 %</td></tr></tbody></table>



2. **Période de temps – Quand la taxe est-elle prélevée**

* La taxe est prélevée à la **fin de l'événement CAKE.PAD**, lorsque l'utilisateur réclame son allocation.
* Même si un utilisateur s'inscrit tôt (par ex. lorsque la souscription est à 30 % de l'objectif de levée de fonds), la taxe finale est basée sur le **niveau de sursouscription final du pool**.
  * Exemple : Si le pool se retrouve sursouscrit à 50x, la taxe applicable est celle du palier 50x (0,8 %).

#### Étapes de calcul

1.  **Allocation de l'utilisateur** = % du pool total de jetons partenaires CAKE.PAD que l'utilisateur reçoit

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Montant payé par l'utilisateur** = Part du dépôt de l'utilisateur utilisée pour obtenir des jetons partenaires CAKE.PAD

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Montant du remboursement** = Excédent du dépôt de l'utilisateur non utilisé pour l'achat de jetons partenaires CAKE.PAD

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Montant de la taxe** = Déduction appliquée sur le montant remboursé à l'utilisateur

    * Le palier de frais est basé sur le % de l'objectif de levée de fonds (voir le tableau ci-dessus).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Résultat final pour l'utilisateur**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (if applicable, else = refund_amount)
    ```

#### Exemple numérique

* **Objectif de levée (raisingAmountPool) :** 100 CAKE
* **Votre dépôt (user\_deposit\_amount) :** 10 CAKE
* **Total des dépôts incluant le vôtre (totalAmountPool) :** 5 100 CAKE (51x souscrit = 5 100 % de l'objectif de levée, implique un taux de sursouscription de 50x)
  * Palier de frais correspondant = 0,80 % (d'après le tableau des taux de taxe ci-dessus)

**Étapes :**

1. `user_allocation = 10 / 5 100 = 0,00196 (allocation de 0,196 % du pool)`
2. `user_pay_amount = 100 × 0,00196 = 0,196 CAKE`
3. `refund_amount = 10 − 0,196 = 9,804 CAKE`
4. `tax_amount = 9,804 × 0,008 = 0,0784 CAKE`
5. `final_refund = 9,804 − 0,0784 = ~9,72 CAKE`

**Montants finaux reçus par l'utilisateur**

1. **Allocation en jetons :** 0,196 CAKE en valeur de jetons partenaires CAKE.PAD
2. **Remboursement final :** ~9,72 CAKE (sur un dépôt de 10 CAKE − 0,196 CAKE pour l'allocation de jetons − 0,0784 CAKE de taxe)
