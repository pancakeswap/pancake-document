# Tokenomics de CAKE

<figure><img src="../../.gitbook/assets/image (185).png" alt=""><figcaption></figcaption></figure>

## **Taxa de Emissão** <a href="#emission-rate" id="emission-rate"></a>

### **Por bloco**

| **Métrica**         | **Emissão/bloco (CAKE)** | **Emissão/dia (CAKE)** |
| ------------------- | ------------------------ | ---------------------- |
| Emissão             | 40                       | 1.152.000              |
| Queima Semanal      | \~38,1626                | \~1.099.085            |
| **Emissão Efetiva** | **\~1,8374\***           | **\~52.915\***         |

{% hint style="info" %}
Em 11 de agosto de 2022, os Chefs implementaram algumas atualizações de configuração para aproveitar ao máximo o MasterChef v2. Ele elimina a queima diária de 45.000 CAKE para as injeções de loteria legacy. Essas queimas agora serão tratadas pelo MasterChef v2 diretamente junto com a queima semanal habitual do CAKE. Portanto, as emissões efetivas agora são ainda menores.
{% endhint %}

{% hint style="warning" %}
Além do dito acima, uma quantidade dinâmica de CAKE também é [cunhada no endereço Dev ](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns)a uma taxa de 9,09%. Isso significa que, se 100 CAKE forem colhidos, 9,09 CAKE serão cunhados e enviados para o endereço do desenvolvedor.

Todo CAKE cunhado no endereço Dev é queimado na queima semanal e nunca entra em circulação.&#x20;

Como tal, não o incluímos na taxa de emissão acima.
{% endhint %}

## Distribuição <a href="#distribution" id="distribution"></a>

| Distribuído para                  | Recompensa/bloco(% da emissão) | Recompensa/bloco(total CAKE) | Recompensa/dia       |
| --------------------------------- | ------------------------------ | ---------------------------- | -------------------- |
| Trade(Farms)                      | \~3%                           | \~1,1984                     | 34.515 (aprox)       |
| Stake                             | \~1,25%                        | \~0,5                        | 14.400 (aprox)       |
| Outros                            | \~0,35%                        | \~0,1389                     | 4.000 (aprox)        |
| **Emissão Total Diária de CAKE**  | ​                              | ​                            | \~**52.915 (aprox)** |

## **Outros Mecanismos Deflacionários** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
O processo de queima é atualmente manual. [Veja as transações de queima aqui](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Além do acima, o CAKE também é queimado das seguintes maneiras:

* **0,001\~0,23%** de todo trade feito através do V3 na:
  * BNB Chain
  * Ethereum
* **0,0575%** de todo trade feito através da V2 na:&#x20;
  * BNB Smart Chain&#x20;
  * Ethereum&#x20;
  * Aptos&#x20;
* **0,004%\~0,016%** de todas as negociações feitas no StableSwap da PancakeSwap&#x20;
* **100%** do CAKE enviado para o endereço do Dev&#x20;
* **100%** das taxas de performance em CAKE das IFOs&#x20;
* **100%** do CAKE gasto na criação de perfil e cunhagem de NFT&#x20;
* **100%** dos lances em CAKE durante os leilões de farms&#x20;
* **20%** do CAKE gastos em bilhetes da loteria&#x20;
* **20%** de todos os lucros do Trade de Perétuos&#x20;
* **8%** do prêmio do Pottery distribuído a cada semana&#x20;
* **3%** de cada rodada de mercados de previsão de BNB é usado para comprar CAKE para queimá-lo&#x20;
* **3%** de cada rodada de mercados de Previsão de CAKE&#x20;
* **2%** de cada colheita de todas as posições de stake flexíveis na pool de CAKE&#x20;
* **2%** de cada venda NFT no mercado NFT é usado para comprar CAKE para queimar

## Por que a queima de CAKE é manual?

Para começar, a PancakeSwap foi lançada como um MVP (produto mínimo viável) com o contrato MasterChef emitindo 40 CAKE por bloco. Por esse motivo, a equipe inicial não adicionou funções adicionais, como a capacidade de personalizar a lógica de cunhagem do CAKE. A equipe vem controlando as emissões do CAKE por meio de um processo de queima manual, criando duas pools no MasterChef v1:

* Legacy Lottery Pool (PID - 137) - CAKE queimado da loteria
* Burn Pool (PID - 138) - CAKE queimado por bloco

Essas pools funcionam de forma semelhante às farms, onde os Chefs podem ajustar a porcentagem dos 40 CAKE por bloco alocados para elas após cada voto de redução de emissão de CAKE.&#x20;

**No entanto, em abril de 2022, a PancakeSwap migrou para um novo contrato MasterChef v2.** A proporção da queima do CAKE por bloco é finalmente controlada por um contrato dedicado. Isso permite que a queima seja muito mais precisa.

{% hint style="warning" %}
Devido ao MasterChef v2 ocasionalmente colher o total de 40 CAKE por bloco. A oferta mostrada na página inicial (ou alguns rastreadores de terceiros) pode repentinamente aumentar em vários milhões de CAKE.&#x20;

Não se preocupe - **A EMISSÃO AGORA É CONTROLADA CUIDADOSAMENTE PELO MASTERCHEF V2. CAKE PARA QUEIMA NUNCA ENTRARÁ REALMENTE EM CIRCULAÇÃO!**
{% endhint %}

## Como confirmar o fornecimento de CAKE por você mesmo

Para confirmar se o fornecimetno de CAKE mostrado na página inicial da PancakeSwap está correto:

1. Vá para o contrato de token CAKE no BscScan e [veja quanto CAKE é mantido pelo Burn Address](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances). Essa é a quantidade total de CAKE que foi queimado (removido de circulação PARA SEMPRE e impossível de recuperar).&#x20;
2. Em seguida, subtraia essa quantidade queimada do "Fornecimento total" que a BscScan mostra.&#x20;
3. Isso dá o fornecimento real de CAKE.

**Leia mais sobre a mecânica deflacionária do CAKE na próxima página.**
