# 🎯 PancakeSwap Auto-Kursabweichung

PancakeSwap hat die automatische Kursabweichung eingeführt, um den Handel einfacher und effizienter zu gestalten. Die automatische Kursabweichung passt die Kursabweichung basierend auf den aktuellen Marktbedingungen automatisch für Sie an und hilft dabei, fehlgeschlagene Trades zu verhindern und das Verlustrisiko durch Kursabweichungsfehler zu reduzieren.

## Was ist Kursabweichung?

**Kursabweichung** tritt auf, wenn der von Ihnen erwartete Preis für einen Trade von dem Preis abweicht, zu dem der Trade tatsächlich abgeschlossen wird. Dies kann aus verschiedenen Gründen geschehen:

* Marktvolatilität – Preise können sich schnell zwischen dem Zeitpunkt der Platzierung und der Bestätigung bewegen
* Geringe Liquidität – Es stehen nicht genügend Token zu Ihrem erwarteten Preis zur Verfügung
* Blockchain-Verzögerungen – Bestätigungszeiten können dazu führen, dass sich der Preis ändert, bevor der Trade abgeschlossen wird

{% hint style="info" %}
Beispiel:

Sie versuchen, 100 CAKE gegen BNB zu tauschen, und erwarten 1 CAKE = 0,01 BNB. Aber bis Ihr Trade ausgeführt wird, hat sich der Preis geändert, und Sie erhalten nur 0,0098 BNB pro CAKE. Dieser kleine Unterschied ist das, was wir Kursabweichung nennen.
{% endhint %}

## Was ist Kursabweichungstoleranz?

**Kursabweichungstoleranz** ist die maximale Preisdifferenz, die Sie bereit sind zu akzeptieren, bevor Ihr Trade storniert wird. Wenn sich der Preis über Ihre festgelegte Toleranz hinaus bewegt, schlägt Ihre Transaktion fehl, um unerwartete Verluste zu verhindern.

{% hint style="info" %}
Beispiel:

Wenn Sie eine Kursabweichungstoleranz von 1 % festlegen und sich der Preis vor Abschluss des Trades um mehr als 1 % ändert, wird der Trade nicht durchgeführt.
{% endhint %}

## Was passiert, wenn meine Kursabweichungstoleranz zu niedrig ist?

Wenn Ihre Kursabweichungstoleranz **zu niedrig eingestellt** ist, besteht eine höhere Chance, dass Ihre Transaktion fehlschlägt – insbesondere wenn:

* Der Markt volatil ist
* Sie Token mit geringer Liquidität tauschen
* Sie Token mit Steuern oder komplexen Mechanismen verwenden

{% hint style="warning" %}
Wichtig: Auch wenn die Transaktion fehlschlägt, verbrauchen Sie weiterhin Gasgebühren für den Versuch.
{% endhint %}

## Einführung der automatischen Kursabweichung – Warum ist sie hilfreich?

Die automatische Kursabweichung passt Ihre Kursabweichung basierend auf den aktuellen Marktbedingungen automatisch an, spart Zeit und reduziert das Risiko fehlgeschlagener Trades.&#x20;

Mit der **automatischen Kursabweichung** müssen Sie Ihre Kursabweichungstoleranz nicht mehr manuell anpassen. Dies hilft dabei, häufige Probleme zu vermeiden, wie:

* **Zu niedrige Kursabweichung**, die dazu führen kann, dass Transaktionen aufgrund geringfügiger Preisänderungen während der Ausführung fehlschlagen.
* **Zu hohe Kursabweichung**, die dazu führen kann, dass Sie weniger Token als erwartet erhalten, weil Sie eine breitere Preisspanne akzeptieren.

{% hint style="info" %}
Um das beste Handelserlebnis zu gewährleisten, wurde die automatische Kursabweichung **automatisch aktiviert**. Wenn eine manuelle Kursabweichungstoleranz festgelegt wurde, wird die neue Kursabweichungseinstellung angewendet.
{% endhint %}



## Wie funktioniert die automatische Kursabweichung?

<pre class="language-html"><code class="lang-html"><strong>Automatische Kursabweichung (%) = (Gaskosten in USD / Ausgabe-Token-Wert in USD) * 100%
</strong></code></pre>

* Wenn die Gaskosten im Verhältnis zum Wert des Ausgabe-Tokens hoch sind, legt die automatische Kursabweichung eine höhere Kursabweichung fest, um sicherzustellen, dass der Trade durchgeführt wird.
* Wenn das Gas günstig und der Wert des Ausgabe-Tokens hoch ist, wird eine kleinere Kursabweichung verwendet.

Die automatische Kursabweichung wählt einen Wert zwischen **0,5 %** und **5,0 %**, abhängig von Token- und Netzwerkbedingungen.



## Ist die automatische Kursabweichung auf allen Netzwerken verfügbar?

Nein – die automatische Kursabweichung wird nur auf Layer-1-(L1-)Chains wie BNB Chain, Ethereum usw. unterstützt.

Sie wird auf Layer-2-(L2-)Chains nicht unterstützt, weil:

* Die Formel für die automatische Kursabweichung auf aussagekräftige Gaskostenwerte angewiesen ist, um eine nützliche Kursabweichungseinstellung zu berechnen
* Da L2-Gasgebühren sehr niedrig sind, würde die Anwendung der automatischen Kursabweichung auf L2s die Trade-Erfolgsraten nicht verbessern

{% hint style="success" %}
&#x20;Wenn die automatische Kursabweichung auf einem Netzwerk **nicht unterstützt** wird:

* Ihre zuvor verwendete Kursabweichungseinstellung wird angewendet
* Wenn Sie noch keine festgelegt haben, wird standardmäßig 0,5 % verwendet
{% endhint %}


