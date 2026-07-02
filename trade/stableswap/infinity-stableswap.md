# Infinity StableSwap

### Visão Geral

O Infinity StableSwap é um tipo de pool dentro do [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) otimizado para trocar ativos que devem ser negociados próximos ao mesmo preço — como stablecoins (por exemplo, USDC/USDT) ou ativos com peg próximo (por exemplo, pares de tokens embrulhados, tokens de liquid staking e tokens de liquid restaking).

Ele é alimentado por um hook StableSwap rodando na arquitetura Infinity, inspirado no design StableSwap NG da Curve. Atualmente está disponível na BNB Chain, com planos de expansão para redes adicionais no futuro.

***

### Como Funciona

O Infinity StableSwap usa uma curva invariante estável — um híbrido entre soma constante e produto constante:

* Próximo ao peg → a curva se comporta próximo à soma constante, resultando em Slippage muito baixo para negociações em torno de 1:1.
* Longe do peg → a curva gradualmente transiciona para produto constante, o que ajuda a restaurar o equilíbrio e protege o pool durante grandes desequilíbrios ou eventos de depeg.

Isso o torna especialmente eficaz para pares estáveis onde precificação precisa e baixo Slippage são mais importantes.

***

### Principais Recursos

Otimizado para Swaps próximos ao peg: Baixo Slippage para negociações entre ativos que se espera que sejam negociados aproximadamente ao mesmo preço.

Provisão de Liquidez simples: Os provedores de Liquidez (LPs) depositam ambos os tokens proporcionalmente sem precisar selecionar ou gerenciar intervalos de preço — ao contrário dos pools CLAMM.

Tokens LP ERC-20: Sua posição LP é representada como um token ERC-20 padrão, facilitando o uso com programas de rendimento, campanhas de pontos e outros protocolos DeFi.

Taxas dinâmicas: As taxas podem ser ajustadas com base nas condições de equilíbrio do pool, recompensando negociações que ajudam a restaurar o pool para o equilíbrio e desencorajando aquelas que pioram o desequilíbrio.

Suporte de roteamento Infinity: As negociações são roteadas automaticamente pelos pools StableSwap quando oferecem o melhor preço — sem etapas extras necessárias para os traders.

Parâmetro de Amplificação (A) ajustável: Os operadores do pool podem aumentar ou diminuir gradualmente o parâmetro A ao longo do tempo para se adaptar às condições de mercado em mudança, com salvaguardas para evitar mudanças abruptas.

***

### Parâmetros do Pool

O comportamento do pool StableSwap é governado por um pequeno conjunto de parâmetros, geralmente definidos no momento da criação do pool.

#### Coeficiente de Amplificação (A)

O parâmetro A controla quão firmemente o pool segue o peg de preço 1:1.

| Valor de A  | Efeito                                                                              |
| ----------- | ------------------------------------------------------------------------------------ |
| A mais alto | Curva mais estreita em torno do peg; menor Slippage próximo a 1:1; mais sensível ao desequilíbrio |
| A mais baixo | Curva mais ampla; comporta-se mais como um pool de produto constante padrão        |

Regra geral: Use um A maior para ativos com um peg forte e confiável (por exemplo, USDC/USDT). Use um A menor para ativos com pegs mais soltos ou mais voláteis (por exemplo, alguns pares LST).

O parâmetro A pode ser gradualmente aumentado ou diminuído pelo operador do pool durante um período de tempo definido. As alterações são aplicadas gradualmente com salvaguardas para evitar manipulação ou mudanças repentinas de precificação.

#### Multiplicador de Taxa Fora do Peg

Um parâmetro adicional que ajusta as taxas efetivas quando o pool se afasta do equilíbrio. Ele ajuda a desencorajar negociações que desequilibrariam ainda mais o pool e torna o pool mais robusto durante estresse de mercado ou eventos de depeg.

#### Taxas Dinâmicas

Uma taxa cobrada em cada Swap, paga aos provedores de Liquidez. O Infinity StableSwap suporta taxas dinâmicas — o que significa que a taxa efetiva em uma determinada negociação pode variar dependendo do estado atual do pool (por exemplo, se a negociação melhora ou piora o equilíbrio).

***

### Infinity StableSwap vs. Classic StableSwap

Se você já usou o StableSwap existente do PancakeSwap, aqui está o que muda — e o que permanece igual.

| <p><br></p>                   | Classic StableSwap                                        | Infinity StableSwap                                                     |
| ----------------------------- | --------------------------------------------------------- | ----------------------------------------------------------------------- |
| Curva de precificação         | Invariante estável (híbrido soma constante / produto constante) | Mesma curva invariante estável, mesmo baixo Slippage próximo ao peg |
| Tokens LP ERC-20              | ✅ Sim                                                     | ✅ Sim                                                                   |
| Criação de pool               | Pesada em operações; requer configuração manual pela equipe | Sem permissão — qualquer pessoa pode criar um pool                   |
| Taxas de Swap                 | Fixa por par (por exemplo, 0,01% para USDC/USDT)          | Taxas dinâmicas — ajusta com base em como a negociação afeta o equilíbrio do pool |
| Parâmetro de Amplificação (A) | Estático — definido uma vez, não pode ser alterado        | Ajustável — pode ser aumentado ou diminuído gradualmente ao longo do tempo |
| Multiplicador de taxa fora do peg | ❌ Não suportado                                       | ✅ Suportado — ajuda a proteger o pool durante eventos de depeg         |
| Eficiência de gas             | Padrão                                                    | Melhorada — beneficia-se do Singleton e Flash Accounting do Infinity   |

