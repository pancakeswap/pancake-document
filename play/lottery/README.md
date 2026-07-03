# 🎟️ Loteria

Jogar a Loteria da PancakeSwap oferece a chance de ganhar enormes prêmios em CAKE! É fácil, justo e você pode participar quantas vezes quiser, desde que tenha CAKE para comprar um bilhete.

[Ver contrato inteligente](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Detalhes:**

* Custo do bilhete de Loteria por 1 bilhete: \~$5 USD em CAKE.
* Limite de participação individual na Loteria: Sem limite geral, mas apenas 100 bilhetes podem ser comprados de uma vez.
* Pagar por um bilhete dará aos usuários uma combinação aleatória de 6 dígitos, sendo cada dígito entre 0-9, por ex. "1-9-3-2-0-4". Combine números da esquerda para ganhar prêmios — quanto mais números corresponderem, maior será o pool de prêmios que você compartilhará.
* A Loteria usa a implementação de VRF da Chainlink para verdadeira aleatoriedade e segurança.

## Custos dos bilhetes e desconto por compra em volume

Os preços dos bilhetes de Loteria são definidos no início de cada nova rodada e têm como alvo $5 USD (pode variar levemente com flutuações repentinas de preço).

Comprar vários bilhetes de Loteria de uma vez oferece um desconto por volume na sua compra. Você pode comprar até 100 bilhetes em uma única compra, com o desconto começando pequeno com 2 bilhetes e escalando até 10% com 100 bilhetes.

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%20PM.png>)

## **Como ganhar**

Combine os números, **do lado esquerdo do seu bilhete**, com os números vencedores sorteados ao final de uma rodada de Loteria.

* Combinar apenas o primeiro número já garante um pequeno prêmio.&#x20;
* Combine mais números para ganhar uma parte de um pool de prêmios maior.

## **‌**Elegibilidade ao prêmio

‌Há um total de seis bolas de loteria, de 0 a 9, em cada bilhete. Para ganhar, seus números precisam corresponder aos números sorteados na mesma ordem que as bolas da loteria, começando pela esquerda do bilhete. Por exemplo:

Números sorteados

![Números Sorteados](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png>)

Os números do seu bilhete

![Seu Bilhete A](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png>)

No exemplo acima, Bilhete A, cinco dos números do bilhete correspondem aos mesmos números sorteados, na mesma ordem: todos exceto o quarto.

No entanto, como o quarto dígito **não** corresponde ao número sorteado, apenas os três primeiros dígitos contam como correspondentes em ordem. Isso ganharia um prêmio "Combinar os primeiros 3".

![Seu Bilhete B](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png>)

Bilhete B de exemplo. Este é um caso de azar. Mesmo que os últimos cinco dígitos correspondam, o primeiro dígito não corresponde, então este bilhete não ganha nada.

Você compartilhará apenas os prêmios do nível mais alto para o qual é elegível. Um bilhete que corresponde aos três primeiros números só será elegível para prêmios do nível de correspondência de três, e não para os níveis de correspondência de um ou dois.

**Lembre-se: Os dígitos devem corresponder em ordem, da esquerda para a direita.**

## Distribuição de prêmios entre os níveis

‌Após o sorteio de uma rodada e a identificação dos bilhetes com números correspondentes, os prêmios são concedidos. O valor ganho por cada bilhete dependerá de quantos outros bilhetes venceram no mesmo nível.

‌Por exemplo, se você tiver o único bilhete que combinou três números em ordem, e a participação predefinida do pool de prêmios para o seu nível for 2000 CAKE, você receberá os 2000 CAKE inteiros.

‌Se, no entanto, você e outras três pessoas corresponderem três números em ordem, os 2000 CAKE seriam divididos entre os quatro bilhetes vencedores, o que significa que você receberia 500 CAKE.

Veja o [FAQ da Loteria para uma descrição dos prêmios](lottery-faq.md#how-are-prizes-broken-down-between-brackets) em cada nível.
