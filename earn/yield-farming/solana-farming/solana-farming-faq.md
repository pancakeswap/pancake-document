# FAQ de Farming na Solana

### 1. Como funciona o Farming SOL?

* O Farming V3 é **baseado em campanhas**, o que significa que os farms ficam ativos apenas por uma duração definida.
* Durante a campanha:
  * Os tokens de recompensa são distribuídos **a cada segundo** para **posições de liquidez ativas**.
  * O APR de farming será mostrado na página de lista de pools e na página de minhas posições.
* Após o término da campanha:
  1. **Nenhuma recompensa adicional** será distribuída.
  2. **O APR de farming não será mais exibido** na página de lista de pools e na página de minhas posições.
  3. O farm fica **inativo**, mas pode ser reiniciado pelo criador adicionando mais recompensas.

### 2. Preciso fazer Staking do meu LP NFT para ganhar recompensas de farming?

* **Não é necessário fazer Staking**.
* Desde que sua posição de liquidez esteja **ativa (dentro do intervalo)** em um pool com um farm ativo, você ganhará recompensas automaticamente.

### 3. Existem impulsionadores de farm?

* **Não**, os farms V3 **não** suportam nenhum mecanismo de impulsionamento.
* As recompensas são baseadas exclusivamente na sua parcela de liquidez ativa no pool.

### 4. Múltiplos farms podem ser criados para o mesmo pool?

* **Não**, apenas **um farm por par de tokens e nível de taxa** pode existir.

### 5. Como os farms SOL são configurados?

#### A. Tokens de Recompensa

* Até **3 tokens de recompensa diferentes** podem ser atribuídos por farm.
* Uma vez definidos, os tipos de tokens de recompensa **não podem ser alterados**.
* O criador do farm pode:
  * **Recarregar** os tokens de recompensa alocados.
  * **Estender a duração do farming** após o término da campanha.

#### B. Duração da Campanha

* As campanhas devem durar no mínimo **7 dias** e no máximo **90 dias**.

### 6. Um farm pode ser editado após a criação?

Os criadores de farms podem editar os seguintes parâmetros **após a criação do farm**:

1. Taxa de distribuição de recompensas (por segundo)
2. Data de término da campanha
3. Adicionar um token de recompensa e o valor de recompensa correspondente (apenas se menos de 3 tokens foram inicialmente atribuídos)
