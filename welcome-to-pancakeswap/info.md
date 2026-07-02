# 📈 Análises (Página de Informações)

## Página de Informações&#x20;

Veja o site de análises nativas do PancakeSwap aqui: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Todos os dados das métricas principais são provenientes do Indexador interno do PCS, que, por sua vez, coleta dados de eventos acionados quando o contrato é chamado.&#x20;

Para a dimensão de data no indexador interno do PancakeSwap, utilizamos o horário padrão internacional (UTC) para estatísticas diárias. Portanto, quando o eixo horizontal no Painel exibe uma data, ela representa a data no horário padrão internacional (UTC).<br>

## Métricas Principais

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume (Volume de Negociação):** Monitoramos os dados diários de cada par de negociação e os dados diários de negociação de cada token. O volume de negociação diário é determinado multiplicando o volume de negociação de cada token no dia pelo seu preço.

**Total de Valor Bloqueado:** Obtém todos os pools do Indexador interno e lê o reserve\_usd ou total\_value\_locked\_usd de cada pool.&#x20;

**Preço:** No Indexador Interno do PCS, utilizamos vários pools base para calcular preços relacionados a USD. O pool principal é o pool de negociação de stablecoin, onde usamos o pool de negociação com maior volume como pool base e calculamos o preço em USD da stablecoin com base no peso do volume de negociação. Adicionalmente, o pool de negociação do token base para a stablecoin da rede também é considerado um pool base para fornecer o preço em USD.

_Tokens que não estão na lista de permissões ou não estão emparelhados com tokens permitidos são excluídos desses cálculos._

<br>
