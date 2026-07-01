# 📈 Analytics (Página de Información)

## Página de Información&#x20;

Consulta el sitio de analytics nativo de PancakeSwap aquí: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Todos los datos de métricas principales provienen del Indexer interno de PCS, que a su vez recopila datos de los eventos activados cuando se llama al contrato.&#x20;

Para la dimensión de fecha en el indexer interno de PancakeSwap, utilizamos el tiempo estándar internacional (UTC) para las estadísticas diarias. Por lo tanto, cuando el eje horizontal en el Panel de Control muestra una fecha, representa la fecha en tiempo estándar internacional (UTC).<br>

## Métricas Principales

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volumen (Volumen de Trading):** Monitorizamos los datos diarios de cada par de trading y los datos diarios de trading de cada token. El volumen de trading diario se determina multiplicando el volumen de trading de cada token del día por su precio.

**Total Value Locked:** Obtiene todos los pools del Indexer interno y lee el reserve\_usd o total\_value\_locked\_usd de cada pool.&#x20;

**Precio:** En el Indexer Interno de PCS, utilizamos varios pools base para calcular los precios relacionados con USD. El pool primario es el pool de trading de stablecoin, donde utilizamos el pool de trading con mayor volumen como pool base y calculamos el precio en USD de la stablecoin basándose en la ponderación del volumen de trading. Además, el pool de trading del token base a la stablecoin de la cadena también se considera un pool base para proporcionar el precio en USD.

_Los tokens que no están en la lista blanca o que no están emparejados con tokens de la lista blanca están excluidos de estos cálculos._

<br>
