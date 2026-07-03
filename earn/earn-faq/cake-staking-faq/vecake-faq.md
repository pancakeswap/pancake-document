---
hidden: true
---

# FAQ veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Qual è la differenza tra CAKE bloccato e veCAKE? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE è una nuova versione dello Staking CAKE a termine fisso con più benefici e potere per i detentori di CAKE bloccato. Include la Votazione del peso dei gauge, incentivi aggiuntivi, potenziamento del rendimento e altro ancora.

#### Cosa succede alle ricompense del Pool CAKE quando viene deployato il nuovo veCAKE <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

Le emissioni delle ricompense del Pool CAKE verranno dirottate per ricompensare tutti i detentori di veCAKE in base al loro saldo veCAKE rispetto alla fornitura totale.

Le ricompense CAKE e le ricompense settimanali di condivisione dei ricavi possono ora essere reclamate settimanalmente ogni giovedì.

Nota che per continuare a ricevere ricompense, gli utenti dovranno migrare al nuovo Staking veCAKE.

#### Qual è la durata massima per cui posso bloccare il mio CAKE <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

La durata massima per cui puoi bloccare il tuo CAKE è stata ora estesa a 4 anni.

#### veCAKE è un nuovo token? Può essere trasferito? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE è un numero generato in tempo reale basato sul numero di CAKE bloccati e sul tempo di blocco rimanente. Non è un token standard e non può essere trasferito.

#### Perché il mio saldo veCAKE è cambiato? Come calcolarne il saldo? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

Il saldo veCAKE diminuisce linearmente fino a 0 in base alla durata di blocco rimanente. Pertanto, avvicinandosi al tempo di sblocco, il tuo saldo diminuisce.

Il saldo veCAKE può essere calcolato con:

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### Come aumentare il mio veCAKE? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Una volta che hai una posizione veCAKE attiva, puoi aggiungere più CAKE oppure rinnovare/estendere la durata del blocco per aumentare il tuo saldo veCAKE.

#### Cosa succede quando la posizione si sblocca? Posso rinnovarla immediatamente? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Quando la posizione di Staking veCAKE si sblocca, puoi prelevare tutti i CAKE in Staking.

Per rinnovare la tua posizione, devi prelevare tutti i CAKE e impostare una nuova posizione di Staking scegliendo la quantità da bloccare e la durata del blocco.

#### Ho bloccato per 1 settimana, perché il tempo di blocco rimanente è inferiore a 1 settimana? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Quando blocchi con il nuovo veCAKE, il tempo di sblocco viene arrotondato in avanti al giovedì più vicino in orario UTC. Ad esempio, quando blocchi per 1 settimana di martedì, il tuo tempo di sblocco effettivo sarà il prossimo giovedì, che è 2 giorni dopo.

Puoi visualizzare in anteprima il tuo tempo di sblocco effettivo in basso.

#### Posso bloccare più CAKE nel Pool CAKE? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

No.

Una volta deployato veCAKE, il Pool di Staking CAKE sarà deprecato e non accetterà più alcuna estensione o deposito di CAKE.

Per bloccare CAKE e godere dei suoi benefici, vai alla pagina veCAKE.

#### Perché non riesco a migrare? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

La migrazione dal Pool CAKE a veCAKE richiede una posizione attiva. Se la tua posizione di Staking nel Pool CAKE è già sbloccata, preleva semplicemente quei CAKE e crea una posizione di Staking veCAKE nativa.

In alcuni casi, la migrazione non può essere eseguita quando il tuo tempo di blocco rimanente nel Pool CAKE è inferiore a 7 giorni. In tal caso, attendi semplicemente lo sblocco, preleva quei CAKE e crea una posizione di Staking veCAKE nativa.

#### Posso prelevare anticipatamente il mio CAKE bloccato? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

No.

Una volta bloccato, il CAKE sarà in Staking nel contratto veCAKE fino al tempo di sblocco.

#### Posso migrare parzialmente il mio CAKE? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

No.

Puoi migrare solo l'intera posizione del Pool CAKE in una volta sola.

#### Cosa succederà a iCAKE, bCAKE, vCAKE e rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Per iCAKE:**

L'IFO iCAKE è stato aggiornato per supportare veCAKE. Scopri:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Per bCAKE:**

Il potenziamento Farm bCAKE è stato aggiornato per supportare veCAKE. Scopri:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Per vCAKE:**

La Votazione vCAKE è stata aggiornata per supportare veCAKE. Scopri:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Per rCAKE:**

Tutti i detentori di veCAKE (sia nativi che migrati) verranno automaticamente iscritti al nuovo Pool di condivisione dei ricavi. Le quote dei ricavi vengono distribuite secondo il calendario esistente. Il vecchio Pool di condivisione dei ricavi verrà interrotto; gli utenti possono reclamare le ricompense in sospeso andando alla scheda benefici. Scopri:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### I portafogli multisig possono essere usati per interagire con veCAKE?

Sì

Tuttavia, nel contratto di Staking veCAKE è stato implementato un modificatore `noContract` per gli indirizzi non in whitelist. Per abilitare lo Staking o la migrazione dal Pool di Staking CAKE a termine fisso, tutti i portafogli multisig basati su contratto devono eseguire un'azione di auto-whitelisting una tantum.

Per aggiungere alla whitelist, visita una delle seguenti pagine:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Dovrebbe apparire un prompt. Clicca "Aggiungi alla whitelist" e procedi con la tx nel tuo portafoglio multisig.

Verrà inviata una tx al proprietario del veCAKE, che è un contratto con una funzione di scrittura priva di permessi per consentire a qualsiasi contratto di eseguire l'auto-whitelisting.

Se il prompt non appare, segui queste istruzioni per eseguire la tx da [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11):

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Perché ci sono più APR?

Bloccare CAKE per ottenere veCAKE offre numerosi grandi benefici nell'ambito della suite di prodotti creati da PancakeSwap. I benefici e gli incentivi arrivano in forme diverse e da fonti diverse. Pertanto esistono più APR.

Puoi guadagnarli tutti contemporaneamente, quindi l'APR combinato sarà la somma di tutti gli APR.

Nota che molti altri benefici di veCAKE non possono essere quantificati nel formato degli APR, come il [Potenziatore del rendimento Farm bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) o l'[IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). Assicurati di dare un'occhiata anche a quelli.

#### Cos'è l'APR del Pool veCAKE?

Questo è l'incentivo proveniente dalle emissioni CAKE, con il suo tasso controllato dal gauge di Votazione del Pool veCAKE.

Per aumentare le emissioni verso questo gauge, consulta [Votazione Gauges](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### Cos'è l'APR di Condivisione dei Ricavi?

Questo è l'incentivo proveniente dalla condivisione dei ricavi del protocollo, derivante dalle commissioni di Swap raccolte nei prodotti DEX.

Consulta [Condivisione dei Ricavi](/broken/pages/wQegezs7c6A2HzQjPEjh) per ulteriori informazioni.
