---
description: >-
  Sappiamo che potresti avere domande sul nostro ultimo aggiornamento. Abbiamo
  compilato questa FAQ completa per rispondere a tutte le tue domande. Iniziamo:
---

# FAQ PancakeSwap Infinity

**D1 In che modo PancakeSwap Infinity avvantaggia trader e fornitori di Liquidità?**

**Risp:** PancakeSwap Infinity porta numerosi vantaggi sia per i trader che per i fornitori di Liquidità:

**1. Operazioni semplificate e risparmio gas:** Grazie a funzionalità come Singleton e Flash Accounting, PancakeSwap Infinity riduce drasticamente le commissioni gas. Singleton consolida tutti i pool in un unico contratto, abbattendo i costi di deployment del 99%. Flash Accounting ottimizza i processi contabili calcolando i saldi netti per le transazioni, riducendo al minimo il consumo di gas.

**2. Benefici diretti dalle funzionalità avanzate:** L'integrazione degli Hooks consente di implementare commissioni dinamiche, tipi di ordine personalizzati e moduli di gestione attiva della Liquidità. I fornitori di Liquidità possono godere di una perdita impermanente (IL) mitigata, protezione MEV e accesso a vari livelli di commissioni, garantendo esperienze di trading più redditizie e sicure.

\
**3. Flessibilità nei design AMM:** PancakeSwap Infinity supporta più tipi di pool, tra cui CLAMM e LBAMM, consentendo a trader e LP di scegliere tra diversi tipi di pool. Questo approccio inclusivo consente anche il supporto di qualsiasi asset futuro che richieda nuove curve di prezzo. Consulta questo blog per [saperne di più](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2016.16.56.png" alt=""><figcaption></figcaption></figure>

**D2** In che modo PancakeSwap Infinity avvantaggia sviluppatori e protocolli DeFi?

**Risp:** PancakeSwap Infinity apre un mondo di possibilità per sviluppatori e protocolli DeFi.

**1. Infinite possibilità di personalizzazione:** Con PancakeSwap Infinity, gli sviluppatori possono costruire Hooks per introdurre funzionalità personalizzate; dalle commissioni dinamiche agli ordini limite on-chain e agli oracoli personalizzati. PancakeSwap Infinity supporta il deployment di nuovi tipi di pool (CLAMM, LBAMM e qualsiasi altro tipo di pool in futuro), migliorando l'efficienza del capitale e la flessibilità del trading.

**2. Accesso a Liquidità robusta e base utenti:** Con oltre 1,8 milioni di utenti attivi e 2,1 miliardi di dollari in Liquidità, sviluppatori e protocolli DeFi hanno un'opportunità senza precedenti di attingere a una vasta comunità attiva, favorendo lo sviluppo e l'adozione dei prodotti.

**3. Opportunità di generazione di entrate:** Gli sviluppatori possono stabilire un flusso di entrate costante attraverso le commissioni degli Hooks, consentendo loro di impostare commissioni per l'utilizzo dei propri Hooks. Monetizzando le loro innovazioni con commissioni, gli sviluppatori possono contribuire alla crescita e allo sviluppo dell'ecosistema PancakeSwap. Consulta questo blog per [saperne di più](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2009.40.42.png" alt=""><figcaption></figcaption></figure>

**D3** Quali miglioramenti porta PancakeSwap Infinity rispetto a v3?

**Risp:** PancakeSwap Infinity introduce la capacità di migliorare le funzionalità dei Pool di Liquidità con caratteristiche personalizzate senza reimplementare il protocollo principale. Supporta anche l'implementazione di qualsiasi curva di prezzo al volo e offre sostanziali risparmi gas per gli utenti.

**D4** Ci saranno cambiamenti all'interfaccia utente o all'esperienza utente in PancakeSwap Infinity?

**Risp:** Gli utenti possono fare Swap su Infinity attraverso la pagina di Swap di PancakeSwap, proprio come la solita esperienza familiare. Trader e fornitori di Liquidità hanno più opzioni per aggiungere Liquidità tra i tipi di pool supportati, inclusi CLAMM e LBAMM.

**D5** Come può la community partecipare al testing o fornire feedback per PancakeSwap Infinity?

**Risp:** Se sei un membro della community, sentiti libero di condividere il tuo feedback attraverso i nostri social su [Telegram](https://t.me/PancakeSwapAnn), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) e [Twitter](https://twitter.com/PancakeSwap). Se sei uno sviluppatore, unisciti alla nostra community Discord degli sviluppatori e condividi i tuoi pensieri.

**D6** Dove possono trovare gli utenti ulteriori informazioni su PancakeSwap Infinity e tenersi aggiornati sui progressi del suo sviluppo?

**Risp:** Visita il nostro [sito ufficiale](https://pancakeswap.finance/v4?utm_source=v4announcementblog\&utm_medium=blog\&utm_campaign=v4announcementblog\&utm_id=v4announcementblog), leggi il nostro [whitepaper](https://github.com/pancakeswap/pancake-v4-core/blob/main/docs/whitepaper-en.pdf) e seguici sui social media per gli ultimi aggiornamenti e sviluppi. Se sei uno sviluppatore, unisciti alla nostra community Discord degli sviluppatori.\
\
**D7** Qual è il meccanismo di licenza per PancakeSwap Infinity?

**Risp:** PancakeSwap Infinity è impegnato nei principi open-source. Il nostro codice verrà rilasciato sotto una licenza open-source, consentendo agli sviluppatori di innovare liberamente. Tuttavia, come parte della nostra [iniziativa Affiliate](https://forum.pancakeswap.finance/t/discussion-on-pancakeswap-affiliates-a-multichain-expansion-strategy/395), i protocolli DeFi che fanno fork di PancakeSwap saranno accolti calorosamente e ufficialmente riconosciuti dalla Kitchen.\
\
**D8** Come riduce le commissioni gas PancakeSwap Infinity?

**Risp:** PancakeSwap Infinity sfrutta i meccanismi Singleton e Flash Accounting per ridurre significativamente le commissioni gas. Consolidando tutti i pool in un unico contratto (singleton), le transazioni multi-pool vengono semplificate, rendendole più convenienti. Flash Accounting sostituisce i trasferimenti individuali con saldi netti, calcolati collettivamente alla fine di ogni transazione, risultando in sostanziali risparmi gas. ERC-6909 riduce ulteriormente il gas per gli utenti frequenti consentendo loro di mantenere i loro fondi all'interno del protocollo e utilizzarli quando necessario, eliminando i trasferimenti da/verso i loro Portafogli.\
\
**D9** Cosa sono gli Hooks in PancakeSwap Infinity e come abilitano l'innovazione?

**Risp:** Gli Hooks sono componenti aggiuntivi personalizzabili che migliorano la funzionalità dei Pool di Liquidità, consentendo agli sviluppatori di introdurre funzionalità personalizzate e opzioni di gestione delle commissioni. Deployati esternamente, gli Hooks possono eseguire logica predefinita durante le azioni chiave del pool, offrendo infinite possibilità, tra cui commissioni dinamiche, tipi di ordine, oracoli personalizzati e strategie di gestione attiva della Liquidità. Consulta questo blog per [saperne di più](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)\
\
**D10** Quali opportunità presenta PancakeSwap Infinity per gli sviluppatori?

**Risp:** Gli sviluppatori possono costruire soluzioni innovative, generare entrate attraverso le commissioni degli Hooks e attingere all'ampia base utenti e alla Liquidità profonda di PancakeSwap. Leggi il nostro [post dedicato sul blog](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks) su perché gli sviluppatori dovrebbero costruire su PancakeSwap.

**D11** Come contribuisce PancakeSwap Infinity all'ecosistema DeFi più ampio?

**Risp:** PancakeSwap Infinity mira ad affrontare le carenze degli attuali AMM, migliorare l'esperienza DEX ed evolversi nella piattaforma DeFi con la massima funzionalità supportata dal nostro approccio open-source. Leggi la [visione del nostro Head Chef, Chef Mochi, per Infinity](https://blog.pancakeswap.finance/articles/chef-mochi-s-vision-for-pancake-swap-v4-a-leap-forward-in-de-fi-innovation) per saperne di più\
\
**D12** Dove possiamo trovare il repository del template hook?

**Risp:** Il template degli Hooks si trova su [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) e gli Hooks di esempio su [https://github.com/pancakeswap/infinity-hooks](https://github.com/pancakeswap/infinity-hooks)\
\
**D13** Puoi spiegare i cicli di vita degli Hooks e i loro esempi?

**Risp:** Gli Hooks possono essere implementati prima/dopo 5 azioni chiave: initialize, swap, addLiquidity, removeLiquidity, donate. Ad esempio, quando un utente avvia uno Swap, il contratto PoolManager verifica se esiste un callback hook beforeSwap. Se esiste, viene eseguita la logica sotto il metodo beforeSwap nel contratto hook; altrimenti, lo Swap procede normalmente. Una volta completato lo Swap, lo stesso processo si verifica per il callback afterSwap.\
\
**D14:** Dobbiamo eseguire il mining degli indirizzi per garantire che gli Hooks vengano deployati a un indirizzo specifico?\
**Risp:** Gli Hooks possono essere deployati su qualsiasi indirizzo come gli altri contratti. I permessi di callback sono impostati nel PoolKey. Per ulteriori informazioni, consulta la faq sugli Hooks qui

[https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook](https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook)\
\
**D15:** Come possiamo verificare un contratto hook su etherscan?

**Risp:** Se stai usando foundry, puoi fare riferimento alla guida foundry qui [https://book.getfoundry.sh/reference/forge/forge-verify-contract](https://book.getfoundry.sh/reference/forge/forge-verify-contract) \
O se stai usando hardhat, fai riferimento alla guida hardhat qui [https://hardhat.org/hardhat-runner/docs/guides/verifying](https://hardhat.org/hardhat-runner/docs/guides/verifying)\
\
**D16:** Dovremmo usare foundry o hardhat per lo sviluppo degli Hooks?

**Risp:** Il template [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) è basato su foundry; pertanto, consigliamo di usare foundry. Inoltre, foundry sta crescendo in popolarità!

**D17:** Cosa sono le pool key?

**Risp:** PoolKey è una struct che descrive ogni pool. Vedi di più [qui](https://developer.pancakeswap.finance/contracts/infinity/overview/amm-layer-poolmanager).\
\
\
PancakeSwap Infinity rappresenta una tappa fondamentale nello spazio DeFi, offrendo vantaggi senza pari per trader, sviluppatori, fornitori di Liquidità e la comunità più ampia. Siamo entusiasti di intraprendere questo percorso con te e non vediamo l'ora di plasmare insieme il futuro della DeFi. Speriamo che questa FAQ abbia risposto alle tue domande su PancakeSwap Infinity. Se hai ulteriori domande, sentiti libero di contattarci tramite ([Twitter](https://twitter.com/PancakeSwap), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) e [Telegram](https://t.me/PancakeSwap)) o controlla la nostra [documentazione](https://developer.pancakeswap.finance) per sviluppatori.
