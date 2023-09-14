---
description: ApolloX lançará Programa de Recompensas de Trade na V2
---

# Programa de Recompensas de Trade

## Visão Geral do Programa de Recompensa

Os detalhes são os seguintes:&#x20;

Período de atividade: as datas variam de ciclo para ciclo e para diferentes chains&#x20;

Horário de distribuição de recompensas: Cada ciclo é das 00h00 (UTC) às 23h59 (UTC) diariamente. As recompensas são emitidas no dia seguinte por volta das 03:00 (UTC). Os usuários devem reivindicar suas recompensas dentro de 30 dias após a emissão das recompensas. Caso contrário, a plataforma revogará as recompensas.&#x20;

Valor da recompensa: limitado a US$ 15.000 em APX por dia&#x20;

Regras de atividade: Os usuários que negociam na V2 ganham um conjunto de prêmios de recompensa. Aqueles que fazems take de APX na DAO para obter o veNFT irão desfrutar do aumento dos multiplicadores correspondentes ao valor de potência calculado a partir do veNFT.

| Valor do Poder            | Multiplicador de Impulsionamento |
| ------------------------- | -------------------------------- |
| 50,000 < Poder =<100,000  | 1,5                              |
| 100,000 < Poder =<300,000 | 2                                |
| Poder > 300,000           | 2,5                              |

Fórmula de cálculo de recompensas trade:&#x20;

No final de cada ciclo de recompensa de negociação, as taxas de negociação efetivas do usuário e o valor de stake nesse ciclo serão calculados para determinar a ponderação e o valor das recompensas APX. A fórmula é a seguinte:

r = R\*W / sum(Wi)

| r       | Recompensa de APX do usuário para este ciclo                                                                                                                                                                                                                                                                                                  |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Determinado pela contribuição da taxa de negociação V2 do usuário no dia anterior e pelo preço mais recente do token APX                                                                                                                                                                                                                      |
| W       | Pontuação pelo peso total individual W=f\*w, onde; f refere-se às taxas de negociação efetivas contribuídas pelo usuário neste ciclo, que serão convertidas em dólares americanos. w é o Multiplicador de Impulsionamento obtido pelo usuário neste ciclo ao fazer stake de APX na DAO. (Consulte a tabela acima para obter mais informações) |
| sum(Wi) | A pontuação total de todos os usuários. Wi representa a pontuação de qualquer usuário individual e sum(Wi) representa a soma de todas as pontuações do usuário                                                                                                                                                                                |

A fórmula de cálculo para R é a seguinte:&#x20;

R = Min (multiplicador de valor em dólar \* Taxa de negociação, limite de valor em dólar) / Máx (último preço APX, preço mínimo APX)

* Multiplicador de valor em dólar: 0,70 nesta época&#x20;
* Taxa de negociação: valor da receita da taxa V2 do dia anterior convertido em dólares americanos&#x20;
* Valor em dólares Limite: 15.000 com base na configuração do sistema&#x20;
* Último preço APX: com base no preço mais recente do token APX&#x20;
* Preço mínimo APX: 0,04 nesta época&#x20;

Termos e Condições

* Após o término de cada ciclo, a ApolloX poderá ajustar as regras do programa de acordo com o feedback dos usuários e as condições do mercado. As recompensas serão liberadas de forma não linear.&#x20;
* Durante a atividade, a plataforma reduzirá o percentual da receita da taxa de negociação V2 injetada na pool de ALP de 50% para 20%. Os 30% restantes serão usados para recomprar APX.&#x20;
* Devido à diferença nas taxas de negociação para cada par de negociação na V2, as recompensas que os usuários recebem podem variar, mesmo que seus volumes de negociação efetivos sejam os mesmos.&#x20;
* As recompensas a serem distribuídas para cada ciclo serão armazenadas no seguinte endereço de contrato: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E&#x20;
* A ApolloX reserva-se o direito de interpretação final desta atividade.

Aviso de risco: a negociação de futuros de cripto acarreta um risco substancial. Todas as atividades de negociação são realizadas a seu critério e por sua própria conta e risco. As informações aqui não devem ser consideradas conselhos financeiros ou de investimento da ApolloX. A ApolloX não será responsável por qualquer perda que possa surgir do uso da ApolloX.

## Reivindicando as Recompensas

Como o programa de recompensa comercial é hospedado por nossos amigos da ApolloX, prossiga com as seguintes etapas para reivindicar sua recompensa:

Etapa 1: Vá para nossa [Página dos Perpétuos da PancakeSwap](https://perp.pancakeswap.finance/en/futures/v2/)

Etapa 2: Clique na aba da Recompensa de Trade (V2) no topo da página

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2Ft1S9Ij6AUAoYDSnQVmNI%2FScreenshot%202023-06-29%20at%2010.23.18%20AM.png?alt=media\&token=9ce6e130-8448-4fa3-9909-f1cce4e8a068)

Etapa 3: você será redirecionado para a página de reivindicação de recompensas ApolloX para verificar o status atual de sua recompensa. Clique em "Reivindicar" para resgatar suas recompensas durante o período da atividade.

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FAOcLJMumAT3iZLz1AT98%2FScreenshot%202023-06-29%20at%2010.26.11%20AM.png?alt=media\&token=a4a2e612-19f9-472e-8610-9e25387b299f)
