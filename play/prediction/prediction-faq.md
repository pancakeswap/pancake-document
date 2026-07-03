# FAQ Prediction

{% hint style="info" %}
Utilisez la barre latérale pour trouver rapidement les réponses à vos questions !
{% endhint %}

## A) Questions générales

### **1. Quels sont les frais ?**

3 % du pot total de chaque tour seront versés au Trésor, dont 100 % seront utilisés pour racheter et brûler du CAKE.

### 2. Comment le paiement est-il calculé ?

* Ratio de paiement pour le pool À LA HAUSSE = Valeur totale des deux pools ÷ Valeur du pool À LA HAUSSE
* Ratio de paiement pour le pool À LA BAISSE = Valeur totale des deux pools ÷ Valeur du pool À LA BAISSE

**Exemple — Mise de 2 BNB « À LA BAISSE », résultat = « À LA BAISSE » :**

* Côté À LA BAISSE = 15 BNB, pot total = 150 BNB&#x20;
* Ratio de paiement À LA BAISSE = 150 BNB / 15 BNB = 10x
* Montant du paiement = Ratio de paiement × Position × (1 - Frais de Trésor)
  * Si vous misez 2 BNB À LA BAISSE, paiement = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Bénéfice = 19,4 − 2 = 17,4 BNB

### 3. Y a-t-il un délai avant de pouvoir récupérer mes gains ?

Non, vous pourrez récupérer vos gains à tout moment dans le futur.

### 4. Quelle est l'adresse du contrat de PancakeSwap Prediction ?

**BNB Chain**

