---
description: Einfache Liquiditätsbereitstellung mit nur einem Klick
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Was ist Zap? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap ermöglicht eine einfache Liquiditätsbereitstellung. Fügen Sie Liquidität mit nur einem Token und einem einzigen Klick hinzu, ohne manuelles Swappen oder Token-Ausbalancieren.

* Liquidität mit nur einem Token hinzufügen: Sie können Liquidität mit nur einem Token des Handelspaares hinzufügen. Zap führt automatisch Swaps mit dem von Ihnen bereitgestellten Token durch und balanciert das Handelspaar automatisch auf eine 50/50-Aufteilung aus, bevor Liquidität hinzugefügt wird.
* Liquidität mit einer unausgeglichenen Anzahl von Tokens im Handelspaar hinzufügen: Sie können Liquidität hinzufügen, auch wenn die Anzahl der von Ihnen bereitgestellten Tokens im Handelspaar nicht perfekt mit dem aktuellen Pool ausbalanciert ist. Zum Beispiel 30:70, was vom Standard-Pool-Gewicht von 50:50 abweicht. Zap balanciert die Tokens automatisch auf eine 50/50-Aufteilung aus, bevor Liquidität hinzugefügt wird.
* Liquidität entfernen und wählen, welche Token Sie erhalten möchten: Beim Entfernen von Liquidität ermöglicht Zap Ihnen, nur einen Token des Handelspaares zu erhalten. Zap führt automatisch Swaps durch, bevor Ihre Token zurückgegeben werden.

### Zap aktivieren <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Standardmäßig ist die Zap-Funktion für jeden Nutzer aktiviert. Wenn die neue Zap-Benutzeroberfläche beim Hinzufügen oder Entfernen von Liquidität nicht angezeigt wird, aktivieren Sie sie bitte im Einstellungsbereich. Den Einstellungsbereich öffnen Sie durch Klicken auf das Zahnrad-Symbol.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Hinweis: Derzeit befindet sich die Zap-Funktion in der Beta-Phase. Bitte beachten Sie, dass einige Token nicht unterstützt werden, wie z. B. Token mit Übertragungsgebühren. Falls Sie beim Hinzufügen oder Entfernen von Liquidität Probleme haben, deaktivieren Sie die Funktion bitte im Einstellungsbereich.
{% endhint %}

### Zap In (Liquidität hinzufügen) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Besuchen Sie die [Liquiditätsseite](https://pancakeswap.finance/liquidity) und wählen Sie „Add Liquidity".

Wählen Sie das Handelspaar, für das Sie Liquidität bereitstellen möchten, indem Sie zwei Eingabe-Token auswählen. Weitere Informationen finden Sie im [Liquiditätsleitfaden](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Klicken Sie auf den Button „Add Liquidity", um fortzufahren.

Wenn der Token im Handelspaar, für das Sie Liquidität hinzufügen, ein Guthaben in Ihrer Wallet hat, wird das Kontrollkästchen für diesen Token automatisch markiert. Wenn beide Tokens ein Guthaben in Ihrer Wallet haben, werden beide Kontrollkästchen markiert.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap mit einem Token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Sie können Liquidität mit nur einem Token des Handelspaares hinzufügen. Markieren Sie einfach nur das Kontrollkästchen des Tokens, den Sie verwenden möchten. Zap tauscht automatisch die Hälfte der markierten Token in den anderen Token des Handelspaares, bevor Liquidität hinzugefügt wird. Es wird eine Warnmeldung angezeigt, die angibt, welcher Token konvertiert wird.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Wenn der Preiseinfluss zu hoch ist, schützt Zap Sie durch Kursabweichung. Klicken Sie auf „Reduce TOKEN", um ihn auf das bevorzugte Limit zu reduzieren.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap mit zwei Tokens mit unausgeglichenen Beträgen <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Wenn beide Tokens markiert sind, aber die Beträge der Eingabe-Token keiner 50/50-Aufteilung entsprechen, wird Zap-Ausbalancierung eingesetzt. Es wird die Meldung „Ein Teil Ihres Token A wird in Token B konvertiert" angezeigt.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Wenn Sie nicht möchten, dass Zap die Anzahl der Tokens vor dem Hinzufügen von Liquidität ausbalanciert, klicken Sie einfach auf „Don't Convert". In diesem Fall passt Zap die Anzahl der Eingabe-Token an eine 50/50-Aufteilung an, anstatt zu versuchen, zu swappen und neu auszubalancieren.
{% endhint %}

### Mit Zap fortfahren <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Wenn Sie auf „Supply" klicken, werden die Details des Zap angezeigt und Sie werden zur Bestätigung aufgefordert.

Sie sehen:

1. Wie viele LP-Token Sie erhalten werden.
2. Was die Eingabe-Token sind und die Anzahl der Token, die Sie einsetzen.
3. Wie die Eingabe-Token gehandelt werden, um eine 50/50-Aufteilung zu erreichen.
4. Die von Ihnen verwendete Kursabweichungs-Toleranz.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap Out (Liquidität entfernen) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap ermöglicht es Ihnen auch, beim Entfernen von Liquidität einen einzigen Token des Handelspaares zu erhalten.

1. Besuchen Sie die [Liquiditätsseite](https://pancakeswap.finance/swap#/pool).
2. Klicken Sie unter „Your Liquidity" auf das Paar, aus dem Sie Liquidität entfernen möchten.
3. Klicken Sie auf „Remove". Ein neues Pop-up erscheint.

Im Abschnitt „You Will Receive" können Sie das Kontrollkästchen für den Token deaktivieren, den Sie nicht erhalten möchten. Zap konvertiert beim Entfernen von Liquidität automatisch 100 % der Rückgaben in den markierten Token.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
