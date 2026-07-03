# 📔 Governança

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Como parte da [atualização Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), esta página foi atualizada em 15 de maio de 2025
{% endhint %}

A Votação dá voz à comunidade PancakeSwap, permitindo que ela participe das decisões sobre como o PancakeSwap se desenvolve no futuro.

Confira o [portal de votação nativo do PancakeSwap](https://pancakeswap.finance/voting) e nossa página do [Fórum](https://forum.pancakeswap.finance/).

## Mecânica de Votação

:notebook\_with\_decorative\_cover:Resumo - O que Mudou (após a [Atualização Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Componente de Governança</th><th width="218.01953125">Antes do Tokenomics 3.0</th><th width="205.1796875">Após o Tokenomics 3.0</th><th>Status<select><option value="q1dVFsCri7zA" label="✅ Alterado" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Inalterado" color="blue"></option></select></th></tr></thead><tbody><tr><td>Poder de Votação</td><td>1 veCAKE = 1 poder de votação</td><td>1 CAKE = 1 poder de votação</td><td><span data-option="q1dVFsCri7zA">✅ Alterado</span></td></tr><tr><td>Delegação</td><td>Permitida (via mecânica veCAKE)</td><td>Delegação não é permitida</td><td><span data-option="q1dVFsCri7zA">✅ Alterado</span></td></tr><tr><td>Limite para Submissão de Proposta</td><td>Snapshot de 100K veCAKE necessário</td><td>Snapshot de 100K CAKE necessário</td><td><span data-option="q1dVFsCri7zA">✅ Alterado</span></td></tr><tr><td>Propostas Core vs. Comunidade</td><td>Funções e finalidades definidas para cada tipo de proposta</td><td>Sem alteração</td><td><span data-option="4AGl26rwjYcI">🔁 Inalterado</span></td></tr><tr><td>Período de Votação</td><td>Comunidade: Fixo<br>Core: Variável</td><td>Sem alteração</td><td><span data-option="4AGl26rwjYcI">🔁 Inalterado</span></td></tr><tr><td>Momento do Snapshot</td><td>No bloco em que a proposta foi publicada</td><td>Sem alteração</td><td><span data-option="4AGl26rwjYcI">🔁 Inalterado</span></td></tr><tr><td>Quórum</td><td>Sem quórum mínimo</td><td>Sem alteração</td><td><span data-option="4AGl26rwjYcI">🔁 Inalterado</span></td></tr></tbody></table>

### 1. **Poder de Votação (Alterado)**

* **Todos os detentores de CAKE têm direitos de voto diretos.**
* **O poder de votação corresponde diretamente ao número de CAKE mantido no endereço da carteira no momento do snapshot**
  * **1 CAKE = 1 poder de votação**
  * **CAKE em Staking em Syrup Pools não conta** para o seu poder de votação, pois não faz parte do saldo da sua carteira no momento do snapshot
  * Saldo do snapshot = Mesmo bloco em que a proposta foi publicada
* **A delegação não é mais suportada.** Cada detentor de CAKE deve votar individualmente.

### 2. **Submissão de Proposta (Inalterado)**

* **Como Submeter uma Proposta**
  * Envie em [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Deve incluir:
    * Título
    * Conteúdo
    * Descrição
    * Ação(ões) on-chain (se necessário)
    * Duração da Votação
* Tipos de Propostas
  1.  Propostas Core

      * Só podem ser propostas pela **Equipe Core do PancakeSwap**.
      * Requerem votação dos detentores de CAKE.
      * Se aprovadas, serão implementadas pela equipe do PancakeSwap.

      Exemplos

      1. Ajustes de protocolo (mudanças de produto, mudanças de taxa)
      2. Usos significativos de fundos de Crescimento do Ecossistema não cobertos por propostas anteriores
  2. Propostas da Comunidade
     * Propostas da **Comunidade** são publicadas pela comunidade PancakeSwap. Elas são usadas para propor ideias e expressar o ponto de vista da comunidade. São **sugestões não vinculativas** da comunidade.
     * Qualquer pessoa com **100.000 CAKE (saldo do snapshot)** pode submeter.
     * A equipe do PancakeSwap pode adotar propostas fortes em futuras Propostas Core
     * Membros da comunidade também podem utilizar nosso [Fórum](https://forum.pancakeswap.finance/) para fornecer feedback e fazer sugestões ao protocolo.

### **3. Duração da Votação (Inalterado)**

* Todos os detentores de CAKE podem votar **durante a janela de votação** de cada proposta.
  * Proposta da Comunidade: Fixo em 3 dias
  * Proposta Core: Variável, definido pelo PancakeSwap
* Seu poder de votação é determinado por um **snapshot do seu saldo de CAKE no bloco em que a proposta é publicada**.
* **Adicionar mais CAKE após a publicação da proposta não aumentará seu poder de votação** para essa votação específica.

Para detalhes completos, consulte o [Guia de Votação](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Resultado da Votação (Inalterado)**

* O resultado é baseado no **total de votos emitidos** (total de CAKE usado para votação)
* **Atualmente não há quórum mínimo necessário** para uma proposta ser aprovada.

## Observação: Direitos de Veto

Para proteger o protocolo, a **Equipe Core do PancakeSwap reserva o direito de intervir em situações críticas**—como ameaças à segurança ou problemas que afetam a operação estável da plataforma—**sem exigir uma votação da comunidade ou enquete no Snapshot**.

Em qualquer caso em que uma ação de veto seja tomada, a Equipe Core irá **compartilhar publicamente uma explicação clara** da decisão.

**Possíveis ações de veto podem incluir:**

1. **Pausar temporariamente contratos inteligentes** para corrigir bugs ou vulnerabilidades urgentes.
