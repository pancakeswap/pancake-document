# 🎁 Pancake Gifts

### 🎯 O que são os Pancake Gifts?

Os **Pancake Gifts** permitem que qualquer pessoa envie tokens — incluindo gas opcional — para amigos, usuários ou comunidades usando apenas um **link** ou **código QR**. É uma experiência simples, segura e sem gas para o destinatário.

Foi criado para tornar a integração ao cripto tão fácil quanto enviar uma mensagem — sem necessidade de financiar Carteira, fazer Bridge ou pagar taxas antecipadas.

### 🤝 Por que Criamos os Pancake Gifts

A integração ao Web3 ainda está repleta de atrito. Novos usuários frequentemente desistem antes mesmo de começar devido a:

* **Sem gas na Carteira** → Não é possível realizar nenhuma ação onchain
* **Sem fundos na rede correta** → Bridge necessário antes de usar dApps
* **Precisar comprar cripto apenas para começar** → Requer cadastro em CEX ou rampa fiat

Os Pancake Gifts eliminam esses obstáculos ao:

* ✅ **Incluir tokens de gas nativos** no presente para que os destinatários possam interagir instantaneamente
* ✅ **Patrocinar a taxa de gas antecipadamente** (o remetente paga uma pequena taxa)
* ✅ **Habilitar resgate via link simples ou QR** — sem integração complexa



É uma ferramenta tanto para:

* Novos usuários começando onchain
* Comunidades nativas de Web3 que desejam **aumentar a adoção, recompensar usuários ou executar campanhas** de forma mais amigável

***

### ⚙️ Resumo de Recursos

| Recurso                      | Descrição                                                              |
| ---------------------------- | ---------------------------------------------------------------------- |
| **Suporte a Redes**          | BNB Chain (lançamento inicial)                                         |
| **Tipos de Código de Presente** | Link **ou** Código QR                                               |
| **Uso Único**                | Cada código só pode ser resgatado uma vez                              |
| **Suporte a Tokens**         | Máx. 2 tokens: 1 BEP-20 (obrigatório), 1 token de gas nativo (opcional) |
| **Valores Personalizados**   | Defina valores diferentes por token                                    |
| **Taxa de Gas do Resgate**   | Remetente paga o gas antecipadamente (\~$0,05 em BNB)                  |
| **Histórico de Presentes**   | Usuários podem ver todos os presentes enviados, status de resgate, expiração |
| **Verificações de Segurança** | Tokens com taxa de transferência e lógica complexa são bloqueados     |

### 🚫 Limitações

1. **Um presente por código** — Envio em massa ainda não é suportado.
2. **Presentes não podem ser restaurados** — Uma vez cancelados ou expirados, não podem ser reutilizados.
3. **Tokens não suportados são bloqueados** — Tokens com taxas de transferência ou lógica especial exibirão um erro na criação.
4. **Tentativas de resgate mal-sucedidas são repetidas** — O backend tenta novamente algumas vezes. Se ainda falhar, o presente é marcado como **não resgatável** e deve ser cancelado manualmente para recuperar os fundos.
5. **O presente deve ser resgatado na mesma rede** — ex.: um presente em ETH deve ser resgatado no Ethereum. O resgate cross-chain ainda não é suportado.

***

### 🕒 Lógica de Cancelamento e Expiração

Os presentes seguem um ciclo de vida definido com base no status e no tempo:

#### Cancelamento Manual

* O **criador** pode cancelar qualquer presente que ainda esteja **não resgatado** e **dentro do prazo de expiração**.
* Os tokens (menos a Taxa de Gas do Resgate inicial) serão devolvidos ao remetente.
* Presentes cancelados **não podem** ser reativados ou reutilizados.

#### Expiração Automática

* Os presentes **expiram automaticamente** após um período definido pelo usuário (padrão: 7 dias).
* Tokens não resgatados serão **devolvidos automaticamente** à Carteira do remetente.
* Presentes expirados também não são reutilizáveis.

***

### 🔄 Status dos Presentes e Seus Significados

| Status          | Descrição                                                                      |
| --------------- | ------------------------------------------------------------------------------ |
| **Pendente**    | O presente foi criado e aguarda resgate                                        |
| **Resgatado**   | O presente foi resgatado com sucesso pelo destinatário                         |
| **Cancelado**   | O presente foi cancelado manualmente pelo remetente                            |
| **Expirado**    | O presente passou do prazo de expiração sem ser resgatado                      |
| **Não Resgatável** | Número de tentativas excedido; o presente precisa ser cancelado para recuperar fundos |

***

### ⚠️ Tratamento de Erros e Casos Especiais

1. **Token Não Suportado**
   * A criação do presente é bloqueada para tokens com taxas de transferência ou lógica especial.
2. **Incompatibilidade de Gas**
   * Se o **custo real de gas do resgate ≥** à taxa pré-paga pelo remetente, o resgate falha automaticamente para evitar uso excessivo. Será tentado novamente quando os níveis de taxa de gas estiverem dentro do intervalo.
3. **Tentativas de Resgate Mal-sucedidas**
   * Novas tentativas serão feitas após o primeiro resgate mal-sucedido.
   * Se ainda mal-sucedido:
     * O destinatário vê "Não Resgatável"
     * O remetente deve cancelar manualmente o presente para recuperar os fundos e o destinatário terá que solicitar um novo código de presente.
