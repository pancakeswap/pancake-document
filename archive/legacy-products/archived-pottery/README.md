# 🍯 [Archiviert] Pottery

{% hint style="danger" %}
[Archiviert] Pottery – Stand 3. November 2023
{% endhint %}

Pottery kombiniert CAKE Lock-Staking mit Lotterie-Elementen, um Ihnen die Chance auf eine höhere Rendite auf Ihre CAKE-Einzahlung zu geben! Es ist einfach und sicher, da Sie immer mindestens alle einbezahlten CAKE zurückbekommen.

## Details:

* Zahlen Sie CAKE auf der Pottery-Seite mit einem Minimum von 1 CAKE ein&#x20;
* Die Einzahlung schließt am ersten Montag jedes Monats für eine andere Pottery-Kohorte (23:59 UTC an diesem Montag) und ist ab dem Freitag davor ab ca. 10:00 UTC geöffnet, sofern keine besonderen Regelungen angekündigt wurden (die erste Pottery schloss am 8. August 2022 um 23:59 UTC)
* In der Beta-Phase des Produkts gibt es eine Obergrenze für die Gesamteinzahlung jeder Pottery-Kohorte (die maximale Einzahlungsgrenze beträgt 600.000 CAKE)
* Eingezahltes CAKE wird in den Lock-Staking-Pool geleitet und für zehn (10) Wochen gesperrt. 80 % der gesamten Staking-Belohnungen werden für die Auslosung an den Pottery-Pool gesendet, 20 % werden für Ihre Abhebung reserviert&#x20;
* Für jede Pottery-Kohorte (eine pro Monat) gibt es zehn (10) wöchentliche Auslosungen an jedem Freitag (um Mittag UTC) nach der Einzahlung, die acht (8) Gewinner pro Woche produzieren. Jede Adresse kann mehr als einen der acht Gewinner-Plätze pro Woche gewinnen \*
* Je größer Ihre Einzahlung im Verhältnis zum Gesamtpool, desto höher die Gewinnchance; Gewinner können ihren Preis direkt nach jeder Auslosung einfordern&#x20;
* Jede Pottery-Kohorte führt die Auslosung separat durch&#x20;
* Erst nach 10 Wochen ab dem Sperrdatum der Pottery-Kohorte können Sie Ihr CAKE abheben&#x20;
* Pottery verwendet Chainlinks Implementierung von VRF für echte, sichere Zufälligkeit

## Pottery-Kohorte&#x20;

Am Freitag vor dem ersten Montag jedes Monats wird eine Pottery-Kohorte geöffnet, in die Sie CAKE einzahlen und an ihr für die nächsten 10 Wochen teilnehmen können. Diese Regelung kombiniert die Einzahlung zur Weiterleitung an den gesperrten Staking-Pool, sodass der Pottery-Contract der Kohorte die Staking-Belohnungen der Einzahlung aus dem gesperrten Staking-Pool koordinieren kann.

Jedes Einzahlungs- und Sperrdatum ist eine separate Kohorte — eine für jeden Monat. Beispielsweise sind alle Einzahlungen vom 5. September 2022 in einer Kohorte, alle Einzahlungen vom 3. Oktober 2022 in einer anderen Kohorte.

Während Auslosungen möglicherweise gleichzeitig für verschiedene Kohorten stattfinden, sind die Preispools für jede Kohorte getrennt, um Fairness zu gewährleisten.

![(Nur zur Veranschaulichung; das tatsächliche Sperrdatum der ersten Pottery wurde auf den 8. August 2022 festgelegt)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

Beispielsweise gibt es am 9. September 2022 zwei separate Auslosungen: eine für die Aug-1-Kohorte als sechste wöchentliche Auslosung und eine für die Sep-5-Kohorte als erste wöchentliche Auslosung. Wenn die Aug-1-Kohorte insgesamt 100.000 CAKE einbezahlt hat und die Sep-5-Kohorte insgesamt 300.000 CAKE, stammt der wöchentliche Preis für die Aug-1-Kohorte nur aus den Staking-Belohnungen dieser 100.000 CAKE, während der wöchentliche Preis für die Sep-5-Kohorte nur aus den Staking-Belohnungen dieser 300.000 CAKE stammt. Wenn Sie nur CAKE in der Aug-1-Kohorte eingezahlt haben, haben Sie am 9. September eine Chance, den wöchentlichen Preis basierend auf den Staking-Belohnungen von 100.000 CAKE zu gewinnen. Wenn Sie CAKE sowohl in der Aug-1- als auch in der Sep-5-Kohorte eingezahlt haben, haben Sie am 9. September eine Chance, beide wöchentlichen Preise zu gewinnen.

#### Warum brauchen wir das Kohortensystem? Warum fassen wir nicht alles zusammen?

Da Pottery mit dem Fixed-Term-Staking von CAKE interagiert, kann jede Einzahlung erst nach der Sperrdauer abgehoben werden. Wenn wir alle Einzahlungen zusammenfassen möchten, während wir nach der anfänglichen Sperrung weitere Einzahlungen hinzufügen und diese ebenfalls für 10 Wochen sperren können, könnten die ursprünglichen Einzahler nicht rechtzeitig abheben.

## **Preisfinanzierung & Staking-Belohnungsverteilung**

Die Einzahlungen werden in monatliche Kohorten gruppiert für eine effizientere Verwaltung der Staking-Belohnungen, die ebenfalls für jede Kohorte zusammengefasst werden. Die Staking-Belohnungen werden zur Finanzierung des Preispools und einiger Staking-Belohnungen für die Einzahlung in die Pottery verwendet.

80 % der Staking-Belohnungen werden zur Finanzierung des Preispools für 10 wöchentliche Auslosungen verwendet, und die restlichen 20 % werden als Staking-Belohnungen reserviert, wenn Sie Ihre CAKE-Einzahlung nach 10 Wochen abheben.

Da die Staking-Belohnungen des CAKE-Lock-Staking-Pools jedoch nur nach der Sperrdauer — in diesem Fall 10 Wochen — verteilt werden, leiht sich der Contract für ein besseres Produkterlebnis und zur Ermöglichung der wöchentlichen Auslosungen direkt nach dem Einzahlungsdatum 80 % der geschätzten Gesamtstaking-Belohnungen der Kohorte aus dem CAKE-Treasury basierend auf der APR zum Zeitpunkt der Sperrung. Das geliehene CAKE wird für die Auszahlung bei jeder wöchentlichen Auslosung verwendet.

Am Ende der 10 Wochen, wenn die Belohnungen aus dem Staking-Pool verteilt werden, wird zunächst das CAKE-Treasury zurückgezahlt, dann wird der Rest zurück in den Vault geleitet, damit Nutzer es zusammen mit ihrer Anfangseinzahlung in der Kohorte abheben können.

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEF6IySHEmy1P1k5S3W_PvnFMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMZKuQ4TnNTfKRdU8s3UXO1n0Smnp8_6sAg)

