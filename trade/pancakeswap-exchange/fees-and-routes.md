# Commissioni e Percorsi

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

In Exchange V3, per impostazione predefinita, PancakeSwap Smart Router utilizzerà la liquidità da V3, V2, StableSwap (BNB Chain), e l'AMM e i market maker (BNB Chain & Ethereum), per eseguire gli scambi e trovare il miglior prezzo per i trader.

Tuttavia, gli utenti possono sempre personalizzare il proprio scambio scegliendo quali fonti di liquidità il router dovrà utilizzare, e abilitare o disabilitare i multihop e il routing diviso.

### **Controlla il tasso e l'importo della commissione attualmente applicati**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Per verificare quanto ti verrà addebitato sul tuo Swap corrente, controlla la sezione "Commissione" nei dettagli dello swap.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

Per verificare il tipo di pool e il livello di commissione attraverso cui viene instradato il tuo scambio, controlla la sezione "Percorso".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Per maggiori dettagli, clicca sull'icona della lente di ingrandimento per visualizzare il percorso di trading completo.



### **Personalizza le fonti di liquidità**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

In cima all'interfaccia "Personalizza il Routing", puoi scegliere quale fonte di liquidità il router dovrà usare durante il routing del tuo scambio. Per aprire questa interfaccia, puoi:

* Cliccare "Personalizza il Routing" in fondo alla visualizzazione del percorso di trading.
* Cliccare l'icona dell'ingranaggio nell'interfaccia di swap, e poi cliccare "Personalizza il Routing" in fondo.

Per impostazione predefinita, tutte le fonti di liquidità sono abilitate e Smart Router sfrutterà al massimo tutta la liquidità disponibile all'interno di PancakeSwap.

Tieni presente che il router NON instraderà gli scambi tra i pool di liquidità AMM e i market maker MM. Quando il tuo scambio viene eseguito dai market maker MM, non passerà attraverso alcun pool di liquidità AMM.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Puoi cliccare il pulsante "Ripristina" in alto a destra per reimpostare le configurazioni ai valori predefiniti.



### **Personalizza le preferenze di routing**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

In fondo all'interfaccia "Personalizza il Routing", puoi personalizzare le tue preferenze di routing abilitando o disabilitando i multihop e il routing diviso.

I multihop consentono ai token di essere scambiati attraverso più passaggi tra diversi pool di liquidità per ottenere il miglior risultato. Disattivarli limiterà gli scambi agli swap diretti, il che potrebbe causare uno Slippage più elevato o persino la perdita di fondi.

Il routing diviso consente di suddividere gli swap di token in più percorsi per ottenere il miglior risultato. Disattivarlo limiterà l'esecuzione degli scambi a un singolo percorso, il che potrebbe comportare una minore efficienza o uno Slippage più elevato.

{% hint style="warning" %}
Quando il tuo scambio non può essere eseguito a causa di una configurazione di trading personalizzata, apparirà un avviso: puoi cliccare "Controlla le impostazioni" per aprire rapidamente l'interfaccia "Personalizza il Routing". Oppure scegli "Ripristina predefinito" per reimpostare rapidamente le tue configurazioni ai valori di default.
{% endhint %}
