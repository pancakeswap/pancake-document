# FAQ do Monad

#### 1. Quais níveis de taxa estão disponíveis nos pools de liquidez do PancakeSwap?

**Níveis de Taxa Suportados:**

* Os seguintes níveis de taxa estão disponíveis para pools V3 (liquidez concentrada): `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Para pools V2, apenas o nível de taxa de 0.25% é suportado

#### 2. Qualquer pessoa pode criar um pool?

Sim. A criação de pools não requer permissão, com algumas exceções:

* Apenas um pool pode existir para uma determinada combinação de **par de tokens + nível de taxa** (ex.: apenas um pool WMON <> USDC 0.05% pode existir por vez)

#### 3. Quanto tempo leva para um pool recém-criado aparecer?

* Os pools normalmente aparecem na lista de pools aproximadamente **5 minutos** após a criação.
* Se não aparecer:
  * Use a **barra de pesquisa** para localizá-lo manualmente.
  * Pools podem ser filtrados da lista devido a **TVL baixo**.

#### 4. Por que o APR ou TVL do meu pool ainda está mostrando zero?

Isso é esperado logo após a criação de um novo pool:

* Os dados de APR e TVL só serão preenchidos após ocorrer **pelo menos um Swap** no pool.
* Após um Swap, essas métricas começarão a ser exibidas em aproximadamente **15 minutos**.

#### **5. Por que minhas transações às vezes falham quando minha carteira tem menos de 10 MON?**

O Monad tem uma regra de que toda conta deve manter um **buffer de segurança mínimo de 10 MON**. Se seu saldo estiver baixo e você enviar muitas transações rapidamente, a rede pode **parar de aceitar novas**.

#### **6. Por que as primeiras 1–2 transações funcionam, mas as seguintes falham?**

O Monad processa blocos usando uma visão ligeiramente "atrasada" do seu saldo. Portanto:

* Sua **primeira** transação geralmente funciona bem.
* A **segunda** também pode passar.
* Mas se você enviar **múltiplas transações em um curto período**, a rede acha que você pode não ter MON suficiente para pagar todas as taxas de gas.

Então ela **bloqueia** a próxima transação. Isso é normal e faz parte do sistema de segurança.

#### **7. Por que parece mais restrito em contas inteligentes (contract wallets)?**

As contas inteligentes seguem **regras mais rígidas**:

* Elas devem **sempre** manter pelo menos **10 MON** enquanto executam código de contrato.
* Se sua conta inteligente estiver abaixo de 10 MON, a transação pode **reverter imediatamente**, mesmo que EOAs ainda funcionem por mais algumas transações.

É por isso que usuários de contas inteligentes veem falhas mais cedo.

#### **8. Isso significa que não posso usar o Monad com menos de 10 MON?**

Você _pode_ ainda usar, especialmente com uma EOA normal — mas:

* Não envie várias transações seguidas.
* Aguarde alguns blocos entre as transações.
* Mantenha um pouco de MON na carteira para evitar problemas.

#### **9. Como evitar essas falhas?**

Dicas simples:

* Mantenha **10 MON ou mais** na sua carteira se possível.
* Se você estiver com pouco MON, **espaçe suas transações** (não as envie em spam).
* Usuários de contas inteligentes devem manter **um pouco mais de 10 MON**, pois chamadas de contrato usam mais gas.
