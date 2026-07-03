# Agente de Referência — Agente de Liquidação de Ordens/Intenções

> Um agente Provedor ERC-8183 que cumpre um único Job de intenção de Swap por vez roteando-o pela agregação PancakeSwap e entregando o token de destino diretamente ao Cliente.

### 0. Como se mapeia ao ERC-8183

O ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) define um **Job** com três funções e estados Open → Funded → Submitted → Terminal. O **BNBAgent SDK** da BNB é a implementação ativa.

| Função                                                    | Neste agente                                                                                                                          |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Cliente** (Agent-A)                                     | publica uma intenção de Swap: "faça Swap de X do token A → token B, entregue-me ≥ `minOut`", deposita o input + uma gorjeta no escrow |
| **Provedor** (Agent-B) — **este é nosso agente de referência** | cota via **agregação PancakeSwap**, e se puder atingir/superar `minOut`, executa o Swap e entrega token B ao Cliente            |
| **Avaliador**                                             | verifica se o Cliente recebeu quantidade de token-B ≥ `minOut`; libera a gorjeta (ou reembolsa o Cliente)                             |

O produto a entregar é objetivo ("o Cliente recebeu ≥ `minOut`?"), que é exatamente o motivo pelo qual isso se encaixa no ERC-8183 onde o rebalanceador não se encaixou.

***

### 1. Propósito e escopo em uma linha

> Um agente **Provedor** que cumpre um único Job de intenção de Swap por vez roteando-o pela agregação PancakeSwap e entregando o token de destino diretamente ao Cliente — e nada mais.

***

### 2. O que o agente tem PERMISSÃO de fazer (lista de permissões de capacidade)

| # | Capacidade             | Superfície                                                      | Notas                                                                         |
| - | ---------------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| A | Descobrir Jobs abertos | BNBAgent SDK (registro ERC-8183)                                | Somente leitura; filtrar para Jobs de intenção de Swap que pode atender       |
| B | Cotar uma rota         | **Agregação PancakeSwap** (Aggregator API / Smart Router)       | Somente leitura; melhor preço em V3                                           |
| C | Aceitar um Job         | BNBAgent SDK (Funded → comprometido)                            | Apenas se sua cotação recente ≥ `minOut` e gorjeta ≥ mínimo                  |
| D | Executar o Swap        | Roteador PancakeSwap                                            | Input retirado do escrow do Job; **destinatário de saída = o Cliente**, em uma tx |
| E | Submeter o produto     | BNBAgent SDK (→ Submitted)                                      | O hash da tx de liquidação como prova                                         |
| F | Reivindicar a gorjeta  | Escrow ERC-8183 / x402                                          | Apenas após o Avaliador marcar o Job como Terminal                            |

**O resultado de toda liquidação vai diretamente ao Cliente. O único ganho do agente é a gorjeta do Job.**

***

### 3. Controles rígidos (o portão para inclusão)

| Controle                             | Regra                                                                                                                                                            |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nunca aceite o que não pode cumprir** | Aceite um Job apenas se uma cotação _recente_ superar `minOut`. Se não puder, deixe o Job Funded para outro Provedor.                                        |
| **Recotar na execução**              | Recote imediatamente antes de liquidar; aborte se a rota não superar mais `minOut` (sem cotações desatualizadas).                                                |
| **Liquidação atômica**               | Retirada do escrow → Swap → entrega ao Cliente em **uma transação**, destinatário de saída = Cliente. O agente nunca deve manter os fundos do Cliente entre uma etapa com falha. |
| **Slippage**                         | Slippage de execução limitado; o valor entregue ainda deve ser ≥ `minOut` após o Slippage, ou a tx é revertida. Nunca `amountOutMin = 0`.                       |
| **Prazo**                            | Prazo curto na tx de liquidação (≤ 5 min); respeite o prazo do próprio Job.                                                                                      |
| **Gorjeta mínima / valor máximo**    | Não aceite Jobs abaixo de um mínimo de gorjeta ou acima de um limite de valor por Job.                                                                           |
| **Lista segura de tokens**           | Sirva apenas Jobs cujos tokens estão na lista de tokens PancakeSwap (anti-honeypot / token falso).                                                               |
| **Concorrência de Job único (v1)**   | Cumpra um Job por vez; sem excesso de comprometimento.                                                                                                           |
| **Pré-condição de gas**              | Confirme BNB suficiente para a liquidação completa antes de aceitar.                                                                                             |
| **Idempotente**                      | Nunca envie duplicadamente ou recumpra um Job já em Submitted/Terminal.                                                                                          |

