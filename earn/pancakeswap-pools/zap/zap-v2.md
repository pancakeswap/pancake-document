---
description: Fornitura di liquidità semplice con un solo clic
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Cos'è Zap? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap consente una fornitura di liquidità semplice. Aggiungi liquidità con un solo token e un solo clic, senza Swap manuali o bilanciamento dei token.

* Aggiungere liquidità con un solo token: Puoi aggiungere liquidità usando solo un token nella coppia di trading. Zap eseguirà automaticamente degli Swap usando l'unico token che fornisci e bilancerà automaticamente la coppia di trading in un rapporto 50/50 prima di aggiungere liquidità.
* Aggiungere liquidità con un numero sbilanciato di token nella coppia di trading: Puoi aggiungere liquidità anche se il numero di token che fornisci nella coppia di trading non è perfettamente bilanciato con la pool corrente. Ad esempio 30:70, che differisce dal peso predefinito della pool di 50:50. Zap ribilancerà automaticamente i token in un rapporto 50/50 prima di aggiungere liquidità.
* Rimuovere liquidità e scegliere quale/i token ricevere: Quando rimuovi liquidità, Zap ti permette di ricevere solo un token nella coppia di trading. Zap eseguirà automaticamente degli Swap prima di restituirti i token.

### Abilitare Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Per impostazione predefinita, la funzione Zap è attivata per ogni utente. Se non vedi la nuova interfaccia Zap quando aggiungi o rimuovi liquidità, abilitala nel pannello delle impostazioni. Puoi aprire il pannello delle impostazioni cliccando l'icona dell'ingranaggio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Nota: Attualmente, la funzione Zap è in beta. Tieni presente che non supporta alcuni token, come i token con commissioni sui trasferimenti. Se riscontri problemi durante l'aggiunta o la rimozione di liquidità, disabilitala nel pannello delle impostazioni.
{% endhint %}

### Zap In (Aggiungere Liquidità) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Visita la [pagina Liquidità](https://pancakeswap.finance/liquidity) e scegli "Add Liquidity".

Seleziona la coppia di trading per cui vuoi fornire liquidità scegliendo due token di input; consulta la [guida alla Liquidità](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) per saperne di più.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Clicca il pulsante "Add Liquidity" per procedere.

Se il token nella coppia di trading per cui stai aggiungendo liquidità ha un saldo nel tuo portafoglio, la casella di controllo per quel token sarà automaticamente selezionata. Se hai entrambi i token con saldo nel tuo portafoglio, entrambe le caselle saranno selezionate.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap usando un solo token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Puoi aggiungere liquidità usando solo un token nella coppia di trading. Seleziona semplicemente solo la casella del token che vuoi usare. Zap scambierà automaticamente la metà dei token selezionati nell'altro token della coppia di trading prima di aggiungere liquidità. Vedrai un messaggio di avviso che indica quale token verrà convertito.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Se l'impatto sul prezzo è troppo alto, Zap ti proteggerà tramite il Slippage. Clicca "Reduce TOKEN" per ridurlo al limite preferito.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap usando due token con importi sbilanciati <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Se entrambi i token sono selezionati ma gli importi dei token di input non corrispondono a un rapporto 50/50, verrà introdotto il bilanciamento Zap. Vedrai un messaggio "Una parte del tuo Token A verrà convertita in Token B".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Se non vuoi che Zap bilanci il numero di token prima di aggiungere liquidità, clicca semplicemente "Don't Convert". In questo caso, Zap adeguerà il numero di token di input per corrispondere a un rapporto 50/50 invece di provare a fare Swap e ribilanciare.
{% endhint %}

### Procedere con Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Quando clicchi "Supply", verranno mostrati i dettagli dello Zap e ti verrà chiesto di confermare.

Vedrai:

1. Quanti token LP riceverai.
2. Quali sono i token di input e il numero di token che stai impegnando.
3. Come i token di input vengono scambiati per corrispondere a un rapporto 50/50.
4. La tolleranza al Slippage che stai usando.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out (Rimuovere Liquidità) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap ti permette anche di ricevere un singolo token nella coppia di trading quando rimuovi liquidità.

1. Visita la[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj_97-YuUMQjQbYbfN4)[pagina Liquidità](https://pancakeswap.finance/swap#/pool).
2. Clicca sulla coppia da cui vuoi rimuovere liquidità sotto "Your Liquidity".
3. Clicca "Remove". Apparirà un nuovo popup.

Nella sezione "You Will Receive", puoi deselezionare il token che non vuoi ricevere. Zap eseguirà automaticamente degli Swap e convertirà il 100% dei rendimenti nel token selezionato durante la rimozione della liquidità.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
