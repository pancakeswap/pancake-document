# Shared Inventory Hook

O Shared Inventory Hook (SIH) oficial da PancakeSwap foi projetado para permitir que um único pool de capital faça market making em todos os pools que compartilham seus tokens, em vez de bloquear liquidez separada em cada um deles. Ele oferece aos traders cotações mais profundas e menor impacto de preço, enquanto permite que os provedores de liquidez aloquem menos capital para a mesma cobertura.

Desenvolvido pela equipe principal da PancakeSwap, este hook é voltado para emissores de ativos e market makers que desejam cotar vários pares on-chain sem fragmentar seu inventário.

#### 🔍 Por que Shared Inventory?

Fornecer liquidez a vários pares da maneira convencional significa bloquear capital dedicado em pools separados, e a maior parte dele fica parada entre as negociações. Em vez disso, o SIH mantém um saldo por token e o injeta como liquidez somente quando um swap precisa dele, de modo que o mesmo capital pode dar suporte a todos os pools que compartilham aquele token.

#### 📊 Qual é a diferença em relação a outros modelos?

A liquidez concentrada convencional exige comprometer todo o principal em um único pool. Outras abordagens cross-pool, como camadas de liquidação com saldo virtual, normalmente ficam fora do próprio AMM, e a liquidez pode não ser visível como profundidade de pool on-chain nem ser roteada diretamente por agregadores.

A liquidez do SIH entra e sai do pool CLAMM da PancakeSwap Infinity por meio do hook a cada swap, e por isso aparece como profundidade genuína de pool, que os roteadores conseguem enxergar e preencher.

#### ⚙️ Como funciona

* **Injeção just-in-time (JIT)**\
  Antes de cada swap, o hook cria uma posição de liquidez concentrada configurada no pool; depois que o swap é executado, ele a queima e liquida o resultado líquido. A posição existe apenas pela duração de um swap, e o saldo fica livre para atender o próximo pool que precisar dele.
* **Um saldo, vários pools**\
  O inventário é o próprio saldo de tokens do hook, não há depósito por pool. Qualquer token que seja usado em mais de um pool é compartilhado entre todos eles.

{% hint style="success" %}
Isso desvincula a profundidade que um pool cota do capital que ele mantém diretamente: um hook financiado pode cotar liquidez profunda e concentrada em vários pools que compartilham um token.
{% endhint %}

* **Hook configurável**\
  Para cada pool que atende, o hook mantém uma configuração independente e ajustável de faixa de preço e profundidade. Mover a faixa exige apenas uma atualização de configuração, o que facilita recentralizar as cotações em torno de um preço de referência em movimento.

#### 📌 Principais conclusões

* Um saldo de token compartilhado dá suporte a todos os pools que usam esse token. Adicionar um novo pool não utiliza nenhum novo principal.
* Totalmente on-chain e composável: a liquidez do SIH é profundidade real de pool, roteável tanto pela PancakeSwap quanto por agregadores de terceiros.
* Os traders obtêm cotações mais profundas e menor impacto de preço em ordens grandes; os operadores ganham as mesmas taxas de negociação com uma fração do capital convencional.
