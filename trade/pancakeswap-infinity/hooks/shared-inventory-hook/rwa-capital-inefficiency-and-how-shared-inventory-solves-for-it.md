---
description: '2026-09-04'
---

# Ineficiência de Capital em RWA — e Como o Shared Inventory a Resolve

Um experimento de estudo de caso da PancakeSwap (Parte 1: O Cenário)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Esta é a primeira parte de um estudo de caso em duas partes. Nesta parte, apresentamos o problema real de eficiência de capital enfrentado pelos emissores de ativos RWA, mostramos como o Shared Inventory Hook (SIH) da PancakeSwap foi pensado para resolvê-lo e apresentamos um experimento de estudo de caso ao vivo para testá-lo com dados on-chain.

Nas próximas semanas, publicaremos a Parte 2: Os Resultados.

***

### 🧩 Qual é o Problema de Eficiência de Capital?

O setor de RWA adora um número: **quanto já foi tokenizado.** Ele é a manchete de quase todo relatório: uma nova classe de ativos chegando, bilhões emitidos, crescimento de centenas de pontos percentuais.

Mas existe um segundo número que fica enterrado e que talvez seja um sinal mais importante: **quanto disso pode realmente ser negociado?**

A diferença entre esses dois números é onde está a questão. No rastreador de referência, [rwa.xyz](http://rwa.xyz), o valor _representado_ on-chain supera de longe o valor contra o qual é possível _negociar_ em qualquer momento. Os dados mostram valor bloqueado, de referência e distribuído **mais de uma ordem de magnitude maior do que o que está em livros negociáveis.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Fonte: app.rwa.xyz/stocks_

Para um emissor de RWA, essa é a armadilha. Tokenizar uma ação, um ETF ou um título do tesouro é a parte fácil; fazer com que ele seja negociado com spreads apertados e de forma confiável é o desafio, e é aí que a eficiência de capital se ganha ou se perde. O objetivo final é permitir que os traders _realmente negociem_ o ativo tokenizado de forma fácil e barata, pois é daí que vêm o volume e as taxas.

E é por isso que isso é especificamente um problema de _eficiência de capital_, e não apenas de liquidez.

#### Cada pool cotado exige sua própria pilha exclusiva de USDT

Para tornar um par RWA negociável em um pool tradicional de liquidez concentrada (CLAMM), os emissores precisam de ativo de cotação, o USDT, dedicado e disponível para os compradores venderem contra ele. Liste dez pares, e o modelo CLAMM exige o financiamento de **dez pilhas de USDT separadas**, uma por par, nenhuma capaz de ajudar as outras. Assim, o capital de cotação é fragmentado em silos exclusivos.

Medimos isso em nosso próprio book. Pegamos **7 pools de ações tokenizadas ativos na PancakeSwap** (cada um rodando um pool CLAMM v3 tradicional) e levantamos o USDT exclusivo.

Snapshot: **2 de setembro de 2026.**

<table data-search="false"><thead><tr><th>Par</th><th>USDT exclusivo no pool</th><th>TVL do pool</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Total</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

São **\~$745 mil de USDT alocados de forma exclusiva.**

E isso considera apenas os nomes que têm um book.

SNXXB, KORUB, SOXSB e DJTB não têm nenhum book de USDT em CLAMM: são tokenizados, mas difíceis de negociar.

***

### 🎯 Para o que um Emissor deve Otimizar?

Deixando a mecânica de lado, um emissor de RWA precisa resolver três coisas essenciais:

1. **Que seu ativo seja verdadeira e eficientemente negociável**: cotações apertadas em todos os ativos, não apenas nos tokens principais.
2. **O mínimo de capital possível** imobilizado para isso: o ativo de cotação é caro; financiar dez pilhas de USDT de forma exclusiva não é nada eficiente.
3. **Não operar uma mesa de trading —** Emitir ativos sem precisar operar infraestrutura de liquidez todos os dias.

A questão, então, é se a liquidez pode ser estruturada de outra forma, e é isso que o Shared Inventory Hook da PancakeSwap foi projetado para resolver.

***

### 🥞 Shared Inventory Hook (SIH)

**O SIH é um hook do PancakeSwap Infinity que permite a um emissor de RWA sustentar vários pares a partir de um único pote compartilhado de USDT, em vez de uma pilha exclusiva por par.**

O SIH faz isso fornecendo liquidez just-in-time, o que possibilita:

* Cotações mais profundas nos pares
* Menor impacto de preço, especialmente em negociações de grande valor
* Capital liberado para os emissores de RWA, já que menos capital alocado cota mais pares

Vamos ver essas afirmações na prática.

No mesmo snapshot de **2 de setembro de 2026**, o SIH mantém **$635.028** de inventário em um único hook, cotando **11 pares** a partir de **$180.467** de USDT compartilhado, operando com **87,7%** de utilização. Com isso, o SIH processou **$3,56 milhões em 17.299 transações.**

Ou seja: **um saldo compartilhado de USDT de \~$700 mil cotando \~11 pares versus \~$745 mil cotando apenas 7 pares**.

Mesmo trabalho, apenas projetado para parar de duplicar capital.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Relacionando com o que os emissores valorizam:

* N saldos exclusivos de USDT no modelo tradicional → ✅ um pote compartilhado com o SIH
* Emitido, mas não negociável → ✅ negociável\
  O inventário compartilhado injetando liquidez just-in-time em torno do preço ao vivo significa que tokens sem book de USDT na v3 ainda podem ser cotados, e não apenas emitidos.
* Operar uma mesa → ✅ um operador com permissão\
  O emissor fornece o inventário; o hook e seu operador cuidam das cotações.

***

### 🔬 Experimente o Simulador de Shared Inventory

Desenvolva a intuição de como o SIH se comporta com nossa ferramenta interativa de comparação **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Esta é uma **comparação normalizada e de alto nível** do SIH com um book CLAMM tradicional: diversos fatores do mundo real são mantidos constantes nos dois lados para que a mecânica de eficiência de capital possa ser isolada com clareza. É um modelo para entendimento, não um P\&L.

Três abas:

* **Aba Simulador** - brinque com inventário, largura da faixa e fluxo para ver como o SIH _teria_ desempenho em comparação com um pool CLAMM equivalente em diferentes condições.
* **Aba Comparação** - o SIH lado a lado com um book **PancakeSwap v3 CLAMM** nos mesmos pools, para você ver a diferença entre pote compartilhado de USDT e USDT exclusivo em capital comprometido e cobertura.
* **Aba Dados ao vivo** — meça como o SIH está _realmente_ performando agora, com dados das consultas on-chain que alimentam este estudo.

O simulador tem como objetivo ajudar a demonstrar como o Shared Inventory Hook funciona. Experimente e depois compare com os resultados reais que publicaremos nas próximas semanas.

***

### 🧪 O Experimento

Nas **próximas semanas**, vamos operar o SIH ao vivo e medi-lo em relação às afirmações de eficiência de capital acima, usando fontes on-chain. Toda semana divulgaremos novas informações rápidas sobre o desempenho e a arquitetura do SIH.

**Pares RWA ativos no estudo:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Observação: SNXXB, KORUB, SOXSB e DJTB não têm nenhum book CLAMM tradicional._

**Publicaremos os resultados nas próximas semanas no** [**Twitter**](https://x.com/PancakeSwap) **da PancakeSwap.**

Os resultados publicados abordarão:

* **O conjunto completo de dados de desempenho -** Todos os dados do SIH nas próximas semanas, reunidos em um só panorama.
* **A questão da alocação de capital -** Quanto capital o SIH realmente economizou para um emissor de RWA.
* **Acertos / erros -** Onde o SIH superou as expectativas e onde precisa melhorar.
* **O veredito -** Uma conclusão fundamentada sobre o quão eficaz o SIH realmente é para a eficiência de capital em RWA.

_Uma observação sobre os dados: os números aqui vêm de consultas on-chain ao vivo e de dados públicos de pares, citados no texto. Algumas comparações usam janelas diferentes e as sinalizamos; o estudo foi desenhado para medir em bases equivalentes, enquanto esta introdução só pôde enquadrar a pergunta._

***

### Quer ativar o SIH nos seus ativos?

Se você é um emissor de RWA e está cansado de financiar uma pilha de USDT separada para cada pool que cota, isto é para você.

Estamos fazendo o onboarding de emissores de RWA agora. Preencha este formulário do Google e vamos guiar você para ter seu ativo cotado no SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Obrigado por ler! Siga-nos no [X](https://x.com/PancakeSwap) para as últimas novidades e participe da conversa no [Telegram](https://t.me/PancakeSwap) e no [Discord](https://discord.gg/pancakeswap).

Vamos construir,\
The Chefs 🥞

***

_Aviso legal: este conteúdo tem caráter exclusivamente informativo e educacional. Ele não deve ser interpretado como aconselhamento financeiro, jurídico ou profissional de qualquer natureza. Os preços de ativos digitais podem ser voláteis. O valor do seu investimento pode cair ou subir._
