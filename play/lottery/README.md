# 🎟️ Lottery

Participer à la Lottery de PancakeSwap vous donne la chance de remporter d'importants lots en CAKE ! C'est simple, équitable, et vous pouvez y participer aussi souvent que vous le souhaitez, à condition d'avoir suffisamment de CAKE pour acheter un ticket.

[Voir le contrat intelligent](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Détails :**

* Coût d'un ticket de Lottery : \~5 USD en CAKE.
* Limite de participation individuelle : aucune limite globale, mais seulement 100 tickets peuvent être achetés à la fois.
* L'achat d'un ticket attribue à l'utilisateur une combinaison aléatoire de 6 chiffres compris entre 0 et 9, par exemple « 1-9-3-2-0-4 ». Les numéros doivent correspondre en partant de la gauche pour gagner des prix — plus le nombre de chiffres correspondants est élevé, plus la part du lot à remporter est importante.
* La Lottery utilise l'implémentation VRF de Chainlink pour garantir une véritable aléatoire sécurisée.

## Coût des tickets et réduction pour achat groupé

Les prix des tickets de Lottery sont fixés au début de chaque nouveau tour et visent 5 USD (des variations légères peuvent survenir en cas de fluctuations soudaines des prix).

L'achat de plusieurs tickets à la fois donne droit à une réduction sur l'achat groupé. Vous pouvez acheter jusqu'à 100 tickets en une seule transaction ; la réduction commence modestement à partir de 2 tickets et atteint 10 % pour 100 tickets.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%20PM.png)

## **Comment gagner**

Faites correspondre les numéros **en partant du côté gauche de votre ticket** avec les numéros gagnants tirés à la fin d'un tour de Lottery.

* Même le simple fait de faire correspondre le premier numéro vous vaut un petit prix.&#x20;
* Plus vous faites correspondre de numéros, plus vous remportez une part d'un lot important.

## **‌**Conditions d'éligibilité aux prix

‌Chaque ticket comporte six boules de loterie, numérotées de 0 à 9. Pour gagner, vos numéros doivent correspondre aux numéros tirés dans le même ordre que les boules, en commençant par la gauche du ticket. Par exemple :

Numéros tirés

![Drawn Numbers](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png)

Les numéros de votre ticket

![Your Ticket A](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png)

Dans l'exemple ci-dessus, le Ticket A présente cinq numéros qui correspondent aux numéros tirés dans le même ordre exact : tous sauf le quatrième.

Cependant, comme le quatrième chiffre ne **correspond pas** au numéro tiré, seuls les trois premiers chiffres sont comptés comme correspondants dans l'ordre. Cela donne droit au prix « Correspondance des 3 premiers ».

![Your Ticket B](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png)

Exemple du Ticket B. En voici un malchanceux. Même si les cinq derniers chiffres correspondent, le premier ne correspond pas ; ce ticket ne gagne donc rien du tout.

Vous ne partagez les prix que de la tranche la plus élevée pour laquelle vous êtes éligible. Un ticket correspondant aux trois premiers numéros n'est éligible qu'aux prix de la tranche de trois correspondances, et non à celles d'une ou deux correspondances.

**Rappel : les chiffres doivent correspondre dans l'ordre, de gauche à droite.**

## Partage des prix entre les tranches

‌Après le tirage d'un tour et la détermination des tickets gagnants, les prix sont attribués. Le montant remporté par chaque ticket dépend du nombre d'autres tickets gagnants dans la même tranche de prix.

‌Par exemple, si vous êtes le seul à avoir fait correspondre trois numéros dans l'ordre et que la part prédéterminée du lot pour votre tranche est de 2 000 CAKE, vous recevrez la totalité des 2 000 CAKE.

‌En revanche, si vous et trois autres personnes faites correspondre trois numéros dans l'ordre, les 2 000 CAKE seront partagés entre les quatre tickets gagnants, ce qui signifie que vous recevrez 500 CAKE.

Consultez la [FAQ de la Lottery pour une répartition des prix](lottery-faq.md#how-are-prizes-broken-down-between-brackets) selon chaque tranche.
