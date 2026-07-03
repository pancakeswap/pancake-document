# Infinity CLAMM e LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

O CLAMM permite que os provedores de Liquidez aloquem seu capital dentro de **intervalos de preço específicos**. Isso leva a:

* **Maior eficiência de capital**: Mais Liquidez nos preços de negociação ativos.
* **Liquidez mais profunda**: Melhor execução para os traders.
* **Gerenciamento ativo de LP**: Os LPs precisam ajustar posições conforme os preços se movem.
* Maior potencial de **perda impermanente** para posições fora do intervalo.

{% hint style="info" %}
O CLAMM opera na fórmula de produto constante (X \* Y = K). Cada posição de Liquidez é não fungível e representada como um NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM ou "Pool de Bins")

O LBAMM implementa **bins de preço discretos**, cada um contendo Liquidez em um nível de preço específico. O LBAMM segue a **fórmula de soma constante (X + Y = K).**



**Características principais:**

* Negociações com **0 impacto de preço** dentro de um bin.
* **Liquidez fungível** (a Liquidez dentro de cada bin é um token ERC-20).
* **Menores custos de gas** para ajustar posições LP.
* **Suporte a diferentes formas de Liquidez** (por exemplo, assimétrico, uniforme).
* Mais adequado para pares de **baixa volatilidade** devido à curva de precificação plana por bin.

> 🥞 **PancakeSwap é o primeiro protocolo a oferecer pools LBAMM com hooks.**

{% hint style="success" %}
Tanto os pools CLAMM quanto os LBAMM suportam **hooks**, que permitem que os desenvolvedores personalizem o comportamento do pool. Os tipos de pool são extensíveis por meio de novos Pool Managers, que podem ser adicionados sem reimplantação do protocolo.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Recurso</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Curva de Precificação</strong></td><td>Produto Constante (X * Y = K)</td><td>Soma Constante (X + Y = K)</td></tr><tr><td><strong>Token de Liquidez</strong></td><td>Não fungível (NFT)</td><td>Fungível (ERC-20 por bin)</td></tr><tr><td><strong>Melhor Para</strong></td><td>Pares de alta/baixa volatilidade</td><td>Pares de baixa volatilidade</td></tr><tr><td><strong>Vantagens</strong></td><td><ol><li>Eficiência de capital</li><li>Eficiente em gas em intervalo amplo/total</li><li>Amplamente adotado</li></ol></td><td><ol><li>0 impacto de preço dentro do bin</li><li>Gerenciamento de LP mais barato</li><li>Formas de Liquidez flexíveis</li></ol></td></tr><tr><td><strong>Suporte a Hook</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Taxas

O PancakeSwap Infinity suporta um sistema de taxas flexível e extensível por meio de configurações de taxa Estáticas e Dinâmicas. Essa configuração dá tanto aos criadores de pools quanto aos LPs ferramentas poderosas para otimizar diferentes estratégias de negociação e perfis de risco.

#### 🔁 Taxas Dinâmicas

* As Taxas Dinâmicas são determinadas em tempo real via contratos de hook.
* Essas taxas podem flutuar com base em fatores externos como volatilidade, volume de negociação, status do usuário (por exemplo, detenção de CAKE), ou qualquer lógica personalizada codificada no hook.
* Os pools com taxas dinâmicas devem habilitar a configuração no momento da criação do pool e anexar um hook capaz de modificar taxas via `beforeSwap`.
* Uma vez que um pool é inicializado, o tipo de taxa (dinâmica ou estática) é imutável.

As taxas dinâmicas oferecem máxima flexibilidade e otimizam as estruturas de taxa tanto para LPs quanto para swappers com base nas condições de mercado.

#### 📌 Taxas Estáticas

* Os pools de Taxa Estática têm uma taxa fixa definida durante a criação do pool.
* Essas taxas não podem ser alteradas após a inicialização do pool.
* Adequadas para casos de uso mais simples ou onde a previsibilidade da estrutura de taxa é importante.<br>

**🔒 Limites Máximos de Taxa:**

* Pools CLAMM: Até 100% (principalmente para casos de uso especializados ou experimentais)
* Pools LBAMM: Limitado a 10%<br>

**🏛 Taxa de Protocolo (para pools de taxa estática):**

* O PancakeSwap aplica uma taxa de protocolo nos pools Infinity
* 33% da taxa LP, limitado a 0,4%

| **Taxa LP**       | **Taxa de Protocolo** |
| ----------------- | --------------------- |
| 1%               | 0,33%                 |
| 2%               | 0,4% (limitado)       |
| Pool de Taxa Dinâmica | 0%               |

#### 🛠️ Notas de Configuração para Criadores de Pool

* Ao inicializar um pool via PoolManager, o criador deve escolher:
  * Se o pool usa taxa estática ou dinâmica
  * Se um contrato de hook está anexado (necessário para taxas dinâmicas)

Essas configurações são permanentes e definem como o pool se comporta durante toda sua vida útil.
