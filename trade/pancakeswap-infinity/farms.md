# Farms

Le farming sur PancakeSwap Infinity est une méthode simple et économe en gas permettant aux utilisateurs de gagner des récompenses de Liquidité sans avoir besoin de staker leurs LP Tokens. Une fois de la Liquidité ajoutée à un pool éligible, les récompenses commencent à s'accumuler automatiquement.

#### ⚙️ Comment ça fonctionne

Voici un aperçu rapide de la façon dont le système suit et distribue les récompenses :<br>

**✅ Pas de Staking requis**

* Il vous suffit de conserver votre position LP dans votre portefeuille.
* Nul besoin de bloquer vos actifs ni d'interagir avec des contrats intelligents supplémentaires.
* Vous commencez à gagner des récompenses automatiquement lorsque vous ajoutez de la Liquidité.

#### 📈 Distribution des Récompenses

* Seules les positions in-range (celles fournissant une Liquidité active) reçoivent des récompenses.
* Les récompenses sont proportionnelles aux frais générés par votre position au cours de chaque période, appelée epoch.

#### ⏳ Qu'est-ce qu'une Epoch ?

* Une epoch est une fenêtre temporelle fixe — actuellement définie à 8 heures.
* Les récompenses sont calculées et distribuées après chaque epoch.
* Les epochs sont actuellement planifiées à 00:00, 08:00 et 16:00 UTC.

***

#### 🔄 Processus de Farming et de Réclamation

1. **Suivi des positions :** Le système back-end surveille vos positions LP sur tous les Farms.
2. **Calcul des récompenses :** À la fin de chaque epoch,
   1. Le système calcule vos récompenses en fonction de votre Liquidité et des frais générés.
   2. Il traite les récompenses dans un arbre de Merkle et soumet une racine de Merkle à un contrat intelligent.
3. **Période de contestation :**
   1. Après la publication de la racine de Merkle, une période de contestation d'1 heure commence.
   2. Pendant la période de contestation :
      1. Les récompenses nouvellement calculées ne peuvent pas être réclamées.
      2. Les récompenses des epochs précédentes restent disponibles à la réclamation.
      3. Des outils de vérification automatisés et communautaires vérifient l'exactitude des données publiées. En cas d'anomalies détectées, une contestation peut être soulevée pour prévenir des distributions incorrectes.
4. **Réclamation des récompenses :**
   1. Une fois la période de contestation terminée, vous pouvez réclamer vos récompenses pour la dernière epoch.
   2. Toutes les récompenses en attente sur tous les Farms peuvent être réclamées en une seule transaction économe en gas.
5. **Report des récompenses non réclamées :**
   1. Toutes les récompenses non réclamées sont reportées aux epochs suivantes. Chaque mise à jour intègre les récompenses précédentes, garantissant qu'aucun gain n'est perdu ou expiré.

{% hint style="info" %}
Des plages de Liquidité plus étroites conduisent généralement à des gains plus élevés, mais augmentent la probabilité qu'une position sorte de la plage et devienne inéligible aux récompenses.
{% endhint %}

#### 🌱 Résumé

✅ Pas de Staking\
✅ Réclamation économe en gas\
✅ Mises à jour régulières des récompenses\
✅ Processus de contestation équitable et transparent\
✅ Les récompenses s'accumulent jusqu'à ce que vous soyez prêt à les réclamer
