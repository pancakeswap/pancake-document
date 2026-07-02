# FAQ da Solana

### V3 Pools – Perguntas Frequentes (FAQ)

#### 1. Quais níveis de taxa estão disponíveis?

**Níveis de Taxa Suportados:**\
Os seguintes níveis de taxa estão disponíveis para pools V3 (liquidez concentrada):

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Distribuição de Taxas (aplica-se a todos os níveis de taxa):**

* 84% para provedores de liquidez (LPs)
* 16% para o protocolo
  * 8% é queimado
  * 8% vai para o tesouro do protocolo

#### 2. Qualquer pessoa pode criar um pool?

Sim. A criação de pools não requer permissão, com algumas exceções:

* Apenas um pool pode existir para uma determinada combinação de **par de tokens + nível de taxa** (ex.: apenas um pool SOL<>USDC 0.1% pode existir por vez)
* Apenas tokens **SPL** e tokens **Token-2022** selecionados são suportados no momento.

#### 3. Quanto tempo leva para um pool recém-criado aparecer?

* Os pools normalmente aparecem na lista de pools aproximadamente **5 minutos** após a criação.
* Se não aparecer:
  * Use a **barra de pesquisa** para localizá-lo manualmente.
  * Pools podem ser filtrados da lista devido a **TVL baixo**.

#### 4. Por que o APR ou TVL do meu pool ainda está mostrando zero?

Isso é esperado logo após a criação de um novo pool:

* Os dados de APR e TVL só serão preenchidos após ocorrer **pelo menos um Swap** no pool.
* Após um Swap, essas métricas começarão a ser exibidas em aproximadamente **15 minutos**.

#### 5. Como adicionar um token personalizado para criar um pool?

Para adicionar um novo token:

* Na interface de criação de pool, abra o seletor de tokens.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Cole o endereço do token na barra de pesquisa.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* Clique em **"Add Token"**.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* O token agora estará pesquisável na lista.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* Para gerenciar tokens:
  * Clique em **"View Token List"**.
  *   Ative ou desative diferentes listas, incluindo a **Lista de Tokens Adicionados pelo Usuário**, que inclui todos os tokens adicionados manualmente.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Por que minha primeira transação na Solana parece mais cara?

A Solana usa **Contas de Token Associadas (ATAs)** para gerenciar saldos de tokens para cada carteira. Ao interagir com um token pela primeira vez, sua carteira deve criar uma ATA, o que incorre em um custo inicial único (pago em SOL).

* Essa taxa de criação de ATA é exigida pelo protocolo Solana e não é específica do PancakeSwap.
* Se a ATA for fechada posteriormente, o **SOL original usado pode ser reembolsado** para sua carteira.
