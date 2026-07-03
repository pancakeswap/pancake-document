---
hidden: true
---

# Integração com Formadores de Mercado

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Integração com Formadores de Mercado no Ethereum

O PancakeSwap está integrado com formadores de mercado no Ethereum e na Binance Smart Chain para ajudar os traders a executarem negociações com menor custo.

Além do AMM, as negociações no PancakeSwap agora podem ser roteadas para formadores de mercado autorizados na lista branca caso eles ofereçam execução de negociações com preços melhores do que os preços atuais do AMM. Esse roteamento é feito automaticamente pelo [Smart Router](smart-router-v2/) para que as negociações só sejam roteadas para os formadores de mercado quando eles estiverem ativamente cotando preços melhores. Onde o AMM for mais competitivo, os traders serão roteados para os AMMs.

Existem 2 cenários nos quais os formadores de mercado operam no PancakeSwap.

**Cenário 1: Pools de Liquidez AMM existentes**

Se o PancakeSwap já tiver Liquidez para um determinado token (por exemplo, WETH/USDC) no AMM, o PancakeSwap solicitará uma cotação aos formadores de mercado para a mesma negociação. O Smart Router do PancakeSwap então roteará a solicitação de negociação para o AMM ou para os formadores de mercado, dependendo de qual fonte de Liquidez estiver oferecendo o melhor preço em um determinado momento.

**Cenário 2: Sem pools de Liquidez AMM existentes**

Nesse cenário, o Smart Router roteará automaticamente a negociação para os formadores de mercado. No entanto, isso não impede que projetos configurem seu Pool de Liquidez AMM posteriormente e trabalhem conosco para manter a Liquidez DEX descentralizada.

### Taxas

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

O PancakeSwap não cobra taxas dos traders executadas por meio de nós e que são executadas pelos formadores de mercado. No entanto, o PancakeSwap recebe **0,05%** **de taxas de negociação** dos formadores de mercado autorizados pelos volumes executados por eles. O PancakeSwap recebe uma **taxa de negociação** reduzida de **0,01%** se as negociações executadas forem entre pares de stablecoins. Consulte o detalhamento de taxas abaixo:<br>

<table><thead><tr><th width="178">Negociações</th><th width="138">Taxas de Negociação</th><th width="182">Taxa PCS do MM</th><th width="147">Queima de CAKE</th><th align="center">Tesouro PancakeSwap</th></tr></thead><tbody><tr><td>Moedas com Bridge de outras redes</td><td>N/A</td><td>0,25%</td><td>0,083%</td><td align="center">0,167%</td></tr><tr><td>Não-stablecoin no Ethereum (ex: ETH/USDC)</td><td>N/A</td><td>0,05%</td><td>0,017%</td><td align="center">0,033%</td></tr><tr><td>Não-stablecoin na BSC (ex: BNB/USDT)</td><td>N/A</td><td>0,05%</td><td>0,017% </td><td align="center">0,033%</td></tr><tr><td>Stablecoin para Stablecoin no Ethereum</td><td>N/A</td><td>0,01%</td><td>0,003%</td><td align="center">0,007%</td></tr></tbody></table>

#### Ativos atualmente suportados

Os seguintes ativos são suportados atualmente e podem aumentar/diminuir dependendo dos formadores de mercado:

**No Ethereum**

* **Principais:** WETH, WBTC
* **Stablecoins:** USDT, USDC, DAI, BUSD
* **Outros ativos ERC-20 populares:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Na Binance Smart Chain:**

* **Principais:** BNB, ETH, BTCB
* Tokens BNB não nativos: ARB, OP

Observe que, ao contrário dos AMMs, os formadores de mercado não poderão negociar em qualquer valor, e os valores que estão dispostos a executar dependerão de sua própria Liquidez. Não é incomum que às vezes ordens muito grandes não possam ser totalmente preenchidas. Aconselhamos os usuários a revisar cuidadosamente as cotações para garantir que cada negociação reflita o preço e a quantidade de acordo com suas necessidades.

**Períodos de inatividade dos formadores de mercado**

Não se espera que os formadores de mercado cotem 24 horas por dia, 7 dias por semana. Há alguns casos (por exemplo, eventos econômicos importantes, atualizações de sistema) em que o formador de mercado pode estar temporariamente indisponível para fornecer uma cotação. Observe que durante esses períodos, esses tokens simplesmente não serão negociáveis, e aconselhamos os usuários a aguardar algum tempo antes que o formador de mercado volte online.

#### FAQs

**P.** Os formadores de mercado serão integrados no Aptos?

**R:** Possivelmente. Estamos lançando a integração com formadores de mercado apenas no Ethereum e na Binance Smart Chain por enquanto para impulsionar a Liquidez para uma melhor experiência do usuário. Continuaremos a monitorar outras redes.

**P.** Como o PancakeSwap gerará receita se não cobra taxa dos usuários?

**R:** O PancakeSwap não cobrará nenhuma taxa dos usuários, mas receberá uma pequena comissão dos formadores de mercado e a usará para financiar a recompra e queima de CAKE.

**P.** Os provedores de Liquidez continuarão a ganhar taxas LP?

**R:** Sim, os provedores de Liquidez continuarão a ganhar 0,17% de recompensa de taxa de negociação (taxas LP) e rendimento nas Farms de CAKE.

**P.** Os formadores de mercado adicionarão Liquidez ao AMM? Isso causará queda no APR?

**R:** Os formadores de mercado mantêm sua própria Liquidez separada e, portanto, não ganharão nenhum APR com negociações nos pools AMM. Apenas os LPs ganharão taxas e APRs por fornecerem Liquidez aos pools AMM.

**P.** Estou fornecendo Liquidez no PancakeSwap no Ethereum. Preciso fazer algo?

**R:** Não, você não precisa fazer nada. Você continuará a ganhar as taxas LP pelas negociações executadas por meio do AMM e continuará a obter rendimento em CAKE.

**P.** Como alguém pode se tornar um formador de mercado?

**R:** Avaliamos e trabalhamos com formadores de mercado individualmente. Entre em contato conosco diretamente ou por meio de nossos administradores se tiver interesse em trabalhar conosco.
