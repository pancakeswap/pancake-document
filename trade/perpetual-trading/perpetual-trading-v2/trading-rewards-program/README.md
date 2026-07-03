---
description: A ApolloX lançará o Programa de Recompensas de Trading na V2
hidden: true
---

# Programa de Recompensas de Trading

### Visão Geral do Programa de Recompensas

Os detalhes são os seguintes:

Período de atividade: As datas variam de ciclo para ciclo e para diferentes chains

Tempo de Distribuição de Recompensas: Cada ciclo é de 00:00 (UTC) a 23:59 (UTC) diariamente. As recompensas são emitidas no dia seguinte por volta das 03:00 (UTC). Os usuários devem reivindicar suas recompensas dentro de 30 dias após as recompensas serem emitidas. Caso contrário, a plataforma revogará as recompensas.&#x20;

Valor da recompensa: Limitado a $15.000 USD em APX por dia

Regras de atividade: Os usuários que negociam na V2 ganham de um pool de prêmios de recompensas. Aqueles que fazem staking de APX no DAO para obter veNFT desfrutarão de multiplicadores de impulso correspondentes ao valor de Poder calculado a partir do veNFT.&#x20;

| Valor de Poder                | Multiplicador de Impulso |
| ----------------------------- | ------------------------ |
| 50.000 < Poder =<100.000      | 1,5                      |
| 100.000 < Poder =<300.000     | 2                        |
| Poder > 300.000               | 2,5                      |

Fórmula de cálculo das Recompensas de Trading:&#x20;

Ao final de cada ciclo de recompensas de trading, as taxas de trading efetivas e o valor de staking do usuário naquele ciclo serão calculados para determinar o peso e o valor das recompensas em APX. A fórmula é a seguinte:

r = R\*W / sum(Wi)



Parâmetros:

| r       | Recompensa em APX do usuário para este ciclo                                                                                                                                                                                                                                                                                                          |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Determinado pela contribuição em taxas de trading V2 do usuário no dia anterior e pelo preço mais recente do token APX                                                                                                                                                                                                                               |
| W       | <p>Pontuação de peso total individual W=f*w, onde;</p><p>f refere-se às taxas de trading efetivas contribuídas pelo usuário neste ciclo, que serão convertidas em USD.</p><p>w é o Multiplicador de Impulso obtido pelo usuário neste ciclo ao fazer staking de APX no DAO. (Consulte a tabela acima para mais informações)</p> |
| sum(Wi) | A pontuação total de todos os usuários. Wi representa a pontuação de qualquer usuário individual, e sum(Wi) representa a soma de todas as pontuações dos usuários                                                                                                                                                                                     |

&#x20;

A fórmula de cálculo para R é a seguinte:

R=Min(multiplicador de valor em dólar \* Taxa de Trading, Limite de valor em dólar)/ Max(Último Preço APX, Preço Mínimo APX)

* Multiplicador de valor em dólar: 0,70 nesta época
* Taxa de Trading: Valor da receita de taxa V2 do dia anterior convertida em USD
* Limite de valor em dólar: 15.000 baseado na configuração do sistema
* Último Preço APX: Baseado no preço mais recente do token APX
* Preço Mínimo APX: 0,04 nesta época

Termos e Condições

* Após o fim de cada ciclo, a ApolloX pode ajustar as regras do programa de acordo com o feedback dos usuários e as condições de mercado. As recompensas serão liberadas de forma não-linear.
* Durante a atividade, a plataforma reduzirá a porcentagem da receita de taxa de trading V2 injetada no pool ALP de 50% para 20%. Os 30% restantes serão usados para recomprar APX.
* Devido à diferença nas taxas de trading para cada par de trading na V2, as recompensas que os usuários recebem podem variar mesmo que seus volumes de trading efetivos sejam iguais.
* As recompensas a serem distribuídas para cada ciclo serão armazenadas no seguinte endereço de contrato: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* A ApolloX reserva o direito de interpretação final para esta atividade.

Aviso de Risco: O trading de futuros de criptomoedas carrega um risco substancial. Todas as atividades de trading são feitas a seu critério e por sua conta e risco. As informações aqui não devem ser consideradas como conselho financeiro ou de investimento da ApolloX. A ApolloX não será responsável por qualquer perda que possa surgir do seu uso da ApolloX.

### Resgatando Recompensas

Como o programa de recompensas de trading é hospedado por nossos amigos da ApolloX, siga os seguintes passos para resgatar sua recompensa:\
\
Passo 1: Vá para nossa [Página de Perpetuals do PancakeSwap](https://perp.pancakeswap.finance/en/futures/v2/)

Passo 2: Clique na aba Trading Reward (V2) no topo da página

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Passo 3: Você será redirecionado para a página de resgate de recompensas da ApolloX para verificar seu status de recompensa atual. Clique em "Resgatar" para resgatar suas recompensas durante o período de atividade.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
