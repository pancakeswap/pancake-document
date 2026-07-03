# FAQ Pancake Gifts

Cette FAQ couvre le fonctionnement de Pancake Gifts en coulisses, ce qui se passe dans différents scénarios, et les raisons de certains choix de conception.

***

## 1. 🔐 Comportement du code cadeau et accès

### **1.1 Pourquoi le code cadeau n'est-il pas stocké ?**

Nous **ne stockons intentionnellement pas** le code cadeau dans :

* Le stockage local du frontend
* Les bases de données du backend

Cela protège :

* La confidentialité des utilisateurs
* La sécurité contre la compromission des appareils
* Les réclamations accidentelles ou malveillantes de cadeaux

### **1.2 Puis-je régénérer ou récupérer le code cadeau ultérieurement ?**

Non. Le code cadeau :

* N'est affiché **qu'une seule fois** lors de la création
* Est intégré dans le **lien** ou le **code QR** généré
* **Ne sera plus affiché** dans l'interface ou dans l'historique

{% hint style="warning" %}
Si le code est perdu et que vous n'avez pas sauvegardé le lien ou le QR, le cadeau ne peut pas être réclamé manuellement. Pour récupérer le montant de votre cadeau, vous pouvez l'annuler manuellement.
{% endhint %}

### **1.3 Le code cadeau sera-t-il toujours intégré dans le lien de partage ou le QR ?**

Oui :

* Le lien de partage inclut le code cadeau (ex. `pancakeswap.finance/gift#code=xxxx`)
* Le code QR intègre également le code cadeau, mais **ne peut pas être régénéré ultérieurement.**&#x20;

{% hint style="success" %}
**Conseil :** Téléchargez l'image une fois qu'elle est générée
{% endhint %}

* Les réclamations manuelles nécessitent le code cadeau réel — aucune alternative si le lien/QR est perdu

## 2. 🎁 Statut et expiration du cadeau

### **2.1 Puis-je voir si un cadeau a été réclamé, annulé ou expiré ?**

Oui. La section **Historique des cadeaux** affiche :

* Statut : En attente / Réclamé / Annulé / Expiré / Non réclamable
* Détails du cadeau (token, montant, type, chaîne, horodatages)

### **2.2 Que se passe-t-il lorsqu'un cadeau expire ?**

Si un cadeau n'est pas réclamé dans la **fenêtre par défaut de 7 jours** :

* Le **montant total du cadeau est remboursé** dans le portefeuille du créateur
* Les **frais fixes de gaz de réclamation (\~0,05 $) ne sont pas remboursés**

## 3. 🧠 Logique de réclamation et limitations

### **3.1 Les utilisateurs peuvent-ils réclamer un cadeau sur une chaîne différente de celle sur laquelle il a été créé ?**

Non. Un cadeau est **lié à une chaîne** :

* Un cadeau créé sur **BSC** doit être réclamé sur **BSC**
* Les cadeaux cross-chain ne sont pas encore pris en charge

## 4. ⛽ Frais de gaz et conception

### **4.1 Comment le montant fixe de gaz pour la création du cadeau est-il déterminé ?**

Nous fixons un prix de gaz forfaitaire basé sur les conditions actuelles de BNB Chain (\~5 fois le montant de gaz recommandé actuel).

Cette marge :

* Protège contre les pics soudains de gaz
* Garantit que les cadeaux restent réclamables dans des conditions de volatilité normale

\
Exemple

* **Recommandation actuelle : 0,1 Gwei** (voir : [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Donc, frais de gaz de réclamation fixes = 0,1 Gwei x 5 = 0,5 Gwei**