#### O que permanece igual

* A curva de precificação central e o comportamento de baixo Slippage próximo ao peg são inalterados.

#### O que é novo e melhor

* Criação de Pool Sem Permissão: Os pools podem ser criados sem permissão sem necessitar de configuração manual pela equipe.
* Taxas dinâmicas protegem os LPs: Em vez de uma única taxa fixa, a taxa pode ser ajustada por negociação com base em se ela ajuda ou prejudica o equilíbrio do pool — tornando o pool mais resiliente durante condições voláteis.
* Parâmetro A adaptável: O coeficiente de amplificação pode ser ajustado ao longo do tempo conforme as condições de mercado mudam, em vez de ser bloqueado na implantação para sempre.

***

### Perguntas Frequentes

Quais ativos são adequados para Infinity StableSwap?

Ativos que se espera que sejam negociados próximos ao mesmo preço: stablecoins (USDC, USDT, BUSD, etc.), equivalentes embrulhados do mesmo ativo (por exemplo, WBTC/cbBTC), e pares seletos de tokens de liquid staking / liquid restaking tokens (LST/LRT) onde a volatilidade do peg é baixa.

<br>

Como o Infinity StableSwap é diferente do antigo StableSwap do PancakeSwap?

O Infinity StableSwap é implementado como um hook no PancakeSwap Infinity, o que significa que ele herda todos os benefícios de infraestrutura do Infinity, incluindo menores custos de gas via Singleton e Flash Accounting, e um sistema de taxas mais flexível. Ele também suporta novas capacidades como taxas dinâmicas e amplificação ajustável que o StableSwap legado não oferecia.

<br>

Preciso gerenciar minha posição ao longo do tempo?

Não. Ao contrário do CLAMM, você não precisa definir ou ajustar intervalos de preço. Sua Liquidez está sempre ativa em toda a curva, portanto não há risco de sua posição ficar "fora do intervalo".

<br>

Posso fornecer Liquidez com apenas um token?

Sim, depósitos de token único são suportados.

<br>

Como as taxas dinâmicas funcionam?

No Infinity StableSwap, a taxa de Swap pode variar por negociação com base em como a negociação afeta o equilíbrio do pool. Negociações que ajudam a trazer o pool de volta ao equilíbrio podem pagar taxas efetivas menores, enquanto negociações que pioram o desequilíbrio podem pagar taxas maiores. Isso é projetado para proteger os LPs e manter condições de pool mais saudáveis.



***



## Criando um Pool Infinity StableSwap



Os pools Infinity StableSwap são sem permissão — qualquer pessoa pode criar um sem precisar de aprovação da equipe PancakeSwap.

<br>

### Passo a passo

1\. Acesse a página Farm/Liquidez e clique em Criar Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Selecione Pool StableSwap nas opções de tipo de pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Selecione o par de tokens para seu pool (por exemplo, USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Parâmetros do Pool

| Parâmetro               | O que faz                                                                                                           |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Taxa de Swap            | Taxa cobrada em cada Swap, paga aos LPs. O padrão é 0,01% para pares estáveis próximos.                            |
| A (Amplificação)        | Controla quão firmemente a curva segue o peg. Maior = menor Slippage próximo a 1:1, mas mais sensível ao desequilíbrio. |
| Multiplicador de Taxa Fora do Peg | Escala as taxas quando o pool se afasta do equilíbrio, desencorajando negociações que pioram o desequilíbrio. |
| Tempo de Média Móvel    | Janela de tempo usada para calcular o preço médio móvel para ajustes de taxa dinâmica.                              |

⚠️ Defina os parâmetros com cuidado. Parâmetros incorretos — especialmente um A muito alto em um ativo com peg solto — podem aumentar o risco para os LPs. Em caso de dúvida, use o preset para o tipo de ativo e evite alterar as configurações Avançadas.

<br>

Escolha um Preset de Parâmetros de Pool — isso define automaticamente os parâmetros recomendados para o tipo de ativo. Você ainda pode ajustá-los manualmente via alternância Avançada.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                                   | A    | Multiplicador de Taxa Fora do Peg | Tempo de Média Móvel (segundos) |
| ---------------------------------------- | ---- | --------------------------------- | ------------------------------- |
| Stablecoins Resgatáveis por Fiat         | 1000 | 10                                | 600                             |
| Stablecoins com Garantia em Criptomoeda  | 100  | 12.5                              | 600                             |
| Tokens de Liquid Restaking               | 500  | 10                                | 600                             |

<br>

&#x20; Não tem certeza de qual escolher?&#x20;

* Use Stablecoins Resgatáveis por Fiat para pares como USDC/USDT
* Use Stablecoins com Garantia em Criptomoeda para stablecoins algorítmicas ou lastreadas em criptomoedas
* Use Tokens de Liquid Restaking para pares LRT como stkBNB/WBNB.

<br>

5\. Insira o valor do depósito para semear a Liquidez inicial. Ambos os valores de tokens devem ser iguais (por exemplo, 1 USDC e 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Clique em Visualizar Pool, revise suas configurações, marque a caixa de confirmação e clique em Criar Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
