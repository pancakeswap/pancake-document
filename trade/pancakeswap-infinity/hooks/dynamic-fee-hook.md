# Hook de Taxa Dinâmica

O Hook de Taxa Dinâmica oficial do PancakeSwap foi projetado para criar uma troca de valor mais justa entre Provedores de Liquidez e Traders. Ele protege os LPs de perda impermanente (IL) excessiva enquanto mantém o mercado eficiente para os traders.

Construído pela equipe central do PancakeSwap, este hook é especificamente adaptado para oferecer uma alternativa inteligente e adaptativa aos modelos tradicionais de taxa fixa.

#### 🔍 Por que Taxas Dinâmicas?

Grandes negociações de arbitragem causam maior divergência de preços nos pools, aumentando a IL para os LPs. Nosso modelo de taxa dinâmica cobra taxas proporcionalmente maiores em negociações de arbitragem maiores para compensar esse risco — deixando espaço suficiente para os arbitradores lucrarem e manter os preços alinhados.

#### 📊 Como isso é diferente de outros modelos?

Outros modelos no passado usaram dados históricos para estimar a volatilidade e outros fatores para ajustar as taxas. No entanto:

* Dados históricos são um indicador defasado e podem não prever com precisão a volatilidade futura.
* Eventos externos de mercado (como mudanças regulatórias ou mudanças econômicas) podem tornar as tendências passadas não confiáveis.
* Modelos complexos e cheios de parâmetros correm o risco de overfitting — funcionando bem em dados passados, mas mal em condições novas e não previstas.

Nossa abordagem é mais simples, adaptativa e baseada no comportamento de negociação em tempo real.

#### ⚙️ Como Funciona

* **Não prevemos volatilidade ou outros fatores macro**\
  Em vez disso, nosso modelo se beneficia inerentemente do comportamento dos arbitradores sob diferentes regimes de mercado:
  * **Alta volatilidade:** Mais negociações de arbitragem em tamanhos maiores → Taxas mais altas para os LPs, cobrindo uma parcela maior da IL.
  * **Baixa volatilidade:** Negociações menos frequentes e menores → A IL é menor por natureza, mas os LPs ainda ganham taxas maiores do que em um modelo de taxa fixa.
* **Nosso modelo usa**
  * Um preço de pool ponderado exponencialmente para detectar negociações de arbitragem.
  * Uma curva de taxa exponencial baseada no impacto de preço de cada Swap.
  * Uma taxa máxima de 5% para manter a equidade para os traders.

{% hint style="success" %}
Isso garante que as taxas escalem dinamicamente com o impacto da negociação enquanto se adaptam automaticamente às condições de mercado em mudança.
{% endhint %}

* **Incentivos Equilibrados**\
  Os arbitradores ainda retêm \~50% de seus lucros após as taxas dinâmicas, garantindo que estejam motivados a manter os preços do pool alinhados com o mercado.

#### 📌 Pontos-chave

* Sem dependência de previsões de volatilidade ou outros fatores macro.
* Adapta-se automaticamente à volatilidade do mercado com base no comportamento real de negociação.
* Protege os LPs de IL por Swap.
* Mantém fortes incentivos para arbitradores fecharem lacunas de preço.
* Beneficia os traders com Liquidez mais profunda e taxas base mais baixas.
