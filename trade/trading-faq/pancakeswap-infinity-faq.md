---
description: >-
  entendemos que você pode ter perguntas sobre nossa atualização mais recente. Compilamos
  este FAQ abrangente para responder a todas as suas dúvidas. Vamos começar:
---

# FAQ do PancakeSwap Infinity

**P1 Como o PancakeSwap Infinity beneficiará traders e provedores de liquidez?**

**Resp:** O PancakeSwap Infinity traz muitas vantagens tanto para traders quanto para provedores de liquidez:

**1. Operações Simplificadas e Economia de Gas:** Por meio de recursos como Singleton e Flash Accounting, o PancakeSwap Infinity reduz drasticamente as taxas de gas. O Singleton consolida todos os pools em um único contrato, reduzindo os custos de implantação em 99%. O Flash Accounting otimiza os processos de contabilidade computando saldos líquidos para transações, minimizando o consumo de gas.

**2. Benefícios Diretos de Recursos Avançados:** A integração de Hooks permite implementar taxas dinâmicas, tipos de ordens personalizados e módulos de gerenciamento ativo de liquidez. Os provedores de liquidez podem desfrutar de IL mitigada, proteção contra MEV e acesso a várias camadas de taxas, garantindo experiências de negociação mais lucrativas e seguras.

