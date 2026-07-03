# 🎁 Pancake Gifts

### 🎯 Qu'est-ce que Pancake Gifts ?

**Pancake Gifts** permet à quiconque d'envoyer des tokens — y compris du gaz optionnel — à des amis, utilisateurs ou communautés en utilisant simplement un **lien** ou un **code QR**. C'est une expérience simple, sécurisée et sans frais de gaz pour le destinataire.

Il est conçu pour rendre l'intégration dans la crypto aussi simple qu'envoyer un message — pas besoin de financer un portefeuille, pas de Bridging, pas de frais initiaux.

### 🤝 Pourquoi nous avons créé Pancake Gifts

L'intégration dans le Web3 est encore parsemée d'obstacles. Les nouveaux utilisateurs abandonnent souvent avant même de commencer en raison de :

* **Absence de gaz dans le portefeuille** → Impossible d'effectuer une action on-chain
* **Absence de fonds sur la bonne chaîne** → Bridging requis avant d'utiliser les dApps
* **Obligation d'acheter de la crypto pour démarrer** → Nécessite une inscription sur une Bourse Centralisée ou une rampe d'accès fiat

Pancake Gifts élimine ces obstacles en :

* ✅ **Incluant des tokens de gaz natifs** dans le cadeau pour que les destinataires puissent interagir immédiatement
* ✅ **Prenant en charge les frais de gaz à l'avance** (l'expéditeur paie un petit frais)
* ✅ **Permettant la réclamation via un simple lien ou QR** — aucune intégration complexe

Il s'agit d'un outil à la fois pour :

* Les nouveaux utilisateurs qui débutent on-chain
* Les communautés natives du Web3 souhaitant **stimuler l'adoption, récompenser les utilisateurs ou organiser des campagnes** de manière plus conviviale

***

### ⚙️ Résumé des fonctionnalités

| Fonctionnalité              | Description                                                                    |
| --------------------------- | ------------------------------------------------------------------------------ |
| **Prise en charge des chaînes** | BNB Chain (lancement initial)                                              |
| **Types de codes cadeaux**  | Lien **ou** code QR                                                            |
| **Usage unique**            | Chaque code ne peut être utilisé qu'une seule fois                             |
| **Prise en charge des tokens** | Max 2 tokens : 1 BEP-20 (requis), 1 token de gaz natif (optionnel)        |
| **Montants personnalisés**  | Définissez des valeurs différentes par token                                   |
| **Frais de gaz de réclamation** | L'expéditeur prépaye le gaz (\~0,05 $ en BNB)                             |
| **Historique des cadeaux**  | Les utilisateurs peuvent voir tous les cadeaux envoyés, leur statut et leur expiration |
| **Vérifications de sécurité** | Les tokens avec frais de transfert et logique complexe sont bloqués         |

### 🚫 Limitations

1. **Un cadeau par code** — L'envoi groupé n'est pas encore pris en charge.
2. **Les cadeaux ne peuvent pas être rétablis** — Une fois annulé ou expiré, il ne peut pas être réutilisé.
3. **Les tokens non pris en charge sont bloqués** — Les tokens avec des frais de transfert ou une logique particulière afficheront une erreur lors de la création.
4. **Les réclamations infructueuses font l'objet de nouvelles tentatives** — Le backend effectue quelques nouvelles tentatives. En cas d'échec persistant, le cadeau est marqué comme **non réclamable** et doit être annulé manuellement pour récupérer les fonds.
5. **Le cadeau doit être réclamé sur la même chaîne** — par exemple, un cadeau en ETH doit être réclamé sur Ethereum. La réclamation cross-chain n'est pas encore prise en charge.

***

### 🕒 Logique d'annulation et d'expiration

Les cadeaux suivent un cycle de vie défini en fonction du statut et du temps :

#### Annulation manuelle

* Le **créateur** peut annuler tout cadeau encore **non réclamé** et **dans la fenêtre d'expiration**.
* Les tokens (moins les frais initiaux de gaz de réclamation) seront retournés à l'expéditeur.
* Les cadeaux annulés **ne peuvent pas** être réactivés ni réutilisés.

#### Expiration automatique

* Les cadeaux **expirent automatiquement** après une période définie par l'utilisateur (par défaut : 7 jours).
* Les tokens non réclamés seront **automatiquement retournés** dans le portefeuille de l'expéditeur.
* Les cadeaux expirés sont également non réutilisables.

***

### 🔄 Statuts des cadeaux et leur signification

| Statut          | Description                                                                    |
| --------------- | ------------------------------------------------------------------------------ |
| **En attente**  | Le cadeau a été créé et attend d'être réclamé                                  |
| **Réclamé**     | Le cadeau a été réclamé avec succès par un destinataire                        |
| **Annulé**      | Le cadeau a été annulé manuellement par l'expéditeur                           |
| **Expiré**      | Le cadeau a dépassé le délai d'expiration sans être réclamé                    |
| **Non réclamable** | Nombre de tentatives dépassé ; le cadeau doit être annulé pour récupérer les fonds |

***

### ⚠️ Gestion des erreurs et cas particuliers

1. **Token non pris en charge**
   * La création du cadeau est bloquée pour les tokens avec des frais de transfert ou une logique particulière.
2. **Incompatibilité de gaz**
   * Si le **coût réel de gaz de réclamation ≥** les frais prépayés par l'expéditeur, la réclamation échoue automatiquement pour éviter un usage excessif. Une nouvelle tentative sera effectuée lorsque les niveaux de frais de gaz seront dans la fourchette.
3. **Tentatives de réclamation échouées**
   * Des nouvelles tentatives seront effectuées lors du premier échec de réclamation.
   * En cas d'échec persistant :
     * Le destinataire voit « Non réclamable »
     * L'expéditeur doit annuler manuellement le cadeau pour récupérer les fonds et le destinataire devra demander un nouveau code cadeau.