Wenn beispielsweise die Pottery-Kohorte vom 1. August 2022 insgesamt 100.000 CAKE Einzahlungen angezogen hat, beträgt die geschätzte Rendite für 10 Wochen gesperrtes Staking ca. 3.674 CAKE. Der Contract leiht 80 % davon, also ca. 2.940 CAKE, für den Preispool für 10 wöchentliche Auslosungen, d. h. 294 CAKE in Gesamtpreisen für jede wöchentliche Auslosung vor Gebühren.

Es ist wichtig zu beachten, dass die Belohnungen und die APR am Ende der Laufzeit ab der Einzahlung je nach anderen Einzahlungen und deren Sperrzeiträumen im gesperrten CAKE-Pool über die 10-wöchige Dauer variieren können, wobei es kleine Abweichungen von den angegebenen Prozentsätzen geben kann (+/- 10 %).

Alle Staking-Belohnungen nach Gebühren werden den Einzahlern über den Preispool oder Belohnungen zurückgegeben. Wenn die tatsächliche APR niedriger ist als die geschätzte APR zum Zeitpunkt der Sperrung, werden mehr Belohnungen während der wöchentlichen Auslosungen an die Einzahler verteilt und weniger für den Staking-Belohnungsanteil. Wenn die tatsächliche APR höher ist als die geschätzte APR zum Zeitpunkt der Sperrung, werden weniger Belohnungen durch die wöchentlichen Auslosungen verteilt und mehr für die zur Abhebung verfügbaren Staking-Belohnungen reserviert. Letztendlich ist der Erwartungswert gleich.

## **So gewinnen Sie – Berechnung der Gewinnchancen**

Die Gewinnchancen werden basierend auf dem Anteil der Einzahlungssumme relativ zur Gesamteinzahlungsgröße der Kohorte berechnet. Vereinfacht gesagt: Je mehr CAKE Sie eingezahlt haben, desto höher die Chance, bei jeder wöchentlichen Auslosung zu gewinnen. Wenn Sie beispielsweise 10.000 CAKE eingezahlt haben und die Gesamteinzahlung der Kohorte 100.000 CAKE beträgt, haben Sie bei jeder wöchentlichen Auslosung eine 10-prozentige Gewinnchance.

Jede Adresse kann mehr als 1 der 8 Gewinner-Plätze pro Woche gewinnen.

Im Extremfall, wenn alle 100.000 CAKE der Kohorte von Ihnen eingezahlt werden, gewinnen Sie alle Preise jeder wöchentlichen Auslosung. Das bedeutet jedoch auch, dass die endgültige Rendite dieselbe ist wie wenn Sie 100.000 CAKE für 10 Wochen in den Lock-Staking-Pool einzahlen, aber Sie zahlen auch die Pottery-Gebühren.

## **Risiken — Wichtig!**

Es ist garantiert, dass Sie 100 % Ihrer Einzahlung nach 10 Wochen zurückbekommen. Sie können Ihre CAKE-Einzahlung jedoch _nur_ nach 10 Wochen Sperrung abheben, ohne jede andere Möglichkeit einer vorzeitigen Abhebung.

Durch die Teilnahme an Pottery riskieren Sie die Staking-Belohnungen zusammen mit anderen Lock-CAKE-Nutzungsmöglichkeiten wie iCAKE und vCAKE. Falls Sie bei den 10 wöchentlichen Auslosungen nichts gewonnen haben, hätten Sie 80 % der Staking-Belohnungen verloren, die Sie erhalten hätten, wenn Sie Ihr CAKE für 10 Wochen im Staking-Pool gesperrt hätten.

Bitte nehmen Sie basierend auf Ihrer Risikopräferenz teil. Sobald die CAKE eingezahlt sind, kann niemand dabei helfen, sie vorzeitig abzuheben.

## **Gebühren**

Acht Prozent (8 %) des jede Woche verteilten Preistopfs werden als Gebühren für die Verbrennung erhoben. Wir beabsichtigen, die Gebührenstruktur nach der Beta-Phase des Produkts entsprechend zu überprüfen und anzupassen.

## **Bereit zur Teilnahme?**

Wenn Sie die Produktstruktur, die Risiken und die Gebühren kennen — lesen Sie diese Seite, wie Sie [an der Pottery teilnehmen](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) können, und die anderen [Pottery-FAQ](https://docs.pancakeswap.finance/products/pottery/pottery-faq)!


