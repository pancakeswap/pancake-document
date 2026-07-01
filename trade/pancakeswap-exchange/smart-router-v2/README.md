---
hidden: true
---

# Smart Router (V2)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap Smart Router es un algoritmo de enrutamiento que conecta el AMM y StableSwap (BNB Chain), y el AMM y los market makers (Ethereum), para proporcionar mejor liquidez y precios. Utiliza un algoritmo de enrutamiento de órdenes inteligente que ejecuta trades en múltiples pools para encontrar el mejor precio para los traders. Para más información sobre StableSwap [haz clic aquí](/broken/pages/nNPogTZMxocdyFIBYbkE) y para la integración con Market Makers [haz clic aquí](../market-maker-integration.md).

La Kitchen irá lanzando gradualmente pares de StableSwap para seguir probando y mejorando el producto.

## ¿Por qué debería usar el Smart Router para mis intercambios en el AMM?&#x20;

* Intercambia tus stablecoins u otros pares con precios de activos similares de manera más eficiente con los mismos pasos de trading.
* Intercambia con los market makers, que pueden ofrecer una mejor ejecución en los trades que el AMM normal de PancakeSwap.
* Con la función StableSwap, el deslizamiento de trading es menor que en el AMM normal.
* Las comisiones de trading de StableSwap son más bajas en comparación con el AMM normal.

## En Desarrollo&#x20;

* Mejor interfaz en los resultados.
* Rutas divididas para trades más eficientes. P. ej., el router envía el 50% del par por una ruta diferente para ahorrar comisiones dependiendo del tamaño del trade y la liquidez.&#x20;
