# Governança (novo)



{% hint style="info" %}
Estamos fazendo a transição do vCAKE para o veCAKE em nosso sistema de governança. Antes de a migração ser concluída, nem todas as informações nesta página serão precisas.
{% endhint %}

![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FYTV06cKbEYMWcmZtmuzN%2Fimage.png?alt=media\&token=095957a2-dee0-419a-bc74-60ffbfec9a71)

## Visão geral&#x20;

Os holder de veCAKE têm direito a voto no sistema de governança da PancakeSwap.&#x20;

Estes são os temas que estão no âmbito da governança:

1. \[Principal] Ajustes de emissão de CAKE de alto nível (alocação de CAKE para pools principais e outras categorias de alto nível)&#x20;
2. \[Principal] Ajustes de protocolo (alterações de produtos, alterações de taxas)&#x20;
3. \[Principal] Gastos com warchest multichain&#x20;
4. \[Comunidade] Aprovações de medidores&#x20;
5. \[Comunidade] Votação regular do peso do medidor (a cada 2 semanas)

Os tópicos "Principal" devem ser votados pelos holders do veCAKE, mas só podem ser propostos pela Equipe Principal da PancakeSwap. Os tópicos "Comunidade" podem ser propostos por qualquer pessoa e também devem ser votados pelos holders do veCAKE. É necessário um mínimo de 10.000 veCAKE para iniciar uma enquete no Snapshot (isso será implementado posteriormente, quando migrarmos de vCAKE para veCAKE). O resultado da enquete será executado pela Equipe Principal.

## Veto

A equipe principal da PancakeSwap tem direito de veto e pode realizar ações corretivas quando se trata de segurança ou bom funcionamento do protocolo, sem passar por uma enquete Snapshot. No caso de qualquer ação de veto, a equipe principal da PancakeSwap fornecerá uma explicação.&#x20;

As ações possíveis incluem, mas não estão limitadas a:

1. Pausar contratos inteligentes relevantes enquanto corrige um bug crítico no protocolo&#x20;
2. Rejeitar um medidor que foi votado com sucesso se o(s) token(s) em questão for considerado inseguro, malicioso e/ou prejudicial ao ecossistema PancakeSwap

## Processo de Governança

A visão geral do processo de governança dodaPancakeSwap é a seguinte:&#x20;

1. Publicação de uma Verificação de Temperatura no fórum&#x20;
2. Discussão&#x20;
3. Início de uma enquete Snapshot (período de votação mínimo de 24 horas)&#x20;
4. Execução

### Passo 1: Publicação de uma Verificação de Temperatura no fórum&#x20;

* O objetivo de uma Verificação de Temperatura é medir o consenso aproximado da comunidade sobre a proposta antes de iniciar uma enquete oficial no Snapshot.
* Embora a PancakeSwap receba comunidades de diversas origens, o fórum atualmente aceitará apenas propostas escritas em inglês. Por favor, fale com nossos Embaixadores em nossos [vários grupos regionais do Telegram](https://docs.pancakeswap.finance/contact-us/social-accounts-and-communities) se precisar de ajuda com a tradução.
* Os proponentes devem incluir \[Temp Check] no título ao postar no fórum

### Passo 2: Discussão

* Encorajamos todas as propostas de verificação de temperatura a passarem por 48 horas de discussão no fórum antes de uma enquete no Snapshot ser iniciada, embora não seja estritamente necessário
* Isto é para dar tempo suficiente para avaliar o sentimento da comunidade e incorporar qualquer feedback na proposta

### Passo 3: Início de uma enquete Snapshot&#x20;

* Qualquer pessoa com poder de voto de 10.000 veCAKE (será implementado posteriormente) pode iniciar uma enquete no Snapshot e postar o link para o respectivo tópico no fórum&#x20;
* O requisito de veCAKE mitiga propostas de baixa qualidade e garante que uma votação só possa ser iniciada por membros da comunidade alinhados com a PancakeSwap&#x20;
* A enquete Snapshot deve durar no mínimo 48 horas ou no mínimo 24 horas se for um tópico principal&#x20;
* O quórum para uma enquete Snapshot é de 250.000 votos de veCAKE (será implementado posteriormente), incluindo votos de abstenção (este requisito está sujeito a revisão adicional para garantir propostas de alta qualidade)

### Passo 4: Execução

* Se a enquete Snapshot atingir o quórum ao final do período de votação e receber >50% de aprovação dos votos, a equipe principal da PancakeSwap executará com base no resultado da votação&#x20;
* Fórmula para medir a porcentagem de aprovação de votos: Votos a fvor / (Votos a favor + Votos contrários)

