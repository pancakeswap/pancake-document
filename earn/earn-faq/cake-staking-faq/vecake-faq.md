---
hidden: true
---

# FAQ do veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Qual é a diferença entre CAKE bloqueado e veCAKE? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

O veCAKE é uma nova versão do Staking de CAKE com prazo fixo com mais benefícios e poder para os detentores de CAKE bloqueado. Incluindo Votação de peso de gauge, incentivos extras, impulsionamento de rendimento e muito mais.

#### O que acontece com as recompensas do pool CAKE quando o novo veCAKE for implantado <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

As emissões de recompensas do pool CAKE serão redirecionadas para recompensar todos os detentores de veCAKE de acordo com o saldo de veCAKE em relação ao fornecimento total.

As recompensas de CAKE e as recompensas semanais de compartilhamento de receita agora podem ser reivindicadas semanalmente às quintas-feiras.

Observe que para continuar recebendo recompensas, os usuários precisarão migrar para o novo Staking de veCAKE.

#### Qual é a duração máxima que posso bloquear meu CAKE <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

A duração máxima que você pode bloquear seu CAKE agora foi estendida para 4 anos.

#### O veCAKE é um novo token? Pode ser transferido? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

O veCAKE é um número gerado em tempo real com base na quantidade de CAKE bloqueado e no tempo de bloqueio restante. Não é um token padrão e não pode ser transferido.

#### Por que meu saldo de veCAKE mudou? Como calcular seu saldo? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

O saldo de veCAKE diminui linearmente para 0 com base na duração restante do bloqueio. Portanto, à medida que nos aproximamos do tempo de desbloqueio, seu saldo diminui.

O saldo de veCAKE pode ser calculado por:

```javascript
lockedAmount // quantidade de CAKE bloqueado
currentTime // tempo atual
lockEndTime // o tempo de desbloqueio
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // tempo máximo de bloqueio (4 anos)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### Como aumentar meu veCAKE? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Uma vez que você tem uma posição de veCAKE ativa, você pode adicionar mais CAKE ou renovar/estender sua duração de bloqueio para aumentar seu saldo de veCAKE.

#### O que acontece quando a posição é desbloqueada? Posso renovar imediatamente? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Quando a posição de Staking de veCAKE é desbloqueada, você pode retirar todo o CAKE em Staking.

Para renovar sua posição, você precisa retirar todo o CAKE e configurar uma nova posição de Staking escolhendo a quantidade a bloquear e a duração do bloqueio.

#### Bloqueei por 1 semana, por que o tempo de bloqueio restante é menor que 1 semana? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Ao bloquear com o novo veCAKE, o tempo de desbloqueio é arredondado para a quinta-feira mais próxima no horário UTC. Por exemplo, ao bloquear por 1 semana na terça-feira, seu tempo de desbloqueio real será a quinta-feira seguinte, que é 2 dias depois.

Você pode visualizar seu tempo de desbloqueio real na parte inferior.

#### Posso bloquear mais CAKE no pool CAKE? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

Não.

Assim que o veCAKE for implantado, o pool de Staking de CAKE será descontinuado e não aceitará mais extensões ou depósitos de CAKE.

Para bloquear CAKE e desfrutar de seus benefícios, vá para a página do veCAKE.

#### Por que não consigo migrar? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

Migrar do pool CAKE para o veCAKE requer que você tenha uma posição ativa. Se sua posição de Staking no pool CAKE já estiver desbloqueada, basta retirar esse CAKE e criar uma posição nativa de Staking de veCAKE.

Em alguns casos, a migração não pode ser realizada quando o tempo de bloqueio restante no pool CAKE for menor que 7 dias. Nesse caso, basta aguardar o desbloqueio, retirar esse CAKE e criar uma posição nativa de Staking de veCAKE.

#### Posso retirar antecipadamente meu CAKE bloqueado? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

Não.

Uma vez bloqueado, o CAKE ficará em Staking no contrato veCAKE até o tempo de desbloqueio.

#### Posso migrar parcialmente meu CAKE? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

Não.

Você só pode migrar toda a sua posição no pool CAKE de uma só vez.

#### O que acontecerá com iCAKE, bCAKE, vCAKE e rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Para o iCAKE:**

O IFO iCAKE agora foi atualizado para suportar veCAKE. Confira:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Para o bCAKE:**

O bCAKE de impulsionamento de rendimento do Farm agora foi atualizado para suportar veCAKE. Confira:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Para o vCAKE:**

O vCAKE de Votação agora foi atualizado para suportar veCAKE. Confira:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Para o rCAKE:**

Todos os detentores de veCAKE (nativos ou migrados) serão automaticamente inscritos no novo pool de compartilhamento de receita. As parcelas de receita são distribuídas de acordo com o cronograma existente. O antigo pool de compartilhamento de receita será descontinuado; os usuários podem reivindicar suas recompensas pendentes pelo card de benefícios. Confira:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### Carteiras multisig podem ser usadas para interagir com o veCAKE?

Sim

No entanto, havia um modificador `noContract` implementado no contrato de Staking de veCAKE para endereços que não estão na whitelist. Para habilitar o Staking ou a migração do pool de Staking de CAKE com prazo fixo, todas as carteiras multisig baseadas em contratos devem realizar uma ação de autowhitelist única.

Para fazer whitelist, visite qualquer uma das seguintes páginas:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Um prompt deverá aparecer. Clique em "Whitelist" e prossiga com a transação na sua carteira multisig.

Uma transação será enviada ao proprietário do veCAKE, que é um contrato com uma função de escrita sem permissão para permitir que qualquer contrato realize o autowhitelist.

Se o prompt não aparecer, siga estas instruções para executar a transação pelo [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11):

```
// chamar:
VECakeOwner.setWhitelist(bool _status = true)

// Endereço do VECakeOwner:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Por que há múltiplos APRs?

Bloquear CAKE para obter veCAKE oferece uma série de grandes benefícios em toda a suíte de produtos construídos pela PancakeSwap. Os benefícios e incentivos vêm em diferentes formas e de diferentes fontes. Portanto, há múltiplos APRs.

Você pode ganhar todos eles simultaneamente, portanto o APR combinado será a soma de todos os APRs.

Observe que muitos outros benefícios do veCAKE não podem ser quantificados no formato de APRs, como o [Impulsionador de Rendimento do Farm bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) ou o [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). Certifique-se de conferí-los também.

#### O que é o APR do Pool veCAKE?

Este é o incentivo proveniente das emissões de CAKE, com sua taxa controlada pelo gauge de Votação do Pool veCAKE.

Para aumentar a emissão para este gauge, confira a [Votação de Gauge](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### O que é o APR de Compartilhamento de Receita?

Este é o incentivo proveniente do compartilhamento de receita do protocolo, proveniente das taxas de swap coletadas nos produtos DEX.

Confira [Compartilhamento de Receita](/broken/pages/wQegezs7c6A2HzQjPEjh) para mais informações.
