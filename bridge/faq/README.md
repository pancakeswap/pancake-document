# ❓ FAQ de Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Antes de Fazer Bridge

1.  **Posso usar carteiras móveis ou carteiras diferentes da MetaMask para fazer bridge de CAKE?**

    Atualmente, o Bridging de CAKE do PancakeSwap suporta Coinbase Wallet, MetaMask e carteiras compatíveis com MetaMask. Mais suporte a carteiras está chegando em breve.

    _Dica:_ Para evitar copiar e colar arriscado de Chaves privadas ou Frases semente, recomendamos criar novas Carteiras via extensões de Carteira para desktop para bridging.
2.  **Por que uma rota ou token está indisponível?**

    Algumas rotas dependem de capacidade do bridge, suporte ao token ou Liquidez. Por favor, verifique novamente mais tarde ou tente um provedor diferente. Os tokens disponíveis por chain são mostrados diretamente na interface do Bridge.
3.  **Estou recebendo um erro ao enviar a transação de bridging.**

    Tente inserir o valor manualmente em vez de usar o botão "MÁX", e remova as casas decimais do valor se necessário.
4.  **Por que minha cotação de bridging mostra "X insuficiente para cobrir a taxa nativa"**

    ![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png>)

    O bridging requer taxas de gas pagas no token nativo da chain de origem, por exemplo:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Certifique-se de ter tokens nativos suficientes na sua Carteira de origem para cobrir as taxas e concluir a transação.
5.  **Por que o botão mostra "X CAKE Excedido"?**

    Há um limite de capacidade diária para fazer bridge de CAKE entre BSC e Aptos para garantir segurança. Tente uma quantia menor ou aguarde e tente novamente mais tarde. Os limites são ajustados dinamicamente pelos Chefs com base na demanda.
6.  **Por que não consigo encontrar um token específico?**

    O token pode não ser suportado na rota escolhida ou pode não ter Liquidez. Tente outra chain ou um valor diferente.
7.  **Posso fazer bridge da BNB Chain para Ethereum mas para um endereço diferente?**

    Não, por razões de segurança, o bridging funciona apenas entre o mesmo endereço em chains EVM.
8.  **Por que não posso fazer bridge de menos de 0,00000001 CAKE?**

    Os tokens Aptos, incluindo CAKE na Aptos, têm um máximo de 8 casas decimais. Transações abaixo de 0,00000001 serão rejeitadas ou arredondadas para baixo. Isso se aplica ao bridging para Ethereum também. Qualquer valor restante permanece na sua Carteira de origem.

***

## Após o Bridging

1.  **Posso cancelar uma transferência de bridge após confirmar?**

    Não, uma vez iniciada, a transação de bridge é gerenciada pelo provedor e não pode ser cancelada. Para reverter, faça bridge dos ativos de volta via uma nova transação.
2.  **E se minha transação ficar travada como "pendente"?**

    O bridging pode levar até 30 minutos. Verifique o status da sua transação pesquisando seu hash no explorador do respectivo provedor de bridge:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    Se ainda estiver pendente após 60 minutos, entre em contato com nossos administradores pelos [canais sociais](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **Não recebi meu CAKE. O que devo fazer?**
   * Ao fazer bridge de CAKE para Aptos pela primeira vez, você pode precisar **reivindicar manualmente** seu CAKE. Certifique-se de que sua Carteira Aptos tem APT suficiente para gas. Veja o [guia de bridging para Aptos](https://docs.pancakeswap.finance/bridge/bridging/aptos) e a [explicação da Aptos](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Ao fazer bridge para BNB Chain ou Ethereum, algumas carteiras exigem que você adicione manualmente o endereço do token CAKE para ver seu saldo. Como exemplo, siga este [guia da MetaMask](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) — outras carteiras devem ter fluxos semelhantes.
   * Se ainda não encontrar seu CAKE após 60 minutos, entre em contato com nossos administradores pelos [canais sociais](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