* **BNBUSD** : [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD** : [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD** : [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Positions et résultats

### 1. **Puis-je modifier ou annuler ma position ?**

Non. Une fois que vous avez pris position, vous NE POUVEZ PAS changer la direction, ajouter à, ou retirer votre position. Elle est verrouillée, assurez-vous donc d'être entièrement satisfait de la direction de votre position avant de confirmer.&#x20;

### 2. Dans quels cas les marchés sont-ils annulés ? Que se passe-t-il alors ?

* **Quand :** Défaillance de l'Oracle ou du service backend, ou autres circonstances imprévues.
* **Résultat :** Les utilisateurs peuvent réclamer 100 % de leur mise initiale (sans frais).

### 3. Le résultat du tour a changé après la fin du tour ! Pourquoi ?

Parfois, après la clôture d'un tour, le résultat final peut différer du dernier résultat affiché pendant le tour en direct. Si vous observez qu'un tour se termine sur « À LA BAISSE », il peut sembler basculer vers « À LA HAUSSE » quelques secondes plus tard.

C'est parce que nous utilisons le flux de prix de l'Oracle pour déterminer le résultat final d'un tour. La période entre la fin d'un tour et le début du suivant est de 30 secondes, mais l'Oracle se rafraîchit toutes les 20 secondes. Il est possible que pendant cette courte période, l'Oracle envoie une mise à jour alors que la transaction déclenchant le tour suivant est en cours de validation. Cela peut sembler « inverser » le résultat du tour précédent.

### 4. Que sont le Prix verrouillé et le Prix de clôture ?

* **Prix verrouillé :** Prix au début de la phase EN DIRECT.
* **Prix de clôture :** Prix à la fin du tour, utilisé pour déterminer les gagnants.

**Exemple — Tour 400 (Prédiction BNB) :**

1. **12h00–12h05 :** Placement de la mise → L'utilisateur mise 0,1 BNB sur « À LA HAUSSE »
2. **12h05–12h10 :** Phase de verrouillage → Prix verrouillé = 850 $
3. **12h10 :** Phase de clôture → Prix de clôture = 860 $
4. **Résultat :** La mise « À LA HAUSSE » gagne

**Remarques :**

* Le prix de l'Oracle peut prendre jusqu'à 20 secondes pour se mettre à jour.
* Victoire de la maison : Toutes les mises vont à la maison

### 5. Quelles situations sont considérées comme une VICTOIRE DE LA MAISON ?

**Scénarios :**

1. Aucune mise opposée n'existe et l'utilisateur perd (par exemple, un seul utilisateur mise À LA HAUSSE et le résultat = À LA BAISSE)
2. Prix verrouillé = Prix de clôture

**Ce qui se passe :**

* PancakeSwap prend 100 % du pool ; tous les fonds sont utilisés pour brûler du CAKE.
* Les utilisateurs des deux côtés perdent leur mise initiale.

**Exemple — Aucune mise opposée :**

* L'utilisateur A mise À LA HAUSSE, aucune mise À LA BAISSE n'existe, résultat = À LA BAISSE → L'utilisateur A perd ; 100 % des fonds vont au Trésor.
* L'utilisateur B mise À LA HAUSSE, aucune mise À LA BAISSE n'existe, résultat = À LA HAUSSE → L'utilisateur B récupère 97 % de son dépôt.



## C) Pauses des marchés

### 1. Que signifie la mise en pause des marchés ?

Les marchés sont mis en pause lorsque des conditions affectent la fiabilité du contrat. La mise en pause des marchés signifie qu'aucune mise ne sera acceptée pour aucun tour.

### 2. Qu'est-ce qui provoque la pause du marché de Prédiction de PancakeSwap ?

Le marché de Prédiction se met en pause dans les conditions suivantes :

1. Le contrat de Prédiction n'a pas pu obtenir le prix de l'Oracle ChainLink en raison de l'absence de publication du prix par l'Oracle au moment où le tour s'est terminé.
2. Le contrat de Prédiction n'a pas pu exécuter une action (terminer un tour ou obtenir un prix de l'Oracle) en raison d'une transaction bloquée dans le mempool pendant plus de 15 blocs.
3. PancakeSwap a décidé d'interrompre la Prédiction pour ce marché / actif.

### 3. Que se passe-t-il avec ma position si le marché est mis en pause ?

Si les marchés sont mis en pause alors que vous avez une position active, vos fonds seront disponibles pour réclamation, de la même manière que vous réclameriez normalement vos gains.

Pour récupérer vos fonds, vous devrez payer des frais de gaz. Nous ne pouvons pas vous compenser pour les frais de gaz, veuillez donc tenir compte de ce risque mineur avant de participer.

### 4. Quand les marchés reprendront-ils après une pause ?

Les marchés reprendront lorsqu'un administrateur (l'un des chefs) reprendra manuellement le marché.



## D) Résolution de problèmes et réclamations

### 1. Comment réclamer mes anciens gains du marché CAKEUSD sur BNB Chain ?&#x20;

* Rendez-vous sur [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Consultez l'onglet historique pour les gains des tours précédents

### 2. Pourquoi ne puis-je pas voir mes gains dans mon portefeuille ?

Lorsque vous réclamez des gains, ils peuvent ne pas apparaître dans les journaux de transactions de votre portefeuille comme d'habitude.\
C'est parce qu'ils utilisent un type de transaction différent : les transactions internes.\
Entrez l'adresse de votre portefeuille sur BscScan, puis vérifiez l'onglet « Txns internes » pour confirmer leur arrivée.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Pourquoi les résultats de mon tour ne s'affichent-ils pas ?

Il y a un tampon de 15 blocs pour chaque tour, ce qui peut entraîner des délais allant jusqu'à 45 secondes après la fin d'un tour.\
Ce tampon compense le fait que nous ne pouvons pas toujours récupérer un prix et terminer un tour immédiatement : divers facteurs de la blockchain affectent la vitesse à laquelle les transactions sont confirmées sur le réseau.

### 4. Je ne peux pas récupérer mes gains, que dois-je faire ?

Assurez-vous d'avoir suffisamment de BNB dans votre portefeuille pour payer les frais de gaz. Vous aurez besoin d'un peu de BNB pour déclencher le contrat intelligent.

### **5. Que faire si je ne peux pas réclamer mes gains depuis le site web ?**

Vous pourrez peut-être réclamer vos gains directement depuis le contrat. Suivez les étapes des 3 onglets ci-dessous.

{% tabs %}
{% tab title="Check rounds you played" %}
Comment consulter l'historique des tours auxquels vous avez participé

1. Accédez à la page BscScan du [contrat de Prédiction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (par ex. BNBUSD).
2. Faites défiler jusqu'à « 8. getUserRounds ».
3. Saisissez l'adresse de votre portefeuille sous « user(address) ».
4. Définissez « cursor(uint256) » sur 0 et « size(uint256) » sur 1000.
5. Appuyez sur « Query »
6. Les tours auxquels vous avez participé s'afficheront ci-dessous dans la première ligne. (après « uint256\[]: »)
{% endtab %}

{% tab title="Check if you can claim" %}
Vérifiez d'abord si vous devriez réellement pouvoir réclamer pour le tour auquel vous avez participé.

1. Accédez à la page BscScan du [contrat de Prédiction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (par ex. BNBUSD), et accédez à l'onglet Read
2. Faites défiler jusqu'à « 4. claimable ».
3. Saisissez l'identifiant du tour que vous souhaitez vérifier sous « epoch(uint256) ».
4. Saisissez l'adresse de votre portefeuille sous « user(address) ».
5. Appuyez sur « Query »
6. Si un tour est réclamable, il affichera « true ».
7. Si le résultat est « false ». Veuillez répéter les étapes ci-dessus et essayer avec « 19. refundable ».&#x20;
8. Remarque : ⬆️ Si vous voyez qu'un tour retourne « false » à la fois pour « 4. claimable » et « 19. refundable », mais qu'il s'affiche sur le site web, il a probablement déjà été réclamé et le site web accuse un retard.
{% endtab %}

{% tab title="Claim from a round" %}
Comment réclamer

1. Accédez à la page BscScan du [contrat de Prédiction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (par ex. BNBUSD), et accédez à l'onglet Write
2. Appuyez sur « 🔴 Connect to Web3 »
3. Utilisez MetaMask ou WalletConnect pour vous connecter.
4. Faites défiler jusqu'à « 3. claim »
5.  Saisissez le numéro du tour que vous souhaitez réclamer dans ce format, en incluant les crochets \[] : `[12345]`&#x20;

    Si vous souhaitez réclamer plusieurs tours à la fois, séparez les tours par une virgule comme ceci : `[12345,12346,12347]`
6. Appuyez sur « Write »
7. Confirmez dans le portefeuille&#x20;
{% endtab %}
{% endtabs %}
