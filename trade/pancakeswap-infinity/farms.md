# Farms

O Yield Farming no PancakeSwap Infinity é uma forma simples e eficiente em gas para os usuários ganharem recompensas de Liquidez sem precisar fazer Staking de seus tokens LP. Assim que a Liquidez é adicionada a um pool elegível, as recompensas começam a acumular automaticamente.

#### ⚙️ Como Funciona

Aqui está um resumo rápido de como o sistema rastreia e distribui recompensas:<br>

**✅ Sem Staking Necessário**

* Mantenha sua posição LP em sua Carteira.
* Sem necessidade de bloquear seus ativos ou interagir com contratos inteligentes adicionais.
* Você começa a ganhar recompensas automaticamente ao adicionar Liquidez.

#### 📈 Distribuição de Recompensas

* Apenas posições dentro do intervalo (aquelas que fornecem Liquidez ativa) recebem recompensas.
* As recompensas são proporcionais às taxas ganhas pela sua posição durante cada período, chamado de época.

#### ⏳ O que é uma Época?

* Uma época é uma janela de tempo fixo — atualmente definida como 8 horas.
* As recompensas são calculadas e distribuídas após cada época.
* As épocas são atualmente agendadas às 00:00, 08:00 e 16:00 UTC.

***

#### 🔄 Processo de Farming e Resgate

1. **Rastreamento de Posições:** O sistema de back-end monitora suas posições LP em todas as Farms.
2. **Cálculo de Recompensas:** Ao final de cada época,
   1. O sistema calcula suas recompensas com base em sua Liquidez e nas taxas geradas.
   2. Ele processa as recompensas em uma árvore Merkle e envia uma raiz Merkle para um contrato inteligente.
3. **Período de Disputa:**
   1. Após a publicação da raiz Merkle, começa o período de disputa de 1 hora.
   2. Durante o período de disputa:
      1. As recompensas recém-calculadas não podem ser resgatadas.
      2. As recompensas de épocas anteriores continuam disponíveis para resgate.
      3. Ferramentas de verificação automatizadas e operadas pela comunidade verificam a precisão dos dados publicados. Se forem detectadas discrepâncias, uma disputa pode ser levantada para evitar distribuições incorretas.
4. **Resgate de Recompensas:**
   1. Uma vez encerrado o período de disputa, você pode resgatar suas recompensas para a época mais recente.
   2. Todas as recompensas pendentes em todas as Farms podem ser resgatadas em uma única transação eficiente em gas.
5. **Recompensas Não Resgatadas São Transferidas:**
   1. Quaisquer recompensas não resgatadas são transferidas para épocas subsequentes. Cada atualização incorpora recompensas anteriores, garantindo que nenhum ganho seja perdido ou expirado.

{% hint style="info" %}
Intervalos de Liquidez mais estreitos geralmente levam a ganhos maiores, mas aumentam a probabilidade de uma posição sair do intervalo e se tornar inelegível para recompensas.
{% endhint %}

#### 🌱 Resumo

✅ Sem Staking\
✅ Resgate eficiente em gas\
✅ Atualizações regulares de recompensas\
✅ Processo de disputa justo e transparente\
✅ As recompensas acumulam até você estar pronto para resgatar
