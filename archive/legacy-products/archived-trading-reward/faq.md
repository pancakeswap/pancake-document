---
description: FAQ do Trading Reward
---

# FAQ

{% hint style="danger" %}
\[Arquivado] Trading Reward – A partir de 23 de agosto de 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Geral

#### Por que meu volume negociado não foi contabilizado?

* Os números de volume levam tempo para atualizar e estão sujeitos a atrasos do SubGraph. Volte a verificar mais tarde
* Sua negociação deve ser roteada pelo par de negociação **exato** destacado na [página do Trading Reward](https://pancakeswap.finance/trading-reward#rewards-breakdown), incluindo a faixa de taxa. Confira [este tutorial](https://docs.pancakeswap.finance/trade/pancakeswap-exchange/fees-and-routes) para ver como visualizar suas rotas de negociação
* Somente pares de negociação V3 são elegíveis para este programa
* Use o mesmo endereço de carteira elegível ao programa de trading reward tanto na Ethereum quanto na BNB Chain
* Se o seu volume de negociação dentro de um par for muito pequeno, você pode não ser elegível para resgatar nenhuma recompensa
* O uso de agregadores de negociação de terceiros pode fazer com que as negociações sejam roteadas por outros provedores de liquidez e não sejam contabilizadas

#### Por que negociei muito, mas recebi apenas uma quantia muito pequena de recompensas?

O valor do trading reward é baseado na taxa de negociação paga nessas operações.

Se suas negociações são roteadas por pares com uma faixa de taxa baixa, por exemplo, 0,01%, você paga uma taxa muito pequena pela negociação. Por isso, a quantidade de recompensas será proporcionalmente menor.

## Campanha Top Traders

#### Preciso permanecer na classificação exigida durante todo o período para ganhar a campanha?

Não, você só precisa estar melhor classificado que a posição exigida **ao final da campanha**. Mas é recomendável subir na classificação e mantê-la. E lembre-se de verificar com frequência para garantir que você não está saindo da classificação exigida.

#### Em que número a classificação se baseia?

A classificação se baseia na quantidade de recompensas que cada usuário acumula ao negociar. O valor da recompensa equivale a uma % fixa da taxa de negociação que eles pagam nas operações.

## Campanha CAKE Stakers

#### Meu endereço era elegível para a campanha anterior. Por que não é elegível para a mais recente?

Cada campanha tem seus próprios requisitos de elegibilidade, como o limite mínimo de veCAKE no momento do snapshot.

Além disso, o momento do snapshot é definido como o horário de término de cada campanha. Como o veCAKE diminui com o tempo, seu saldo de veCAKE pode ficar abaixo do limite em campanhas futuras.

Talvez você precise aumentar seu veCAKE. Basta seguir as instruções na página.

#### Por que aparece que tenho recompensas adicionais que não podem ser resgatadas?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

A quantidade de veCAKE no momento do snapshot determinará o valor máximo de recompensas que você pode ganhar na campanha. Confira a nota de rodapé da seção “Max Reward Cap”.

Enquanto uma campanha estiver ativa, você pode aumentar seu veCAKE e elevar esse limite a qualquer momento.

#### O que é “veCAKE no momento do snapshot”

O veCAKE diminui gradualmente com o tempo à medida que o tempo de bloqueio restante diminui. Portanto, assim como o iCAKE do IFO, um saldo de veCAKE de snapshot, ou seja, o saldo de veCAKE em um momento específico, que é estático, é mais adequado como métrica de qualificação.

No Trading Reward, o momento do snapshot se refere ao fim de cada campanha. Portanto, seu “saldo de veCAKE no momento do snapshot” significa “seu saldo de veCAKE no horário de término da campanha”.

#### Como o “veCAKE no momento do snapshot” se relaciona com a campanha

* Seu saldo de veCAKE no momento do snapshot é maior que o limite exigido
* O valor máximo de recompensas que você pode ganhar está vinculado a y % do seu saldo de veCAKE no momento do snapshot

Por exemplo:

1. Alice bloqueou 300 CAKE por 2 anos (104 semanas) no dia 1. No dia 1, Alice terá um saldo de veCAKE de `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` .
2. Uma campanha de trading reward é lançada no dia 1, com um limite de veCAKE de 100 e um teto de recompensa de 1%. A campanha termina em 30 dias.
3. Após 30 dias, a posição de Alice terá um tempo de bloqueio restante de aproximadamente 99,71 semanas e, portanto, um saldo de veCAKE de `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Portanto, para esta campanha, Alice terá `143` veCAKE no momento do snapshot.
5. 143 é maior que 100, então Alice é elegível para a campanha e pode começar a negociar os pares elegíveis para ganhar trading rewards.
6. Com o teto de recompensa de 1%, o valor máximo de CAKE que Alice pode ganhar nesta campanha é `143 * 1% = 1.43` CAKE.
7. Alice pode aumentar seu veCAKE a qualquer momento antes do fim da campanha, seja bloqueando mais CAKE ou estendendo sua posição.

#### Como posso verificar meu veCAKE no momento do snapshot durante a campanha?

Você pode verificar na página do Trading Reward.

A página alertará você quando seu veCAKE no momento do snapshot estiver abaixo do limite ou quando suas recompensas estiverem sendo limitadas por ele.

Nesses casos, você pode clicar no botão “Increase veCAKE” para aumentar seu veCAKE sem sair da página.

#### Posso aumentar meu veCAKE durante a campanha?

Sim, você pode aumentar seu veCAKE a qualquer momento antes do fim da campanha. Seu “veCAKE no momento do snapshot” será atualizado de acordo.
