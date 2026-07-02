---
description: Staking de veCAKE e Alocações de IFO
hidden: true
---

# iCAKE

### **O que é o novo iCAKE?**

Após a transição para veCAKE, o novo iCAKE será baseado no saldo de veCAKE

* Assim como o antigo iCAKE, ele determina o limite máximo de commit de CAKE nas vendas públicas de IFO da PancakeSwap. Por exemplo, se você tem 200 iCAKE, pode commitar 200 CAKE nas vendas públicas de IFO.
* O novo número de iCAKE é calculado usando o saldo de veCAKE ao final de cada IFO. Portanto, você terá números de iCAKE diferentes para cada IFO.
* Como o saldo de veCAKE diminui gradualmente com o tempo restante de bloqueio, seu iCAKE em IFOs futuros também diminuirá com seu saldo de veCAKE. Para manter seu número de iCAKE, adicione mais CAKE ao Staking ou renove/estenda seu bloqueio.

**iCAKE NÃO é um novo token; é uma métrica numérica utilizada pelo sistema de IFO da PancakeSwap.**

### Como o iCAKE é calculado?

O número de iCAKE que você possui é baseado no saldo de veCAKE ao final de cada IFO, multiplicado por uma proporção predefinida.

veCAKE é um valor calculado dinamicamente com base na quantidade de CAKE que você bloqueia e no tempo restante no bloqueio. Para saber mais sobre como o veCAKE é calculado, confira [aqui](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Uma proporção adicional é aplicada sobre o saldo de veCAKE, ajustada pela Cozinha para cada IFO. Por exemplo, se a proporção é 2x, e você tem 1 veCAKE ao final do próximo IFO, você pode commitar até 2 CAKE.

Exemplo:

* Você bloqueou 100 CAKE por 2 anos.
  * Seu tempo restante de bloqueio é: `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (segundos)
  * O tempo máximo de bloqueio é: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (segundos)
  * No momento atual, você tem: `100 * (62899200 / 126403199) ~= 49.76` veCAKE
* O próximo IFO está agendado; seu horário de término é exatamente 1 semana depois, que é `604800` segundos após o momento atual.
  * Naquele momento, seu tempo restante de bloqueio é: `62899200 - 604800 = 62294400` (segundos)
  * Naquele momento, você tem: `100 * (62294400 / 126403199) ~= 49.28` veCAKE
* Para este IFO, a proporção está definida em `3x`
* Portanto, para este IFO, você tem: `49.28 * 3 = 147.84` iCAKE, o que significa que você pode commitar até 147.84 CAKE na venda pública.

### Como verificar o número de iCAKE que tenho?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Você pode verificar o número de iCAKE que possui na página de IFO [aqui](https://pancakeswap.finance/ifo).

Tenha em mente que quando não há IFO próximo, seu iCAKE será calculado usando o saldo de veCAKE em tempo real, que diminui gradualmente segundo a segundo.

Quando há um IFO próximo, seu iCAKE será calculado usando o saldo de veCAKE no momento do snapshot, que é o final do IFO. Seu iCAKE não diminuirá nem mudará até o IFO terminar.

### **Como posso aumentar meu número de iCAKE?**

Você pode aumentar o número de iCAKE a qualquer momento:

* Adicionando mais CAKE à sua posição de Staking de veCAKE.
* Estendendo sua posição de Staking de veCAKE.

na [Página de Staking de CAKE](https://pancakeswap.finance/cake-staking)

### O que é a "Proporção" no cálculo do iCAKE?

A Proporção é um fator de controle adicional aplicado sobre o saldo de veCAKE ao calcular o iCAKE.

Por exemplo, se a proporção é 2x, e você tem 1 veCAKE ao final do próximo IFO, você pode commitar até 2 CAKE.

Entre cada IFO, a cozinha vai otimizar a "Proporção" com base em várias métricas. O ajuste será publicado em todos os canais sociais.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Você pode verificar o número atual de "Proporção" para os cálculos de iCAKE acessando [a página de IFO](https://pancakeswap.finance/ifo).
