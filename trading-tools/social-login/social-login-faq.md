# FAQ do Social Login

{% hint style="info" %}
Para mais informações, acesse: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Visão Geral

**1. O que é o Social Login da PancakeSwap e por que devo usá-lo?**

O Social Login permite acessar a PancakeSwap usando sua conta do **Google**, **X (Twitter)**, **Discord** ou **Telegram** — sem extensão de Carteira ou frase semente. Uma Carteira autocustodial é criada nos bastidores, para que você possa experimentar o DeFi instantaneamente, mesmo com pequenas quantias. Isso reduz a barreira de entrada, especialmente em momentos de urgência.

**2. Quais redes o Social Login suporta?**

Sua Carteira de Social Login funciona em todas as redes atualmente suportadas pela PancakeSwap:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Todas as Carteiras são **compatíveis com EVM** e podem ser usadas nessas redes nativamente pela PancakeSwap. Se você quiser ver suporte para outras redes (incluindo non-EVM), nos avise!

**3. Onde posso usar a Carteira de Social Login?**

Você pode usá-la diretamente em qualquer **navegador** de desktop ou mobile pelo aplicativo web da PancakeSwap. Ela **não é compatível** com aplicativos externos de Carteira ou navegadores de dApp.



### 🛠️ Configuração e Uso da Carteira

**4. Como a Carteira é criada e protegida?**

Sua Carteira é criada automaticamente no login e protegida usando um **sistema de 2-de-2 compartilhamentos de chave**. Ambos os compartilhamentos são necessários para reconstruir a chave e gerar uma assinatura.

Para mais informações sobre criptografia de compartilhamentos, acesse:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Quantas Carteiras posso criar?**

Você tem **uma Carteira por conta social por dApp**. Por exemplo, se você usar seu login do Google em outro aplicativo que também usa Privy, ele criará uma Carteira separada.



### 🔐 Segurança e Privacidade

**6. Alguém pode acessar minha Carteira se roubar meu dispositivo?**

Não. Mesmo que alguém tenha acesso ao seu dispositivo, ainda precisarão do seu **Social Login** e (se definida) da sua **senha de recuperação**.

**7. Quais dados são armazenados pela PancakeSwap ou Privy?**

* A PancakeSwap **não armazena** nenhum compartilhamento de chave relacionado à Carteira.
* A Privy armazena o **Auth Share criptografado e o Recovery Share (se o fluxo de recuperação não estiver configurado)**.

> Se você não completou a configuração de recuperação, seu Recovery Share permanece armazenado na Privy por padrão. Para mais informações, acesse: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Recuperação e Gerenciamento de Sessão

**8. Posso usar a mesma Carteira em um dispositivo ou navegador diferente?**

Sim! Basta fazer login com a mesma conta social. Se for um novo dispositivo, você passará pelo processo de recuperação usando sua senha de recuperação (se configurada).

**9. O que acontece se eu trocar de dispositivo?**

Você será solicitado a fazer login novamente com sua conta social e passar pelo fluxo de recuperação (configuração de senha). Se você não configurou uma senha de recuperação, o login com conta social é suficiente.

**10. E se eu perder acesso tanto ao meu Social Login quanto ao método de recuperação?**

Se você perder acesso à sua conta social e ao seu método de recuperação, **sua Carteira não poderá ser recuperada**. Não há fallback de frase semente, e a exportação de Chave Privada não é suportada atualmente.

> ⚠️ Lembre-se: Exportar sua Chave Privada, se habilitado no futuro, concederia controle total de sua Carteira a qualquer pessoa que a tivesse — trate-a com extremo cuidado.

**11. Quanto tempo duram as sessões ativas?**

As sessões duram 30 **dias**. Após isso, você será solicitado a **fazer login novamente** e (se necessário) reinserir suas credenciais de recuperação. Durante uma sessão ativa, você pode realizar transações sem precisar aprovar manualmente cada ação.



### ⚙️ Compatibilidade e Limitações

**12. Posso exportar ou importar Carteiras?**

* **Exportação**: Não suportada por padrão, por razões de segurança. Isso pode mudar em atualizações futuras.
* **Importação**: Não suportada. Você não pode importar Carteiras externas como MetaMask ou Phantom.

**13. Posso conectar esta Carteira a outros dApps usando WalletConnect?**

Não no momento. A Carteira integrada é **limitada apenas à PancakeSwap**. Se você estiver interessado em usá-la de forma mais ampla, nos avise — expansões futuras são possíveis.



### 🚀 Recursos Avançados

**14. A Carteira de Social Login suporta Account Abstraction?**

Sim. Ela suporta **recursos de Account Abstraction** como agrupamento de transações e **patrocínio de gas** por meio de integrações como Biconomy, etc.

**15. Como as transações sem assinatura são habilitadas?**

* Após o login, sua sessão fica ativa por até 30 **dias**. Durante esse período, a PancakeSwap pode solicitar à Privy para assinar transações em seu nome usando suas credenciais de sessão.&#x20;
* Você não verá um popup de Carteira para cada ação — tudo é tratado em segundo plano. Após 30 dias, você precisará fazer login novamente para continuar usando essa experiência sem assinatura.