\
**3. Flexibilidade em Designs de AMM:** O PancakeSwap Infinity suporta múltiplos tipos de pool, incluindo CLAMM e LBAMM, permitindo que traders e LPs escolham diferentes tipos de pool. Essa abordagem inclusiva também permite suportar quaisquer ativos futuros que exijam novas curvas de precificação. Confira este blog para [saber mais](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2016.16.56.png" alt=""><figcaption></figcaption></figure>

**P2** Como o PancakeSwap Infinity beneficiará desenvolvedores e protocolos DeFi?

**Resp:** O PancakeSwap Infinity abre um mundo de possibilidades para desenvolvedores e protocolos DeFi.&#x20;

**1. Infinitas Possibilidades de Personalização:** Com o PancakeSwap Infinity, os desenvolvedores podem criar Hooks para introduzir funcionalidades personalizadas; de taxas dinâmicas a ordens limitadas on-chain e oráculos personalizados. O PancakeSwap Infinity suporta a implantação de novos tipos de pool (CLAMM, LBAMM e quaisquer outros tipos de pool no futuro), melhorando a eficiência de capital e a flexibilidade de negociação.

**2. Acesso a Liquidez Robusta e Base de Usuários:** Com mais de 1,8 milhão de usuários ativos e $2,1 bilhões em liquidez, desenvolvedores e protocolos DeFi têm uma oportunidade incomparável de acessar uma comunidade vasta e ativa, fomentando o desenvolvimento e adoção de produtos.

**3. Oportunidades de Geração de Receita:** Os desenvolvedores podem estabelecer um fluxo de receita consistente por meio de taxas de hook, permitindo-lhes definir taxas pela utilização de seus hooks. Ao monetizar suas inovações com taxas, os desenvolvedores podem contribuir para o crescimento e desenvolvimento do ecossistema PancakeSwap. Confira este blog para[ saber mais](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-03-15%20at%2009.40.42.png" alt=""><figcaption></figcaption></figure>

**P3** Quais melhorias o PancakeSwap Infinity traz em comparação ao v3?

**Resp:** O PancakeSwap Infinity introduz a capacidade de aprimorar as funcionalidades dos pools de liquidez com recursos personalizados sem reimplementar o protocolo principal. Também suporta a implementação de qualquer curva de precificação em tempo real e oferece economias substanciais de gas para os usuários.

**P4** Haverá mudanças na interface ou na experiência do usuário no PancakeSwap Infinity?

**Resp:** Os usuários podem fazer swap no Infinity pela página de swap da PancakeSwap, assim como na experiência habitual e amigável. Traders e provedores de liquidez têm múltiplas opções para adicionar liquidez nos tipos de pool suportados, incluindo CLAMM e LBAMM.

**P5** Como a comunidade pode se envolver em testes ou fornecer feedback para o PancakeSwap Infinity?

**Resp:** Se você é um membro da comunidade, sinta-se à vontade para compartilhar seu feedback por meio de nossas redes sociais no [Telegram](https://t.me/PancakeSwapAnn), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) e [Twitter](https://twitter.com/PancakeSwap). Se você é um desenvolvedor, junte-se à nossa comunidade Discord de desenvolvedores e compartilhe seus pensamentos.

**P6** Onde os usuários podem encontrar mais informações sobre o PancakeSwap Infinity e se manter atualizados sobre seu progresso de desenvolvimento?

**Resp:** Visite nosso [site](https://pancakeswap.finance/v4?utm_source=v4announcementblog\&utm_medium=blog\&utm_campaign=v4announcementblog\&utm_id=v4announcementblog) oficial, leia nosso [whitepaper](https://github.com/pancakeswap/pancake-v4-core/blob/main/docs/whitepaper-en.pdf) e siga-nos nas redes sociais para as últimas atualizações e desenvolvimentos. Se você é um desenvolvedor, junte-se à nossa comunidade Discord de desenvolvedores.\
\
**P7** Qual é o mecanismo de licenciamento do PancakeSwap Infinity?

**Resp:** O PancakeSwap Infinity está comprometido com os princípios de código aberto. Nosso código será lançado sob uma licença de código aberto, capacitando os desenvolvedores a inovar livremente. No entanto, como parte de nossa [iniciativa Affiliate](https://forum.pancakeswap.finance/t/discussion-on-pancakeswap-affiliates-a-multichain-expansion-strategy/395), os protocolos DeFi que fizerem fork da PancakeSwap serão bem-vindos e reconhecidos oficialmente pela Kitchen.\
\
**P8** Como o PancakeSwap Infinity reduz as taxas de gas?

**Resp:** O PancakeSwap Infinity aproveita os mecanismos Singleton e Flash Accounting para reduzir significativamente as taxas de gas. Ao consolidar todos os pools em um único contrato (singleton), as transações com múltiplos pools são simplificadas, tornando-as mais econômicas. O Flash Accounting substitui transferências individuais por saldos líquidos, computados coletivamente no final de cada transação, resultando em economias substanciais de gas. O ERC-6909 reduz ainda mais o gas para usuários frequentes, permitindo que mantenham seus fundos dentro do protocolo e os utilizem quando necessário, eliminando transferências de/para suas carteiras.\
\
**P9** O que são Hooks no PancakeSwap Infinity e como eles permitem a inovação?

**Resp:** Hooks são complementos personalizáveis que aprimoram a funcionalidade dos pools de liquidez, permitindo que os desenvolvedores introduzam recursos personalizados e opções de gerenciamento de taxas. Implantados externamente, os Hooks podem executar lógica predefinida durante ações-chave do pool, oferecendo possibilidades infinitas, incluindo taxas dinâmicas, tipos de ordens, oráculos personalizados e estratégias de gerenciamento ativo de liquidez. Confira este blog para [saber mais](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)\
\
**P10** Quais oportunidades o PancakeSwap Infinity apresenta para desenvolvedores?

**Resp:** Os desenvolvedores podem criar soluções inovadoras, gerar receita por meio de taxas de hook e acessar a extensa base de usuários e a liquidez profunda da PancakeSwap. Leia nossa [postagem de blog dedicada](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks) sobre por que os desenvolvedores devem criar na PancakeSwap.

**P11** Como o PancakeSwap Infinity contribui para o ecossistema DeFi mais amplo?

**Resp:** O PancakeSwap Infinity visa resolver as deficiências dos AMMs atuais, aprimorar a experiência DEX e evoluir para a plataforma DeFi de maior funcionalidade, apoiada por nossa abordagem de código aberto. Leia a [visão do Chef Mochi para o Infinity](https://blog.pancakeswap.finance/articles/chef-mochi-s-vision-for-pancake-swap-v4-a-leap-forward-in-de-fi-innovation), nosso Head Chef, para saber mais\
\
**P12** Onde podemos encontrar o repositório de template de hooks?

**Resp:** O template de Hooks pode ser encontrado em [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) e exemplos de hooks em [https://github.com/pancakeswap/infinity-hooks](https://github.com/pancakeswap/infinity-hooks)\
\
**P13** Você pode explicar os ciclos de vida dos hooks e seus exemplos?

**Resp:** Hooks podem ser implementados antes / depois de 5 ações-chave: initialize, swap, addLiquidity, removeLiquidity, donate. Por exemplo, quando um usuário inicia um swap, o contrato PoolManager verifica se existe um callback de hook beforeSwap. Se existir, a lógica sob o método beforeSwap no contrato de hook é executada; caso contrário, o swap prossegue normalmente. Após a conclusão do swap, o mesmo processo ocorre para o callback afterSwap.\
\
**P14:** Precisamos realizar mineração de endereço para garantir que os hooks sejam implantados em um endereço específico?\
**Resp:** Os Hooks podem ser implantados em qualquer endereço como outros contratos. As permissões de callback são definidas no PoolKey. Para mais informações, consulte o FAQ de hooks aqui&#x20;

[https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook](https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook)\
\
**P15:** Como podemos verificar um contrato de hook no etherscan?&#x20;

**Resp:** Se você estiver usando foundry, pode consultar o guia foundry aqui [https://book.getfoundry.sh/reference/forge/forge-verify-contract](https://book.getfoundry.sh/reference/forge/forge-verify-contract) \
Ou se você estiver usando hardhat, consulte o guia hardhat aqui [https://hardhat.org/hardhat-runner/docs/guides/verifying](https://hardhat.org/hardhat-runner/docs/guides/verifying)\
\
**P16:** Devemos usar foundry ou hardhat para desenvolvimento de hooks?

**Resp:** O template [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) é baseado em foundry; portanto, aconselhamos o uso do foundry. Além disso, o foundry tem crescido em popularidade!&#x20;

**P17:** O que são pool keys?&#x20;

**Resp:** PoolKey é uma struct que descreve cada pool. Veja mais [aqui](https://developer.pancakeswap.finance/contracts/infinity/overview/amm-layer-poolmanager).\
\
\
O PancakeSwap Infinity representa um marco significativo no espaço DeFi, oferecendo benefícios incomparáveis para traders, desenvolvedores, provedores de liquidez e a comunidade em geral. Estamos animados em embarcar nessa jornada com você e aguardamos com expectativa moldar o futuro do DeFi juntos. Esperamos que este FAQ tenha respondido às suas perguntas sobre o PancakeSwap Infinity. Se você tiver mais perguntas, sinta-se à vontade para nos contatar via ([Twitter](https://twitter.com/PancakeSwap), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315) e [Telegram](https://t.me/PancakeSwap)) ou consulte nossa [documentação](https://developer.pancakeswap.finance) para desenvolvedores.
