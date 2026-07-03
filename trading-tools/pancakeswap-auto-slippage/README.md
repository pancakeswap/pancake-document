# 🎯 PancakeSwap Auto Slippage

PancakeSwap a introduit le Glissement automatique pour rendre le Trading plus simple et plus efficace. Le Glissement automatique ajuste automatiquement le Glissement en fonction des conditions actuelles du marché, contribuant ainsi à éviter les transactions échouées et à réduire le risque de pertes dues à des erreurs de Glissement.

## Qu'est-ce que le Glissement ?

Le **Glissement** survient lorsque le prix attendu d'un échange diffère du prix auquel l'échange est effectivement réalisé. Cela peut se produire pour plusieurs raisons :

* Volatilité du marché — les prix peuvent évoluer rapidement entre le moment où vous passez et confirmez votre ordre
* Faible Liquidité — il n'y a pas suffisamment de tokens disponibles au prix attendu
* Délais de la blockchain — les temps de confirmation peuvent entraîner un changement de prix avant que la transaction ne soit finalisée

{% hint style="info" %}
Exemple :

Vous essayez d'échanger 100 CAKE contre du BNB, en vous attendant à ce que 1 CAKE = 0,01 BNB. Mais au moment où votre transaction est validée, le prix a changé et vous n'obtenez que 0,0098 BNB par CAKE. Cette petite différence est ce qu'on appelle le Glissement.
{% endhint %}

## Qu'est-ce que la tolérance au Glissement ?

La **tolérance au Glissement** est la différence de prix maximale que vous acceptez avant que votre transaction soit annulée. Si le prix évolue au-delà de votre tolérance définie, votre transaction échouera afin d'éviter des pertes inattendues.

{% hint style="info" %}
Exemple :

Si vous définissez une tolérance au Glissement de 1 % et que le prix change de plus de 1 % avant la finalisation de la transaction, celle-ci ne sera pas exécutée.
{% endhint %}

## Que se passe-t-il si ma tolérance au Glissement est trop basse ?

Si votre tolérance au Glissement est **trop basse**, il y a une plus grande probabilité que votre transaction échoue — surtout lorsque :

* Le marché est volatile
* Vous échangez des tokens avec une faible Liquidité
* Vous utilisez des tokens avec des taxes ou des mécanismes complexes

{% hint style="warning" %}
Important : même si la transaction échoue, vous consommerez quand même des frais de gaz pour la tentative.
{% endhint %}

## Présentation du Glissement automatique — Pourquoi est-il utile ?

Le Glissement automatique ajuste automatiquement votre Glissement en fonction des conditions actuelles du marché, vous faisant gagner du temps et réduisant le risque de transactions échouées.&#x20;

Avec le **Glissement automatique**, il n'est pas nécessaire d'ajuster manuellement votre tolérance au Glissement. Cela permet d'éviter des problèmes courants tels que :

* **Un Glissement trop bas**, ce qui peut provoquer l'échec des transactions en raison de légères variations de prix lors de l'exécution.
* **Un Glissement trop élevé**, ce qui peut entraîner la réception de moins de tokens que prévu en acceptant une plage de prix plus large.

{% hint style="info" %}
Pour garantir la meilleure expérience de Trading, le Glissement automatique a été **activé automatiquement**. Si une tolérance au Glissement manuelle a été définie, le nouveau paramètre de Glissement sera appliqué.
{% endhint %}



## Comment fonctionne le Glissement automatique ?

<pre class="language-html"><code class="lang-html"><strong>Glissement automatique (%) = (Coût du gaz en USD / Valeur du token de sortie en USD) * 100%
</strong></code></pre>

* Si le coût du gaz est élevé par rapport à la valeur du token de sortie, le Glissement automatique définira un Glissement plus élevé pour s'assurer que la transaction est exécutée.
* Si le gaz est bon marché et que la valeur du token de sortie est importante, un Glissement plus faible sera utilisé.

Le Glissement automatique choisira une valeur comprise entre **0,5 %** et **5,0 %**, selon les conditions du token et du réseau.



## Le Glissement automatique est-il disponible sur tous les réseaux ?

Non — le Glissement automatique est uniquement pris en charge sur les chaînes de couche 1 (L1) comme BNB Chain, Ethereum, etc.

Il n'est pas pris en charge sur les chaînes de couche 2 (L2), parce que :

* La formule de Glissement automatique repose sur des valeurs significatives de coût de gaz pour calculer un paramètre de Glissement utile
* Étant donné que les frais de gaz L2 sont très bas, l'application du Glissement automatique sur les L2 n'améliorerait pas les taux de réussite des transactions

{% hint style="success" %}
&#x20;Si le Glissement automatique n'est **pas pris en charge** sur un réseau :

* Votre paramètre de Glissement précédemment utilisé sera appliqué
* Si vous n'en avez pas défini auparavant, il sera défini par défaut à 0,5 %
{% endhint %}


