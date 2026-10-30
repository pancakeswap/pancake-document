# Tokenomics do CAKE v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Taxa de emissão** <a href="#emission-rate" id="emission-rate"></a>

### **Por bloco**

| **Métrica**                                                                  | **Emissão/bloco (CAKE)** | **Emissão/dia (CAKE)** |
| ---------------------------------------------------------------------------- | ------------------------: | ----------------------: |
| Emissão                                                                      |                        40 |               1.152.000 |
| Queima semanal [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                    -25,75 |                -787.600 |
| **Emissão efetiva**                                                          |              **<14,25\*** |           **364.400\*** |

\*A emissão efetiva é, na verdade, ligeiramente inferior a esse valor: mais 45.000 CAKE por dia são desviados do valor alocado à loteria e queimados (PID 137 - detalhes abaixo).

Além do valor acima, uma quantidade dinâmica de CAKE também é [emitida para o endereço Dev](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) a uma taxa de 9,09%. Isso significa que, se 100 CAKE forem coletados (harvest), 9,09 CAKE são emitidos adicionalmente e enviados ao endereço Dev.

{% hint style="info" %}
Todo o CAKE emitido para o endereço Dev é queimado na queima semanal e nunca entra em circulação.&#x20;

Por isso, não o incluímos na taxa de emissão acima.
{% endhint %}

## Distribuição <a href="#distribution" id="distribution"></a>

| Distribuído para              | Recompensa/bloco (% da emissão) | Recompensa/bloco (total de CAKE) |           Recompensa/dia |
| ----------------------------- | ---------------------------: | ------------------------: | -------------------: |
| Farms e Loteria               |                       10,62% |                      4,25 |     122.400 (aprox.) |
| dos quais desviados e queimados |                              |                           |              -46.000 |
| Syrup Pools                   |                          25% |                        10 |     288.000 (aprox.) |
| **Emissão diária total de CAKE** |                              |                           | **364.400 (aprox.)** |

## **Outros mecanismos deflacionários** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
O processo de queima é atualmente manual. [Veja as transações de queima aqui](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Além do acima, o CAKE também é queimado das seguintes formas:

* **0,05%** de cada negociação feita na PancakeSwap v2
* **100%** do CAKE enviado ao endereço Dev
* **100%** das taxas de desempenho em CAKE das IFOs
* **100%** do CAKE gasto na criação de Perfil e na emissão de NFTs
* **100%** do CAKE ofertado em Leilões de Farm
* **20%** do CAKE gasto em bilhetes da loteria
* **45.000** CAKE por dia (historicamente destinados à loteria) (_O CAKE para isso é gerado por uma farm - PID 137)_
* **3%** de cada rodada dos mercados de Previsão é usado para comprar CAKE para queima
* **2%** de cada harvest de rendimento no Auto CAKE Pool
* **2%** de cada venda de NFT no NFT Market é usado para comprar CAKE para queima

## Por que a queima de CAKE é manual?

Para sair na frente, a PancakeSwap foi lançada como um MVP (produto mínimo viável), com o contrato MasterChef emitindo 40 CAKE por bloco. Por esse motivo, a equipe inicial não adicionou funções extras, como a capacidade de personalizar a lógica de emissão de CAKE. Como migrar para um novo MasterChef exigiria muito tempo e esforço, a equipe optou por reduzir as emissões de CAKE por meio de um processo de queima manual, criando dois pools:

* Legacy Lottery Pool (PID - 137) - queimava o CAKE da loteria
* Burn Pool (PID - 138) - queimava CAKE por bloco

Esses pools funcionam de forma semelhante às farms, em que os Chefs podem ajustar a porcentagem dos 40 CAKE por bloco alocada a eles após cada votação de redução de emissão de CAKE.

{% hint style="warning" %}
No dia da queima, o supply exibido na página inicial pode subir de repente em vários milhões de CAKE.&#x20;

Não se preocupe - **ESSE CAKE NUNCA ENTRA REALMENTE EM CIRCULAÇÃO:**
{% endhint %}

Esse aparente salto ocorre apenas por causa da forma como todo o CAKE alocado para a queima é armazenado durante a semana.&#x20;

O CAKE enviado a ambos os pools PID-137 e PID-138 é coletado (harvest) antes da conclusão das queimas semanais de tokens, e isso faz o Supply Total exibido no site subir cerca de \~6M. Isso acontece porque o CAKE pendente não é registrado no Supply Total até ser coletado no dia da queima. Assim que a transação de queima de tokens é concluída, os \~6M passam a aparecer em Burned to Date.&#x20;

## Como confirmar o supply de CAKE por conta própria

Para confirmar que o supply circulante de CAKE exibido na página inicial da PancakeSwap está correto,&#x20;

1. Acesse o contrato do token CAKE no BscScan e [veja quanto CAKE está no Burn Address.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Esse é o total de CAKE que foi queimado (removido de circulação PARA SEMPRE, e impossível de recuperar).
2. Em seguida, subtraia esse valor queimado do "Total Supply" exibido pelo BscScan.
3. Isso dá o supply real de CAKE.



#### **Leia mais sobre os mecanismos deflacionários do CAKE na próxima página.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