Se qualquer regra não puder ser atendida, **pule o Job** — nunca force uma liquidação.

***

### 4. Fora do escopo — o agente NÃO DEVE

1. **Usar fundos do Cliente para qualquer coisa além do Swap especificado.** O destinatário de saída é sempre o Cliente.
2. **Adiantar seu próprio inventário / assumir risco de capital.** v1 é **somente retirada do escrow** — roteia o input depositado no escrow do Cliente; não preenche a partir do próprio saldo.
3. **Rotear por contratos não-PancakeSwap ou não verificados**, ou liquidar fora da agregação PancakeSwap.
4. **Servir Jobs com tokens não na lista segura**, ou (v1) qualquer token scaled-UI / RWA (§5).
5. **Usar Alavancagem, perps, margem ou empréstimos.**
6. **Submeter um produto que não cumpriu de verdade** (sem atestação falsa) ou **avaliar seus próprios Jobs** (conflito de interesses).
7. **Chamar qualquer função de proprietário/administrador** na PancakeSwap ou nos contratos ERC-8183.
8. **Manter aprovações de tokens permanentes** além de uma única liquidação; limite as aprovações ao valor do Job.

***

### 5. Lógica específica da PancakeSwap (correção da aplicação)

* **Rotear via agregação PancakeSwap**, não um único pool — melhor execução em V2 / V3 / Stable é toda a proposta de valor ("melhor preço ganha a gorjeta").
* **Entregar atomicamente ao Cliente** definindo o `recipient` do roteador para o endereço do Cliente; nunca um processo de dois passos "fazer Swap para si mesmo, depois transferir".
* **Atualidade da cotação** — o preço onchain muda entre a descoberta e a liquidação; recote na execução (controle §3).
* **`minOut` é em unidades brutas.** Para tokens **scaled-UI / ERC-8056** (Binance Stock Tokens / RWA de ações) bruto ≠ exibido; manipulação incorreta silenciosamente entrega errado. **Exclua tokens scaled-UI do v1** até que eng confirme o tratamento de unidades brutas de ponta a ponta.
* **Mínimo de Slippage** no Swap de liquidação deve ser derivado para que o valor _entregue_ ≥ `minOut`, considerando a divisão de gorjeta/taxa.

***

### 6. Comportamento de falha e recuperação

* **Cotação falha em `minOut` na execução** → aborte antes/atomicamente com a retirada do escrow; o Job permanece Funded para outro Provedor. Sem estado parcial.
* **Já em Submitted/Terminal** → pule (idempotente).
* **Tx de liquidação revertida** → Job permanece reivindicável por outros; o agente registra a falha e segue em frente.
* **Falhas repetidas em um Job** → coloque esse Job na lista negra localmente e alerte, em vez de repetir em loop.

***

### 7. Pontos de integração (a metade BNB / ERC-8183)

Estes são fornecidos pelo BNB Agent Studio / BNBAgent SDK, não construídos pela PancakeSwap — mas as especificações dependem deles:

* **Ciclo de vida do Job** (descobrir Open → aceitar Funded → Submitted → reivindicar) via BNBAgent SDK.
* **Identidade do Provedor** via ERC-8004.
* **Escrow + pagamento** via escrow ERC-8183 / x402.
* **Avaliador** — o predicado deve ser "saldo de token-B do Cliente aumentou em ≥ `minOut`". Confirme com a BNB **quem executa o Avaliador** (neutro/protocolo vs. Cliente) e que o predicado é aplicável onchain.

***

### 8. Postura recomendada para v1 e decisões pendentes

1. **Somente retirada de escrow, um Job por vez, somente tokens da lista segura, sem tokens scaled-UI.** Menor superfície segura para lançar.
2. **Confirme a interface de Swap PancakeSwap** — a **API HTTP do Aggregator (`aggr`)** vs o **SDK do Smart Router**. A nota de Jerry diz "use pcs aggr api"; precisa confirmar qual o agente chama, pois muda a integração (e se o guia precisa de uma seção de agregação).
3. **Confirme o mecanismo de escrow** com a BNB — o Provedor pode retirar o input depositado no escrow do Cliente para rotear o Swap, e a entrega ao Cliente é aplicável como produto a entregar?
4. **Confirme o proprietário e o predicado do Avaliador** (§7).

> Aprovação de eng antes de incluir: roteamento atômico retirada do escrow → Swap → entrega ao Cliente; recotação na execução; matemática de `minOut` após Slippage; aplicação da lista segura; tratamento idempotente de Jobs.
