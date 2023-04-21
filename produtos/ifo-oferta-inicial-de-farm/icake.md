---
description: Alocação de CAKE de Prazo Fixo e Alocações de IFO
---

# iCAKE

## O que é ICAKE?

O iCAKE é semelhante aos “créditos IFO” do pool de staking de IFO de CAKE anterior, que foi retirado durante a migração do MasterChef v2. Após essa atualização, o iCAKE determinará o limite máximo de CAKE que você pode comprometer nas vendas públicas do IFO da PancakeSwap. Por exemplo, se você tiver 200 iCAKE, poderá comprometer 200 CAKE em qualquer venda pública IFO futura.

**O iCAKE NÃO é um novo token, é uma métrica numérica usada pelo sistema de IFO da PancakeSwap.**

### Como é calculado o iCAKE? <a href="#882f" id="882f"></a>

O número de iCAKE que você tem é baseado no número de CAKE em stake na pool de prazo fixo de CAKE e na duração total do staking da sua posição de staking de prazo fixo atual.

O iCAKE funciona com base em um limite de duração de staking para todos os usuários do iCAKE.

Se a duração do seu stake estiver acima do limite, o número de iCAKE que você possui é igual ao número do CAKE na sua posição de staking.

Se a duração do seu stake estiver abaixo do limite, o número de iCAKE que você possui será diminuído e ajustado linearmente.

Se a sua posição do seu stake terminar, o número de iCAKE que você tem é 0.

Por exemplo, se o limite for 35 semanas:

* Sua posição atual de stake de prazo fixo tem uma duração de 40 semanas e 200 CAKE staking. Então o número de iCAKE que você tem é 200.
* Sua posição atual de stake de prazo fixo tem uma duração de 21 semanas e 200 CAKE staking. Então o número de iCAKE que você tem é igual a 200 × (21 ÷ 35) = 120.
* Sua posição atual de stake de prazo fixo tem uma duração de 7 semanas e 200 CAKE staking. Então o número de iCAKE que você tem é igual a 200 × (7 ÷ 35) = 40.
* Sua posição atual de stake de prazo fixo tem uma duração de 10 semanas e 200 SAKES staking. Mas a posição acabou. Então o número de iCAKE que você tem é 0.

![](<../../.gitbook/assets/image (102) (1).png>)

### Como verificar o número de iCAKE que tenho? ![](<../../.gitbook/assets/image (134).png>)

Você pode verificar o número de iCAKE que você tem na página IFO [aqui](https://pancakeswap.finance/ifo).

### Como aumentar o número de iCAKE que tenho?&#x20;

Você pode aumentar o número de iCAKE que você tem:&#x20;

* Adicionando mais CAKE à sua posição de stake de prazo fixo na pool de syrup de CAKE.&#x20;
* Estenda sua duração de stake de prazo fixo se sua duração atual forem menores que o exigido.

![](<../../.gitbook/assets/image (59) (2).png>)

Você pode visualizar o número de iCAKE gerado a partir de sua posição de stake ao ajustar ou inicializar o stake de prazo fixo.

### Qual é o limiar para os cálculos de iCAKE?&#x20;

Entre cada IFOs, a cozinha otimizará o limiar com base na duração média de stake da pool de CAKE de staking de prazo fixo. O reajuste será publicado em todas as redes sociais.

![](<../../.gitbook/assets/image (35) (1).png>)

Você pode verificar o limiar atual para cálculos de iCAKE passando o mouse ou tocando no texto iCAKE sublinhado na janela do pool de syrup CAKE.

