# FAQ

{% hint style="info" %}
Utilisez la barre latérale pour trouver rapidement les réponses à vos questions !
{% endhint %}

## Ordres Limit et TWAP

Veuillez consulter la FAQ fournie par Orbs :

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (Abandonné)

### Pourquoi ne puis-je pas retrouver mes ordres ?

Les ordres Limit V2 sont désormais abandonnés. Veuillez y accéder via ce lien :

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Pourquoi mon ordre n'a-t-il pas été exécuté ?

Les ordres Limit sont exécutés lorsqu'ils atteignent le prix souhaité. Cependant, en raison des fluctuations des frais de gas, le prix d'exécution réel peut légèrement différer du prix que vous avez spécifié dans l'interface. En général, le prix d'exécution et le prix souhaité devraient être presque identiques. Toutefois, si vous avez soumis un ordre particulièrement petit (\~<1 000 $), le prix d'exécution peut être légèrement plus élevé pour tenir compte des frais.

Votre ordre peut donc ne pas avoir été exécuté pour les raisons suivantes :

* Il n'a pas été possible de remplir l'intégralité de l'ordre au prix et au montant souhaités en raison de l'impact sur le prix.
* L'un des tokens de l'ordre Limit est soumis à des frais de transfert (voir ci-dessous).

**Avant de soumettre un ordre, veuillez consulter l'interface qui indique le prix d'exécution réel.**

{% hint style="info" %}
Remarque : le tableau d'historique des ordres récupère les données depuis le Subgraph et peut afficher des informations légèrement retardées.
{% endhint %}

### Puis-je soumettre un ordre Limit pour des tokens avec des frais de transfert ?

**Non.** Les tokens comportant des frais de transfert ne doivent pas être utilisés avec des ordres Limit. Procédez à vos propres risques.

### Comment définir le Glissement lors de l'utilisation des ordres Limit ?

Le Glissement n'est pas pertinent pour les ordres Limit. Vous spécifiez un montant d'entrée (ex. 1 000 CAKE) et un montant de sortie (ex. 20 BNB). Les ordres Limit garantissent que vous recevrez au moins le montant de sortie spécifié (20 BNB) pour votre montant d'entrée (1 000 CAKE) si le prix de la paire atteint le prix souhaité. **Notez que les tokens avec des frais de transfert ne doivent pas être utilisés avec des ordres Limit** (voir ci-dessus).

### Le prix d'exécution réel indique "ne s'exécute jamais". Qu'est-ce que cela signifie ?

Cela signifie essentiellement que vous essayez d'échanger un montant très faible de tokens, insuffisant pour couvrir les frais de gas. En général, vous devez augmenter le montant dans le champ "entrée" pour éliminer cette erreur.

### Y a-t-il une date d'expiration pour mes ordres Limit ?

Les ordres ouverts ont une date d'expiration de 90 jours. Passé ce délai, votre ordre pourrait ne jamais être exécuté. Veuillez annuler votre ordre une fois qu'il a expiré.

Une fonctionnalité de date d'expiration personnalisable est prévue dans un avenir proche.

### Pourquoi ne puis-je pas créer d'ordres Limit en dessous du prix du marché ?

Pour vendre en dessous du prix du marché, vous avez besoin d'**ordres Stop Limit**, et non d'ordres Limit. La fonctionnalité d'ordres Stop Limit sera disponible prochainement.

### J'ai passé un ordre et il n'apparaît pas dans le tableau des ordres ou est bloqué en statut "en attente".

L'historique des ordres provient du subgraph et peut donc afficher des informations légèrement retardées. En général, les délais ne dépassent pas quelques minutes au maximum. Veuillez consulter l'indicateur du subgraph en bas à droite du tableau d'historique des ordres.
